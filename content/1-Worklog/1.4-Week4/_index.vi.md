---
title: "Worklog Tuần 4"
date: 2026-06-29
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

{{% notice tip %}}
Tuần 4 tập trung tìm hiểu lý thuyết về hệ thống gợi ý phim. Các phương pháp được nghiên cứu gồm popularity ranking, content-based filtering, collaborative filtering và hybrid recommendation, kèm theo cách đánh giá mô hình trước khi triển khai.
{{% /notice %}}

## Mục tiêu tuần 4

- Hiểu bài toán gợi ý và các loại dữ liệu phản hồi từ người dùng.
- Tìm hiểu các phương pháp gợi ý phù hợp với từng trạng thái người dùng.
- Hiểu thuật toán implicit ALS và cách kết hợp nhiều danh sách gợi ý.
- Nắm các vấn đề cold-start, lọc nội dung đã xem và giải thích kết quả.
- Tìm hiểu cách chia dữ liệu và đánh giá mô hình offline.

## Các công việc triển khai trong tuần

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu mục tiêu của recommendation system.<br>- Phân biệt explicit feedback và implicit feedback.<br>- Tìm hiểu bài toán cold-start. | 29/06/2026 | 29/06/2026 | Tài liệu nhập môn Recommender Systems |
| 3 | - Tìm hiểu popularity ranking.<br>- Tìm hiểu TF-IDF và cosine similarity trong content-based filtering.<br>- Xác định cách gợi ý cho khách và người dùng mới. | 30/06/2026 | 30/06/2026 | Scikit-learn Documentation |
| 4 | - Tìm hiểu collaborative filtering và matrix factorization.<br>- Tìm hiểu implicit feedback và thuật toán ALS.<br>- Ghi chú cách tạo trọng số cho các hành vi người dùng. | 01/07/2026 | 01/07/2026 | Implicit Library Documentation |
| 5 | - Tìm hiểu hybrid recommendation và Reciprocal Rank Fusion.<br>- Tìm hiểu cách loại phim đã xem hoặc không hợp lệ.<br>- Tìm hiểu reason code để giải thích gợi ý. | 02/07/2026 | 02/07/2026 | Tài liệu nghiên cứu và ghi chú dự án |
| 6 | - Tìm hiểu cách chia train, validation và test theo thời gian.<br>- Tìm hiểu Recall@K, NDCG@K và coverage.<br>- Xác định tiêu chí đơn giản để chấp nhận mô hình mới. | 03/07/2026 | 03/07/2026 | Scikit-learn và tài liệu đánh giá hệ gợi ý |

## Kết quả đạt được tuần 4

Sau tuần 4, đã hoàn thành phần lý thuyết nền tảng và xác định được hướng xây dựng hệ thống gợi ý cho dự án.

Một số kết quả đạt được gồm:

- Hiểu sự khác nhau giữa popularity, content-based, collaborative filtering và hybrid recommendation.
- Chọn popularity cho khách, content-based cho người dùng mới và ALS cho người dùng có lịch sử.
- Hiểu cách chuyển các sự kiện click, watch, rate, like thành implicit score.
- Nắm mục đích của TF-IDF, cosine similarity, ALS và Reciprocal Rank Fusion.
- Hiểu các metric Recall@K, NDCG@K và coverage.
- Hoàn thành bản thiết kế logic cho recommendation pipeline trước khi thực hành.
