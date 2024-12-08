Bài toán đặt ra là dự báo doanh số bán hàng trong tương lai tại các cửa hàng bán lẻ. Tập dữ liệu được sử dụng trong notebook này chứa thông tin về doanh số bán hàng trong quá khứ cùng các thông tin đi kèm của một công ty có tên là Corporación Favorita, một nhà bán lẻ thực phẩm lớn ở Ecuador . Công ty này cũng hoạt động ở các quốc gia khác ở Nam Mỹ. Tập dữ liệu này được lấy từ một cuộc thi công khai trên trang web Kaggle. Vậy nên chúng ta có đánh giá hiệu quả của mô hình xây dựng so với những người khác cùng tham gia cuộc thi này.

Dưới đây là đường dẫn của cuộc thi -> https://www.kaggle.com/competitions/store-sales-time-series-forecasting


<img src="https://raw.githubusercontent.com/EkremBayar/Kaggle/refs/heads/main/Images/CF.png" width="25%" />
<img src="https://raw.githubusercontent.com/EkremBayar/Kaggle/refs/heads/main/Images/CF1.jpg" width="35%" />


Tập dữ liệu gồm có **54 cửa hàng** và **33 nhóm sản phẩm**. Chuỗi thời gian bắt đầu từ **2013-01-01** và kết thúc vào **2017-08-31**. Trong đó, **15 ngày** cuối cùng là những ngày chúng ta phải dự đoán doanh thu (tức là từ **2017-08-16** đến **2017-08-31** chưa cho biết doanh thu).

Tập dữ liệu của chúng ta chia thành 6 tập con:

1. _Train_
2. _Test_
3. _Store_
4. _Transactions_
5. _Holidays and Events_
6. _Daily Oil Price_

**Train** là tập chứa chuỗi thời gian của các tổ hợp cửa hàng và nhóm sản phẩm. Cột `sales` cung cấp tổng doanh số bán hàng của một nhóm sản phẩm tại một cửa hàng vào một ngày cụ thể. Cột `onpromotion` cho biết tổng số sản phẩm trong một nhóm đang được khuyến mãi tại một cửa hàng vào một ngày cụ thể.

**Store** cung cấp thông tin về các cửa hàng như thành phố (city), tiểu bang (state), loại cửa hàng (type), và cụm (cluster).

**Transaction** có mối tương quan cao với cột `sales` trong tập **Train**. Dữ liệu này giúp hiểu được số lượng mặt hàng được bán tại các cửa hàng.

**Holidays and Events data** là siêu dữ liệu. Nó cho biết thông tin về các ngày lễ ở Ecuador, rất hữu ích cho phân tích doanh số.

**Daily Oil Price** là một dữ liệu bổ sung. Theo như mô tả, **Ecuador** là một quốc gia phụ thuộc vào dầu mỏ và tình hình kinh tế của họ dễ bị ảnh hưởng bởi biến động giá dầu. Vì vậy, dữ liệu này có thể giúp chúng ta hiểu nhóm sản phẩm nào bị ảnh hưởng tích cực hoặc tiêu cực bởi giá dầu.

Tập dữ liệu có một vài “Ghi chú bổ sung”. Những ghi chú này có thể rất quan trọng để nhận ra các mẫu hoặc điểm bất thường. Dưới đây là một vài ghi chú quan trọng:
- Lương trong khu vực công được trả hai tuần một lần, vào ngày 15 và vào ngày cuối cùng của tháng. Doanh số bán hàng tại siêu thị có thể bị ảnh hưởng bởi điều này.
- Một trận động đất mạnh 7,8 độ đã xảy ra ở Ecuador vào ngày 16 tháng 4 năm 2016. Người dân đã tham gia vào các hoạt động cứu trợ, quyên góp nước và các nhu yếu phẩm khác, làm tăng đáng kể doanh số bán hàng tại siêu thị trong vài tuần sau đó.

