# PHÂN TÍCH NGHIỆP VỤ – DỰ ÁN CAB SYSTEM

---

# Bước 1: Phân tích ngữ cảnh nghiệp vụ – Dự án CAB System

## 1.1. Vấn đề nghiệp vụ khách hàng muốn giải quyết

Công ty ABC đang vận hành dịch vụ đặt xe theo cách thủ công và phân mảnh. Việc phân công tài xế chủ yếu do nhân viên thực hiện thủ công, dẫn đến thời gian xử lý lâu và khó tối ưu khi số lượng chuyến tăng cao.

Khách hàng hiện chưa có khả năng theo dõi đầy đủ trạng thái chuyến đi, dẫn đến trải nghiệm chưa tốt và làm tăng số lượng cuộc gọi đến bộ phận hỗ trợ.

Thông tin thanh toán chưa được quản lý tập trung, gây khó khăn cho việc đối soát giao dịch và lập báo cáo doanh thu, đồng thời làm tăng nguy cơ sai lệch dữ liệu.

Ngoài ra, hệ thống hiện tại gồm tổng đài kết hợp với một ứng dụng đơn giản chưa đáp ứng được khả năng mở rộng quy mô và bổ sung các tính năng mới trong tương lai.

### Các vấn đề nghiệp vụ chính

- Phân công tài xế còn phụ thuộc nhiều vào thao tác thủ công.
- Khách hàng chưa thể theo dõi trạng thái chuyến đi một cách đầy đủ.
- Thông tin thanh toán chưa được quản lý tập trung.
- Việc đối soát và lập báo cáo doanh thu còn khó khăn.
- Hệ thống hiện tại khó mở rộng khi số lượng người dùng và chuyến đi tăng.
- Việc bổ sung tính năng mới có thể ảnh hưởng đến các chức năng đang hoạt động.
- Khi một thành phần gặp lỗi, có nguy cơ ảnh hưởng đến hoạt động chung của hệ thống.

### Nhận định vấn đề

Đây không phải là bài toán "chưa có hệ thống", mà là bài toán **hệ thống hiện tại chưa đủ khả năng tự động hóa, quản lý tập trung, mở rộng và đáp ứng nhu cầu phát triển của doanh nghiệp**.

---

## 1.2. Nguyên nhân khiến hệ thống hiện tại chưa đáp ứng được

Dựa trên thông tin nghiệp vụ hiện có, có thể xác định một số nguyên nhân có khả năng tồn tại:

- Quy trình phân công tài xế còn phụ thuộc nhiều vào nhân viên tổng đài.
- Hệ thống chưa có cơ chế tự động tìm kiếm và ghép nối khách hàng với tài xế phù hợp.
- Khả năng cập nhật trạng thái chuyến đi theo thời gian thực còn hạn chế.
- Dữ liệu khách hàng, tài xế, chuyến đi và thanh toán có thể chưa được quản lý tập trung.
- Hệ thống hiện tại có khả năng mở rộng hạn chế khi số lượng người dùng tăng.
- Các chức năng có thể còn phụ thuộc lẫn nhau, làm tăng nguy cơ ảnh hưởng dây chuyền khi một thành phần gặp lỗi.
- Việc tích hợp thêm phương thức thanh toán hoặc kênh thông báo mới có thể khó khăn.

> **Lưu ý:** Tài liệu chưa cung cấp thông tin cụ thể về công nghệ và kiến trúc của hệ thống cũ. Vì vậy, các nguyên nhân trên cần được xác nhận lại với khách hàng trong quá trình làm rõ yêu cầu.

---

## 1.3. Người sử dụng và các bên liên quan

### Người sử dụng trực tiếp

**Khách hàng (Customer/Passenger)**

- Đăng ký và đăng nhập.
- Quản lý thông tin cá nhân.
- Đặt xe.
- Theo dõi trạng thái chuyến đi.
- Xem thông tin tài xế và phương tiện.
- Thanh toán.
- Xem lịch sử chuyến đi.
- Đánh giá tài xế.

**Tài xế (Driver)**

- Quản lý thông tin cá nhân và phương tiện.
- Cập nhật trạng thái sẵn sàng nhận chuyến.
- Nhận thông báo chuyến mới.
- Chấp nhận hoặc từ chối chuyến.
- Cập nhật trạng thái chuyến đi.
- Cập nhật vị trí.

**Nhân viên vận hành (Operations Staff)**

- Quản lý khách hàng.
- Quản lý tài xế.
- Quản lý phương tiện.
- Giám sát các chuyến đang diễn ra.
- Xử lý các chuyến gặp sự cố.
- Tra cứu lịch sử chuyến đi và giao dịch.
- Thực hiện các thao tác quản trị theo quyền được cấp.

### Các bên liên quan khác

- **Ban lãnh đạo:** sử dụng báo cáo để theo dõi doanh thu và hiệu quả vận hành.
- **Nhà cung cấp thanh toán:** xử lý các giao dịch thanh toán điện tử.
- **Bộ phận chăm sóc khách hàng:** hỗ trợ xử lý khiếu nại và vấn đề liên quan đến chuyến đi.
- **Bộ phận tài chính/kế toán:** sử dụng dữ liệu giao dịch và báo cáo doanh thu để đối soát.
- **Cơ quan quản lý/pháp lý:** đặt ra các yêu cầu liên quan đến bảo vệ dữ liệu và hoạt động vận tải.
- **Đội ngũ phát triển/BA:** phân tích, thiết kế, xây dựng và triển khai hệ thống.

---

## 1.4. Giá trị nghiệp vụ sau khi triển khai hệ thống

Sau khi triển khai CAB System, doanh nghiệp dự kiến đạt được các giá trị sau:

### Đối với hoạt động vận hành

- Tự động hóa quá trình tìm kiếm và phân công tài xế.
- Giảm sự phụ thuộc vào nhân viên tổng đài.
- Rút ngắn thời gian xử lý yêu cầu đặt xe.
- Giảm sai sót trong quá trình phân công.
- Hỗ trợ nhân viên vận hành giám sát chuyến đi tập trung.

### Đối với khách hàng

- Đặt xe thuận tiện hơn.
- Theo dõi được trạng thái chuyến đi.
- Biết được thông tin tài xế và phương tiện.
- Có nhiều lựa chọn thanh toán.
- Xem được lịch sử chuyến đi.
- Có thể đánh giá tài xế sau chuyến.

### Đối với tài xế

- Nhận chuyến một cách rõ ràng.
- Chủ động chấp nhận hoặc từ chối chuyến.
- Cập nhật trạng thái chuyến.
- Cập nhật vị trí để hỗ trợ phân công và theo dõi.

### Đối với tài chính và quản trị

- Quản lý dữ liệu thanh toán tập trung.
- Hỗ trợ đối soát giao dịch.
- Cung cấp báo cáo doanh thu.
- Theo dõi tỷ lệ hoàn thành và hủy chuyến.
- Đánh giá hiệu quả hoạt động của tài xế.
- Hỗ trợ ban lãnh đạo ra quyết định dựa trên dữ liệu.

### Đối với khả năng phát triển lâu dài

- Hệ thống có khả năng mở rộng khi số lượng người dùng tăng.
- Có thể bổ sung phương thức thanh toán mới.
- Có thể bổ sung kênh thông báo mới.
- Có thể mở rộng các thành phần độc lập.
- Hạn chế ảnh hưởng dây chuyền khi một thành phần gặp lỗi.

---

## 1.5. Nhận định tổng quát

CAB System là dự án chuyển đổi từ mô hình vận hành thủ công/bán tự động sang một nền tảng số hóa dịch vụ đặt xe.

Ba luồng nghiệp vụ cốt lõi của hệ thống gồm:

1. **Đặt xe và phân công tài xế.**
2. **Quản lý vòng đời và theo dõi chuyến đi.**
3. **Thanh toán, quản trị và báo cáo.**

Ngoài các chức năng nghiệp vụ chính, hệ thống cần đáp ứng các yêu cầu về khả năng mở rộng, bảo mật, ổn định và khả năng mở rộng chức năng trong tương lai.

