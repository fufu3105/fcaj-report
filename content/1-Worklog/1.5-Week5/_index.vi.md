---
title: "Worklog Tuần 5"
date: 2026-07-06
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

{{% notice tip %}}
Tuần 5 bắt đầu giai đoạn thực hành bằng việc thiết lập môi trường dự án, khảo sát và làm sạch dữ liệu phim. Sau đó chuẩn bị cấu trúc lưu trữ trên Amazon S3, tạo các bảng DynamoDB và nạp dữ liệu ban đầu cho ứng dụng.
{{% /notice %}}

## Mục tiêu tuần 5

- Chuẩn bị đầy đủ môi trường phát triển cho frontend, backend và Machine Learning.
- Khảo sát, làm sạch và chuẩn hóa dữ liệu phim.
- Tổ chức các vùng dữ liệu và model artifact trên Amazon S3.
- Tạo năm bảng DynamoDB theo access pattern của ứng dụng.
- Nạp và kiểm tra dữ liệu phim, danh sách phổ biến ban đầu.

## Các công việc triển khai trong tuần

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Khởi tạo repository và ML submodule.<br>- Cài Python, Node.js, Docker và AWS CLI.<br>- Chuẩn bị file biến môi trường từ mẫu của dự án. | 06/07/2026 | 06/07/2026 | README và ghi chú dự án |
| 3 | - Khảo sát các file movie, rating, link, credit và keyword.<br>- Kiểm tra giá trị thiếu, trùng lặp và kiểu dữ liệu.<br>- Ánh xạ MovieLens ID sang TMDB ID. | 07/07/2026 | 07/07/2026 | Kaggle Dataset, Pandas Documentation |
| 4 | - Tạo bucket S3 cho dự án.<br>- Chuẩn bị các prefix raw, processed, training, inference, models và evaluation.<br>- Bật Block Public Access và encryption. | 08/07/2026 | 08/07/2026 | Amazon S3 Documentation |
| 5 | - Tạo các bảng Movies, PopularMovies, Users, UserInteractions và RecommendationCache.<br>- Kiểm tra partition key, sort key và trạng thái bảng. | 09/07/2026 | 09/07/2026 | Amazon DynamoDB Documentation |
| 6 | - Nạp metadata phim và danh sách phim phổ biến.<br>- Kiểm tra một số bản ghi bằng AWS Console và CLI.<br>- Sửa các bản ghi thiếu trường bắt buộc. | 10/07/2026 | 10/07/2026 | AWS CLI và script dữ liệu của dự án |

## Kết quả đạt được tuần 5

Sau tuần 5, tầng dữ liệu cơ bản đã sẵn sàng để phục vụ ứng dụng và quá trình huấn luyện mô hình.

Một số kết quả đạt được gồm:

- Thiết lập được môi trường phát triển và chạy kiểm tra các thành phần chính.
- Làm sạch dữ liệu phim, xử lý giá trị thiếu và thống nhất định danh phim.
- Tạo cấu trúc S3 cho dữ liệu thô, dữ liệu đã xử lý, model và báo cáo.
- Tạo thành công năm bảng DynamoDB theo thiết kế.
- Nạp được dữ liệu Movies và PopularMovies.
- Kiểm tra dữ liệu mẫu và sửa các lỗi định dạng đơn giản.
