---
title: "Worklog Tuần 3"
date: 2026-06-22
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

{{% notice tip %}}
Tuần 3 tập trung tìm hiểu kiến trúc của ứng dụng web sử dụng React/Vite và FastAPI. Bên cạnh luồng request và cách tổ chức mã nguồn, tuần này còn tìm hiểu JWT, Docker, CI/CD, cache và phương án xử lý khi dịch vụ gợi ý gặp lỗi.
{{% /notice %}}

## Mục tiêu tuần 3

- Hiểu kiến trúc client-server và nguyên tắc thiết kế REST API.
- Nắm vai trò của React/Vite ở frontend và FastAPI ở backend.
- Hiểu cách tổ chức backend theo router, service và repository.
- Tìm hiểu xác thực bằng JWT và cách bảo vệ thông tin nhạy cảm.
- Nắm lý thuyết cơ bản về Docker, CI/CD, logging, cache và fallback.

## Các công việc triển khai trong tuần

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu kiến trúc client-server.<br>- Ôn HTTP method, status code, header và JSON.<br>- Tìm hiểu nguyên tắc thiết kế REST API. | 22/06/2026 | 22/06/2026 | MDN Web Docs |
| 3 | - Tìm hiểu component, props, state và hook trong React.<br>- Tìm hiểu quy trình phát triển và build ứng dụng bằng Vite.<br>- Ghi chú cách frontend gọi API. | 23/06/2026 | 23/06/2026 | React và Vite Documentation |
| 4 | - Tìm hiểu router, request model và dependency của FastAPI.<br>- Tìm hiểu mô hình router-service-repository.<br>- Phân tích luồng xử lý một request backend. | 24/06/2026 | 24/06/2026 | FastAPI Documentation |
| 5 | - Tìm hiểu password hashing, JWT, access token và thời hạn token.<br>- Tìm hiểu CORS và protected route.<br>- Ghi chú cách lưu secret an toàn. | 25/06/2026 | 25/06/2026 | FastAPI Security, JWT Documentation |
| 6 | - Tìm hiểu Docker image, container và Docker Compose.<br>- Tìm hiểu CI/CD bằng GitHub Actions.<br>- Tìm hiểu CloudWatch Logs, cache và fallback trong ứng dụng. | 26/06/2026 | 26/06/2026 | Docker và GitHub Actions Documentation |

## Kết quả đạt được tuần 3

Sau tuần 3, đã hình dung được cấu trúc và luồng xử lý đầy đủ của ứng dụng trước khi bắt đầu lập trình.

Một số kết quả đạt được gồm:

- Hiểu request đi từ giao diện React đến FastAPI và các dịch vụ AWS như thế nào.
- Nắm vai trò của component, state và API client trong frontend.
- Hiểu cách tách router, service và repository trong backend.
- Nắm quy trình đăng nhập, phát hành và kiểm tra JWT.
- Hiểu mục đích của Docker Compose và CI/CD khi triển khai ứng dụng.
- Biết vai trò của logging, cache và fallback đối với độ ổn định hệ thống.