Một số vấn đề chưa được chốt như cách tính cước chi tiết, tiêu chí ưu tiên tài xế, thời gian tài xế phản hồi, chính sách hủy chuyến và xử lý khi mất kết nối cần được làm rõ với khách hàng trước khi xây dựng các yêu cầu chi tiết.

---

# Bước 2: Xác định Stakeholder – Các bên liên quan

## 2.1. Danh sách Stakeholder

| STT | Stakeholder | Vai trò |
|---|---|---|
| 1 | Khách hàng (Customer/Passenger) | Đăng ký, đặt xe, theo dõi chuyến, thanh toán và đánh giá tài xế |
| 2 | Tài xế (Driver) | Nhận/từ chối chuyến, cập nhật trạng thái chuyến, vị trí và thông tin phương tiện |
| 3 | Nhân viên vận hành (Operations Staff) | Quản lý khách hàng, tài xế, phương tiện, giám sát và xử lý chuyến |
| 4 | Ban lãnh đạo (Executive Sponsor) | Phê duyệt dự án, theo dõi hiệu quả và sử dụng báo cáo quản trị |
| 5 | Nhà cung cấp thanh toán (Payment Gateway Provider) | Xử lý các giao dịch thanh toán điện tử |
| 6 | Bộ phận chăm sóc khách hàng (Customer Support) | Tiếp nhận và xử lý khiếu nại, hỗ trợ khách hàng |
| 7 | Bộ phận tài chính/kế toán (Finance/Accounting) | Đối soát giao dịch và sử dụng báo cáo doanh thu |
| 8 | Cơ quan quản lý/pháp lý (Regulatory Body) | Đảm bảo hệ thống đáp ứng các yêu cầu pháp lý liên quan |
| 9 | Đội ngũ phát triển và BA (Development Team/BA) | Phân tích, thiết kế, phát triển và triển khai hệ thống |

---

## 2.2. Ma trận Power/Interest

| Nhóm | Mức ảnh hưởng | Mức quan tâm | Stakeholder | Chiến lược quản lý |
|---|---|---|---|---|
| **Manage Closely** | Cao | Cao | Ban lãnh đạo, Nhân viên vận hành, Đội ngũ BA/Development | Làm việc thường xuyên, lấy ý kiến và báo cáo tiến độ |
| **Keep Satisfied** | Cao | Thấp | Nhà cung cấp thanh toán, Cơ quan quản lý/pháp lý | Đảm bảo các yêu cầu quan trọng được đáp ứng |
| **Keep Informed** | Thấp | Cao | Khách hàng, Tài xế, CSKH, Tài chính/kế toán | Cập nhật thông tin thường xuyên và thu thập phản hồi |
| **Monitor** | Thấp | Thấp | Các bên liên quan khác | Theo dõi và phối hợp khi cần thiết |

---
<img width="870" height="1050" alt="image" src="https://github.com/user-attachments/assets/b73f9827-12a4-4dd2-9ee6-07c752a84383" />


## 2.3. Stakeholder quan trọng nhất

Các stakeholder cần ưu tiên trong quá trình thu thập và xác nhận yêu cầu:

- **Ban lãnh đạo:** quyết định phạm vi, ngân sách và mục tiêu dự án.
- **Nhân viên vận hành:** hiểu rõ quy trình vận hành thực tế.
- **Khách hàng:** cung cấp yêu cầu về trải nghiệm đặt và theo dõi chuyến.
- **Tài xế:** cung cấp yêu cầu về nhận chuyến và cập nhật trạng thái.
- **Nhà cung cấp thanh toán:** cung cấp các ràng buộc kỹ thuật và bảo mật.
- **BA/Development:** chuyển nhu cầu nghiệp vụ thành yêu cầu hệ thống.

---

# Bước 3: Xác định Business Goals (BG) – Dự án CAB System

Business Goal được xác định dựa trên các vấn đề nghiệp vụ và nhu cầu của stakeholder ở Bước 1 và Bước 2.

| Mã | Business Goal | Mô tả |
|---|---|---|
| **BG_01** | Tự động hóa đặt xe và phân công tài xế | Tự động tiếp nhận yêu cầu đặt xe và tìm tài xế phù hợp dựa trên vị trí và trạng thái sẵn sàng |
| **BG_02** | Quản lý và theo dõi chuyến đi theo thời gian thực | Cho phép khách hàng và nhân viên vận hành theo dõi trạng thái chuyến đi trong suốt vòng đời chuyến |
| **BG_03** | Quản lý thanh toán tập trung và đa dạng | Hỗ trợ thanh toán tiền mặt và điện tử, đồng thời quản lý dữ liệu giao dịch tập trung mà không lưu thông tin thanh toán nhạy cảm |
| **BG_04** | Cung cấp hệ thống thông báo linh hoạt | Gửi thông báo cho khách hàng và tài xế tại các sự kiện quan trọng của chuyến đi |
| **BG_05** | Nâng cao hiệu quả quản trị vận hành | Cung cấp công cụ quản lý khách hàng, tài xế, phương tiện, chuyến đi và xử lý sự cố |
| **BG_06** | Cung cấp báo cáo hỗ trợ ra quyết định | Cung cấp báo cáo về số lượng chuyến, doanh thu, tỷ lệ hoàn thành, tỷ lệ hủy và hiệu quả tài xế |
| **BG_07** | Đảm bảo khả năng mở rộng hệ thống | Hệ thống có thể phục vụ số lượng lớn khách hàng, tài xế và chuyến đi khi doanh nghiệp tăng trưởng |
| **BG_08** | Đảm bảo tính ổn định và khả năng chịu lỗi | Hạn chế việc lỗi ở một thành phần như thanh toán hoặc thông báo ảnh hưởng đến toàn bộ hệ thống |
| **BG_09** | Đảm bảo an toàn và bảo mật thông tin | Bảo vệ thông tin cá nhân, vị trí, dữ liệu giao dịch và kiểm soát quyền truy cập |
| **BG_10** | Đảm bảo khả năng mở rộng chức năng trong tương lai | Cho phép bổ sung dịch vụ, phương thức thanh toán và kênh thông báo mới mà không phải thay đổi toàn bộ hệ thống |

---

## 3.1. Phân loại Business Goal

### Nhóm mục tiêu nghiệp vụ cốt lõi

- **BG_01:** Tự động hóa đặt xe và phân công tài xế.
- **BG_02:** Quản lý và theo dõi chuyến đi.
- **BG_03:** Quản lý thanh toán.
- **BG_04:** Cung cấp hệ thống thông báo.
- **BG_05:** Quản trị vận hành.
- **BG_06:** Báo cáo và hỗ trợ ra quyết định.

### Nhóm mục tiêu phi chức năng và kiến trúc

- **BG_07:** Khả năng mở rộng quy mô.
- **BG_08:** Ổn định và chịu lỗi.
- **BG_09:** An toàn và bảo mật.
- **BG_10:** Khả năng mở rộng chức năng trong tương lai.

---

## 3.2. Thứ tự ưu tiên đề xuất

Với thời gian triển khai dự kiến 7 tuần, thứ tự ưu tiên đề xuất:

**Ưu tiên cao:**

- BG_01 – Đặt xe và phân công tài xế.
- BG_02 – Quản lý và theo dõi chuyến.
- BG_03 – Thanh toán.
- BG_05 – Quản trị vận hành.

**Ưu tiên trung bình:**

- BG_04 – Thông báo.
- BG_06 – Báo cáo.

**Yêu cầu nền tảng cần đảm bảo:**

- BG_07 – Khả năng mở rộng.
- BG_08 – Ổn định và chịu lỗi.
- BG_09 – Bảo mật.

**Định hướng phát triển:**

- BG_10 – Khả năng mở rộng chức năng trong tương lai.

> Thứ tự ưu tiên trên là đề xuất ban đầu và cần được xác nhận với Ban lãnh đạo và các stakeholder chính.

---

