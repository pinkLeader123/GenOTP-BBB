Module kernel driver DS1307 đọc thời gian RTC qua I2C.

Layer user-space (user.c) giao tiếp với driver bằng IOCTL.

user.c sử dụng:

sha1.c + otp.c → sinh mã OTP (Time-based, 30 giây 1 lần).

user.c và senOTP.py chạy 2 tiến trình, giao tiếp qua FIFO:
    user.c  --->  FIFO  --->  senOTP.py

senOTP.py:

Gửi OTP qua email

Đồng thời chạy Flask server (HTTPS)

Tool C# (client):

Người dùng nhập OTP nhận trong mail

Tool gửi OTP nhập vào → Flask Server

Flask Server so sánh OTP đang lưu từ user.c

Nếu đúng → trả JSON: {"status": "OK"}

Nếu sai → {"status": "FAIL"}

Hệ thống OTP hoạt động theo chu kỳ 30s.

sơ đồ:  

https://drive.google.com/file/d/1NwFVfBTj5-4-dfkXQVN23d0GrAOv-joX/view?usp=sharing