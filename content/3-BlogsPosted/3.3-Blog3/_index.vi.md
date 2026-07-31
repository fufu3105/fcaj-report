---
title: "Blog 3"
date: 2026-07-29
weight: 3
chapter: false
pre: " <b> 3.3. </b> "
---

# TÌM HIỂU AMAZON DATA LIFECYCLE MANAGER (DLM) – TỰ ĐỘNG QUẢN LÝ EBS SNAPSHOT

Trong quá trình học AWS, mình thường tạo EBS Snapshot để sao lưu dữ liệu của EC2 trước khi thực hiện các thay đổi quan trọng. Tuy nhiên, nếu phải tự tạo snapshot mỗi ngày hoặc tự xóa các bản snapshot cũ thì sẽ khá mất thời gian, đặc biệt khi số lượng EC2 ngày càng nhiều.

Khi tìm hiểu thêm, mình biết đến Amazon Data Lifecycle Manager (Amazon DLM). Đây là một service giúp tự động hóa việc tạo, lưu trữ và xóa Amazon EBS Snapshots theo các chính sách được cấu hình trước.

Theo tài liệu của AWS, DLM giúp giảm thao tác thủ công và đảm bảo các bản backup luôn được tạo đúng lịch.

## Amazon DLM hoạt động như thế nào?

Ý tưởng của DLM khá đơn giản.

Thay vì chọn từng EBS Volume để tạo snapshot, mình chỉ cần xây dựng một Lifecycle Policy. Chính sách này sẽ quy định:
- Tài nguyên nào cần backup.
- Backup vào thời gian nào.
- Giữ lại bao nhiêu bản snapshot.
- Khi nào tự động xóa snapshot cũ.

Ví dụ, mình có thể cấu hình để AWS:
- Tạo snapshot lúc 1:00 AM mỗi ngày.
- Chỉ giữ lại 7 bản snapshot gần nhất.
- Tự động xóa các snapshot cũ hơn.

Nhờ đó, mình không cần nhớ lịch backup hay dọn dẹp snapshot thủ công nữa.

## Thử tạo một Lifecycle Policy

Để hiểu rõ hơn, mình thử tạo một chính sách backup cho EBS Volume.

**Bước 1:** Truy cập AWS Console và tìm Amazon Data Lifecycle Manager.

**Bước 2:** Chọn Create lifecycle policy.

**Bước 3:** Chọn loại tài nguyên.

Trong ví dụ này mình chọn:

```text
EBS Snapshot Policy
```

**Bước 4:** Chọn tài nguyên cần backup.

Có thể chọn thông qua Tags. Ví dụ:

```text
Environment = Production
```

Khi đó, tất cả các EBS Volume có tag này sẽ tự động được áp dụng chính sách backup.

**Bước 5:** Thiết lập lịch chạy.

Ví dụ:
- Chạy mỗi ngày.
- Thời gian: 01:00 UTC.

**Bước 6:** Thiết lập Retention Rule.

Ví dụ:
- Giữ lại 7 snapshot gần nhất.

AWS sẽ tự động xóa những snapshot vượt quá giới hạn này.

**Bước 7:** Kiểm tra và tạo Policy.

Sau khi hoàn tất, DLM sẽ tự động thực hiện việc backup theo đúng lịch đã cấu hình.

{{% notice tip %}}
Việc sử dụng Tags để áp dụng chính sách là một điểm khá hay vì khi có thêm EC2 mới, chỉ cần gắn đúng Tag là sẽ tự động được backup.
{{% /notice %}}

## Những điểm mình thấy hữu ích

Sau khi tìm hiểu, mình thấy Amazon DLM có một số ưu điểm như:
- Tự động tạo EBS Snapshot theo lịch.
- Tự động xóa snapshot cũ để tránh lãng phí dung lượng lưu trữ.
- Có thể áp dụng cho nhiều tài nguyên thông qua Tags.
- Không cần tự viết script hoặc sử dụng cron job.
- Giúp chuẩn hóa quy trình backup trong các dự án.

## Một số điểm cần lưu ý

Bên cạnh những ưu điểm trên, mình cũng thấy có một vài điều cần cân nhắc:
- Amazon DLM chủ yếu phục vụ việc quản lý Amazon EBS Snapshots, nên nếu muốn sao lưu nhiều dịch vụ khác như RDS, DynamoDB hoặc EFS thì AWS Backup sẽ phù hợp hơn.
- Ngoài ra, mặc dù DLM giúp tự động xóa snapshot cũ, nhưng người dùng vẫn cần xây dựng chính sách retention hợp lý. Nếu giữ snapshot quá lâu hoặc tạo quá thường xuyên thì chi phí lưu trữ vẫn sẽ tăng theo thời gian.

## Khi nào nên sử dụng?

Theo mình, Amazon DLM sẽ phù hợp khi:
- Có nhiều EC2 sử dụng EBS Volume.
- Muốn backup EBS định kỳ mà không cần thao tác thủ công.
- Muốn quản lý snapshot theo chính sách thống nhất.
- Muốn giảm chi phí bằng cách tự động xóa snapshot cũ.

## Kết luận

Sau khi tìm hiểu, mình thấy Amazon Data Lifecycle Manager là một service khá đơn giản nhưng rất hữu ích trong việc tự động hóa quy trình sao lưu EBS. Thay vì phải nhớ tạo snapshot hoặc dọn dẹp thủ công, chỉ cần thiết lập một Lifecycle Policy là AWS sẽ thực hiện toàn bộ phần còn lại. Đây là một service mình nghĩ khá phù hợp với những ai đang quản lý nhiều EC2 hoặc muốn xây dựng quy trình backup tự động ngay từ đầu.

## Tài liệu tham khảo

1. [AWS Documentation – Amazon Data Lifecycle Manager:](https://docs.aws.amazon.com/.../snapshot-lifecycle.html)

2. [Automate Amazon EBS Snapshots with Data Lifecycle Manager:](https://docs.aws.amazon.com/.../snapshot-ami-policy.html)

3. [Amazon EBS Snapshots Documentation:](https://docs.aws.amazon.com/.../use.../ebs-snapshots.html)

4. [Amazon EBS Pricing (Snapshots):](https://aws.amazon.com/ebs/pricing/)