# Bước 4: Xác định Phạm vi (Scope) – Dự án CAB System

## 4.1. In Scope – Trong phạm vi

### 1. Quản lý khách hàng

- Đăng ký tài khoản.
- Đăng nhập.
- Quản lý thông tin cá nhân.
- Nhập điểm đón và điểm đến.
- Lựa chọn loại xe.
- Gửi yêu cầu đặt xe.
- Theo dõi trạng thái chuyến đi.
- Xem thông tin tài xế và phương tiện.
- Xem lịch sử chuyến đi.
- Xem số tiền phải thanh toán.
- Đánh giá tài xế sau chuyến.

### 2. Quản lý tài xế

- Tạo/quản lý tài khoản tài xế.
- Cập nhật thông tin cá nhân.
- Cập nhật thông tin phương tiện.
- Chuyển trạng thái sẵn sàng/không sẵn sàng.
- Nhận thông báo chuyến mới.
- Chấp nhận hoặc từ chối chuyến.
- Cập nhật trạng thái chuyến đi.
- Cập nhật vị trí.

### 3. Tìm kiếm và phân công tài xế

- Tiếp nhận yêu cầu đặt xe.
- Xác định tài xế phù hợp dựa trên vị trí và trạng thái sẵn sàng.
- Gửi yêu cầu chuyến đến tài xế.
- Chuyển yêu cầu sang tài xế khác khi tài xế từ chối hoặc không phản hồi.
- Thông báo cho khách hàng khi không tìm được tài xế.

### 4. Quản lý chuyến đi

- Tạo chuyến đi.
- Cập nhật trạng thái chuyến.
- Theo dõi chuyến theo thời gian thực.
- Hiển thị thông tin tài xế và phương tiện.
- Quản lý trạng thái hoàn thành chuyến.
- Ghi nhận lịch sử chuyến đi.

### 5. Thanh toán và tính cước

- Tính số tiền phải thanh toán sau khi hoàn thành chuyến.
- Hỗ trợ thanh toán tiền mặt.
- Hỗ trợ thanh toán điện tử.
- Tích hợp với một nhà cung cấp thanh toán bên ngoài.
- Không lưu thông tin thanh toán nhạy cảm.
- Ghi nhận trạng thái giao dịch.
- Thông báo kết quả thanh toán.
- Hỗ trợ xử lý lại giao dịch điện tử thất bại.

### 6. Thông báo

Hệ thống gửi thông báo đến khách hàng tại các mốc:

- Tiếp nhận yêu cầu đặt xe.
- Tài xế nhận chuyến.
- Tài xế đến điểm đón.
- Chuyến đi hoàn thành.
- Thanh toán thành công/thất bại.

Hệ thống gửi thông báo cho tài xế khi:

- Có chuyến mới.
- Chuyến bị thay đổi.
- Có các sự kiện quan trọng liên quan đến chuyến.

### 7. Quản trị vận hành

- Quản lý khách hàng.
- Quản lý tài xế.
- Quản lý phương tiện.
- Quản lý chuyến đi.
- Giám sát các chuyến đang diễn ra.
- Xử lý chuyến bị lỗi hoặc phát sinh sự cố.
- Tra cứu lịch sử chuyến đi.
- Tra cứu lịch sử giao dịch.
- Phân quyền đối với các thao tác quản trị.

### 8. Báo cáo

Hệ thống cung cấp:

- Báo cáo số lượng chuyến.
- Báo cáo doanh thu.
- Báo cáo tỷ lệ hoàn thành.
- Báo cáo tỷ lệ hủy chuyến.
- Báo cáo hiệu quả hoạt động của tài xế.

### 9. Yêu cầu nền tảng

- Xác thực người dùng.
- Kiểm soát quyền truy cập.
- Lưu vết các thao tác quan trọng.
- Bảo vệ dữ liệu cá nhân.
- Bảo vệ dữ liệu vị trí.
- Bảo vệ dữ liệu giao dịch.
- Hỗ trợ khả năng mở rộng.
- Hạn chế ảnh hưởng khi một thành phần gặp lỗi.
- Cho phép mở rộng các thành phần độc lập.

---

## 4.2. Out of Scope – Ngoài phạm vi giai đoạn hiện tại

Các nội dung sau chưa được đưa vào phạm vi triển khai MVP do chưa có yêu cầu hoặc chưa được xác nhận:

| STT | Hạng mục | Lý do |
|---|---|---|
| 1 | Công thức tính cước chi tiết | Chưa được xác định cụ thể |
| 2 | Tiêu chí ưu tiên tài xế nâng cao | Chưa được xác nhận ngoài vị trí và trạng thái sẵn sàng |
| 3 | Thời gian tài xế phải phản hồi | Chưa được xác định |
| 4 | Chính sách hủy chuyến và phí hủy | Chưa được xác định |
| 5 | Cơ chế xử lý khi mất kết nối mạng | Chưa được xác định |
| 6 | Thời gian lưu trữ dữ liệu | Chưa được xác định |
| 7 | Khuyến mãi và mã giảm giá | Không được đề cập |
| 8 | Chương trình khách hàng thân thiết | Không được đề cập |
| 9 | Đa ngôn ngữ | Không được đề cập |
| 10 | Đa tiền tệ | Không được đề cập |
| 11 | Nhiều nhà cung cấp thanh toán | Giai đoạn đầu chỉ tích hợp một nhà cung cấp |
| 12 | Bổ sung loại dịch vụ mới | Định hướng mở rộng trong tương lai |
| 13 | Routing/bản đồ nâng cao | Chưa xác định mức độ tích hợp |
| 14 | Ứng dụng mobile native riêng cho iOS/Android | Chưa xác định kênh triển khai cụ thể |
| 15 | Quy định pháp lý chi tiết theo từng khu vực | Cần xác nhận với bộ phận pháp lý |

> **Lưu ý:** Out of Scope không có nghĩa là các chức năng này không bao giờ được xây dựng. Đây là những nội dung chưa thuộc phạm vi MVP hoặc cần được làm rõ trước khi triển khai.

---

## 4.3. Kết quả xác định Scope

Phạm vi hệ thống được tập trung vào các nghiệp vụ cốt lõi:

**Đặt xe → Tìm tài xế → Phân công → Theo dõi chuyến → Hoàn thành chuyến → Thanh toán → Đánh giá → Quản trị và báo cáo.**

Phạm vi này phù hợp với các Business Goal từ **BG_01 đến BG_10**, đồng thời phù hợp với thời gian triển khai ngắn và định hướng xây dựng MVP.

---

# Bước 5: Chuyển đổi yêu cầu thành Business Requirement (BR)

Business Requirement được xây dựng dựa trên:

- Các vấn đề nghiệp vụ ở Bước 1.
- Nhu cầu của Stakeholder ở Bước 2.
- Business Goal ở Bước 3.
- Phạm vi In Scope ở Bước 4.

Mỗi Business Requirement được đánh mã từ **BR_01** để thuận tiện cho việc quản lý, truy vết và chuyển đổi thành Functional Requirement ở bước tiếp theo.

---

## 5.1. Danh sách Business Requirement

