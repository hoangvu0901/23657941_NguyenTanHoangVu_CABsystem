# Bước 1: Phân tích ngữ cảnh nghiệp vụ – Dự án CAB System

## 1. Vấn đề nghiệp vụ khách hàng muốn giải quyết

Công ty ABC đang vận hành dịch vụ đặt xe theo cách thủ công và phân mảnh. Việc phân công tài xế chủ yếu do con người thực hiện thủ công, dẫn đến chậm trễ và khó tối ưu khi số lượng chuyến tăng lên. Khách hàng không thể theo dõi trạng thái chuyến đi của mình, gây ra trải nghiệm kém và làm tăng số lượng cuộc gọi hỗ trợ đến tổng đài. Thông tin thanh toán chưa được quản lý tập trung, khiến việc đối soát và làm báo cáo doanh thu gặp khó khăn, đồng thời tiềm ẩn rủi ro sai lệch dữ liệu. Và quan trọng nhất, hệ thống hiện tại (tổng đài kết hợp một ứng dụng đơn giản) không đủ khả năng mở rộng để phục vụ quy mô lớn hơn hoặc bổ sung tính năng mới trong tương lai.

Nói cách khác, đây không phải là bài toán "chưa có hệ thống" mà là bài toán hệ thống hiện tại không đủ khả năng tự động hóa và mở rộng để đáp ứng tốc độ tăng trưởng của doanh nghiệp.

## 2. Tại sao hệ thống hiện tại không đáp ứng được

Dựa trên mô tả trong tài liệu, có thể suy luận một số nguyên nhân gốc rễ — đây là những giả định có căn cứ mà BA cần xác nhận lại với khách hàng ở bước làm rõ yêu cầu:

Khả năng cao kiến trúc hệ thống cũ chưa phù hợp cho việc mở rộng, phụ thuộc nhiều vào xử lý thủ công của con người (tổng đài) thay vì có cơ chế tự động ghép nối cung–cầu giữa tài xế và khách hàng. Ứng dụng hiện tại được mô tả là "đơn giản", nên nhiều khả năng chưa có cơ chế cập nhật trạng thái hoặc vị trí theo thời gian thực. Ngoài ra, dữ liệu thanh toán, lịch sử chuyến đi, thông tin tài xế có thể đang nằm rời rạc ở nhiều nơi khác nhau thay vì được quản lý tập trung. Cuối cùng, yêu cầu phi chức năng trong tài liệu cho thấy hệ thống cũ nhiều khả năng là một khối duy nhất (monolithic) — một lỗi ở chức năng thanh toán có thể làm sập toàn bộ hệ thống, điều mà doanh nghiệp hiện đang muốn tránh ở hệ thống mới.

> Lưu ý: tài liệu chưa nêu rõ công nghệ hay kiến trúc của hệ thống cũ, nên đây cần được đưa vào danh sách câu hỏi làm rõ với khách hàng.

## 3. Ai sử dụng hệ thống

Tài liệu xác định ba nhóm người dùng trực tiếp: khách hàng (người đặt xe, theo dõi chuyến, thanh toán, đánh giá tài xế), tài xế (người nhận chuyến, cập nhật trạng thái chuyến đi, cập nhật thông tin phương tiện và vị trí), và nhân viên vận hành (người quản trị hệ thống, giám sát chuyến đang diễn ra, xử lý sự cố, tra cứu lịch sử giao dịch).

Bên cạnh đó còn có các tác nhân gián tiếp: nhà cung cấp thanh toán bên ngoài (xử lý giao dịch điện tử, hệ thống CAB không lưu thông tin nhạy cảm), ban lãnh đạo (người tiêu thụ các báo cáo về doanh thu, tỷ lệ hoàn thành, tỷ lệ hủy chuyến), và hệ thống thông báo (có thể là thành phần nội bộ nhưng cần có khả năng mở rộng thêm kênh mới trong tương lai mà không ảnh hưởng đến toàn hệ thống).

## 4. Giá trị hệ thống mang lại sau khi triển khai

Về mặt vận hành, hệ thống mới giúp tự động hóa việc tìm và phân công tài xế, giảm phụ thuộc vào xử lý thủ công và tăng tốc độ xử lý yêu cầu đặt xe. Về trải nghiệm khách hàng, việc theo dõi chuyến đi theo thời gian thực, minh bạch trạng thái, lưu lịch sử và cho phép đánh giá tài xế sẽ giúp tăng sự hài lòng và giữ chân khách hàng. Về phía tài xế, cơ chế nhận/từ chối chuyến rõ ràng cùng khả năng cập nhật trạng thái linh hoạt sẽ cải thiện hiệu suất làm việc.

