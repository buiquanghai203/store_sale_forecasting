# Dự báo Doanh số Bán hàng tại Cửa hàng Bán lẻ

## Giới thiệu
Bài toán đặt ra là dự báo doanh số bán hàng trong tương lai tại các cửa hàng bán lẻ. Tập dữ liệu được sử dụng trong project này chứa thông tin về doanh số bán hàng trong quá khứ cùng với các thông tin liên quan của **Corporación Favorita**, một nhà bán lẻ thực phẩm lớn tại Ecuador. Công ty này cũng hoạt động tại các quốc gia khác ở Nam Mỹ. 

<img src="https://raw.githubusercontent.com/EkremBayar/Kaggle/refs/heads/main/Images/CF.png" width="25%" />
<img src="https://raw.githubusercontent.com/EkremBayar/Kaggle/refs/heads/main/Images/CF1.jpg" width="35%" />

Tập dữ liệu này được lấy từ cuộc thi công khai trên Kaggle: [Store Sales - Time Series Forecasting](https://www.kaggle.com/competitions/store-sales-time-series-forecasting). Điều này cho phép chúng ta đánh giá hiệu quả mô hình so với những người tham gia khác trong cuộc thi.

## Thông tin về Dữ liệu
Tập dữ liệu bao gồm **54 cửa hàng** và **33 nhóm sản phẩm**. Chuỗi thời gian bắt đầu từ **2013-01-01** và kết thúc vào **2017-08-31**. Trong đó, **15 ngày cuối cùng (2017-08-16 đến 2017-08-31)** là khoảng thời gian cần dự báo doanh số.

### Cấu trúc dữ liệu
Dữ liệu được chia thành **6 tập con**:

1. **Train**: Chứa chuỗi thời gian của các tổ hợp cửa hàng và nhóm sản phẩm. 
   - `sales`: Tổng doanh số bán hàng của một nhóm sản phẩm tại một cửa hàng vào một ngày cụ thể.
   - `onpromotion`: Tổng số sản phẩm trong nhóm đang được khuyến mãi tại một cửa hàng vào một ngày cụ thể.

2. **Test**: Dữ liệu cho giai đoạn cần dự báo doanh số.

3. **Store**: Cung cấp thông tin về cửa hàng như:
   - `city`: Thành phố
   - `state`: Tiểu bang
   - `type`: Loại cửa hàng
   - `cluster`: Cụm cửa hàng

4. **Transactions**: Số lượng giao dịch tại mỗi cửa hàng, có mối tương quan cao với `sales` trong tập Train.

5. **Holidays and Events**: Thông tin về các ngày lễ và sự kiện quan trọng ở Ecuador, hỗ trợ phân tích tác động đến doanh số bán hàng.

6. **Daily Oil Price**: Dữ liệu về giá dầu hàng ngày. Vì Ecuador phụ thuộc vào dầu mỏ, giá dầu có thể ảnh hưởng đến nền kinh tế và sức mua của người tiêu dùng.

## Những Lưu ý Quan Trọng
Tập dữ liệu có một số ghi chú quan trọng giúp hiểu rõ các xu hướng và điểm bất thường:
- **Lương khu vực công** được trả hai lần một tháng (vào ngày 15 và ngày cuối tháng), có thể ảnh hưởng đến doanh số bán hàng.
- **Trận động đất ngày 16/04/2016** (magnitude 7.8) đã ảnh hưởng đáng kể đến hành vi mua sắm, làm tăng doanh số bán hàng tại siêu thị trong thời gian cứu trợ sau đó.

---

## Mục tiêu
Mục tiêu chính của dự án này là **xây dựng mô hình học máy** dự báo doanh số bán hàng chính xác nhất có thể, đồng thời đánh giá hiệu quả so với các phương pháp khác trong cuộc thi Kaggle.

## Liên kết hữu ích
- [Kaggle Competition](https://www.kaggle.com/competitions/store-sales-time-series-forecasting)
- [Kaggle Dataset](https://www.kaggle.com/c/store-sales-time-series-forecasting/data)

---

## Hướng dẫn sử dụng
### 1. Cài đặt thư viện cần thiết
```bash
pip install -r requirements.txt
```

### 2. Chạy notebook chính
- Mở file notebook (`store_sales_forecast.ipynb`) để xem quá trình phân tích dữ liệu và xây dựng mô hình.

### 3. Dự báo doanh số
- Chạy mô hình trên tập test để tạo ra dự báo doanh số cho **15 ngày cuối cùng**.

### 4. So sánh kết quả
- Đánh giá hiệu suất mô hình dựa trên các metric như **RMSE**.

---

## Tác giả
- **Tên của bạn**  
- 📧 Email: your.email@example.com  
- 🔗 GitHub: [github.com/yourprofile](https://github.com/yourprofile)