| Mã | Business Requirement | Business Goal liên quan |
|---|---|---|
| **BR_01** | Hệ thống phải cho phép khách hàng đăng ký, đăng nhập và quản lý thông tin tài khoản cá nhân. | BG_05, BG_09 |
| **BR_02** | Hệ thống phải cho phép khách hàng nhập điểm đón và điểm đến để tạo yêu cầu đặt xe. | BG_01 |
| **BR_03** | Hệ thống phải cho phép khách hàng lựa chọn loại xe khi đặt chuyến. | BG_01 |
| **BR_04** | Hệ thống phải tự động tìm kiếm và phân công tài xế phù hợp dựa trên vị trí và trạng thái sẵn sàng. | BG_01 |
| **BR_05** | Hệ thống phải chuyển yêu cầu sang tài xế khác khi tài xế được đề nghị không phản hồi hoặc từ chối chuyến. | BG_01, BG_08 |
| **BR_06** | Hệ thống phải thông báo cho khách hàng khi không tìm được tài xế phù hợp. | BG_01, BG_04 |
| **BR_07** | Hệ thống phải cho phép tài xế cập nhật trạng thái sẵn sàng hoặc không sẵn sàng nhận chuyến. | BG_01 |
| **BR_08** | Hệ thống phải cho phép tài xế chấp nhận hoặc từ chối yêu cầu chuyến đi. | BG_01 |
| **BR_09** | Hệ thống phải cho phép tài xế cập nhật trạng thái chuyến đi trong toàn bộ vòng đời chuyến. | BG_02 |
| **BR_10** | Hệ thống phải cho phép tài xế cập nhật vị trí để phục vụ việc phân công và theo dõi chuyến. | BG_01, BG_02 |
| **BR_11** | Hệ thống phải cho phép khách hàng theo dõi trạng thái chuyến đi theo thời gian thực. | BG_02 |
| **BR_12** | Hệ thống phải cung cấp thông tin tài xế và phương tiện cho khách hàng sau khi chuyến được phân công. | BG_02 |
| **BR_13** | Hệ thống phải cho phép khách hàng xem lịch sử các chuyến đi đã thực hiện. | BG_02, BG_05 |
| **BR_14** | Hệ thống phải xác định số tiền khách hàng phải thanh toán sau khi chuyến đi hoàn thành. | BG_03 |
| **BR_15** | Hệ thống phải hỗ trợ thanh toán bằng tiền mặt. | BG_03 |
| **BR_16** | Hệ thống phải hỗ trợ thanh toán điện tử thông qua nhà cung cấp thanh toán bên ngoài. | BG_03 |
| **BR_17** | Hệ thống không được lưu trữ thông tin thanh toán nhạy cảm của khách hàng. | BG_03, BG_09 |
| **BR_18** | Hệ thống phải ghi nhận và thông báo kết quả thanh toán cho khách hàng. | BG_03, BG_04 |
| **BR_19** | Hệ thống phải hỗ trợ xử lý lại giao dịch khi thanh toán điện tử thất bại. | BG_03, BG_08 |
| **BR_20** | Hệ thống phải gửi thông báo cho khách hàng tại các mốc quan trọng của chuyến đi. | BG_04 |
| **BR_21** | Hệ thống phải gửi thông báo cho tài xế khi có chuyến mới hoặc thay đổi liên quan đến chuyến. | BG_04 |
| **BR_22** | Hệ thống phải cho phép khách hàng đánh giá tài xế sau khi chuyến đi hoàn thành. | BG_02 |
| **BR_23** | Hệ thống phải cho phép nhân viên vận hành quản lý thông tin khách hàng, tài xế và phương tiện. | BG_05 |
| **BR_24** | Hệ thống phải cho phép nhân viên vận hành quản lý và giám sát các chuyến đang diễn ra. | BG_05 |
| **BR_25** | Hệ thống phải cho phép nhân viên vận hành xử lý các chuyến bị lỗi hoặc phát sinh sự cố. | BG_05, BG_08 |
| **BR_26** | Hệ thống phải cho phép nhân viên vận hành tra cứu lịch sử chuyến đi và giao dịch. | BG_05 |
| **BR_27** | Hệ thống phải kiểm soát quyền truy cập đối với các chức năng quản trị và thao tác nhạy cảm. | BG_05, BG_09 |
| **BR_28** | Hệ thống phải lưu vết các thao tác quan trọng của người dùng và nhân viên vận hành. | BG_09 |
| **BR_29** | Hệ thống phải cung cấp báo cáo về số lượng chuyến, doanh thu, tỷ lệ hoàn thành và tỷ lệ hủy chuyến. | BG_06 |
| **BR_30** | Hệ thống phải cung cấp báo cáo về hiệu quả hoạt động của tài xế. | BG_06 |
| **BR_31** | Hệ thống phải có khả năng phục vụ số lượng lớn khách hàng, tài xế và chuyến đi khi nhu cầu tăng. | BG_07 |
| **BR_32** | Hệ thống phải cho phép các thành phần được mở rộng và triển khai độc lập khi cần thiết. | BG_07, BG_08, BG_10 |
| **BR_33** | Lỗi của một thành phần như thanh toán hoặc thông báo không được làm ngừng toàn bộ chức năng đặt xe. | BG_08 |
| **BR_34** | Hệ thống phải hỗ trợ khả năng bổ sung dịch vụ, phương thức thanh toán hoặc kênh thông báo mới trong tương lai. | BG_04, BG_10 |
| **BR_35** | Hệ thống phải bảo vệ thông tin cá nhân, thông tin vị trí và dữ liệu giao dịch của người dùng. | BG_09 |

---

## 5.2. Phân nhóm Business Requirement

### Nhóm 1 – Quản lý khách hàng

- **BR_01:** Đăng ký, đăng nhập và quản lý tài khoản.
- **BR_02:** Nhập điểm đón, điểm đến và đặt xe.
- **BR_03:** Lựa chọn loại xe.
- **BR_11:** Theo dõi trạng thái chuyến.
- **BR_12:** Xem thông tin tài xế và phương tiện.
- **BR_13:** Xem lịch sử chuyến.
- **BR_22:** Đánh giá tài xế.

### Nhóm 2 – Quản lý tài xế và phân công chuyến

- **BR_04:** Tự động tìm và phân công tài xế.
- **BR_05:** Chuyển sang tài xế khác khi tài xế từ chối hoặc không phản hồi.
- **BR_06:** Thông báo khi không tìm được tài xế.
- **BR_07:** Cập nhật trạng thái sẵn sàng.
- **BR_08:** Nhận hoặc từ chối chuyến.
- **BR_09:** Cập nhật trạng thái chuyến.
- **BR_10:** Cập nhật vị trí.

### Nhóm 3 – Quản lý chuyến đi

- **BR_09:** Cập nhật trạng thái chuyến.
- **BR_10:** Cập nhật vị trí tài xế.
- **BR_11:** Theo dõi chuyến theo thời gian thực.
- **BR_12:** Hiển thị thông tin tài xế và phương tiện.
- **BR_13:** Lưu và xem lịch sử chuyến.
- **BR_22:** Đánh giá tài xế.

### Nhóm 4 – Thanh toán

- **BR_14:** Xác định số tiền phải thanh toán.
- **BR_15:** Thanh toán tiền mặt.
- **BR_16:** Thanh toán điện tử.
- **BR_17:** Không lưu dữ liệu thanh toán nhạy cảm.
- **BR_18:** Ghi nhận và thông báo kết quả thanh toán.
- **BR_19:** Xử lý lại khi thanh toán thất bại.

### Nhóm 5 – Thông báo

- **BR_06:** Thông báo khi không tìm được tài xế.
- **BR_20:** Thông báo cho khách hàng.
- **BR_21:** Thông báo cho tài xế.

### Nhóm 6 – Quản trị vận hành

- **BR_23:** Quản lý khách hàng, tài xế và phương tiện.
- **BR_24:** Giám sát chuyến đang diễn ra.
- **BR_25:** Xử lý chuyến bị lỗi.
- **BR_26:** Tra cứu lịch sử.
- **BR_27:** Phân quyền quản trị.
- **BR_28:** Audit Log.

### Nhóm 7 – Báo cáo

- **BR_29:** Báo cáo hoạt động và doanh thu.
- **BR_30:** Báo cáo hiệu quả tài xế.

### Nhóm 8 – Khả năng mở rộng, ổn định và bảo mật

- **BR_31:** Hỗ trợ mở rộng số lượng người dùng và chuyến đi.
- **BR_32:** Mở rộng và triển khai các thành phần độc lập.
- **BR_33:** Cô lập lỗi giữa các thành phần.
- **BR_34:** Dễ bổ sung tính năng và dịch vụ mới.
- **BR_35:** Bảo vệ dữ liệu người dùng.

---

## 5.3. Kiểm tra tính đồng bộ giữa Business Goal – Scope – Business Requirement

