


## Bài tổng hợp: Nhóm SmartCampus chạy nước rút trước deadline

### Phần 1: Thiết lập Hybrid Workflow

**1.1. Sự cố hỏng ổ cứng có xảy ra không?**

Nếu nhóm đã dùng đúng Hybrid Workflow thì **không mất file**. Mỗi lần lưu (Ctrl+S), Auto Sync tự đưa bản mới lên Cloud. Dù laptop hỏng, bản Slide mới nhất vẫn nằm trên Cloud và có thể mở từ máy khác. Sự cố xảy ra vì nhóm đang lưu file trên máy từng người và gửi qua Zalo, chưa có bản sao lưu tự động

**1.2. Ba bước thiết lập Auto Sync cho cả nhóm làm hôm nay**

1.  Cài ứng dụng đồng bộ (Google Drive for desktop hoặc OneDrive) và đăng nhập tài khoản
2.  Chọn thư mục dự án SmartCampus làm thư mục đồng bộ, và chuyển tất cả file đang để rời rạc trên máy vào thư mục này
3.  Bật Auto Sync và kiểm tra biểu tượng trên file chuyển sang **tích xanh** (đã đồng bộ xong)

**1.3. Khôi phục 2 trang bị xóa nhầm**

Dùng **Version History** (Lịch sử phiên bản): mở file `BaoCao_CuoiKy_SmartCampus.docx`, vào **File → Version History**, chọn phiên bản cách đây khoảng 10 phút (trước lúc xóa) rồi bấm **Restore** (Khôi phục). Không cần gõ lại từ đầu

**1.4. Đồng bộ node_modules và phim 4K**

Đây là 2 sai lầm đã học:

-   **Đồng bộ thư mục node_modules:** hàng vạn file nhỏ làm phần mềm sync bị treo
--   **Đồng bộ file nặng, không liên quan đồ án (phim 4K):** làm đầy dung lượng Cloud
**Cách xử lý đúng:** chỉ đồng bộ những thứ cần thiết (code, tài liệu, báo cáo, slide). Loại `node_modules` ra khỏi vùng đồng bộ (có thể tạo lại bằng `npm install`, và dùng `.gitignore` nếu dùng Git). Chuyển phim 4K ra ngoài thư mục dự án

### Phần 2: Phân quyền chia sẻ an toàn

**2.1. Bảng phân quyền**


**Restricted** (chỉ email giảng viên)

Giảng viên chỉ cần xem để chấm, Viewer không sửa đè được nội dung.

Slide_BaoCao.pptx (5 thành viên)

**Editor**

**Restricted** (email 5 thành viên)

Cả nhóm cần cùng sửa gấp, và chỉ người trong nhóm mới được truy cập.

GopY_BanNhap.docx (anh khóa trên)

**Commenter**

**Restricted** (email của anh)

Anh chỉ cần để lại nhận xét, không được sửa trực tiếp.

ThongTin_CaNhan_NhomVien.xlsx

**Viewer**

**Restricted** (chỉ người thật sự cần)

File chứa CCCD, SĐT nên chỉ chia sẻ hẹp nhất có thể

**2.2. Quy tắc Cờ Đỏ Bảo mật với file ThongTin_CaNhan_NhomVien.xlsx**

**Quy tắc Cờ Đỏ:** file chứa dữ liệu cá nhân nhạy cảm (CCCD, SĐT...) thì tuyệt đối không dùng **Anyone with the link + Editor**.

* Hậu quả là lộ thông tin cá nhân của cả nhóm và dữ liệu có thể bị phá hỏng.

**2.3. Hai thao tác trong Settings của Slide_BaoCao.pptx**

1.  **Tắt** tùy chọn cho phép Editor tự thay đổi quyền và mời thêm người để không ai mời người lạ vào file.
2.  **Tắt** tùy chọn cho Viewer/Commenter tải xuống, in và sao chép file, để hạn chế việc file bị mang ra ngoài

### Phần 3: Tổ chức giao tiếp nhóm chuẩn doanh nghiệp

**3.1. Ba vấn đề trong đoạn hội thoại Zalo**

1.  **Vi phạm quy tắc No-Hello:** Lan nhắn “có ai rảnh không”, rồi “giúp em cái này được không ạ” mà không nói rõ việc gì, nên người đọc phải hỏi lại nhiều lần và mất thời gian
2.  **Spam @all giờ khuya:** trưởng nhóm tag @all lúc 23:47 làm cả nhóm bị làm phiền ngoài giờ, trong khi chỉ một vài người chưa xong
3.  **Tin nhắn không phân luồng:** chuyện công việc, ảnh mèo và tán gẫu nằm chung một chỗ, nên thông báo quan trọng dễ bị trôi

**3.2. Đề xuất Channel/Topic**

-   `#thong-bao`: thông báo deadline, thông tin quan trọng của nhóm
-   `#cong-viec-bao-cao`: trao đổi, hỏi đáp về nội dung báo cáo và slide
-   `#tan-gau`: ảnh mèo, meme, chuyện ngoài lề

**3.3. Viết lại tin nhắn của Lan (tư duy Asynchronous)**

> Chào cả nhóm, mình đang làm phần 3 của báo cáo (Thiết kế hệ thống) và chưa biết cách vẽ sơ đồ Use Case cho chức năng đăng ký phòng học. Bạn nào đã làm sơ đồ này rồi có thể gửi mình file mẫu hoặc hướng dẫn giúp mình được không? Mình cần hoàn thành trước 17h thứ Năm. Bạn nào rảnh thì trả lời ngay trong thread này nhé. Cảm ơn cả nhóm!

Tin nhắn này đủ ngữ cảnh  nên ai đọc lúc 2h chiều hay 10h đêm cũng trả lời được ngay.

**3.4. Viết lại tin nhắn @all lúc 23:47 (Schedule Send)**

**Hẹn gửi lúc 08:00 sáng hôm sau:**

> Chào @Lan, hôm nay là hạn nộp báo cáo cuối kỳ (nộp trước 17h). Hiện phần 3 của bạn vẫn chưa hoàn thành. Bạn cập nhật tiến độ trong thread này và gửi bản hoàn chỉnh trước 14h giúp nhóm nhé, để mọi người còn kịp ghép file. Nếu bạn cần hỗ trợ, nhắn mình ngay. Cảm ơn bạn!


### Phần 4: Thông báo tổng hợp đăng lên kênh #thong-bao

> **[Cập nhật không gian làm việc nhóm SmartCampus]**
> 
> Chào cả nhóm, mình đã tổ chức lại không gian làm việc như sau:
> 
> 1.  **Đã bật Auto Sync** cho thư mục dự án SmartCampus. Mọi người đưa file vào thư mục này và kiểm tra có tích xanh nhé, file sẽ được lưu tự động lên Cloud và có thể khôi phục bằng Version History nếu lỡ xóa nhầm.
> 2.  **Đã chia sẻ file báo cáo** `BaoCao_CuoiKy_SmartCampus.docx` cho giảng viên với quyền **Viewer / Restricted** (chỉ email của thầy/cô), nên không ai bị sửa đè nội dung.\
> 3.  **Phần việc còn thiếu:** @Lan vui lòng hoàn thành phần 3 trước 14h hôm nay. @Nam vui lòng kiểm tra lại phần tài liệu tham khảo trước 15h. Bạn nào cần hỗ trợ thì trả lời ngay trong thread này
