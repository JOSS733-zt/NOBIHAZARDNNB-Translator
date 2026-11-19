# Nobihazard NNB-Translation — Hướng dẫn sử dụng

Tác giả: JOSS · một file exe · không cần cài đặt

## Engine hỗ trợ

| Engine | Dữ liệu | Cách làm |
|---|---|---|
| RPG Maker MV / MZ | `data\*.json` | ghi lại, hoặc cài plugin đối chiếu |
| RPG Maker XP | `Data\*.rxdata` | ghi trực tiếp |
| RPG Maker VX | `Data\*.rvdata` | ghi trực tiếp |
| RPG Maker VX Ace | `Data\*.rvdata2` | ghi trực tiếp |

RPG Maker 2000 / 2003 (`.ldb`) chưa hỗ trợ.

## Ba bước

1. **① Chọn game** — chọn thư mục chứa `www` / `data` / `Data`, bấm **Nhận diện**
2. **② Cài đặt** — chọn engine, bấm **Kiểm tra engine**, rồi **③ chọn phân vùng**
3. **Quét văn bản** → **Bắt đầu dịch** → **Ghi vào game** (tự động sao lưu trước)

## Engine (đều không cần khóa)

| Engine | Ghi chú |
|---|---|
| Microsoft (mặc định) | `cn.bing.com`, dùng được ở Trung Quốc đại lục; bị giới hạn thì giảm luồng về 1 |
| MyMemory | dùng được ở đại lục, khoảng 5000 ký tự/ngày; giữ `[[0]]` tốt nhất |
| Google miễn phí | cần proxy tại Trung Quốc đại lục |

## Phân vùng

Chỉ những phân vùng được chọn mới được quét và dịch: Sự kiện bản đồ / Tên bản đồ / Sự kiện chung / Vật phẩm / Kỹ năng / Vũ khí / Giáp / Nhân vật / Trạng thái+Kẻ địch / Nhóm địch / Hệ thống / Khác.

Các dòng bị bỏ chọn sẽ ẩn khỏi bảng và không được dịch.

## Vị trí tệp

```
<thư mục game>
├── translate\cache_<ngôn ngữ>.json   bộ nhớ đệm
├── translate\glossary.txt            thuật ngữ tự thêm
├── translate\đối chiếu_*.html        bảng đối chiếu
└── translate\backup_*\               sao lưu trước khi ghi
```

MV/MZ dùng thêm `data\TranslatePlus\` và `js\plugins\TranslatePlus.js`.

## Câu hỏi thường gặp

- **Mở là tắt** — xem `startup.log` / `crash.log` cạnh exe
- **Không nhận diện** — chọn đúng thư mục chứa `data` / `Data`; giải nén `Game.rgss3a` trước
- **"phản hồi rỗng"** — bị giới hạn; giảm luồng về 1 và đợi vài phút
- **Trạng thái "cần soát"** — engine làm mất mã điều khiển; sửa trực tiếp ô bản dịch
- **Chữ Hán hiện ô vuông** (XP/VX/VA) — thay phông trong `Fonts\`
- **Đổi tên / ngôn ngữ** — sửa `name=` / `lang=` trong `nnb.ini`

## Giấy phép

MIT. Miễn phí vĩnh viễn, không thu phí, không cần kích hoạt. Không chứa tài nguyên game.
