# Thư viện của lớp

## Cách chạy

### Phần A - JavaScript thuần
Mở file `phan-a/index.html` bằng trình duyệt (chuột phải → Open with Live Server hoặc double-click).
Dữ liệu mẫu trong `phan-a/books.json` (10 cuốn, 3 thể loại).

### Phần B - React + Vite
Cách chuẩn:
```bash
cd phan-b-react
npm install
npm run dev
```
Dữ liệu trong `src/data/books.js` (chưa gọi API).

Muốn mở ngay không cài: double-click `phan-b-react/mo-ngay-khong-can-cai.html` (cần mạng).
Chi tiết xem `phan-b-react/README.md`.

## So sánh Phần A và Phần B

| Tiêu chí | Phần A (JS thuần) | Phần B (React) |
|---|---|---|
| Cập nhật giao diện | Tự tạo `createElement`, tự `render()` lại cả lưới khi state đổi | Chỉ đổi `state`, React tự render lại component cần thiết |
| Dữ liệu | `fetch('books.json')` + `async/await`, có "Đang tải..." và báo lỗi | `import` từ file `books.js`, đơn giản, không gọi API |
| Lọc / tìm kiếm | Lọc thủ công bằng `filter`, thể loại tạo bằng `Set` | Cũng dùng `filter` + `Set`, nhưng kết quả tự tính từ `state genre` |
| Yêu thích | Mảng `favorites` + `localStorage`, dùng event delegation trên lưới | `useState` ở `App`, truyền hàm `onToggleFav` xuống `BookCard` qua props |
| Chia giao diện | 1 file HTML + CSS + 3 module JS (`api`, `render`, `main`) | Chia nhiều component: `Header`, `Section` (children), `GenreFilter`, `BookList`, `BookCard`, `Footer` |
| Code | Dài, phải tự quản DOM | Ngắn gọn, khai báo theo component, dễ tái dùng |

Kết luận: Phần A giúp hiểu DOM, fetch, event; Phần B code gọn hơn nhờ component, props, state.
