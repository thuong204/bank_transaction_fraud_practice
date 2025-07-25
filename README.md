<img width="968" height="549" alt="image" src="https://github.com/user-attachments/assets/e0135db2-22e7-4f41-9081-22cb0b01788a" />

# Hệ thống Phát hiện Gian lận trong Giao dịch Ngân hàng

## 📝 Mô tả dự án

Dự án này xây dựng một hệ thống phát hiện gian lận tự động cho các giao dịch ngân hàng, sử dụng các kỹ thuật học máy để phân tích và dự đoán các giao dịch đáng ngờ.

## 🎯 Tính năng chính

- Phân tích dữ liệu giao dịch đa chiều
- Xây dựng điểm đánh giá gian lận (Fraud Score)
- Huấn luyện và so sánh nhiều mô hình học máy
- Đánh giá và tối ưu hiệu suất mô hình
- Xuất báo cáo và dự đoán chi tiết

## 🔧 Cấu trúc dự án

```
.
├── models/                 # Thư mục chứa các mô hình đã huấn luyện
├── results/               # Thư mục chứa kết quả dự đoán
├── Test/                  # Thư mục chứa notebook và mã nguồn
│   └── bank.ipynb        # Jupyter notebook chính
└── README.md             # Tài liệu dự án
```

## 📊 Dữ liệu

Dữ liệu giao dịch bao gồm các trường:

- TransactionID: ID giao dịch
- AccountID: ID tài khoản
- TransactionAmount: Số tiền giao dịch
- TransactionType: Loại giao dịch
- Location: Địa điểm
- DeviceID: ID thiết bị
- IP Address: Địa chỉ IP
- MerchantID: ID người bán
- AccountBalance: Số dư tài khoản
- PreviousTransactionDate: Ngày giao dịch trước đó
- Channel: Kênh giao dịch
- CustomerAge: Tuổi khách hàng
- CustomerOccupation: Nghề nghiệp khách hàng
- TransactionDuration: Thời gian giao dịch
- LoginAttempts: Số lần đăng nhập

## 🚀 Quy trình xử lý

1. **Phân tích & Đề xuất quy tắc**

   - Phân tích các trường dữ liệu
   - Xác định các chỉ số bất thường
   - Xây dựng quy tắc gán nhãn gian lận

2. **Tiền xử lý dữ liệu**

   - Xử lý giá trị thiếu
   - Mã hóa biến phân loại
   - Chuẩn hóa dữ liệu số
   - Tạo đặc trưng mới

3. **Chọn đặc trưng**

   - Sử dụng SelectKBest
   - Phân tích độ quan trọng của đặc trưng
   - Trực quan hóa kết quả

4. **Huấn luyện mô hình**

   - RandomForestClassifier
   - LogisticRegression
   - Pipeline xử lý và huấn luyện

5. **Đánh giá mô hình**

   - Hold-out Validation
   - K-Fold Cross Validation
   - Stratified K-Fold
   - Learning Curves
   - ROC và PR Curves

6. **Lưu mô hình và dự đoán**
   - Lưu pipeline hoàn chỉnh
   - Xuất kết quả dự đoán
   - Phân tích độ tin cậy

## 📈 Kết quả

Kết quả dự đoán được lưu trong file CSV với các thông tin:

- TransactionID và AccountID
- TransactionAmount
- FraudScore ban đầu
- Predicted_Fraud: Dự đoán nhị phân (0/1)
- Fraud_Probability: Xác suất gian lận
- Prediction_Confidence: Độ tin cậy
- Confidence_Level: Mức độ tin cậy (Thấp/Trung bình/Cao)

## 💻 Hướng dẫn sử dụng

### Cài đặt môi trường

```bash
sudo apt install python3-sklearn python3-seaborn
```

### Nạp và sử dụng mô hình

```python
import joblib

# Nạp mô hình
model = joblib.load('models/fraud_detection_model.pkl')

# Dự đoán
predictions = model.predict(X_new)
probabilities = model.predict_proba(X_new)[:, 1]
```

### Lưu ý quan trọng

- Dữ liệu đầu vào phải có cùng cấu trúc với dữ liệu huấn luyện
- Các biến phân loại phải được mã hóa tương tự
- Dữ liệu số phải được chuẩn hóa cùng cách

## 🔍 Đánh giá hiệu suất

- Accuracy
- Precision & Recall
- ROC-AUC Score
- Confusion Matrix
- Learning Curves

## 🛠️ Công nghệ sử dụng

- Python 3
- scikit-learn
- pandas
- numpy
- seaborn
- matplotlib

## 📝 Tác giả

[Tên tác giả]

## 📄 Giấy phép

[Loại giấy phép]
