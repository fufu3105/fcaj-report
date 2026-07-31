---
title: "Blog 1"
date: 2026-07-29
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

# TÌM HIỂU AWS RESOURCE EXPLORER – TÌM TÀI NGUYÊN AWS TRÊN NHIỀU REGION TỪ MỘT NƠI

Trong quá trình sử dụng AWS Console, mình nhận thấy một vấn đề khá đơn giản nhưng dễ gây mất thời gian: không nhớ tài nguyên đã được tạo ở Region nào.

Ví dụ, mình biết tài khoản đang có một EC2 instance hoặc DynamoDB table, nhưng khi mở service lại không thấy. Sau một lúc kiểm tra mới phát hiện tài nguyên đó được tạo ở một Region khác.

AWS có một service hỗ trợ giải quyết vấn đề này là **AWS Resource Explorer**. Service này cho phép tìm kiếm tài nguyên trong tài khoản AWS dựa trên tên, ID, Region, loại tài nguyên và tag. Cách sử dụng khá giống một công cụ tìm kiếm dành riêng cho tài nguyên AWS.

## AWS Resource Explorer dùng để làm gì?

Trong một tài khoản AWS, tài nguyên có thể nằm rải rác ở nhiều nơi, chẳng hạn như:

- EC2 instance tại Singapore.
- DynamoDB table tại Tokyo.
- Lambda function tại North Virginia.
- S3 bucket có phạm vi toàn cầu.
- Một số tài nguyên thử nghiệm đã được tạo từ trước nhưng chưa xóa.

Thay vì phải lần lượt chuyển qua từng Region và mở từng service để kiểm tra, Resource Explorer cho phép tìm các tài nguyên đó từ một giao diện chung.

{{% notice note %}}
Resource Explorer duy trì các index chứa thông tin về tài nguyên trong từng Region. Khi cấu hình một Region làm aggregator index, người dùng có thể tìm kiếm tài nguyên từ nhiều Region tại một nơi.
{{% /notice %}}

## Các bước thực hành

Trong bài thực hành này, mình thử tìm các tài nguyên EC2, S3 và những tài nguyên chưa được gắn tag.

**Bước 1:** Truy cập AWS Resource Explorer.

Đăng nhập AWS Management Console và tìm: AWS Resource Explorer

Sau đó chọn Resource search.

AWS hiện cho phép người dùng có quyền phù hợp bắt đầu tìm kiếm ngay khi truy cập service. Với policy `AWSResourceExplorerReadOnlyAccess`, người dùng có thể nhận kết quả tìm kiếm ban đầu. Để có inventory đầy đủ và tự động tạo các thành phần cần thiết, tài khoản cần thêm quyền `iam:CreateServiceLinkedRole`, quyền này được bao gồm trong policy `AWSResourceExplorerFullAccess`.

**Bước 2:** Thử tìm tất cả tài nguyên EC2.

Trong ô tìm kiếm, nhập:

```text
service:ec2
```

Query này trả về các tài nguyên được quản lý bởi Amazon EC2 mà Resource Explorer đã lập index.
Nếu chỉ muốn tìm EC2 instance, có thể dùng query cụ thể hơn:

```text
resourcetype:ec2:instance
```

Resource Explorer hỗ trợ các bộ lọc như `service`, `resourcetype`, `region`, `tag` và nhiều loại metadata khác.

**Bước 3:** Tìm tài nguyên trong một Region.

Để tìm tài nguyên tại Region Singapore, nhập:

```text
region:ap-southeast-1
```

Có thể kết hợp nhiều điều kiện:

```text
service:ec2 region:ap-southeast-1
```

Query trên chỉ tìm tài nguyên thuộc EC2 tại Region Singapore.

{{% notice tip %}}
Khi sử dụng nhiều bộ lọc, Resource Explorer kết hợp chúng để thu hẹp kết quả tìm kiếm. Đây là cách khá tiện khi tài khoản có nhiều loại tài nguyên khác nhau.
{{% /notice %}}

**Bước 4:** Tìm tài nguyên theo tag.

Giả sử các tài nguyên production được gắn tag:

```text
Environment=Production
```

Có thể tìm bằng query:

```text
tag:Environment=Production
```

Hoặc kết hợp với loại service:

```text
service:ec2 tag:Environment=Production
```

Để tìm theo tag, view đang sử dụng phải được cấu hình bao gồm thuộc tính `tags`. View mặc định được tạo trong quá trình thiết lập đầy đủ thường hỗ trợ việc tìm kiếm này.

**Bước 5:** Tìm những tài nguyên chưa được gắn tag
Một query mình thấy khá hữu ích là:

```text
tag:none
```

Query này trả về các tài nguyên không có tag do người dùng tạo.

Trong thực tế, việc tìm các tài nguyên chưa có tag giúp kiểm tra lại những tài nguyên chưa được phân loại theo project, environment hoặc owner. Đây cũng có thể là bước đầu tiên trước khi rà soát chi phí hoặc dọn dẹp tài nguyên thử nghiệm.

Có thể giới hạn kết quả trong một Region:

```text
tag:none region:ap-southeast-1
```

**Bước 6:** Bật tìm kiếm trên nhiều Region

Nếu tài khoản chưa bật cross-Region search, vào: AWS Resource Explorer → Settings

Chọn **Complete setup and enable cross-Region search**. Tiếp theo:

