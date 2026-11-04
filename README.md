# BÀI TẬP SESSION 16 – EX03: CSS BOX MODEL VÀ INSPECT ELEMENT

## Phần 1. Phân tích

1\. Xác định phần tử bị lỗi

- Nhấn `F12` để mở DevTools.
- Chọn công cụ Inspect Element.
- Nhấp vào khung Thông tin tài xế.
- Tìm thẻ HTML tương ứng trong tab Elements.
- Chọn tab Computed để xem kích thước phần tử.

2\. Phân tích CSS Box Model

CSS Box Model gồm 4 lớp:

```
        MARGIN
   ┌─────────────────┐
   │     BORDER      │
   │  ┌───────────┐  │
   │  │  PADDING  │  │
   │  │ ┌───────┐ │  │
   │  │ │CONTENT│ │  │
   │  │ └───────┘ │  │
   │  └───────────┘  │
   └─────────────────┘
```

- Content: Nội dung bên trong.
- Padding: Khoảng cách giữa nội dung và viền.
- Border: Đường viền phần tử.
- Margin: Khoảng cách bên ngoài phần tử.

Lỗi chồng lấn có thể do Margin không hợp lý, kích thước quá lớn hoặc sử dụng `position` không phù hợp.

## Phần 2. Triển khai

Đề xuất CSS mới:

Chỉnh sửa trực tiếp trong tab Styles của DevTools:

```
.driver-info {
    width: 100%;
    box-sizing: border-box;
    margin-bottom: 20px;
    padding: 15px;
    position: static;
}

.station-list {
    width: 100%;
    box-sizing: border-box;
    margin-top: 20px;
    padding: 15px;
    position: static;
}
```

Kết quả mong muốn:

- Hai khung không còn chồng lên nhau.
- Nội dung được hiển thị rõ ràng.
- Khoảng cách giữa hai khung hợp lý.

Lưu ý: Đây là CSS đề xuất, cần điều chỉnh theo tên class và cấu trúc HTML thực tế.

## Phần 3. Kiểm thử

Nếu thay đổi Margin nhưng phần tử vẫn không di chuyển, cần kiểm tra:

- `position: absolute` hoặc `fixed` có thể khiến phần tử nằm ngoài luồng bố cục thông thường.
- `!important` có thể ghi đè thuộc tính Margin.
- Kiểm tra tab Computed để xem giá trị CSS cuối cùng.
- Kiểm tra các quy tắc CSS bị gạch ngang trong tab Styles.

Kết luận: Có thể dùng `position: static` để đưa phần tử trở lại luồng bố cục thông thường nếu không cần định vị đặc biệt.

