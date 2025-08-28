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
           Gini= 1− i=∑(pi)2, Entropy(T) = -\sum_{i=1}^{C} p_i \log_2(p_i)