1. Chọn một Region làm aggregator index, chẳng hạn Singapore.
2. Chọn **Enable cross-Region search in all Regions**.
3. Xác nhận thiết lập.
4. Theo dõi trạng thái indexing.
5. Sau khi hoàn tất, quay lại Resource search và chọn view thuộc aggregator Region.

AWS sẽ tạo index trong các Region được chọn, chuyển index của Region chính thành aggregator index và tạo default view để tìm tài nguyên trên các Region đó.

{{% notice note %}}
Cần lưu ý rằng quá trình indexing không phải lúc nào cũng hoàn thành ngay. Theo tài liệu AWS, tài nguyên có tag thường xuất hiện sau vài phút, trong khi tài nguyên không có tag có thể cần nhiều thời gian hơn. Quá trình đồng bộ ban đầu đến aggregator index cũng có thể có độ trễ.
{{% /notice %}}

## Những điểm mình thấy hữu ích

Điểm hữu ích nhất của Resource Explorer là không phải nhớ chính xác tài nguyên nằm ở Region nào.

Service này cũng hỗ trợ tìm kiếm theo nhiều loại metadata. Ví dụ, thay vì chỉ tìm tên tài nguyên, người dùng có thể tìm theo service, resource type, Region hoặc tag.

Resource Explorer còn được tích hợp với thanh Unified Search trên AWS Management Console. Vì vậy, trong một số trường hợp có thể tìm tài nguyên ngay trên thanh tìm kiếm phía trên của Console mà không cần mở riêng Resource Explorer.

Một điểm khác là Resource Explorer hỗ trợ sử dụng view để kiểm soát phạm vi tài nguyên mà từng người dùng được phép tìm thấy. Ví dụ, một view có thể chỉ hiển thị các tài nguyên mang tag `Environment=Production`, sau đó chỉ cấp quyền truy cập view đó cho nhóm vận hành phù hợp.

## Một số hạn chế cần lưu ý

Resource Explorer là công cụ tìm kiếm và khám phá tài nguyên, không phải công cụ quản lý toàn bộ tài nguyên. Sau khi tìm thấy một EC2 instance hoặc DynamoDB table, người dùng thường vẫn phải mở trang quản lý của service tương ứng để thay đổi cấu hình.

Kết quả tìm kiếm cũng phụ thuộc vào quyền IAM, view và trạng thái indexing. Vì vậy, việc một tài nguyên không xuất hiện chưa chắc có nghĩa là tài nguyên đó không tồn tại.

Với quyền read-only cơ bản, người dùng có thể chỉ nhận được kết quả một phần. Muốn có inventory hoàn chỉnh hoặc tìm kiếm trên nhiều Region thì cần thực hiện thêm phần thiết lập và có các quyền phù hợp.

Ngoài ra, khi dùng từ khóa tự do, thao tác Search có giới hạn số lượng kết quả được trả về. Nếu tài khoản có rất nhiều tài nguyên, nên sử dụng thêm các bộ lọc như Region, service hoặc resource type để thu hẹp kết quả.

## Chi phí

Theo trang pricing của AWS, Resource Explorer được cung cấp mà không có phí sử dụng bổ sung và không có phí thiết lập ban đầu.

Tuy nhiên, một số tính năng hiển thị trong Resource Explorer có thể phụ thuộc vào các dịch vụ khác như AWS Config. Các dịch vụ liên quan vẫn có thể tính phí riêng. Một số API List hoặc Describe của service được gọi cũng có thể phát sinh phí nếu service đó áp dụng cách tính phí cho các API này.

## Kết luận

Sau khi thử AWS Resource Explorer, mình thấy đây là một service khá đơn giản nhưng hữu ích, đặc biệt khi tài khoản có tài nguyên nằm ở nhiều Region.

Service này không trực tiếp tối ưu chi phí hay bảo mật hệ thống, nhưng giúp người dùng có cái nhìn rõ hơn về những tài nguyên đang tồn tại. Từ đó, việc kiểm tra tài nguyên thử nghiệm, tìm tài nguyên thiếu tag hoặc xác định vị trí của một resource trở nên nhanh hơn.

Đối với các tài khoản học tập, Resource Explorer cũng có thể giúp kiểm tra xem mình có vô tình để lại tài nguyên ở một Region khác sau khi hoàn thành bài lab hay không.

Mọi người đã từng gặp trường hợp không tìm thấy tài nguyên chỉ vì chọn nhầm Region chưa? Mình rất mong được nghe thêm các trường hợp thực tế khi sử dụng Resource Explorer.

## Tài liệu tham khảo

1. [AWS Resource Explorer User Guide:](https://docs.aws.amazon.com/.../userguide/welcome.html)

2. [Hướng dẫn bắt đầu với Resource Explorer:](https://docs.aws.amazon.com/resource-explorer/latest/userguide/getting-started.html)

3. [Hướng dẫn tìm kiếm tài nguyên:](https://docs.aws.amazon.com/resource-explorer/latest/userguide/using-search.html)

4. [Cú pháp truy vấn Resource Explorer:](https://docs.aws.amazon.com/resource-explorer/latest/userguide/using-search-query-syntax.html)

5. [Ví dụ các câu truy vấn:](https://docs.aws.amazon.com/resource-explorer/latest/userguide/using-search-query-examples.html)

6. [Thiết lập tìm kiếm trên nhiều Region:](https://docs.aws.amazon.com/resource-explorer/latest/userguide/getting-started-setting-up.html)

7. [Chi phí AWS Resource Explorer:](https://aws.amazon.com/resourceexplorer/pricing/)