Các Business Requirement được xây dựng để bao phủ các Business Goal chính:

| Business Goal | Business Requirement liên quan |
|---|---|
| **BG_01 – Đặt xe và phân công tài xế** | BR_02, BR_03, BR_04, BR_05, BR_06, BR_07, BR_08, BR_10 |
| **BG_02 – Theo dõi chuyến đi** | BR_09, BR_10, BR_11, BR_12, BR_13, BR_22 |
| **BG_03 – Thanh toán** | BR_14, BR_15, BR_16, BR_17, BR_18, BR_19 |
| **BG_04 – Thông báo** | BR_06, BR_20, BR_21, BR_34 |
| **BG_05 – Quản trị vận hành** | BR_01, BR_13, BR_23, BR_24, BR_25, BR_26, BR_27 |
| **BG_06 – Báo cáo** | BR_29, BR_30 |
| **BG_07 – Khả năng mở rộng** | BR_31, BR_32 |
| **BG_08 – Ổn định và chịu lỗi** | BR_05, BR_19, BR_25, BR_32, BR_33 |
| **BG_09 – Bảo mật** | BR_01, BR_17, BR_27, BR_28, BR_35 |
| **BG_10 – Mở rộng chức năng** | BR_32, BR_34 |

# Bước 6: Kết hợp các nghiệp vụ thành Business Process

Dựa trên các Business Requirement đã xác định ở Bước 5, các nghiệp vụ của CAB System được kết hợp thành các Business Process chính. Mỗi Business Process mô tả một luồng nghiệp vụ hoàn chỉnh và được biểu diễn bằng sơ đồ Mermaid.

## 6.1. Tổng quan các Business Process

| Mã | Business Process | Mô tả |
|---|---|---|
| BP01 | Quản lý tài khoản | Đăng ký, đăng nhập và quản lý thông tin khách hàng/tài xế |
| BP02 | Đặt xe và phân công tài xế | Tiếp nhận yêu cầu, tìm kiếm và phân công tài xế |
| BP03 | Thực hiện chuyến đi | Quản lý toàn bộ trạng thái của chuyến từ khi tài xế nhận đến khi hoàn thành |
| BP04 | Thanh toán | Tính cước, lựa chọn phương thức và xử lý giao dịch |
| BP05 | Thông báo | Gửi thông báo cho khách hàng và tài xế theo từng sự kiện |
| BP06 | Quản trị vận hành | Quản lý người dùng, tài xế, phương tiện, chuyến đi và xử lý sự cố |
| BP07 | Báo cáo | Tổng hợp dữ liệu chuyến đi, doanh thu và hiệu quả tài xế |
# Bước 7: Phân rã các yêu cầu về chức năng

Dựa trên các Business Requirement (BR) đã xác định ở Bước 5 và các Business Process (BP) ở Bước 6, các yêu cầu nghiệp vụ được tiếp tục phân rã thành các **Functional Requirement (FR)**.

Functional Requirement mô tả hệ thống **phải thực hiện chức năng gì** để đáp ứng yêu cầu nghiệp vụ.

Mỗi Functional Requirement được đánh mã từ **FR_01** trở đi và được liên kết với Business Requirement tương ứng nhằm đảm bảo khả năng truy vết từ:

**Business Goal → Business Requirement → Functional Requirement → Business Process → Use Case**

---

# 7.1. Nguyên tắc phân rã

Việc phân rã yêu cầu được thực hiện theo các nguyên tắc:

* Mỗi BR có thể được phân rã thành một hoặc nhiều FR.
* Một FR phải mô tả một hành vi/chức năng cụ thể của hệ thống.
* FR phải có thể kiểm thử được.
* FR phải xác định được Actor sử dụng hoặc kích hoạt.
* FR phải có khả năng liên kết với một Business Process.
* Không đưa các yêu cầu chưa được xác nhận vào Functional Requirement chính thức.
* Các yêu cầu về hiệu năng, bảo mật, khả năng mở rộng và chịu lỗi sẽ được quản lý bổ sung dưới nhóm Non-Functional Requirement.

---

# 7.2. Phân rã chức năng tổng thể

CAB System được phân rã thành các nhóm chức năng chính:

```text
CAB SYSTEM
│
├── 1. Quản lý tài khoản
│   ├── Đăng ký tài khoản
│   ├── Đăng nhập
│   ├── Đăng xuất
│   ├── Xem thông tin cá nhân
│   └── Cập nhật thông tin cá nhân
│
├── 2. Quản lý tài xế
│   ├── Quản lý hồ sơ tài xế
│   ├── Quản lý phương tiện
│   ├── Cập nhật trạng thái sẵn sàng
│   ├── Nhận yêu cầu chuyến
│   ├── Chấp nhận chuyến
│   └── Từ chối chuyến
│
├── 3. Đặt xe và phân công tài xế
│   ├── Nhập thông tin chuyến
│   ├── Chọn loại xe
│   ├── Tạo yêu cầu đặt xe
│   ├── Tìm tài xế phù hợp
│   ├── Gửi yêu cầu đến tài xế
│   ├── Xử lý tài xế từ chối
│   ├── Xử lý tài xế không phản hồi
│   └── Thông báo không tìm được tài xế
│
├── 4. Quản lý chuyến đi
│   ├── Tạo chuyến
│   ├── Cập nhật trạng thái chuyến
│   ├── Cập nhật vị trí tài xế
│   ├── Theo dõi chuyến
│   ├── Xem thông tin tài xế
│   ├── Xem thông tin phương tiện
│   ├── Hoàn thành chuyến
│   └── Xem lịch sử chuyến
│
├── 5. Thanh toán
│   ├── Tính cước
│   ├── Chọn phương thức thanh toán
│   ├── Thanh toán tiền mặt
│   ├── Thanh toán điện tử
│   ├── Ghi nhận giao dịch
│   ├── Xử lý thanh toán thất bại
│   └── Thông báo kết quả thanh toán
│
├── 6. Thông báo
│   ├── Thông báo đặt xe
│   ├── Thông báo tài xế nhận chuyến
│   ├── Thông báo tài xế đến điểm đón
│   ├── Thông báo hoàn thành chuyến
│   ├── Thông báo thanh toán
│   └── Thông báo chuyến mới cho tài xế
│
├── 7. Đánh giá
│   ├── Đánh giá tài xế
│   ├── Ghi nhận đánh giá
│   └── Xem đánh giá
│
├── 8. Quản trị vận hành
│   ├── Quản lý khách hàng
│   ├── Quản lý tài xế
│   ├── Quản lý phương tiện
│   ├── Giám sát chuyến
│   ├── Xử lý sự cố
│   ├── Tra cứu lịch sử
│   └── Phân quyền
│
├── 9. Báo cáo
│   ├── Báo cáo chuyến đi
│   ├── Báo cáo doanh thu
│   ├── Báo cáo hoàn thành/hủy
│   └── Báo cáo hiệu quả tài xế
│
└── 10. Bảo mật và Audit
    ├── Xác thực
    ├── Phân quyền
    ├── Ghi nhận Audit Log
    └── Bảo vệ dữ liệu
```

---

# 7.3. FR – Nhóm 1: Quản lý tài khoản

## FR_01 – Đăng ký tài khoản

**BR liên quan:** BR_01

Hệ thống phải cho phép khách hàng và tài xế tạo tài khoản bằng các thông tin được yêu cầu.

### Chức năng con

* FR_01.1 – Nhập thông tin đăng ký.
* FR_01.2 – Kiểm tra dữ liệu bắt buộc.
* FR_01.3 – Kiểm tra thông tin tài khoản đã tồn tại.
* FR_01.4 – Tạo tài khoản mới.
* FR_01.5 – Thông báo kết quả đăng ký.

---

## FR_02 – Đăng nhập

**BR liên quan:** BR_01

Hệ thống phải cho phép người dùng đăng nhập vào hệ thống.

### Chức năng con

