---
title: "Worklog Tuần 6"
date: 2026-07-13
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

{{% notice tip %}}
Tuần 6 tập trung xây dựng ứng dụng web xem phim bằng React/Vite và FastAPI. Các luồng đăng ký, đăng nhập, onboarding, xem danh mục phim và ghi nhận hành vi người dùng được hoàn thiện trước khi đóng gói bằng Docker và chạy thử trên EC2.
{{% /notice %}}

## Mục tiêu tuần 6

- Xây dựng giao diện danh mục và trang thông tin phim.
- Tạo cấu trúc backend FastAPI và các API chính.
- Hoàn thiện đăng ký, đăng nhập và onboarding.
- Ghi nhận các tương tác của người dùng vào DynamoDB.
- Chạy ứng dụng bằng Docker Compose trên EC2.

## Các công việc triển khai trong tuần

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tạo layout, thanh điều hướng và movie card.<br>- Xây dựng trang danh mục và trang chi tiết phim.<br>- Tạo API client dùng chung ở frontend. | 13/07/2026 | 13/07/2026 | React và Vite Documentation |
| 3 | - Tạo cấu trúc router, service và repository FastAPI.<br>- Xây dựng API lấy danh sách phim, phim phổ biến và chi tiết phim.<br>- Kết nối backend với DynamoDB. | 14/07/2026 | 14/07/2026 | FastAPI, Boto3 Documentation |
| 4 | - Xây dựng API đăng ký và đăng nhập.<br>- Hash mật khẩu và phát hành JWT.<br>- Xây dựng màn hình onboarding chọn thể loại yêu thích. | 15/07/2026 | 15/07/2026 | FastAPI Security Documentation |
| 5 | - Ghi nhận sự kiện click, watch, rate, reaction và share.<br>- Kiểm tra dữ liệu trong UserInteractions.<br>- Sửa lỗi validate request đơn giản. | 16/07/2026 | 16/07/2026 | Boto3, DynamoDB Documentation |
| 6 | - Tạo Docker image cho frontend và backend.<br>- Chạy hệ thống bằng Docker Compose trên EC2.<br>- Cấu hình Security Group và kiểm tra ứng dụng bằng trình duyệt. | 17/07/2026 | 17/07/2026 | Docker và Amazon EC2 Documentation |

## Kết quả đạt được tuần 6

Sau tuần 6, ứng dụng web cơ bản đã hoạt động và có thể lưu dữ liệu người dùng trên DynamoDB.

Một số kết quả đạt được gồm:

- Hoàn thành giao diện danh mục, movie card và trang chi tiết phim.
- Xây dựng các API đọc dữ liệu phim từ DynamoDB.
- Hoàn thành đăng ký, đăng nhập, JWT và onboarding.
- Ghi nhận được các hành vi chính của người dùng.
- Đóng gói frontend và backend bằng Docker.
- Chạy được ứng dụng trên EC2 và sửa các lỗi cấu hình ban đầu.