Về mặt tài chính, việc quản lý thanh toán tập trung và tích hợp với cổng thanh toán bên ngoài (mà không lưu dữ liệu nhạy cảm trong hệ thống CAB) giúp giảm rủi ro bảo mật và dễ dàng đối soát hơn. Về mặt quản trị, các báo cáo về doanh thu, tỷ lệ hoàn thành/hủy chuyến, hiệu quả hoạt động của tài xế sẽ hỗ trợ ban lãnh đạo ra quyết định dựa trên dữ liệu thay vì cảm tính.

Về lâu dài, kiến trúc hệ thống được thiết kế để cho phép mở rộng độc lập giữa các thành phần, triển khai tính năng mới từng phần, và bổ sung dịch vụ, phương thức thanh toán hay kênh thông báo mới mà không cần xây dựng lại toàn bộ ứng dụng — điều này giúp doanh nghiệp giảm chi phí thay đổi trong tương lai. Đồng thời, việc cô lập lỗi giữa các thành phần (ví dụ lỗi thanh toán không làm sập cả hệ thống đặt xe) sẽ giúp tăng độ tin cậy và ổn định của hệ thống, đặc biệt vào những thời điểm nhu cầu tăng cao.

---

**Nhận định tổng quát:** Đây là bài toán chuyển đổi từ mô hình vận hành thủ công/bán tự động sang một nền tảng số hóa toàn diện, có khả năng mở rộng, với ba luồng nghiệp vụ cốt lõi: ghép nối tài xế–khách hàng, quản lý vòng đời chuyến đi, và thanh toán/báo cáo. Nhiều chi tiết nghiệp vụ quan trọng như cách tính cước, tiêu chí ưu tiên tài xế, thời gian tài xế phải phản hồi, chính sách hủy chuyến, cách xử lý khi mất kết nối mạng, và thời gian lưu trữ dữ liệu vẫn chưa được chốt — đây sẽ là trọng tâm chính của bước làm rõ yêu cầu tiếp theo.

---

# Xác định Stakeholder (Các bên liên quan)

## Bảng 1: Danh sách Stakeholder và Vai trò

| STT | Stakeholder | Vai trò |
|---|---|---|
| 1 | Khách hàng (Customer/Passenger) | Đăng ký, đặt xe, theo dõi chuyến, thanh toán, đánh giá tài xế sau chuyến |
| 2 | Tài xế (Driver) | Nhận/từ chối chuyến, cập nhật trạng thái chuyến đi, cập nhật vị trí và thông tin phương tiện |
| 3 | Nhân viên vận hành (Operations Staff) | Quản trị khách hàng/tài xế/phương tiện, giám sát chuyến đang diễn ra, xử lý sự cố, tra cứu lịch sử |
| 4 | Ban giám đốc / Ban lãnh đạo (Executive Sponsor) | Phê duyệt phạm vi dự án, ra quyết định đầu tư, tiêu thụ báo cáo doanh thu và hiệu quả vận hành |
| 5 | Nhà cung cấp thanh toán bên ngoài (Payment Gateway Provider) | Xử lý giao dịch thanh toán điện tử, đặt ràng buộc kỹ thuật/bảo mật tích hợp |
| 6 | Đội ngũ phát triển (Development Team, gồm cả BA) | Phân tích yêu cầu, thiết kế và xây dựng hệ thống trong 7 tuần |
| 7 | Bộ phận chăm sóc khách hàng (Customer Support) — *cần xác nhận* | Tiếp nhận và xử lý khiếu nại liên quan đến chuyến đi/thanh toán |
| 8 | Bộ phận tài chính/kế toán (Finance/Accounting) — *cần xác nhận* | Đối soát giao dịch, sử dụng báo cáo doanh thu |
| 9 | Cơ quan quản lý/pháp lý (Regulatory Body) — *cần xác nhận* | Đặt ràng buộc pháp lý về bảo vệ dữ liệu cá nhân, vận tải hành khách |

## Bảng 2: Ma trận Stakeholder (Power/Interest)

