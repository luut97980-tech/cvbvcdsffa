# Sửa giao diện iOS — 2026-11-16

- Khi mở đa nhiệm, Trung tâm điều khiển hoặc chuyển ứng dụng: tạm dừng backend, giữ trạng thái công tắc. Khi ứng dụng thực sự active trở lại, chờ 1,25 giây rồi tiếp tục; có thể chờ thêm khi cảnh đang thay đổi.
- Timer gắn overlay không được tiếp tục backend khi ứng dụng còn inactive.
- Nhả trạng thái giữ nút nhảy khi mất hoạt động. Phải đè lại nút nhảy để spam tiếp.
- Bản Speed khôi phục tốc độ gốc khi suspend, áp dụng lại sau khi nhân vật/cảnh hợp lệ.
- Bỏ UITextField secure dùng làm container để loại bỏ nguồn gây gợi ý mật khẩu từ menu. Không sửa bàn phím hay AutoFill của game/iOS.
- Tùy chọn đổi tên thành “Ẩn khi quay”: ẩn toàn bộ overlay cả trên màn hình thiết bị khi đang quay/chia sẻ màn hình. Không còn bảo vệ ảnh chụp màn hình. Vùng overlay ẩn không chặn chạm.
- Tắt hết, mất/đổi key và đóng hẳn ứng dụng vẫn giữ hành vi tắt chức năng. Không tự bật lại sau khi tiến trình bị iOS kết thúc.

## Xác minh

Chưa build Objective-C++ bằng Xcode và chưa kiểm thử trên iPhone. Kết quả kiểm thử portable của lượt sửa được ghi riêng trong VALIDATION_UI_FIX.json; báo cáo VALIDATION.json cũ là lịch sử, không chứng nhận bản sửa này.

Sau khi build lại cả dylib và IPA: bật tính năng, mở/đóng Trung tâm điều khiển; chuyển ứng dụng rồi trở lại; mở chat và kiểm tra thanh mật khẩu; thử bật/tắt “Ẩn khi quay” khi quay màn hình; thử Tắt hết và đóng/mở hẳn ứng dụng.
