# Build từ Windows

Đưa mã nguồn lên repository của bạn và chạy workflow trong .github/workflows/build-ios.yml bằng runner macOS. Tải artifact gồm VTMenu.dylib, menu-build.json và tao_ipa_menu.py. Dùng IPA 2.33.2 (233430), đóng gói rồi ký hợp lệ trước khi cài.

Cần build mới dylib, không chỉ đổi tên file cũ. Nếu báo UUID/SHA-256 framework không khớp, cần UnityFramework mới của VNG/quốc tế để cập nhật; không bỏ kiểm tra. Xem README.md về giới hạn xác minh.