* FR_02.1 – Nhập thông tin đăng nhập.
* FR_02.2 – Kiểm tra thông tin xác thực.
* FR_02.3 – Xác định loại tài khoản.
* FR_02.4 – Tạo phiên đăng nhập.
* FR_02.5 – Thông báo lỗi khi đăng nhập không thành công.

---

## FR_03 – Quản lý thông tin cá nhân

**BR liên quan:** BR_01

Hệ thống phải cho phép người dùng xem và cập nhật thông tin cá nhân.

### Chức năng con

* FR_03.1 – Xem thông tin cá nhân.
* FR_03.2 – Cập nhật thông tin cá nhân.
* FR_03.3 – Kiểm tra dữ liệu cập nhật.
* FR_03.4 – Lưu thông tin thay đổi.

---

## FR_04 – Đăng xuất

**BR liên quan:** BR_01

Hệ thống phải cho phép người dùng kết thúc phiên đăng nhập.

---

# 7.4. FR – Nhóm 2: Quản lý tài xế

## FR_05 – Quản lý hồ sơ tài xế

**BR liên quan:** BR_07, BR_23

Hệ thống phải cho phép quản lý thông tin tài xế.

### Chức năng con

* FR_05.1 – Tạo hồ sơ tài xế.
* FR_05.2 – Xem hồ sơ tài xế.
* FR_05.3 – Cập nhật hồ sơ tài xế.
* FR_05.4 – Quản lý trạng thái tài xế.

---

## FR_06 – Quản lý phương tiện

**BR liên quan:** BR_23

Hệ thống phải cho phép tài xế và nhân viên vận hành quản lý thông tin phương tiện.

### Chức năng con

* FR_06.1 – Thêm phương tiện.
* FR_06.2 – Cập nhật thông tin phương tiện.
* FR_06.3 – Xem thông tin phương tiện.
* FR_06.4 – Quản lý trạng thái phương tiện.

---

## FR_07 – Cập nhật trạng thái sẵn sàng

**BR liên quan:** BR_07

Tài xế phải có khả năng chuyển đổi trạng thái:

```text
OFFLINE
   ↓
AVAILABLE
   ↓
BUSY
   ↓
AVAILABLE
```

Các trạng thái chính:

* Không sẵn sàng.
* Sẵn sàng nhận chuyến.
* Đang thực hiện chuyến.

---

## FR_08 – Nhận yêu cầu chuyến

**BR liên quan:** BR_08

Hệ thống phải gửi yêu cầu chuyến đến tài xế phù hợp.

Thông tin yêu cầu tối thiểu gồm:

* Điểm đón.
* Điểm đến.
* Loại xe.
* Thông tin chuyến.
* Thời gian yêu cầu.

---

## FR_09 – Chấp nhận hoặc từ chối chuyến

**BR liên quan:** BR_08

Tài xế phải có khả năng:

* Chấp nhận chuyến.
* Từ chối chuyến.

Kết quả thao tác phải được hệ thống ghi nhận để tiếp tục quá trình phân công.

---

# 7.5. FR – Nhóm 3: Đặt xe và phân công tài xế

## FR_10 – Nhập thông tin đặt xe

**BR liên quan:** BR_02

Khách hàng phải có khả năng nhập:

* Điểm đón.
* Điểm đến.
* Thông tin liên quan đến chuyến.

---

## FR_11 – Lựa chọn loại xe

**BR liên quan:** BR_03

Hệ thống phải hiển thị các loại xe được hỗ trợ và cho phép khách hàng lựa chọn loại xe phù hợp.

---

## FR_12 – Tạo yêu cầu đặt xe

**BR liên quan:** BR_02

Sau khi khách hàng xác nhận đặt xe, hệ thống phải:

1. Kiểm tra thông tin đặt xe.
2. Tạo yêu cầu chuyến.
3. Gán trạng thái yêu cầu.
4. Bắt đầu quá trình tìm tài xế.

---

## FR_13 – Tìm kiếm tài xế phù hợp

**BR liên quan:** BR_04

Hệ thống phải tìm tài xế dựa trên các tiêu chí đã được xác định.

Trong phạm vi MVP, tiêu chí chính gồm:

* Tài xế đang sẵn sàng.
* Tài xế phù hợp với loại xe.
* Vị trí tài xế phù hợp với điểm đón.

---

## FR_14 – Gửi yêu cầu đến tài xế

**BR liên quan:** BR_04, BR_08

Hệ thống phải gửi yêu cầu chuyến đến tài xế được lựa chọn.

Nếu tài xế chấp nhận:

```text
Yêu cầu đặt xe
      ↓
Tài xế chấp nhận
      ↓
Phân công thành công
      ↓
Tạo chuyến
```

---

## FR_15 – Xử lý tài xế từ chối

**BR liên quan:** BR_05

Nếu tài xế từ chối chuyến:

```text
Tài xế từ chối
      ↓
Đánh dấu tài xế không phù hợp
      ↓
Tìm tài xế tiếp theo
      ↓
Gửi yêu cầu mới
```

---

## FR_16 – Xử lý tài xế không phản hồi

**BR liên quan:** BR_05

Nếu tài xế không phản hồi trong khoảng thời gian được hệ thống xác định, hệ thống phải có khả năng chuyển yêu cầu sang tài xế khác.

> Thời gian phản hồi cụ thể cần được xác nhận với khách hàng trước khi triển khai chính thức.

---

## FR_17 – Xử lý không tìm được tài xế

**BR liên quan:** BR_06

Nếu hệ thống không tìm được tài xế phù hợp, hệ thống phải:

* Cập nhật trạng thái yêu cầu.
* Thông báo cho khách hàng.
* Ghi nhận sự kiện vào lịch sử hệ thống.

---

# 7.6. FR – Nhóm 4: Quản lý chuyến đi

## FR_18 – Tạo chuyến đi

**BR liên quan:** BR_09

Sau khi tài xế chấp nhận yêu cầu, hệ thống phải tạo chuyến đi chính thức.

Thông tin chuyến bao gồm:

* Mã chuyến.
* Khách hàng.
* Tài xế.
* Phương tiện.
* Điểm đón.
* Điểm đến.
* Loại xe.
* Trạng thái chuyến.
* Thời gian tạo.

---

## FR_19 – Quản lý trạng thái chuyến

**BR liên quan:** BR_09

Hệ thống phải quản lý vòng đời chuyến.

Luồng trạng thái đề xuất:

```text
REQUESTED
    ↓
SEARCHING_DRIVER
    ↓
DRIVER_ASSIGNED
    ↓
DRIVER_ARRIVING
    ↓
DRIVER_ARRIVED
    ↓
IN_PROGRESS
    ↓
COMPLETED
```

Các trạng thái kết thúc khác:

```text
CANCELLED
FAILED
```

---

## FR_20 – Cập nhật trạng thái chuyến

**BR liên quan:** BR_09

Tài xế phải có khả năng cập nhật trạng thái chuyến theo từng giai đoạn.

Ví dụ:

* Đang di chuyển đến điểm đón.
* Đã đến điểm đón.
* Đang thực hiện chuyến.
* Đã hoàn thành chuyến.

---

## FR_21 – Cập nhật vị trí tài xế

**BR liên quan:** BR_10

Hệ thống phải tiếp nhận và cập nhật vị trí hiện tại của tài xế để phục vụ:

* Phân công.
* Theo dõi chuyến.
* Hiển thị vị trí cho khách hàng.

---

## FR_22 – Theo dõi chuyến theo thời gian thực

**BR liên quan:** BR_11

Khách hàng phải có khả năng xem:

* Trạng thái chuyến.
* Vị trí tài xế.
* Thông tin tài xế.
* Thông tin phương tiện.

---

## FR_23 – Xem thông tin tài xế và phương tiện

**BR liên quan:** BR_12

Sau khi chuyến được phân công, hệ thống phải cung cấp thông tin cần thiết cho khách hàng.

Ví dụ:

* Tên tài xế.
* Thông tin phương tiện.
* Biển số xe.
* Thông tin liên quan đến chuyến.

---

## FR_24 – Hoàn thành chuyến

**BR liên quan:** BR_09

