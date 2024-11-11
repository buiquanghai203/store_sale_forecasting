Mô Tả Sản Phẩm: Dự Án Dự Đoán Doanh Thu Cửa Hàng Bán Lẻ
Dự án này được xây dựng để dự đoán doanh thu hàng ngày của các cửa hàng bán lẻ, sử dụng dữ liệu lịch sử bán hàng và các đặc trưng liên quan đến cửa hàng, sản phẩm và thời gian.
Mục tiêu chính của dự án là dự báo doanh thu cho từng cửa hàng trong một khoảng thời gian xác định (thường là 16 ngày tiếp theo),
giúp các nhà quản lý cửa hàng lên kế hoạch và tối ưu hóa các chiến lược bán hàng, tiếp thị và kho bãi.
Đây là một cuộc thi trên Kaggle , nếu muốn tìm hiểu chi tiết hơn có thể theo đường dẫn sau https://www.kaggle.com/competitions/store-sales-time-series-forecasting

Mô hình sử dụng XGBoost, một thuật toán học máy mạnh mẽ trong việc xử lý các bài toán dự báo chuỗi thời gian, đặc biệt là trong các vấn đề có dữ liệu phi tuyến tính và phức tạp.
Mô hình này áp dụng kỹ thuật gradient boosting để kết hợp nhiều cây quyết định và tối ưu hóa kết quả dự đoán, giúp tăng độ chính xác và khả năng tổng quát hóa của mô hình.

Mô hình được đánh giá dựa trên RMSE (Root Mean Squared Log Error), một chỉ số quan trọng trong các bài toán dự báo thời gian để đo lường độ chính xác của dự đoán.
Các kỹ thuật cross-validation và train-test split được sử dụng để kiểm tra tính tổng quát của mô hình.

