---
title: "Tự đánh giá"
date: 2026-07-31
weight: 6
chapter: false
pre: " <b> 6. </b> "
---

{{% notice tip %}}
Phần này đánh giá kiến thức, kỹ năng, thái độ làm việc và những hạn chế được ghi nhận trong kỳ thực tập từ ngày 01/06/2026 đến 31/07/2026. Nội dung đánh giá dựa trên dự án hệ thống gợi ý phim, tài liệu workshop và kết quả kiểm thử đã thực hiện.
{{% /notice %}}

## Tổng quan kỳ thực tập

Trong chương trình First Cloud AI Journey, tôi dành bốn tuần đầu để tìm hiểu điện toán đám mây, các dịch vụ AWS, kiến trúc web, bảo mật và lý thuyết hệ thống gợi ý. Trong bốn tuần cuối, tôi áp dụng các kiến thức này để xây dựng và viết tài liệu cho hệ thống gợi ý phim sử dụng React/Vite, FastAPI, Amazon S3, DynamoDB, EC2, SageMaker, IAM và CloudWatch.

Dự án giúp tôi kết nối kiến thức lý thuyết với một luồng kỹ thuật hoàn chỉnh: chuẩn bị dữ liệu, lưu trữ dữ liệu ứng dụng, huấn luyện mô hình gợi ý, cung cấp kết quả qua API, kiểm thử các nhóm người dùng và rà soát bảo mật, chi phí cloud.

## Kết quả đạt được

### Kiến thức Cloud và AWS

- Hiểu vai trò của IAM, VPC, EC2, S3, DynamoDB, SageMaker, CloudWatch và AWS Budgets.
- Biết cách tách dữ liệu ứng dụng trong DynamoDB khỏi dataset và model artifact trên S3.
- Hiểu nguyên tắc least privilege, service role, instance profile, logging và kiểm soát chi phí cơ bản.
- Phân biệt xử lý theo batch bằng SageMaker Processing Job và suy luận thời gian thực bằng SageMaker Endpoint.

### Phát triển ứng dụng

- Xây dựng các giao diện React/Vite chính cho việc xem phim, xác thực và onboarding.
- Tổ chức backend FastAPI theo router, service, repository và recommendation provider.
- Xây dựng các luồng chính cho tài khoản, dữ liệu phim, tương tác, cache gợi ý và fallback.
- Đóng gói frontend, backend bằng Docker và chạy thử ứng dụng trên EC2.

### Dữ liệu và Machine Learning

- Khảo sát, làm sạch và ánh xạ dữ liệu từ bộ dữ liệu phim.
- Xây dựng popularity ranking, content-based filtering, implicit ALS và hybrid ranking.
- Biết cách đánh giá kết quả gợi ý bằng Recall@K, NDCG@K và coverage.
- Lưu model artifact, mapping và báo cáo đánh giá trên S3.

### Tài liệu và kiểm thử

- Viết tài liệu về kiến trúc, luồng dữ liệu, huấn luyện, suy luận, bảo mật và cleanup.
- Chuẩn bị screenshot và sơ đồ để minh họa các bước triển khai.
- Kiểm thử các luồng khách, người dùng mới, người dùng quay lại, tương tác, cache và fallback.
- Duy trì nội dung báo cáo tiếng Anh và tiếng Việt nhất quán.

## Bảng tự đánh giá

