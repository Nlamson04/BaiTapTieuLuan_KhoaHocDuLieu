# BaiTapTieuLuan_KhoaHocDuLieu
## Họ và tên: Nguyễn Lam Sơn
## lớp: K58KTPM
## MSSV: K225480106076
## BÀI TẬP TIỂU LUẬN KẾT THUCS HỌC PHẦN
Link Youtube: https://www.youtube.com/watch?v=1RaNPiNNFHA
Link DemoWeb: https://drive.google.com/drive/folders/1vixJWO0zY-PNQboBw6ylrU10mUKJyDrD?usp=drive_link

# 🎬 Phân Tích Dữ Liệu Điện Ảnh & Xây Dựng Hệ Thống Gợi Ý Phim (TMDB 5000)

## 📌 Giới thiệu dự án
Đây là bài tiểu luận môn Khoa học Dữ liệu (Data Science), tập trung vào việc nghiên cứu, khai phá và áp dụng các thuật toán Học máy (Machine Learning) trên bộ dữ liệu điện ảnh nổi tiếng **TMDB 5000 Movie Dataset**. 

Dự án không chỉ hướng đến việc xây dựng một hệ thống gợi ý phim thông minh (Content-Based) mà còn thực hiện Phân tích Dữ liệu Thăm dò (EDA) và Phân cụm (Clustering) để tìm ra các insight sâu sắc về thị trường điện ảnh, đặc biệt là mối quan hệ giữa chi phí đầu tư và khả năng sinh lời.

## 📂 Nguồn dữ liệu (Dataset)
* **Dataset:** [TMDB 5000 Movie Dataset](https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata) trên Kaggle.
* **Kích thước gốc:** 4803 bộ phim với 20 thuộc tính khác nhau (Ngân sách, Doanh thu, Thể loại, Điểm đánh giá, Dàn diễn viên...).

## 🚀 Nội dung chính của dự án

### 1. Tiền xử lý và Làm sạch Dữ liệu (Data Preprocessing)
* Lọc bỏ các dữ liệu nhiễu/thiếu hụt thông tin tài chính (loại bỏ các bộ phim có Ngân sách hoặc Doanh thu <= 1000 USD). Sau khi làm sạch, tập dữ liệu còn lại **3211 bộ phim** chất lượng.
* Xử lý, chuyển đổi định dạng `datetime` và trích xuất các đặc trưng thời gian (năm phát hành).

### 2. Phân tích Dữ liệu Thăm dò (EDA)
Thực hiện trả lời 5 câu hỏi trọng tâm bằng hình ảnh trực quan hóa:
1. Thể loại phim (Genres) nào được sản xuất nhiều nhất trên thị trường?
2. Phân bổ điểm số đánh giá (Vote Average) của khán giả dành cho các tác phẩm điện ảnh.
3. Mối tương quan giữa Ngân sách (Budget) đầu tư và Doanh thu (Revenue) thu về.
4. Top những bộ phim mang lại lợi nhuận khổng lồ nhất lịch sử.
5. Xu hướng số lượng phim phát hành qua các năm.

### 3. Phân cụm Dữ liệu (Clustering bằng K-Means)
* Áp dụng thuật toán Học máy không giám sát **K-Means Clustering** trên 2 biến số kinh tế: Ngân sách và Doanh thu.
* Phân mảnh thành công thị trường điện ảnh thành các cụm đặc trưng. Nổi bật nhất là việc nhận diện và phân tích đặc điểm của cụm phim **"Đầu tư thấp, sinh lời khủng"** (chủ yếu tập trung ở các kịch bản xuất sắc thuộc thể loại Drama, Comedy, Horror thay vì dựa dẫm vào kỹ xảo đắt tiền).

### 4. Hệ thống Gợi ý Phim (Movie Recommendation System)
* Xây dựng hệ thống gợi ý sử dụng phương pháp **Lọc dựa trên nội dung (Content-Based Filtering)**.
* Sử dụng thuật toán `TfidfVectorizer` để mã hóa dữ liệu dạng văn bản (text) thành ma trận đặc trưng.
* Áp dụng **Cosine Similarity** để tính toán độ tương đồng giữa các ma trận vector, từ đó gợi ý cho người dùng những bộ phim có nội dung cốt truyện và phong cách giống nhất với bộ phim họ vừa xem (Đã test nghiệm thu thành công với phim *The Dark Knight Rises*).

## 💡 Kết luận rút ra (Insights)
* Ngành công nghiệp điện ảnh TMDB được "chống lưng" chủ yếu bởi 3 thể loại phổ biến nhất: Drama, Comedy và Thriller.
* Dù chi phí đầu tư có độ tương quan thuận khá mạnh tới doanh thu phòng vé, tuy nhiên cốt truyện và chất lượng kịch bản (thuộc tính nội dung) mới là thứ định đoạt tỷ suất lợi nhuận thực tế (như đã chứng minh qua thuật toán K-Means).
* Thuật toán gợi ý bằng Cosine Similarity chạy ổn định, nhanh chóng, mang lại trải nghiệm cá nhân hóa chính xác mà không gặp phải vấn đề "Cold-start" cho các bộ phim mới.

## 🛠️ Công nghệ & Thư viện sử dụng (Tech Stack)
* **Ngôn ngữ:** Python 3
* **Môi trường:** Jupyter Notebook
* **Thư viện thao tác dữ liệu:** `pandas`, `numpy`
* **Thư viện trực quan hóa:** `matplotlib`, `seaborn`
* **Thư viện Machine Learning:** `scikit-learn` (KMeans, StandardScaler, TfidfVectorizer, cosine_similarity)
* **Xử lý dữ liệu văn bản/JSON:** `json`, `ast`
