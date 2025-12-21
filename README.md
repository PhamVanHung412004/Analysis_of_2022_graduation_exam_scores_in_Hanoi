# 📊 Analysis of 2022 Graduation Exam Scores in Hanoi

Dự án này là một công cụ toàn diện để thu thập, xử lý, phân tích và trực quan hóa dữ liệu điểm thi tốt nghiệp THPT năm 2022 tại Hà Nội. Dự án giúp người dùng có cái nhìn tổng quan và chi tiết về phổ điểm, số lượng thí sinh dự thi và các thống kê liên quan.

## 🚀 Tính năng chính

- **Thu thập dữ liệu (Crawling):** Tự động tải dữ liệu điểm thi từ nguồn công khai (Vietnamnet) và lưu trữ dưới dạng HTML.
- **Làm sạch dữ liệu (Data Cleaning):** Trích xuất thông tin từ các file HTML thô và chuyển đổi sang định dạng CSV cấu trúc (`data_clean.csv`).
- **Phân tích thống kê (Analysis):**
  - Thống kê số lượng thí sinh dự thi và không dự thi theo từng môn.
  - Phân tích số lượng môn thi của thí sinh.
  - Tạo phổ điểm chi tiết cho 9 môn học: Toán, Văn, Ngoại Ngữ, Lý, Hóa, Sinh, Sử, Địa, GDCD.
- **Trực quan hóa (Visualization):** Sử dụng **Streamlit** để hiển thị các biểu đồ tương tác, bảng dữ liệu và báo cáo phân tích sinh động.

## 📂 Cấu trúc dự án

Dự án được tổ chức theo cấu trúc chuyên nghiệp để dễ dàng quản lý và mở rộng:

```
Analysis_of_2022_graduation_exam_scores_in_Hanoi/
├── data/                       # Thư mục chứa dữ liệu
│   ├── raw/                    # Dữ liệu thô (HTML files tải về)
│   ├── processed/              # Dữ liệu đã làm sạch (data_clean.csv)
│   └── results/                # Kết quả phân tích (Các file CSV thống kê & phổ điểm)
├── src/                        # Mã nguồn (Source code)
│   ├── down_data.py            # Script tải dữ liệu từ web
│   ├── get_data.py             # Script trích xuất và làm sạch dữ liệu
│   ├── fixed.py                # Script thống kê số lượng thí sinh
│   ├── phodiem1.py             # Script tạo phổ điểm các môn
│   ├── show.py                 # Ứng dụng Streamlit hiển thị Dashboard
│   └── init.py                 # Các hàm/lớp hỗ trợ vẽ biểu đồ
├── requirements.txt            # Danh sách các thư viện cần thiết
└── README.md                   # Tài liệu hướng dẫn
```

## 🛠️ Yêu cầu hệ thống

- Python 3.7 trở lên
- Các thư viện Python: `pandas`, `streamlit`, `matplotlib`
- Công cụ `curl` (đã có sẵn trên Linux/macOS, cần cài đặt trên Windows hoặc sử dụng Git Bash)

## 📦 Cài đặt

1.  **Clone dự án về máy:**
    ```bash
    git clone <repository_url>
    cd Analysis_of_2022_graduation_exam_scores_in_Hanoi
    ```

2.  **Cài đặt các thư viện phụ thuộc:**
    ```bash
    pip install -r requirements.txt
    ```

## ▶️ Hướng dẫn sử dụng

Để chạy toàn bộ quy trình từ tải dữ liệu đến hiển thị biểu đồ, hãy thực hiện lần lượt các bước sau:

### Bước 1: Tải dữ liệu (Data Collection)
Chạy script để tải các file HTML chứa điểm thi về thư mục `data/raw`.
```bash
python src/down_data.py
```
*Lưu ý: Quá trình này có thể mất thời gian tùy thuộc vào số lượng thí sinh và tốc độ mạng.*

### Bước 2: Xử lý dữ liệu (Data Processing)
Chuyển đổi dữ liệu từ HTML sang CSV sạch tại `data/processed/data_clean.csv`.
```bash
python src/get_data.py
```

### Bước 3: Phân tích dữ liệu (Data Analysis)
Tính toán thống kê và tạo các file phổ điểm trong `data/results`.
```bash
python src/fixed.py
python src/phodiem1.py
```

### Bước 4: Chạy ứng dụng Dashboard (Visualization)
Khởi chạy ứng dụng web Streamlit để xem kết quả.
```bash
cd src
streamlit run show.py
```
Sau khi chạy, trình duyệt sẽ tự động mở địa chỉ (thường là `http://localhost:8501`) hiển thị Dashboard.

## 📊 Công nghệ sử dụng

- **Python**: Ngôn ngữ lập trình chính.
- **Pandas**: Thư viện mạnh mẽ để xử lý và phân tích dữ liệu dạng bảng.
- **Matplotlib**: Thư viện vẽ biểu đồ căn bản.
- **Streamlit**: Framework giúp xây dựng ứng dụng web khoa học dữ liệu nhanh chóng và đẹp mắt.

## 📝 Ghi chú

- Dữ liệu được thu thập cho mục đích học tập và nghiên cứu cá nhân.
- Hãy đảm bảo bạn có kết nối mạng ổn định khi chạy Bước 1.

---
**Author:** Pham Van Hung
**Project Project:** Analysis of 2022 Graduation Exam Scores in Hanoi