Khi chuyến kết thúc, hệ thống phải:

1. Cập nhật trạng thái thành `COMPLETED`.
2. Ghi nhận thời gian hoàn thành.
3. Xác định số tiền cần thanh toán.
4. Chuyển sang quy trình thanh toán.
5. Cho phép khách hàng đánh giá tài xế.

---

## FR_25 – Xem lịch sử chuyến

**BR liên quan:** BR_13

Khách hàng phải có khả năng xem danh sách các chuyến đã thực hiện.

Thông tin có thể bao gồm:

* Mã chuyến.
* Thời gian.
* Điểm đón.
* Điểm đến.
* Tài xế.
* Loại xe.
* Giá trị chuyến.
* Trạng thái chuyến.

---

# 7.7. FR – Nhóm 5: Thanh toán

## FR_26 – Tính cước chuyến đi

**BR liên quan:** BR_14

Sau khi chuyến hoàn thành, hệ thống phải xác định số tiền khách hàng cần thanh toán.

> Công thức tính cước chi tiết chưa được xác nhận và cần được bổ sung sau khi có quy định nghiệp vụ chính thức.

---

## FR_27 – Lựa chọn phương thức thanh toán

**BR liên quan:** BR_15, BR_16

Khách hàng phải có khả năng lựa chọn:

* Tiền mặt.
* Thanh toán điện tử.

---

## FR_28 – Thanh toán tiền mặt

**BR liên quan:** BR_15

Hệ thống phải ghi nhận việc thanh toán bằng tiền mặt sau khi chuyến hoàn thành.

---

## FR_29 – Thanh toán điện tử

**BR liên quan:** BR_16

Hệ thống phải tích hợp với nhà cung cấp thanh toán bên ngoài.

Luồng:

```text
CAB System
    ↓
Payment Gateway
    ↓
Xử lý giao dịch
    ↓
Kết quả giao dịch
    ↓
CAB System
```

---

## FR_30 – Ghi nhận giao dịch

**BR liên quan:** BR_18

Hệ thống phải lưu thông tin cần thiết để quản lý giao dịch, chẳng hạn:

* Mã giao dịch.
* Mã chuyến.
* Số tiền.
* Phương thức thanh toán.
* Trạng thái giao dịch.
* Thời gian giao dịch.

Hệ thống không lưu thông tin thanh toán nhạy cảm.

---

## FR_31 – Xử lý thanh toán thất bại

**BR liên quan:** BR_19

Nếu thanh toán điện tử thất bại, hệ thống phải:

* Ghi nhận trạng thái thất bại.
* Thông báo cho khách hàng.
* Cho phép thực hiện lại giao dịch theo chính sách được xác định.

---

## FR_32 – Thông báo kết quả thanh toán

**BR liên quan:** BR_18

Hệ thống phải thông báo cho khách hàng:

* Thanh toán thành công.
* Thanh toán thất bại.
* Giao dịch đang xử lý nếu có.

---

# 7.8. FR – Nhóm 6: Thông báo

## FR_33 – Thông báo cho khách hàng

**BR liên quan:** BR_20

Hệ thống phải gửi thông báo tại các sự kiện:

* Đặt xe thành công.
* Tài xế nhận chuyến.
* Tài xế đang đến.
* Tài xế đã đến.
* Chuyến hoàn thành.
* Thanh toán thành công/thất bại.
* Không tìm được tài xế.

---

## FR_34 – Thông báo cho tài xế

**BR liên quan:** BR_21

Hệ thống phải gửi thông báo khi:

* Có chuyến mới.
* Chuyến bị thay đổi.
* Có sự kiện quan trọng liên quan đến chuyến.

---

# 7.9. FR – Nhóm 7: Đánh giá

## FR_35 – Đánh giá tài xế

**BR liên quan:** BR_22

Sau khi chuyến hoàn thành, khách hàng phải có khả năng đánh giá tài xế.

Chức năng bao gồm:

* Chọn mức đánh giá.
* Nhập nhận xét nếu có.
* Gửi đánh giá.
* Lưu đánh giá.

---

## FR_36 – Quản lý đánh giá

**BR liên quan:** BR_22, BR_30

Hệ thống phải lưu trữ đánh giá để phục vụ:

* Tra cứu.
* Thống kê.
* Đánh giá hiệu quả tài xế.

---

# 7.10. FR – Nhóm 8: Quản trị vận hành

## FR_37 – Quản lý khách hàng

**BR liên quan:** BR_23

Nhân viên vận hành phải có khả năng:

* Xem danh sách khách hàng.
* Tìm kiếm khách hàng.
* Xem thông tin khách hàng.
* Cập nhật thông tin theo quyền được cấp.
* Theo dõi lịch sử hoạt động cần thiết.

---

## FR_38 – Quản lý tài xế

**BR liên quan:** BR_23

Nhân viên vận hành phải có khả năng:

* Xem danh sách tài xế.
* Tìm kiếm tài xế.
* Xem hồ sơ tài xế.
* Quản lý trạng thái tài xế.
* Xem thông tin phương tiện.

---

## FR_39 – Quản lý phương tiện

**BR liên quan:** BR_23

Nhân viên vận hành phải có khả năng:

* Thêm phương tiện.
* Cập nhật phương tiện.
* Xem thông tin phương tiện.
* Quản lý trạng thái phương tiện.

---

## FR_40 – Giám sát chuyến đang diễn ra

**BR liên quan:** BR_24

Nhân viên vận hành phải có khả năng theo dõi:

* Các chuyến đang hoạt động.
* Trạng thái từng chuyến.
* Tài xế đang thực hiện chuyến.
* Vị trí tài xế nếu có dữ liệu.
* Các chuyến gặp vấn đề.

---

## FR_41 – Xử lý sự cố chuyến đi

**BR liên quan:** BR_25

Nhân viên vận hành phải có khả năng tiếp nhận và xử lý các chuyến gặp sự cố.

Ví dụ:

* Không tìm được tài xế.
* Tài xế không phản hồi.
* Thanh toán lỗi.
* Chuyến bị lỗi trạng thái.
* Vấn đề phát sinh trong quá trình thực hiện chuyến.

---

## FR_42 – Tra cứu lịch sử

**BR liên quan:** BR_26

Nhân viên vận hành phải có khả năng tra cứu:

* Lịch sử chuyến.
* Lịch sử giao dịch.
* Lịch sử trạng thái.
* Thông tin liên quan đến sự cố.

---

## FR_43 – Quản lý quyền truy cập

**BR liên quan:** BR_27

Hệ thống phải hỗ trợ phân quyền theo vai trò.

Các vai trò chính:

```text
Customer
Driver
Operations Staff
Administrator
```

Mỗi vai trò chỉ được phép truy cập các chức năng tương ứng.

---

# 7.11. FR – Nhóm 9: Báo cáo

## FR_44 – Báo cáo số lượng chuyến

**BR liên quan:** BR_29

Hệ thống phải cung cấp thống kê:

* Tổng số chuyến.
* Số chuyến hoàn thành.
* Số chuyến hủy.
* Số chuyến thất bại.

---

## FR_45 – Báo cáo doanh thu

**BR liên quan:** BR_29

Hệ thống phải cung cấp báo cáo doanh thu theo khoảng thời gian.

Có thể hỗ trợ:

* Theo ngày.
* Theo tuần.
* Theo tháng.
* Theo khoảng thời gian tùy chọn.

---

## FR_46 – Báo cáo tỷ lệ hoàn thành và hủy

**BR liên quan:** BR_29

Hệ thống phải tính toán và hiển thị:

* Tỷ lệ hoàn thành.
* Tỷ lệ hủy.
* Tỷ lệ thất bại.

---

## FR_47 – Báo cáo hiệu quả tài xế

**BR liên quan:** BR_30

Hệ thống phải hỗ trợ thống kê hiệu quả tài xế dựa trên dữ liệu nghiệp vụ.

Có thể bao gồm:

* Số chuyến nhận.
* Số chuyến hoàn thành.
* Số chuyến bị từ chối.
* Tỷ lệ hoàn thành.
* Điểm đánh giá trung bình.

