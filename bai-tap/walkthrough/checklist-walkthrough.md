# Checklist Walkthrough luồng tạo đơn BranchFlow

**Phiên dự kiến:** 08:00 ngày 17/12/2026, trực tuyến.  
**Phiên bản mã tham chiếu khi chuẩn bị:** `8f56909e3088f2d9712ef65f5ddaab11275d64ea`; xác minh lại trước phiên.  
**Kết quả thực tế:** chưa thực hiện Walkthrough; toàn bộ mục dưới đây đang chờ rà soát.

Quy ước kết quả khi họp: **Đạt / Có vấn đề / Cần làm rõ / Không áp dụng**. Mỗi nhận xét cần có vị trí, căn cứ và người theo dõi nếu nhóm xác nhận; không coi trạng thái “chờ rà soát” là đạt.

| Mã | Câu hỏi/tiêu chí rà soát | Vị trí tham chiếu | Kết quả | Minh chứng / ghi chú |
|---|---|---|---|---|
| W01 | Phạm vi, mục tiêu và phiên bản mã đã được xác nhận trước phiên? | `docs/mvp-scope.md`; kế hoạch Mục 3 | Chờ rà soát | Chưa có |
| W02 | Endpoint tạo đơn chỉ cho vai trò được xác định trong yêu cầu? | `OrdersController.cs:8–17` | Chờ rà soát | Chưa có |
| W03 | Danh tính người dùng được lấy và truyền xuống service nhất quán? | `OrdersController.cs:13–21` | Chờ rà soát | Chưa có |
| W04 | Request chỉ chứa dữ liệu được phép; dữ liệu giá do client gửi có được xử lý đúng contract? | `Contracts.cs:26–31`; `OrderService.cs:12–13` | Chờ rà soát | Chưa có |
| W05 | Mã chi nhánh không hợp lệ bị từ chối trước khi xử lý? | `OrderService.cs:77–82` | Chờ rà soát | Chưa có |
| W06 | Quyền chi nhánh được kiểm tra trước khi đọc menu và xử lý đơn? | `OrderMenuService.cs:29–35`; `OrderService.cs:88–93` | Chờ rà soát | Chưa có |
| W07 | Menu/chi nhánh không khả dụng được chuyển thành kết quả phù hợp? | `OrderMenuService.cs:33–40`; `OrdersController.cs:24–27` | Chờ rà soát | Chưa có |
| W08 | Danh sách món, số dòng, số ly và mã size được kiểm tra? | `OrderService.cs:15–25` | Chờ rà soát | Chưa có |
| W09 | Topping không trùng, không vượt số phần cho phép và thuộc menu? | `OrderService.cs:30–44` | Chờ rà soát | Chưa có |
| W10 | Lựa chọn ghi chú có được kiểm tra mã, nhóm và giới hạn? | `OrderService.cs:46–55` | Chờ rà soát | Chưa có |
| W11 | Giá, tên sản phẩm, size và topping được lấy từ menu và lưu snapshot? | `OrderService.cs:24–44` | Chờ rà soát | Chưa có |
| W12 | Tính tiền từng dòng, tổng tiền và trường hợp tràn/số vượt giới hạn có được xem xét? | `OrderService.cs:42,57,60–72,93–94` | Chờ rà soát | Chưa có |
| W13 | Ngày nghiệp vụ và trạng thái đơn khớp yêu cầu đã xác nhận? | `OrderService.cs:85–86,99–109`; `docs/mvp-scope.md` | Chờ rà soát | Chưa có |
| W14 | Mã đơn được cấp sau khi xác nhận quyền, menu và dữ liệu hợp lệ? | `OrderService.cs:88–97` | Chờ rà soát | Chưa có |
| W15 | Header, dòng món và snapshot được lưu trong giao dịch; có nhánh rollback khi lỗi? | `OrderService.cs:82–84,99–126` | Chờ rà soát | Chưa có |
| W16 | Phản hồi API cho các ngoại lệ được đối chiếu với contract và yêu cầu? | `OrdersController.cs:21–27` | Chờ rà soát | Chưa có |
| W17 | Yêu cầu gửi lại khi phản hồi bị gián đoạn đã được làm rõ? | `OrderService.cs:96–116`; contract tạo đơn | Chờ rà soát | Câu hỏi; chưa kết luận có lỗi. |
| W18 | Mỗi vấn đề đã thống nhất có vị trí, mô tả, người theo dõi và bước tiếp theo? | Biên bản và danh sách vấn đề của phiên | Chờ rà soát | Chưa có |

## Mẫu ghi nhận trong phiên

| Mã | Vị trí và phiên bản | Mô tả / căn cứ | Loại / ảnh hưởng cần xác minh | Người theo dõi | Hành động / hạn thống nhất | Trạng thái |
|---|---|---|---|---|---|---|
| Chưa ghi | Chưa ghi | Chưa ghi | Chưa ghi | Chưa ghi | Chưa ghi | Chưa ghi |

## Ghi chú sau phiên

- Người tham dự thực tế và thời gian kết thúc: chưa có.
- Vấn đề được nhóm thống nhất: chưa có.
- Quyết định, nội dung cần làm rõ và người theo dõi: chưa có.
- Liên kết sửa đổi và kết quả kiểm tra lại: chưa có.

Các tệp test tham chiếu là đầu vào để nhóm xem xét, không phải kết quả kiểm thử đã chạy trong nhiệm vụ chuẩn bị này.
