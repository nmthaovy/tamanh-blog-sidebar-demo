# Đề xuất điều chỉnh bố cục bài blog tamanhhospital.vn

Bản demo (`index.html`) mô phỏng trang bài viết với giao diện đề xuất. Thanh công cụ phía trên cho phép đổi thiết bị (PC / Tablet / Mobile), so sánh bố cục **Hiện tại** với **B · 3 cột**, đổi loại bài và số banner để xem từng trường hợp. Nội dung bài trong demo là bản mô phỏng, không phải bài thật.

**Mục tiêu:** tận dụng khoảng trống hai bên sidebar (hiện có khoảng 27% bài Sản - Phụ khoa không treo banner nên trống cả hai bên). Đồng thời đưa form đặt lịch và hỏi bác sĩ đến gần người đọc, không dẫn họ sang trang khác.

## 1. PC: mục lục và nút chia sẻ ở cột trái

- **Mục lục luôn hiển thị bên trái** thay vì chỉ nằm trong bài. Ở bất kỳ vị trí nào trên trang, người đọc vẫn thấy toàn bộ các chủ đề chính và mục mình đang đọc (có thanh tiến độ), không tốn thêm lượt click. Hiện tại mục lục trong bài trôi mất khi cuộn qua; muốn xem lại phải bấm nút nổi.
- **Nút chia sẻ nằm ngay dưới mục lục** và đi theo khi cuộn, nên người đọc chia sẻ được bất cứ lúc nào. Hiện tại nút chỉ có ở cuối bài và chưa có Zalo; đề xuất gồm Facebook, Zalo, Messenger và Sao chép liên kết.
- Bố cục 3 cột (190px | 865px | 300px) **giữ nguyên độ rộng nội dung 865px** như hiện tại, nên ảnh trong bài không phải chỉnh. Bài không có mục lục, hoặc màn hình dưới 1420px, tự chuyển về bố cục 2 cột kèm cột icon chia sẻ hẹp. Nút back-to-top dạng mũi tên nổi giữ như site hiện tại.

## 2. PC: cột phải (banner + form) và "Bác sĩ đã trả lời"

- **Banner sidebar dạng slide, bám theo khi cuộn.** Hiện tại banner không bám theo khi cuộn nên chỉ hiện ở màn hình đầu, và bài có 2 banner thì xếp chồng khoảng 700px. Đề xuất: 1 khung slide (tối đa 3 banner), người dùng kéo/vuốt để chuyển hoặc tự chuyển sau 7 giây; dừng khi rê chuột. Nhãn "Ưu đãi hiện có tại Tâm Anh".
- **Chọn banner theo cate chính của bài.** Loại banner lệch chuyên khoa, ví dụ bài "Bà bầu đau nhức xương khớp" đang hiện banner "Mổ cấp cứu gãy xương".
- **Bỏ banner chèn trong bài trên PC.** Cột phải đã hiện banner suốt bài; hiện tại cùng một chiến dịch xuất hiện 2 lần (sidebar và trong bài).
- **Form đặt lịch mở sẵn ngay dưới banner**, điền sẵn chuyên khoa theo cate chính (người dùng đổi được), chỉ cần nhập họ tên và số điện thoại. Hiện tại bấm "Đặt lịch" sẽ rời bài sang trang khác và phải chọn lại 6 mục.
- **"Bác sĩ đã trả lời"** (câu hỏi đã được bác sĩ trả lời cùng chuyên khoa, kèm nút đặt câu hỏi) hiện ở cột phải khi bài không có banner. Demo có thêm lựa chọn chèn thẻ này vào trong bài để so sánh.

## 3. Mobile: banner, form, hỏi đáp và thanh đáy

- **Banner in-content giữ trên mobile**, vì mobile không có sidebar nên đây là vị trí banner duy nhất. Gom tất cả banner vào **1 khung slide** có mũi tên và hé lộ banner kế tiếp, thay vì nhiều banner rời.
- **Vị trí banner:** nếu biên tập chèn shortcode `[ta_banner]` thì hiện đúng chỗ đó. Nếu không, hệ thống tự đặt trước H2 sau mốc 30% bài (bài không có H2 thì đặt giữa 2 đoạn văn). Banner **không bao giờ chen vào giữa danh sách/bảng** như lỗi hiện tại: CMS đang đếm cả thẻ `<p>` nằm trong `<li>`.
- **Form đặt lịch** (`[ta_booking]`) và **"Bác sĩ đã trả lời"** (`[ta_qa]`) chỉ hiện trong bài khi biên tập chèn shortcode ở vị trí phù hợp với nội dung. Không chèn thì tự ẩn, vì thanh đáy đã có nút đặt lịch và tư vấn.
- **Thanh đáy** cao 56px (hiện tại 32px, nhỏ hơn chuẩn bấm 44–48px), gồm 3 nút:
  - **Gọi**: chọn tổng đài Hà Nội hoặc TP.HCM.
  - **Chat tư vấn**: giữ Messenger như hiện tại, thêm Zalo, kèm lựa chọn gửi câu hỏi cho bác sĩ.
  - **Đặt lịch khám**: mở form ngay trong bài, không chuyển trang.
- **Mục lục nổi** (nút tròn có vòng tiến độ đọc) giữ như site hiện tại, bổ sung hiển thị cả H3 và mục đang đọc.

## 4. Hộp thông tin Hệ thống BVĐK Tâm Anh (cuối bài)

Hiện tại là một khối chữ liền dồn 5 cơ sở, khó tìm cơ sở mình cần. Đề xuất:
- **PC:** chia 2 cột TP.HCM | Hà Nội.
- **Mobile:** 2 tab, mặc định theo cơ sở của bác sĩ tư vấn bài.
- Mỗi cơ sở có địa chỉ, giờ làm việc, nhãn **Cấp cứu 24/7**, nút **Chỉ đường** (Google Maps) và **hotline bấm gọi**.

Người đọc tìm được cơ sở gần mình và gọi hoặc chỉ đường chỉ với 1 chạm. Thông tin tên, địa chỉ, hotline từng cơ sở cũng được trình bày rõ ràng, nhất quán.

## Cần xác nhận

- **Dev:** form gửi chung API đặt lịch hiện tại; lấy được Primary Category của bài; làm shortcode/block `[ta_banner]`, `[ta_booking]`, `[ta_qa]`.
- **Marketing:** đặt mức ưu tiên banner; làm thêm 1 kích thước banner dọc chuẩn cho slide.
- **CSKH:** thời gian gọi lại cam kết.
- **Pháp chế:** duyệt câu chữ đồng ý xử lý dữ liệu cá nhân và nhãn banner.
