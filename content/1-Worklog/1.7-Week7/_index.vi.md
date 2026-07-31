---
title: "Worklog Tuần 7"
date: 2026-07-20
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

{{% notice tip %}}
Tuần 7 tập trung xây dựng các chiến lược recommendation đã tìm hiểu ở tuần 4. Mô hình được huấn luyện và đánh giá trước khi chạy bằng SageMaker Processing Job, sau đó kết nối với FastAPI qua real-time Endpoint, cache và cơ chế fallback.
{{% /notice %}}

## Mục tiêu tuần 7

- Xây dựng phương pháp gợi ý cho khách và người dùng mới.
- Huấn luyện mô hình implicit ALS cho người dùng quay lại.
- Kết hợp và đánh giá các kết quả gợi ý.
- Chạy quy trình xử lý mô hình bằng SageMaker.
- Tích hợp recommendation Endpoint với backend.

## Các công việc triển khai trong tuần

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Xây dựng weighted popularity ranking cho khách.<br>- Tạo TF-IDF feature và cosine similarity cho người dùng mới.<br>- Kiểm tra kết quả với một số thể loại mẫu. | 20/07/2026 | 20/07/2026 | Pandas, Scikit-learn Documentation |
| 3 | - Chuyển tương tác thành implicit score.<br>- Huấn luyện mô hình ALS.<br>- Kết hợp candidate bằng weighted Reciprocal Rank Fusion. | 21/07/2026 | 21/07/2026 | Implicit Library Documentation |
| 4 | - Chia dữ liệu theo thời gian.<br>- Tính Recall@K, NDCG@K và coverage.<br>- Lưu model artifact, mapping và báo cáo đánh giá lên S3. | 22/07/2026 | 22/07/2026 | Scikit-learn, Amazon S3 Documentation |
| 5 | - Đóng gói lệnh huấn luyện.<br>- Gửi SageMaker Processing Job.<br>- Theo dõi trạng thái job và kiểm tra output trên S3. | 23/07/2026 | 23/07/2026 | Amazon SageMaker Documentation |
| 6 | - Kiểm tra response của SageMaker Endpoint.<br>- Kết nối FastAPI với Endpoint.<br>- Bổ sung RecommendationCache và fallback về danh sách phổ biến. | 24/07/2026 | 24/07/2026 | SageMaker Runtime, Boto3 Documentation |

## Kết quả đạt được tuần 7

Sau tuần 7, recommendation pipeline đã được xây dựng và kết nối với ứng dụng.

Một số kết quả đạt được gồm:

- Tạo được danh sách phim phổ biến cho khách.
- Tạo gợi ý theo thể loại cho người dùng mới.
- Huấn luyện được mô hình implicit ALS cho người dùng có lịch sử tương tác.
- Kết hợp được nhiều nguồn candidate và loại bỏ phim không hợp lệ.
- Lưu model artifact và báo cáo đánh giá trên S3.
- Gọi được SageMaker Endpoint từ FastAPI và có cache, fallback khi cần thiết.
