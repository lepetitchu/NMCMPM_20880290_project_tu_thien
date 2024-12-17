# project_tu_thien 20880290 - CHU QUANG THẢO

## Hướng dẫn setup môi trường
    1. Cài đặt database mysql, restore database bằng file bak-db/dump-tuthien.sql
    2. Vào thư mục /Source/backend, chỉnh sửa file .env theo cấu hình kết nối database mới tạo phía trên
    3. Cài đặt nodejs
    4. Sử dụng cửa sổ cmd/Powershell hoặc Terminal trỏ đến thư mục Source/backend và chạy lệnh "npm install -y", thực hiện tương tự cho thư mục Source/frontend.    
    5. Mở 2 terminal:
        + terminal ở thư mục /Source/frontend và chạy lệnh "npm start";
        + terminal ở thư mục /Source/backend và chạy lệnh "node index.js"    
    6. Truy cập vào website bằng địa chỉ http://127.0.0.1[:port]/home (vd, http://127.0.0.1:3000/home),
        hoặc địa chỉ network do nodejs tạo ra (vd, http://192.168.1.3:3000/)
    (Không sử dụng localhost, nếu sử dụng localhost sẽ không gửi OTP về số điện thoại được)
    7. Tài khoản để login (username, password, role)
        + admin         123456  admin
        + chuquangthao  123456  contributor
        + vivinguyen    123456  charity
        + tranhoa95     123456  recipient

    NOTE: nếu ở bước 5, bị báo lỗi "File C:\Program Files\nodejs\npm.ps1 cannot be loaded ..." thì
    vào Powershell chạy lệnh Set-ExecutionPolicy Unrestricted => Yes

## Chức năng chính
    1. Tạo tài khoản: 
        - Người dùng đăng ký mới với 1 trong 3 vai trò: Người đóng góp - contributor, người nhận hỗ trợ - recipient, tổ chức từ thiện - charity;
        - Có đăng kí để xác thực bằng mã OTP được gửi về số điện thoại (sử dụng Firebase App)
        - Người dùng đăng nhập vào website với tài khoản hợp lệ (Không trùng tên tài khoản, email và số điện thoại)
        - Người dùng 
    2. Chức năng chính (màn hình Home):
        - Đăng ký / Đăng nhập / Đăng xuất người dùng;
        - Chuyển đổi theme sáng/tối;
        - Theo dõi các tổ chức từ thiện (charity);
        - Theo dõi Danh sách các chiến dịch từ thiện (campaign) do tổ chức thực hiện;
        - Đánh giá phản hồi (reviews) của người dùng về hiệu quả các chiến dịch.
        - Cập nhật tin tức liên quan: bản tin sẽ được lấy và cập nhật theo nguồn newsfeed từ trang: nhandan.vn
    3. Chức năng theo từng vai trò:
        - Người nhận hỗ trợ - recipient:
            + Chỉnh sửa thông tin cá nhân, cập nhật mật khẩu
            + Xem các thông tin về chiến dịch, bình luận và đánh giá về các chiến dịch
        - Người đóng góp cá nhân - contributor:
            + Chỉnh sửa thông tin cá nhân, cập nhật mật khẩu
            + Được xem tất cả các thông tin
            + Đóng góp theo từng chiến dịch và nhận được thông báo về email khi quyên góp của mình được xác nhận
            + Xuất báo cáo về chiến dịch
            + Nhận được thông báo về email khi chiến dịch mình đã từng đóng góp có cập nhật mới
            + Đánh giá, bình luận chiến dịch
        - Tổ chức từ thiện - charity:
            + Khi tạo tài khoản với vai trò tổ chức từ thiện thì thông tin tổ chức từ thiện sẽ được tạo tự động với trạng thái là "Đang chờ duyệt"
            + Chỉnh sửa thông tin tổ chức từ thiện và upload hình ảnh giấy tờ chứng nhận được hoạt động
            + Chỉnh sửa thông tin cá nhân, cập nhật mật khẩu
            + Nhận được email thông báo khi được quản trị viên chấp nhận hoạt động của tổ chức từ thiện, trạng thái sẽ chuyển sang "Đang hoạt động"
            + Tạo chiến dịch mới, quản lí cập nhật các chiến dịch cũ
            + Xuất báo cáo của chiến dịch
        - Quản trị viên (admin):
            + Quản lí tài khoản user
            + Quản lí chiến dịch (Xóa - xuất báo cáo)
            + QUản lí tổ chức từ thiện (Chuyển đổi trạng thái của tổ chức: Đang hoạt động - Dừng hoạt động)
            + Quản lí quyên góp (Xác nhận quyên góp)
    
		