| Nhóm | Quyền lực | Quan tâm | Stakeholder | Chiến lược |
|---|---|---|---|---|
| Quản lý chặt chẽ | Cao | Cao | Ban giám đốc, Nhân viên vận hành, Đội ngũ phát triển (BA) | Trao đổi thường xuyên, thu thập yêu cầu kỹ, báo cáo tiến độ liên tục |
| Giữ hài lòng | Cao | Thấp | Cơ quan quản lý/pháp lý, Nhà cung cấp thanh toán | Tuân thủ ràng buộc, cập nhật khi có thay đổi liên quan |
| Thông báo thường xuyên | Thấp | Cao | Khách hàng, Tài xế | Lắng nghe kỹ khi thu thập yêu cầu, cập nhật tiến độ định kỳ |
| Giám sát | Thấp | Thấp | Bộ phận CSKH, Bộ phận tài chính/kế toán | Theo dõi tối thiểu, liên hệ khi cần |

 | Nhóm               | Mức ảnh hưởng | Mức quan tâm | Cách quản lý                                                 |
| ------------------ | ------------- | ------------ | ------------------------------------------------------------ |
| **Manage Closely** | Cao           | Cao          | Làm việc thường xuyên, lấy ý kiến và phối hợp chặt chẽ       |
| **Keep Satisfied** | Cao           | Thấp         | Đảm bảo nhu cầu quan trọng được đáp ứng, duy trì sự hài lòng |
| **Keep Informed**  | Thấp          | Cao          | Cập nhật thông tin thường xuyên, thu thập phản hồi           |
| **Monitor**        | Thấp          | Thấp         | Theo dõi và chỉ phối hợp khi cần thiết                       |

# Bước 3: Xác định Business Goals (BG) – Dự án CAB System

| Mã | Business Goal | Mô tả |
|---|---|---|
| BG01 | Tự động hóa tìm kiếm và phân công tài xế | Thay thế phân công thủ công bằng cơ chế tự động dựa trên vị trí, trạng thái sẵn sàng và tiêu chí vận hành; có cơ chế dự phòng khi tài xế không phản hồi/từ chối |
| BG02 | Theo dõi chuyến đi theo thời gian thực | Khách hàng biết được trạng thái tìm tài xế, tài xế nhận chuyến, thời gian dự kiến đến và trạng thái hiện tại của chuyến đi |
| BG03 | Hỗ trợ thanh toán đa dạng, quản lý tập trung | Thanh toán tiền mặt/điện tử, tích hợp cổng thanh toán ngoài, không lưu thông tin nhạy cảm, dữ liệu giao dịch quản lý tập trung |
| BG04 | Thông báo linh hoạt, đa kênh | Gửi thông báo theo từng mốc vòng đời chuyến đi; kiến trúc cho phép bổ sung kênh thông báo mới trong tương lai |
| BG05 | Công cụ quản trị vận hành hiệu quả | Quản lý khách hàng/tài xế/phương tiện/chuyến đi, giám sát, xử lý sự cố, tra cứu lịch sử; có phân quyền cho thao tác nhạy cảm |
| BG06 | Báo cáo hỗ trợ ra quyết định | Báo cáo số lượng chuyến, doanh thu, tỷ lệ hoàn thành/hủy, hiệu quả tài xế cho ban lãnh đạo |
| BG07 | Khả năng mở rộng quy mô người dùng | Hệ thống phục vụ được số lượng lớn khách hàng và tài xế, đáp ứng tăng trưởng dài hạn |
| BG08 | Ổn định và chịu lỗi độc lập | Các thành phần mở rộng độc lập, cô lập lỗi — lỗi thanh toán/thông báo không làm sập toàn hệ thống, đặc biệt giờ cao điểm |
| BG09 | An toàn và bảo mật thông tin | Xác thực người dùng, kiểm soát quyền truy cập, bảo vệ dữ liệu cá nhân/vị trí/giao dịch, lưu vết thao tác quan trọng |
| BG10 | Kiến trúc linh hoạt cho phát triển dài hạn | Dễ bổ sung dịch vụ/thanh toán/kênh thông báo mới, triển khai từng phần mà không ảnh hưởng hệ thống đang chạy |

---

**Nhận xét:** BG01–BG06 là mục tiêu nghiệp vụ cốt lõi (chức năng), BG07–BG10 là mục tiêu kiến trúc/kỹ thuật nhưng xuất phát từ nhu cầu kinh doanh. Với thời hạn 7 tuần, cần xác nhận lại mức độ ưu tiên giữa các BG để xác định phạm vi MVP.
# Bước 4: Xác định Phạm vi (Scope) – Dự án CAB System

## 4.1. In Scope (Trong phạm vi)

