🚗 HƯỚNG DẪN SỬ DỤNG HỆ THỐNG NHẬN DẠNG BIỂN SỐ (ALPR)
🚀 1. Cài Đặt Ban Đầu

Để đảm bảo chương trình chạy đúng, hãy cài đặt toàn bộ thư viện cần thiết.

📦 Cài đặt thư viện

Tất cả thư viện đã được liệt kê trong file:

requirements.txt


Hãy chạy lệnh:

pip install -r requirements.txt

🗂️ 2. Các File Chính và Chức Năng
Image_test2.py:	Chạy thử nghiệm nhận dạng biển số trên ảnh tĩnh	
Video_test2.py:	Chạy thử nghiệm nhận dạng biển số trên video	Video nên có độ phân giải 1920x1080 để đạt kết quả tốt
GenData.py:	Tạo dữ liệu huấn luyện cho mô hình KNN	
training_chars.png:	Ảnh đầu vào để GenData.py tạo datasest	
classifications.txt:	Chứa nhãn (label) ký tự của mô hình KNN	Sinh ra từ GenData.py
flattened_images.txt:	Chứa vector đặc trưng của ký tự đã phân đoạn	Sinh ra từ GenData.py
Preprocess.py:	Các hàm tiền xử lý hình ảnh (lọc nhiễu, phân ngưỡng, chuyển màu, …)	
📝 3. Hướng Dẫn Chi Tiết
1️⃣ Chạy thử trên Ảnh Tĩnh

Mở file:

Image_test2.py


Thay đường dẫn ảnh đầu vào (thường nằm trong thư mục data/image/).

Chạy chương trình:

python Image_test2.py

2️⃣ Chạy thử trên Video

Đặt video vào thư mục:

data/video/


Video nên có độ phân giải tối ưu: 1920 × 1080

Chạy chương trình:

python Video_test2.py

3️⃣ Huấn luyện lại mô hình KNN (tùy chọn)

Nếu bạn muốn cập nhật bộ nhận dạng ký tự:

Chuẩn bị ảnh chứa ký tự mẫu:

training_chars.png


Chạy:

python GenData.py


Chương trình tự động tạo (hoặc cập nhật):

classifications.txt

flattened_images.txt

Các file này dùng để huấn luyện lại mô hình KNN.