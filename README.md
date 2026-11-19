# VTMenu iOS — Play Together 2.33.2 (233430)

Bản mã nguồn cập nhật từ bản đã sửa lỗi chuyển ứng dụng và gợi ý mật khẩu khi chat. Biến thể: no_speed.

## Đã đối chiếu

- Info(2).plist: VNG, com.vng.playtogether, PLAYTOGETHERVNG, 2.33.2 / 233430.
- Info(3).plist: quốc tế, com.haegin.playtogether, PLAYTOGETHER, 2.33.2 / 233430.
- dumpvng.cs và dumpqt.cs có SHA-256 trùng hoàn toàn với hai dump ghi nhận ở gói 2.33.1. Vì vậy không có thay đổi trong 82 mục field (74 hằng số) và 18 mục RVA đã đối chiếu. Điều này không chứng minh framework mới giống framework cũ.
- Giữ nguyên các chức năng của từng biến thể, sửa lỗi tạm dừng/chuyển ứng dụng và bỏ secure text field gây nghi ngờ ảnh hưởng gợi ý mật khẩu. Xem IOS_UI_FIX.md.

## Framework đã đối chiếu tĩnh

- Quốc tế: UnityFramework(3), UUID 8e6eb96c64dc36ffa1463adcefcf3a71.
- VNG: UnityFramework(6), UUID 18d923f390483a93ac51df7b15e956f7.
- Cả hai: ARM64 không mã hóa, đủ 26 API bắt buộc, 9 đoạn mã máy kiểm tra và 50 đoạn cho các dynamic target. Bản Speed đối chiếu thêm getter tốc độ và layout field ở cả hai client.
- UUID, SHA-256 và chữ ký mã máy của hai framework mới đã cập nhật trong plugin và công cụ đóng gói. Không bỏ kiểm tra.
- Đây là kiểm tra tĩnh. Chưa build Objective-C++ bằng Xcode và chưa thử trên iPhone; không chứng nhận toàn bộ ABI hoặc hành vi trong game.

Bằng chứng cũ nằm tại analysis/history_2_33_1/. VALIDATION.json và analysis/native_binary_audit.json ghi kết quả mới.

## Build

Dùng build_dylib.sh trên macOS/Xcode hoặc workflow đi kèm. Build mới cả VTMenu.dylib và menu-build.json; không dùng dylib 2.33.1. Chạy tao_ipa_menu.py với IPA gốc 2.33.2 và manifest mới; ký hợp lệ trước khi cài.

Kiểm tra dump:

```sh
python3 scripts/verify_ios_update.py --vng dumpvng.cs --global-dump dumpqt.cs
```

Ẩn khi quay chỉ ẩn overlay cả trên thiết bị khi quay/chia sẻ màn hình, không bảo vệ ảnh chụp. Máy chủ key giữ nguyên; chưa kiểm tra xác thực thực tế trên thiết bị.
