# Hướng dẫn XP / VX / VX Ace

## Khác biệt so với MV/MZ

- Không có plugin đối chiếu — **chỉ ghi trực tiếp vào tệp dữ liệu**
- Định dạng là Ruby Marshal: `.rxdata` / `.rvdata` / `.rvdata2`
- Bản sao lưu nằm ở `translate\backup_<thời gian>\Data\`

## Ba bước

1. Chọn thư mục chứa `Data` → **Nhận diện**
2. **Quét văn bản** → **Bắt đầu dịch**
3. **Ghi vào game**: sao lưu trước, ghi từng tệp, sau đó phân tích lại để tự kiểm tra

## Nội dung được dịch

Hội thoại sự kiện, lựa chọn, văn bản cuộn, tên sự kiện, tên bản đồ, nhân vật (tên/biệt danh/mô tả), nghề, vật phẩm, vũ khí, giáp, kỹ năng, trạng thái, kẻ địch, sự kiện chung, nhóm địch, thuật ngữ và thông báo hệ thống.

## Lưu ý

- **Chữ Hán hiện ô vuông**: phông trong `Fonts\` không có glyph tiếng Trung — hãy thay phông
- **Quét ra 0 mục**: văn bản nằm trong script RGSS, hoặc dữ liệu bị đóng gói `Game.rgss3a` / `.rgss2a` / `.rgssad` (phải giải nén trước)
- **Game lỗi sau khi ghi**: dùng **Khôi phục**, rồi gửi cho tôi thông báo lỗi
- Ghi lại chỉ thay chuỗi và tiền tố độ dài, các byte khác giữ nguyên
