# BTL\_TSR\_DBDS

 **Hệ Thống Dự Báo Doanh Thu Sản Phẩm  Sử Dụng Dữ Liệu Lịch Sử Và Deep Learning**

---

## Giới thiệu

Nhóm em với  mục tiêu xây dựng một hệ thống dự báo doanh thu sản phẩm  dựa trên:

* Dữ liệu lịch sử doanh thu (chuỗi thời gian)
* Thông tin sản phẩm (title, giá, rating, review,...)
* Ứng dụng các mô hình học sâu như LSTM, Autoformer , distilbert

Hệ thống bao gồm:

* Phần huấn luyện mô hình dựa trên lịch sử doanh thu theo từng ASIN
* Giao diện demo dự báo doanh thu sản phẩm sử dụng **Streamlit** , và host trên server Cloud
* Hệ thống API Flask để phục vụ dự đoán (có thể tích hợp web frontend)


---

## 📂 Cấu trúc thư mục chung

```
BTL_TSR_DBDS/
├── data/                  # Dữ liệu lịch sử doanh thu theo từng sản phẩm (ASIN)
│   └── sales_history/
├── best_models/           # Chứa các mô hình LSTM,Auto ,distil đã huấn luyện theo từng ASIN
├── reports/               # Báo cáo mô hình & kết quả huấn luyện
├── src/
│   ├── app.py             # Giao diện Streamlit chính
│   ├── api.py             # REST API dự báo sử dụng Flask
│   ├── model.py           # Kiến trúc mô hình TH
│   └── inference.py       # Hàm gọi dự báo mô hình
└── requirements.txt       # Danh sách thư viện sử dụng
    README.md              # File mô tả này
```

---

## Cách chạy mô hình huấn luyện / inference

1. Cài thư viện:

   ```bash
   pip install -r requirements.txt
   ```

2. Chạy API (Flask):

   ```bash
   python src/api.py
   ```


---

## Cách chạy giao diện dự báo với Streamlit

1. Từ thư mục gốc:

   ```bash
   streamlit run src/app.py
   ```

2. Giao diện sẽ hiển thị:

   * Danh sách sản phẩm có sẵn
   * Thông tin sản phẩm: tên, giá, đánh giá
   * Biểu đồ doanh thu
   * Dự báo doanh thu ngày tiếp theo bằng mô hình LSTM



##  Yêu cầu môi trường

* Python >= 3.9
* `torch`, `streamlit`, `pandas`, `matplotlib`, `numpy`, `flask`


