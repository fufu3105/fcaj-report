---
title: "Worklog Tuần 8"
date: 2026-07-27
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

{{% notice tip %}}
Tuần cuối tập trung kiểm thử các luồng chính, rà soát quyền truy cập và theo dõi hoạt động của hệ thống. Đồng thời hoàn thiện nội dung báo cáo, sắp xếp ảnh minh họa, ghi nhận hạn chế và cleanup các tài nguyên AWS không còn sử dụng.
{{% /notice %}}

## Mục tiêu tuần 8

- Kiểm thử ba nhóm người dùng và các luồng tương tác chính.
- Kiểm tra cache, Endpoint và phương án fallback.
- Rà soát IAM, log và cảnh báo chi phí.
- Hoàn thiện tài liệu, hình ảnh và đánh giá dự án.
- Dọn dẹp tài nguyên AWS có thể tiếp tục phát sinh phí.

## Các công việc triển khai trong tuần

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Kiểm thử khách xem danh mục và danh sách phổ biến.<br>- Kiểm thử đăng ký, đăng nhập và onboarding.<br>- Ghi lại các lỗi giao diện và API. | 27/07/2026 | 27/07/2026 | Test checklist của dự án |
| 3 | - Kiểm thử gợi ý cho người dùng mới và người dùng quay lại.<br>- Kiểm tra cache hit, cache miss và Endpoint fallback.<br>- Sửa các lỗi dữ liệu đơn giản. | 28/07/2026 | 28/07/2026 | Test checklist, CloudWatch Logs |
| 4 | - Rà soát IAM Role của EC2 và SageMaker.<br>- Kiểm tra CloudWatch Logs và AWS Budgets.<br>- Loại bỏ quyền không cần thiết trong phạm vi thực hành. | 29/07/2026 | 29/07/2026 | AWS IAM, CloudWatch và Budgets Documentation |
| 5 | - Hoàn thiện nội dung workshop và worklog.<br>- Sắp xếp screenshot, sơ đồ kiến trúc và bằng chứng kiểm thử.<br>- Rà soát liên kết, chính tả và định dạng. | 30/07/2026 | 30/07/2026 | FCAJ Report Guideline, ghi chú dự án |
| 6 | - Xuất báo cáo và artifact cần lưu giữ.<br>- Cleanup SageMaker Endpoint, Processing Job, EC2, DynamoDB và S3 theo thứ tự phù hợp.<br>- Kiểm tra lại Billing. | 31/07/2026 | 31/07/2026 | AWS Resource Cleanup Checklist |

## Kết quả đạt được tuần 8

Sau tuần cuối, hệ thống và báo cáo đã được rà soát đầy đủ trước khi kết thúc giai đoạn thực tập.

Một số kết quả đạt được gồm:

- Kiểm tra được luồng guest, new user và returning user.
- Xác nhận interaction, cache, Endpoint và fallback hoạt động đúng theo thiết kế.
- Rà soát quyền IAM, CloudWatch Logs và cảnh báo chi phí.
- Sửa một số lỗi nhỏ về dữ liệu, giao diện và cấu hình API.
- Hoàn thiện worklog, tài liệu workshop, hình ảnh và phần đánh giá.
- Lưu lại báo cáo cần thiết và cleanup tài nguyên AWS không còn sử dụng.
