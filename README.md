# Heart_disease_predict-Text-classification-
### comment
  + bảng dữ liệu sẽ có tất cả 14 cột, trong đó cột cuối cũng là nhãn đầu ra bệnh hay không bệnh (nhãn 0 là không bệnh, còn lại là không bệnh)
  + sử dụng các phương pháp học máy để train mô hình classification ( chú ý bộ dữ liệu khi đưa vào train chưa được normalize):
     + sử dụng KNN:
         - độ chính xác train: 0.76, test: 0.69
         - đây là phương pháp nó sẽ tính khoảng cách từ dữ liệu cần dự đoán với các điểm có trong tập train, sau đó nó sẽ vote xem là dữ liệu thuộc nhãn nào dựa vào
           số lượng khoảng cách gần nhất.
     + sử dụng SVM:
         - độ chính xác tập train: 0.66, test:0.67
         - ý tưởng của thuật toán sẽ tìm ra các đường ranh giới, những điểm dữ liệu nằm gần đường ranh giới được gọi là support vector, nó sẽ tìm các đường ranh giới
           sao cho nó có khoảng cách xa nhất với đường ranh giới.
     + sử dụng Naive Bayes:
         - độ chính xác tập train: 0.85, test: 0.84
         - ý tưởng của thuật toán sử dụng công thức xác suất P(A/B) = P(B/A) * P(A) / P(B), trong đó B là nhãn cần dự đoán, A là dữ liệu có để dự đoán
     + sử dụng Decision Tree:
         - độ chính xác tập train: 1, test: 0.75
         - ý tưởng của thuật toán là biến dữ liệu train thành cây, trong đó ở mỗi nốt là feature của dữ liệu, việc chọn nốt ở mỗi tầng sẽ quyết định vào thuật toán
           Gini = $$1 - \sum_{i=1}^{C} (p_i)^2$$, Entropy(T) = $$-\sum_{i=1}^{C} p_i \log_2(p_i)$$, $$Information\ Gain(T, A) = Entropy(T) - \sum_{v \in Values(A)} \frac{|T_v|}{|T|} Entropy(T_v)$$
     + sử dụng Random Forest:
         - độ chính xác tập train: 0.98, test: 0.8
         - ý tưởng của nó sẽ gồm nhiều cây.
     + sử dụng Adaboost:
         - độ chính xác tập train: 0.88, test 0.9
         - ý tưởng của thuật toán là tập hợp rất nhiều mô hình yếu weak leaner thường là những stump, mô hình sẽ được huấn luyện sao cho khi đưa dự đoán sai
           thì mẫu dữ liệu dự đoán sai sẽ được đánh trọng số cao hơn, đúng thì trừ đi để mô hình sẽ tập trung vào những cái sai.
     + sử dụng Gradient boost:
         - độ chính xác tập train: 1, test; 0.85
         - ý tưởng của thuật toán là dự đoán lỗi, ví dụ khi có dự đoán đầu nó sẽ tính ra sự chênh lệch với nhãn đầu ra , đó chính là cái cần dự đoán, kết quả cuối             cùng, cộng với nhãn dự đoán đầu sẽ là kết quả cuối cùng
     + sử dụng Xgboost:
         - độ chính xác tập train: 1, test: 0.87
         - ý tưởng của nó giống hệt thằng gradient nhưng nó sẽ dùng thêm đạo hàm bậc 2 để tìm hướng loss hiệu quả hơn.
     + sử dụng STACKING:
         - độ chính xác tập train: 0.82, test: 0.92
         - ý tưởng kết hợp nhiều mô hình rồi vote. 
