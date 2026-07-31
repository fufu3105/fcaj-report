---
title: "Worklog Tuần 2"
date: 2026-06-15
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

{{% notice tip %}}
Tuần 2 tập trung tìm hiểu chức năng và cách phối hợp của các dịch vụ AWS được lựa chọn cho hệ thống gợi ý phim. Nội dung được học theo từng nhóm gồm bảo mật, mạng, máy chủ, lưu trữ, cơ sở dữ liệu, Machine Learning và giám sát.
{{% /notice %}}

## Mục tiêu tuần 2

- Hiểu vai trò của IAM trong quản lý danh tính và phân quyền.
- Nắm các thành phần mạng cơ bản của VPC.
- Hiểu cách EC2 cung cấp máy chủ cho ứng dụng.
- Phân biệt mục đích sử dụng của Amazon S3 và DynamoDB.
- Hiểu vai trò của SageMaker, CloudWatch và AWS Budgets trong dự án.

## Các công việc triển khai trong tuần

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu IAM User, Group, Role và Policy.<br>- Phân biệt authentication và authorization.<br>- Học nguyên tắc least privilege và MFA. | 15/06/2026 | 15/06/2026 | AWS IAM Documentation |
| 3 | - Tìm hiểu VPC, subnet, route table và Internet Gateway.<br>- Phân biệt Security Group và Network ACL.<br>- Tìm hiểu luồng request từ Internet đến EC2. | 16/06/2026 | 16/06/2026 | Amazon VPC Documentation |
| 4 | - Tìm hiểu EC2 Instance, AMI, EBS, Key Pair và Elastic IP.<br>- So sánh một số loại instance cơ bản.<br>- Tìm hiểu Instance Profile dành cho ứng dụng. | 17/06/2026 | 17/06/2026 | Amazon EC2 Documentation |
| 5 | - Tìm hiểu bucket, object, prefix, versioning và encryption của S3.<br>- Tìm hiểu table, partition key, sort key và access pattern của DynamoDB.<br>- So sánh hai dịch vụ lưu trữ. | 18/06/2026 | 18/06/2026 | Amazon S3 và DynamoDB Documentation |
| 6 | - Tìm hiểu SageMaker Processing Job và real-time Endpoint.<br>- Tìm hiểu CloudWatch Logs, metrics và alarm.<br>- Tìm hiểu cách tạo cảnh báo chi phí bằng AWS Budgets. | 19/06/2026 | 19/06/2026 | Amazon SageMaker, CloudWatch và AWS Budgets Documentation |

## Kết quả đạt được tuần 2

Sau tuần 2, đã hiểu được vai trò của từng dịch vụ AWS trong kiến trúc dự kiến của hệ thống.

Một số kết quả đạt được gồm:

- Hiểu cách IAM quản lý người dùng, role và quyền truy cập.
- Nắm được các thành phần mạng cần thiết để EC2 có thể nhận request từ Internet.
- Hiểu các thành phần cơ bản để tạo và truy cập EC2 Instance.
- Phân biệt S3 dùng cho file, dataset, model artifact và DynamoDB dùng cho dữ liệu truy vấn nhanh.
- Phân biệt SageMaker Processing Job dùng cho xử lý theo batch và Endpoint dùng cho suy luận thời gian thực.
- Hiểu vai trò của CloudWatch và AWS Budgets trong giám sát hệ thống và chi phí.