| Nhóm | Nội dung trong phạm vi |
|---|---|
| Khách hàng | Đăng ký/đăng nhập tài khoản, cập nhật thông tin cá nhân, nhập điểm đón/điểm đến, chọn loại xe, gửi yêu cầu đặt xe, theo dõi trạng thái chuyến đi thời gian thực, xem lịch sử chuyến, xem số tiền phải trả, đánh giá tài xế sau chuyến |
| Tài xế | Đăng ký/được tạo tài khoản bởi nhân viên vận hành, cập nhật hồ sơ và thông tin phương tiện, chuyển trạng thái sẵn sàng nhận chuyến, nhận thông báo chuyến mới, chấp nhận/từ chối chuyến, cập nhật trạng thái chuyến đi (đến điểm đón, đón khách, đang di chuyển, hoàn thành), cập nhật vị trí |
| Tìm kiếm & phân công tài xế | Xác định tài xế phù hợp theo vị trí và trạng thái sẵn sàng, cơ chế chuyển sang tài xế khác khi tài xế đầu tiên không phản hồi/từ chối, thông báo cho khách hàng khi không tìm được tài xế |
| Thanh toán & tính cước | Tính cước sau khi hoàn thành chuyến, hỗ trợ thanh toán tiền mặt và điện tử, tích hợp với một nhà cung cấp thanh toán bên ngoài (không lưu thông tin nhạy cảm), thông báo và cho xử lý lại khi giao dịch điện tử thất bại |
| Thông báo | Thông báo cho khách hàng ở các mốc: tiếp nhận yêu cầu, tài xế nhận chuyến, tài xế đến điểm đón, hoàn thành chuyến, kết quả thanh toán. Thông báo cho tài xế về chuyến mới hoặc thay đổi liên quan |
| Quản trị vận hành | Giao diện quản trị: quản lý khách hàng, tài xế, phương tiện, chuyến đi; xem chuyến đang diễn ra; xử lý chuyến bị lỗi; tra cứu lịch sử giao dịch; phân quyền cho thao tác nhạy cảm |
| Báo cáo | Báo cáo số lượng chuyến, doanh thu, tỷ lệ hoàn thành, tỷ lệ hủy, hiệu quả hoạt động của tài xế |
| Phi chức năng nền tảng | Xác thực người dùng, kiểm soát quyền truy cập cho thao tác quản trị, lưu vết (audit log) thao tác quan trọng, kiến trúc mở rộng độc lập và triển khai từng phần |

## 4.2. Out of Scope (Ngoài phạm vi – ở giai đoạn này)

| Hạng mục | Lý do đưa ra ngoài phạm vi |
|---|---|
| Cách tính cước chi tiết theo từng loại dịch vụ | Chưa chốt — cần làm rõ với khách hàng |
| Tiêu chí ưu tiên tài xế cụ thể (ngoài vị trí, trạng thái sẵn sàng) | Chưa chốt |
| Thời gian tài xế phải phản hồi trước khi chuyển tài xế khác | Chưa chốt |
| Chính sách hủy chuyến (ai được hủy, phí hủy, thời điểm) | Chưa chốt |
| Cơ chế xử lý khi mất kết nối mạng | Chưa chốt |
| Thời gian lưu trữ dữ liệu | Chưa chốt |
| Bổ sung loại dịch vụ/phương thức thanh toán mới | Định hướng tương lai, không bắt buộc ở bản đầu |
| Đa ngôn ngữ, đa tiền tệ | Không được đề cập trong tài liệu |
| Ứng dụng di động native riêng cho iOS/Android | Chưa nêu rõ kênh triển khai, cần xác nhận |
| Tích hợp bản đồ/định tuyến chi tiết (routing tối ưu) | Cần xác nhận mức độ chi tiết |
| Khuyến mãi, mã giảm giá, chương trình khách hàng thân thiết | Không được đề cập |
| Quy định pháp lý theo từng khu vực/quốc gia | Cần xác nhận với bên pháp lý |

---

**Nhận xét:** Phần In Scope bám sát các Business Goal cốt lõi (BG01–BG06) và một phần yêu cầu phi chức năng nền tảng (BG08, BG09). Phần Out of Scope chủ yếu là những điểm tài liệu nêu rõ là "chưa chốt" — đây chính là danh sách ưu tiên cho buổi làm rõ yêu cầu (requirement elicitation) với khách hàng trước khi đội phát triển bắt đầu thiết kế.