| STT | Tiêu chí | Minh chứng trong kỳ thực tập | Tự đánh giá |
| --- | --- | --- | --- |
| 1 | Kiến thức chuyên môn | Áp dụng kiến thức AWS, phát triển web, xử lý dữ liệu và hệ thống gợi ý vào một dự án tích hợp. | Tốt |
| 2 | Khả năng học hỏi | Tìm hiểu nhiều dịch vụ AWS và nội dung Machine Learning mới trong thời gian giới hạn. | Tốt |
| 3 | Khả năng thực hành | Hoàn thành các luồng ứng dụng và gợi ý chính, nhưng chưa hoàn thiện yêu cầu production. | Khá |
| 4 | Tư duy giải quyết vấn đề | Xử lý các vấn đề về định dạng dữ liệu, quyền, môi trường, API và tích hợp mô hình. Cần luyện thêm với sự cố phức tạp. | Khá |
| 5 | Trách nhiệm và tiến độ | Bám sát kế hoạch 8 tuần, hoàn thành các mốc dự án và nội dung báo cáo cần thiết. | Tốt |
| 6 | Kỹ năng viết tài liệu | Ghi lại kiến trúc, quy trình, kết quả mong đợi, screenshot, hạn chế và các bước cleanup. | Tốt |
| 7 | Giao tiếp và báo cáo | Duy trì worklog và tổng hợp quyết định kỹ thuật. Cần báo cáo ngắn gọn, đều đặn hơn. | Khá |
| 8 | Nhận thức bảo mật và chi phí | Quan tâm đến least privilege, credential, logging, budget, fallback và cleanup tài nguyên. | Tốt |
| 9 | Tính chủ động | Chủ động đọc tài liệu, so sánh giải pháp và bổ sung các bước validate, fallback đơn giản. | Tốt |
| 10 | Kết quả tổng thể | Hoàn thành dự án ở mức workshop và đạt các mục tiêu học tập chính của kỳ thực tập. | Tốt |

## Điểm mạnh

- Có khả năng tự học và sắp xếp kiến thức theo trình tự triển khai rõ ràng.
- Có thể kết nối frontend, backend, dữ liệu, Machine Learning và các dịch vụ AWS trong cùng một kiến trúc.
- Cẩn thận khi viết tài liệu về quy trình, minh chứng, hạn chế, bảo mật và cleanup.
- Chủ động kiểm thử nhiều nhóm người dùng và xem xét luồng lỗi thay vì chỉ trình diễn trường hợp thành công.
- Duy trì tiến độ tương đối ổn định từ giai đoạn học lý thuyết đến thực hành.

## Nội dung cần cải thiện

- Cải thiện khả năng tự động hóa hạ tầng bằng AWS CDK, CloudFormation hoặc Terraform.
- Bổ sung thêm unit test, integration test, performance test và kiểm thử phục hồi lỗi.
- Nâng cao kiến thức MLOps về đóng gói model, model registry, tự động phê duyệt, rollback và drift monitoring.
- Tăng tốc độ xử lý lỗi liên quan đến IAM, networking và các dịch vụ cloud phân tán.
- Báo cáo blocker và quyết định kỹ thuật ngắn gọn, nhất quán hơn.
- Tích lũy thêm kinh nghiệm đo lường hành vi người dùng thực tế thay vì chủ yếu dựa vào metric offline.

## Kế hoạch phát triển

1. Xây dựng lại hạ tầng bằng công cụ Infrastructure as Code và tách cấu hình development, production.
2. Bổ sung kiểm thử tự động và CI check cho data pipeline, backend API và các kịch bản gợi ý.
3. Hoàn thiện model deployment pipeline với versioning, approval, monitoring và rollback.
4. Thực hành CloudWatch dashboard, alarm, load test và phân tích chi phí bằng các mục tiêu đo lường cụ thể.
5. Tiếp tục cải thiện giao tiếp kỹ thuật thông qua cập nhật tiến độ ngắn, sơ đồ và báo cáo có cấu trúc.

## Đánh giá tổng thể

Tôi tự đánh giá đã hoàn thành mục tiêu kỳ thực tập ở mức **Tốt**. Tôi hoàn thành lộ trình học tập, xây dựng được dự án hoạt động ở mức workshop và cải thiện kỹ năng AWS, phát triển phần mềm, dữ liệu, Machine Learning và viết tài liệu. Tuy nhiên, hệ thống vẫn cần bổ sung tự động hóa, kiểm thử production, giám sát và kinh nghiệm vận hành trước khi có thể xem là sẵn sàng cho môi trường production.
