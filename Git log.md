334d060 (HEAD -> main, feature/nav-menu) them menu
aa30b66 (origin/main) file ban dau

"Tại sao em dùng <ul> (danh sách không thứ tự) mà không dùng <ol> (danh sách có thứ tự) cho Menu trang web?"

Ý nghĩa ngữ nghĩa (Semantics): Thẻ <ul> đại diện cho danh sách không có thứ tự (Unordered List), nghĩa là các mục trong danh sách đứng cạnh nhau với mức độ quan trọng ngang nhau và thứ tự trước sau không ảnh hưởng đến logic. Menu website (Trang chủ, Sản phẩm, Liên hệ, Tin tức...) hoàn toàn phù hợp với tính chất này vì người dùng có thể nhấp vào mục nào trước cũng được.

Trái lại với <ol>: Thẻ <ol> (Ordered List) dùng cho danh sách có thứ tự (1, 2, 3...), dùng khi các bước thực hiện hoặc thứ tự xếp hạng mang tính tuần tự bắt buộc (ví dụ: hướng dẫn nấu ăn, bảng xếp hạng top 10). Dùng <ol> cho menu sẽ làm cho các công cụ tìm kiếm (SEO) và trình đọc màn hình hiểu lầm rằng menu này là một chuỗi các bước phải làm lần lượt.



"Điều gì sẽ xảy ra nếu em đang ở nhánh feature/nav-menu, em chỉnh sửa file nhưng quên commit, rồi em checkout thẳng sang nhánh main?"

Khi bạn đang đứng ở nhánh feature/nav-menu, chỉnh sửa file nhưng chưa git add hay git commit, sau đó gõ lệnh git checkout main (hoặc git switch main), Git sẽ xử lý theo 2 kịch bản chính:

Kịch bản 1 (Git chặn lại - Phổ biến nhất):
Nếu các file bạn đang sửa cũng có sự tồn tại hoặc thay đổi ở nhánh main, Git sẽ từ chối chuyển nhánh và báo lỗi dạng:

error: Your local changes to the following files would be overwritten by checkout...

Ý nghĩa: Git đang bảo vệ bạn khỏi việc làm mất code hoặc gây xung đột trực tiếp trên nhánh main.

Kịch bản 2 (Mang theo thay đổi sang nhánh main):
Nếu các file bạn đang sửa không bị xung đột với main, Git sẽ cho phép bạn chuyển nhánh và "mang theo" các thay đổi chưa commit đó sang thẳng nhánh main. Lúc này, nhánh main của bạn sẽ dính code chưa hoàn thiện, rất dễ gây lỗi hệ thống.