# Báo cáo Bài tập: Thiết lập và Khai thác GraphQL API với Bagisto Headless

**Họ và tên sinh viên:** Nguyễn Trọng Đại  
**Mã số sinh viên:** 23810310120  
**Môn học:** Lập trình web nâng cao  

---

## Phần 1: Minh chứng cài đặt và thêm dữ liệu
*Đã thực hiện cài đặt thành công Headless Extension và thêm mới 03 sản phẩm theo đúng cú pháp yêu cầu.*

![Danh sách sản phẩm](Hinh1_DanhSachSP.png)
*(Lưu ý: Kéo thả bức ảnh màn hình danh sách 3 sản phẩm trong Admin vào đây)*

---

## Phần 2: Khai thác GraphQL API
*Minh chứng thực hiện Query 3: Sử dụng filters để lọc đúng 03 sản phẩm có tên chứa Họ tên của sinh viên, kèm định danh Console.*

![Kết quả GraphQL API](Hinh2_GraphQL.png)
*(Lưu ý: Kéo thả bức ảnh kết quả Query 3 có tab Console "Bài làm của: Nguyễn Trọng Đại" vào đây)*

---

## Phần 4: Trả lời Câu hỏi Bắt buộc

**1. So sánh sự khác biệt về lưu lượng dữ liệu (Payload) giữa việc dùng REST API (lấy tất cả) và GraphQL (chỉ lấy trường cần thiết) trong bài làm của em?**
Trong bài làm, nếu sử dụng REST API, hệ thống sẽ trả về toàn bộ thông tin của sản phẩm (như ngày tạo, danh mục, trạng thái kho...) dù giao diện Front-end không dùng đến, gây ra hiện tượng dư thừa dữ liệu (Over-fetching). Ngược lại, với GraphQL, em chỉ định nghĩa và yêu cầu lấy đúng 4 trường cần thiết là `id`, `name`, `price`, và `description`. Nhờ vậy, lưu lượng dữ liệu (Payload) tải về từ GraphQL nhỏ gọn hơn rất nhiều, giúp tiết kiệm băng thông mạng và tăng tốc độ tải trang web.

**2. Nếu muốn thay đổi giá của một sản phẩm qua Headless API, em sẽ sử dụng loại hành động nào trong GraphQL (Query hay Mutation)? Giải thích tại sao?**
Em sẽ sử dụng hành động **Mutation**. 
*Giải thích:* Trong kiến trúc GraphQL, **Query** chỉ được thiết kế với mục đích duy nhất là truy xuất và đọc dữ liệu (tương đương phương thức GET trong REST). Trong khi đó, **Mutation** được sử dụng để thực hiện các thao tác làm thay đổi trạng thái của cơ sở dữ liệu trên Server (như Create, Update, Delete). Vì thao tác "thay đổi giá sản phẩm" là hành động cập nhật dữ liệu, nên việc sử dụng Mutation là bắt buộc để đảm bảo đúng nguyên tắc thiết kế API.