---

# 7.12. FR – Nhóm 10: Audit và bảo mật chức năng

## FR_48 – Xác thực người dùng

**BR liên quan:** BR_01, BR_27, BR_35

Hệ thống phải xác thực người dùng trước khi cho phép truy cập các chức năng yêu cầu đăng nhập.

---

## FR_49 – Kiểm soát quyền truy cập

**BR liên quan:** BR_27

Hệ thống phải kiểm tra quyền của người dùng trước khi thực hiện các thao tác quản trị hoặc thao tác nhạy cảm.

---

## FR_50 – Ghi nhận Audit Log

**BR liên quan:** BR_28

Hệ thống phải ghi nhận các thao tác quan trọng.

Thông tin Audit Log có thể gồm:

* Người thực hiện.
* Thời gian.
* Chức năng.
* Hành động.
* Đối tượng bị tác động.
* Kết quả thao tác.

---

## FR_51 – Bảo vệ dữ liệu

**BR liên quan:** BR_35

Hệ thống phải áp dụng các cơ chế bảo vệ đối với:

* Thông tin cá nhân.
* Thông tin tài khoản.
* Dữ liệu vị trí.
* Dữ liệu giao dịch.
* Dữ liệu vận hành.

---

# 7.13. Tổng hợp Functional Requirement

| Nhóm               | Mã FR         | Chức năng                                                     |
| ------------------ | ------------- | ------------------------------------------------------------- |
| Quản lý tài khoản  | FR_01 – FR_04 | Đăng ký, đăng nhập, quản lý thông tin, đăng xuất              |
| Quản lý tài xế     | FR_05 – FR_09 | Hồ sơ, phương tiện, trạng thái, nhận/chấp nhận/từ chối chuyến |
| Đặt xe & phân công | FR_10 – FR_17 | Đặt xe, tìm tài xế, phân công và xử lý từ chối/không phản hồi |
| Quản lý chuyến     | FR_18 – FR_25 | Tạo, cập nhật, theo dõi và lưu lịch sử chuyến                 |
| Thanh toán         | FR_26 – FR_32 | Tính cước, thanh toán, giao dịch và xử lý lỗi                 |
| Thông báo          | FR_33 – FR_34 | Thông báo cho khách hàng và tài xế                            |
| Đánh giá           | FR_35 – FR_36 | Đánh giá và quản lý đánh giá                                  |
| Quản trị           | FR_37 – FR_43 | Quản lý dữ liệu, giám sát, xử lý sự cố, phân quyền            |
| Báo cáo            | FR_44 – FR_47 | Báo cáo chuyến, doanh thu và hiệu quả tài xế                  |
| Bảo mật & Audit    | FR_48 – FR_51 | Xác thực, phân quyền, audit log và bảo vệ dữ liệu             |

Tổng cộng:

**51 Functional Requirement (FR)**

---

# 7.14. Ma trận truy vết BR → FR

| Business Requirement | Functional Requirement                              |
| -------------------- | --------------------------------------------------- |
| BR_01                | FR_01, FR_02, FR_03, FR_04, FR_48                   |
| BR_02                | FR_10, FR_12                                        |
| BR_03                | FR_11                                               |
| BR_04                | FR_13, FR_14                                        |
| BR_05                | FR_15, FR_16                                        |
| BR_06                | FR_17, FR_33                                        |
| BR_07                | FR_05, FR_07                                        |
| BR_08                | FR_08, FR_09                                        |
| BR_09                | FR_18, FR_19, FR_20, FR_24                          |
| BR_10                | FR_21                                               |
| BR_11                | FR_22                                               |
| BR_12                | FR_23                                               |
| BR_13                | FR_25                                               |
| BR_14                | FR_26                                               |
| BR_15                | FR_27, FR_28                                        |
| BR_16                | FR_27, FR_29                                        |
| BR_17                | FR_30, FR_51                                        |
| BR_18                | FR_30, FR_32                                        |
| BR_19                | FR_31                                               |
| BR_20                | FR_33                                               |
| BR_21                | FR_34                                               |
| BR_22                | FR_35, FR_36                                        |
| BR_23                | FR_37, FR_38, FR_39                                 |
| BR_24                | FR_40                                               |
| BR_25                | FR_41                                               |
| BR_26                | FR_42                                               |
| BR_27                | FR_43, FR_49                                        |
| BR_28                | FR_50                                               |
| BR_29                | FR_44, FR_45, FR_46                                 |
| BR_30                | FR_47                                               |
| BR_31                | Yêu cầu phi chức năng – Performance/Scalability     |
| BR_32                | Yêu cầu kiến trúc – Modularity/Scalability          |
| BR_33                | Yêu cầu phi chức năng – Reliability/Fault Isolation |
| BR_34                | Yêu cầu kiến trúc – Extensibility                   |
| BR_35                | FR_48, FR_49, FR_51                                 |

---

# 7.15. Phân biệt Functional Requirement và Non-Functional Requirement

Sau khi phân rã, cần lưu ý rằng không phải tất cả BR đều chuyển trực tiếp thành FR.

### Functional Requirement

Mô tả:

> **Hệ thống phải làm gì?**

Ví dụ:

* Đăng nhập.
* Đặt xe.
* Tìm tài xế.
* Thanh toán.
* Gửi thông báo.
* Tạo báo cáo.
* Quản lý người dùng.

### Non-Functional Requirement

Mô tả:

> **Hệ thống phải hoạt động như thế nào?**

Ví dụ:

* Thời gian phản hồi.
* Khả năng chịu tải.
* Khả năng mở rộng.
* Tính sẵn sàng.
* Khả năng chịu lỗi.
* Bảo mật.
* Khả năng phục hồi.

Do đó, các **BR_31, BR_32, BR_33 và BR_34** không nên cố ép thành các chức năng nghiệp vụ thông thường. Các yêu cầu này sẽ được phân tích sâu hơn ở bước **Non-Functional Requirements và Architecture Requirements**.

---

# 7.16. Liên kết Business Process → Functional Requirement

| Business Process                      | Functional Requirement chính |
| ------------------------------------- | ---------------------------- |
| **BP01 – Quản lý tài khoản**          | FR_01 → FR_04, FR_48, FR_49  |
| **BP02 – Đặt xe và phân công tài xế** | FR_10 → FR_17                |
| **BP03 – Thực hiện chuyến đi**        | FR_18 → FR_25                |
| **BP04 – Thanh toán**                 | FR_26 → FR_32                |
| **BP05 – Thông báo**                  | FR_33 → FR_34                |
| **BP06 – Quản trị vận hành**          | FR_37 → FR_43                |
| **BP07 – Báo cáo**                    | FR_44 → FR_47                |
| **BP08 – Đánh giá tài xế**            | FR_35 → FR_36                |
| **BP09 – Audit & bảo mật**            | FR_48 → FR_51                |

---

# 7.17. Kết quả của Bước 7

Sau Bước 7, các yêu cầu nghiệp vụ của CAB System đã được chuyển từ mức **Business Requirement** sang các chức năng cụ thể của hệ thống.

Luồng phân tích hiện tại:

```text
Business Goal
      ↓
Business Requirement
      ↓
Business Process
      ↓
Functional Requirement
      ↓
Use Case
      ↓
User Story / Acceptance Criteria
      ↓
Thiết kế hệ thống
```

Các chức năng cốt lõi của CAB System hiện được xác định gồm:

**Quản lý tài khoản**
→ **Đặt xe**
→ **Tìm kiếm & phân công tài xế**
→ **Thực hiện chuyến**
→ **Theo dõi chuyến**
→ **Thanh toán**
→ **Thông báo**
→ **Đánh giá**
→ **Quản trị vận hành**
→ **Báo cáo**
→ **Bảo mật & Audit**

Đây là cơ sở để thực hiện bước tiếp theo: **phân rã Functional Requirement thành Use Case và xác định Actor – Use Case – quan hệ giữa các Use Case**.
