# 📦 Hệ Thống Quét Đơn Hàng Etsy Tự Động

## 🎯 Giới Thiệu

Ứng dụng **Etsy Order Scanner** là một công cụ tự động hóa mạnh mẽ giúp người bán hàng trên Etsy quản lý đơn hàng một cách hiệu quả. Thay vì phải kiểm tra email thủ công từng đơn hàng, ứng dụng sẽ tự động quét Gmail của bạn, trích xuất thông tin đơn hàng và lưu trữ vào cơ sở dữ liệu để bạn có thể dễ dàng quản lý và xuất báo cáo.

### 💡 Lợi Ích Chính

- **Tiết kiệm thời gian**: Tự động hóa hoàn toàn việc thu thập thông tin đơn hàng
- **Độ chính xác cao**: Loại bỏ sai sót do nhập liệu thủ công
- **Quản lý tập trung**: Tất cả đơn hàng được lưu trữ một nơi
- **Xuất báo cáo nhanh**: Tạo file CSV/Excel chỉ với một cú nhấp chuột
- **Xử lý số lượng lớn**: Có thể quét 30,000 email trong 1 giờ

## 🔐 1. Đăng Nhập Hệ Thống

### Các Bước Đăng Nhập

1. **Truy cập ứng dụng**: Mở trình duyệt và truy cập vào địa chỉ web của ứng dụng
2. **Nhấn nút "Đăng nhập với Google"**: Một cửa sổ mới sẽ hiện ra
3. **Chọn tài khoản Gmail**: Chọn tài khoản Gmail mà bạn nhận email đơn hàng từ Etsy
4. **Cấp quyền truy cập**:
   - Cho phép ứng dụng đọc email của bạn
   - Cho phép xem thông tin cơ bản của tài khoản
5. **Hoàn tất**: Bạn sẽ được chuyển đến trang Dashboard chính

### ⚠️ Lưu Ý Quan Trọng
- Bạn PHẢI sử dụng tài khoản Gmail đã đăng ký nhận thông báo đơn hàng từ Etsy
- Ứng dụng chỉ đọc email, không thể xóa hoặc gửi email từ tài khoản của bạn
- Thông tin đăng nhập được bảo mật và mã hóa

## 📧 2. Quét Email Đơn Hàng

### Cách Thức Hoạt Động

Ứng dụng tự động tìm kiếm email với các đặc điểm:
- **Người gửi**: transaction@etsy.com
- **Tiêu đề**: "You made a sale on Etsy" (Bạn đã bán được hàng trên Etsy)
- **Nội dung**: Chứa thông tin chi tiết đơn hàng

### Quy Trình Quét Email

1. **Vào tab "Quét Email"** trên Dashboard
2. **Nhấn nút "Bắt đầu quét"**
3. **Theo dõi tiến trình**:
   - Thanh tiến trình hiển thị số email đã xử lý
   - Thông báo số đơn hàng mới tìm thấy
   - Cập nhật trạng thái real-time
4. **Chờ hoàn tất**: Hệ thống sẽ thông báo khi quét xong

### 🔄 Chiến Lược Quét Thông Minh

Ứng dụng sử dụng chiến lược 2 giai đoạn:

**Giai đoạn 1 - Quét Email Mới**:
- Kiểm tra đơn hàng mới nhất trong database
- Chỉ quét email mới hơn ngày này
- Đảm bảo không bỏ sót đơn hàng mới

**Giai đoạn 2 - Quét Lịch Sử**:
- Quét ngược về quá khứ (mặc định 3 năm)
- Tự động điền vào các khoảng trống
- Không quét lại email đã xử lý

### 📊 Thông Tin Được Trích Xuất

Từ mỗi email đơn hàng, ứng dụng tự động lấy:
- **Mã đơn hàng**: Số đơn hàng duy nhất từ Etsy
- **Email khách hàng**: Địa chỉ email người mua
- **Tên sản phẩm**: Tên mặt hàng được mua
- **Tùy chọn sản phẩm**: Màu sắc, kích cỡ, tùy chỉnh
- **Tên shop**: Shop Etsy của bạn
- **Ngày đặt hàng**: Thời gian khách đặt hàng

## 💾 3. Lưu Trữ Và Quản Lý Dữ Liệu

### Xem Danh Sách Đơn Hàng

1. **Vào tab "Đơn Hàng"** trên Dashboard
2. **Các chức năng có sẵn**:
   - **Sắp xếp**: Click vào tiêu đề cột để sắp xếp
   - **Tìm kiếm**: Nhập từ khóa vào ô tìm kiếm
   - **Lọc**: Lọc theo ngày, shop, hoặc trạng thái
   - **Phân trang**: Điều hướng qua các trang kết quả

### Tính Năng Bảng Dữ Liệu

- **Hiển thị chi tiết**: Xem đầy đủ thông tin từng đơn hàng
- **Sắp xếp linh hoạt**: Theo ngày, tên khách, sản phẩm
- **Tìm kiếm nhanh**: Tìm đơn hàng theo bất kỳ thông tin nào
- **Cập nhật tự động**: Dữ liệu cập nhật real-time khi quét email mới

### 🔒 Bảo Mật Dữ Liệu

- Mỗi người dùng chỉ xem được đơn hàng của mình
- Dữ liệu được mã hóa khi lưu trữ
- Backup tự động hàng ngày
- Tuân thủ quy định bảo mật GDPR

## 📤 4. Xuất Báo Cáo

### Các Bước Xuất File

1. **Vào tab "Xuất File"**
2. **Nhấn nút "Xuất CSV"**
3. **Chờ xử lý**:
   - Hệ thống tạo file ở background
   - Thông báo khi file sẵn sàng
4. **Tải xuống**: Click link download khi hiện ra

### 📁 Định Dạng File Xuất

**File CSV bao gồm các cột**:
- Mã đơn hàng
- Email khách hàng
- Tên sản phẩm
- Tùy chọn sản phẩm
- Tên shop
- Ngày đặt hàng
- Thời gian xử lý

### Lịch Sử Xuất File

- Xem danh sách các lần xuất trước đó
- Tải lại file cũ (trong vòng 24 giờ)
- Theo dõi trạng thái: Đang xử lý / Hoàn thành / Lỗi

## 🚀 5. Hướng Dẫn Sử Dụng Hiệu Quả

### Quy Trình Làm Việc Khuyến Nghị

1. **Hàng ngày**:
   - Đăng nhập vào hệ thống
   - Quét email mới (chỉ mất vài phút)
   - Kiểm tra đơn hàng mới

2. **Hàng tuần**:
   - Xuất báo cáo CSV
   - Phân tích xu hướng bán hàng
   - Sao lưu dữ liệu quan trọng

3. **Hàng tháng**:
   - Xuất báo cáo tổng hợp
   - Đối chiếu với Etsy Dashboard
   - Lập kế hoạch kinh doanh

### 💡 Mẹo Sử Dụng

1. **Quét định kỳ**: Nên quét email ít nhất 1 lần/ngày để dữ liệu luôn cập nhật
2. **Kiểm tra trùng lặp**: Hệ thống tự động loại bỏ đơn trùng, không cần lo lắng
3. **Xuất file định kỳ**: Xuất và lưu file hàng tuần để backup
4. **Sử dụng filter**: Tận dụng chức năng lọc để tìm đơn hàng nhanh hơn
5. **Theo dõi tiến trình**: Luôn chờ quét hoàn tất trước khi xuất báo cáo

## ❓ 6. Câu Hỏi Thường Gặp

### Q: Ứng dụng có an toàn không?
**A:** Hoàn toàn an toàn. Chúng tôi:
- Chỉ đọc email, không thể xóa hay gửi
- Sử dụng xác thực Google OAuth chính thức
- Mã hóa toàn bộ dữ liệu
- Không lưu mật khẩu Gmail của bạn

### Q: Tôi có thể quét bao nhiêu email?
**A:** Không giới hạn! Hệ thống có thể xử lý:
- 30,000 email trong 1 giờ
- Quét lịch sử đến 3 năm
- Xử lý hàng triệu đơn hàng

### Q: Email của tôi không được quét?
**A:** Kiểm tra:
- Email phải từ transaction@etsy.com
- Tiêu đề phải chính xác "You made a sale on Etsy"
- Tài khoản Gmail đã được cấp quyền đầy đủ
- Email có thể nằm trong folder Promotions/Social/Updates

### Q: Có thể xuất định dạng Excel không?
**A:** File CSV có thể mở trực tiếp bằng Excel. Chỉ cần:
1. Download file CSV
2. Mở Excel
3. File → Open → Chọn file CSV
4. Excel tự động nhận diện và hiển thị

### Q: Dữ liệu được lưu trong bao lâu?
**A:**
- Dữ liệu đơn hàng: Lưu vĩnh viễn
- File xuất: Link download có hiệu lực 24 giờ
- Lịch sử quét: Lưu để tối ưu hiệu suất
