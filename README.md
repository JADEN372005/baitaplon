Dự án: Ứng dụng Theo dõi Thói quen "StreakFlow"
Phiên bản: 1.0

1. Giới thiệu
1.1. Mục đích
Tài liệu này mô tả chi tiết các yêu cầu chức năng và phi chức năng cho phiên bản đầu tiên (MVP - Minimum Viable Product) của ứng dụng di động "StreakFlow". Mục đích của tài liệu là cung cấp một nền tảng chung, rõ ràng cho đội ngũ phát triển, thiết kế UI/UX và kiểm thử phần mềm để xây dựng sản phẩm đúng với tầm nhìn đã đề ra.

1.2. Tổng quan về Sản phẩm
"StreakFlow" là một ứng dụng di động giúp người dùng xây dựng và duy trì các thói quen tích cực bằng cách theo dõi chuỗi (streak) ngày thực hiện liên tiếp. Ứng dụng tập trung vào sự đơn giản, trải nghiệm người dùng tạo động lực và cung cấp các thống kê trực quan để khuyến khích người dùng gắn bó với mục tiêu của mình.

Đối tượng mục tiêu là những cá nhân mong muốn cải thiện bản thân, từ sinh viên muốn duy trì thói quen học tập, đến nhân viên văn phòng muốn tập thể dục đều đặn hay bất kỳ ai muốn hình thành một lối sống lành mạnh hơn.

1.3. Phạm vi Dự án
Phiên bản 1.0 của ứng dụng sẽ tập trung vào các chức năng cốt lõi sau:

Tạo và quản lý thói quen.

Theo dõi chuỗi ngày thực hiện (streak).

Hệ thống nhắc nhở.

Thống kê tiến độ cơ bản.

Đồng bộ hóa dữ liệu qua tài khoản người dùng.

Các tính năng như chia sẻ mạng xã hội, tạo nhóm thử thách, khoá học... sẽ được xem xét cho các phiên bản sau.

2. Yêu cầu Chức năng (Functional Requirements)
FR1: Quản lý Thói quen (Habit Management)
FR1.1: Tạo Thói quen mới:

Người dùng có thể tạo một thói quen mới bằng cách nhập các thông tin sau:

Tên thói quen (bắt buộc, ví dụ: "Đọc sách 30 phút").

Mô tả (không bắt buộc).

Chọn biểu tượng (icon) và màu sắc để dễ dàng nhận diện.

Thiết lập tần suất (ví dụ: Hàng ngày, hoặc các ngày cụ thể trong tuần như T2-T4-T6).

FR1.2: Xem Danh sách Thói quen:

Màn hình chính phải hiển thị danh sách tất cả các thói quen người dùng đã tạo cho ngày hôm nay.

Mỗi thói quen trong danh sách phải hiển thị: Tên, biểu tượng và số ngày streak hiện tại.

FR1.3: Chỉnh sửa Thói quen:

Người dùng có thể chỉnh sửa tất cả thông tin của một thói quen đã tạo.

FR1.4: Xóa Thói quen:

Người dùng có thể xóa một thói quen. Hệ thống phải yêu cầu xác nhận trước khi xóa vĩnh viễn.

FR2: Theo dõi Tiến độ (Progress Tracking)
FR2.1: Đánh dấu Hoàn thành (Check-in):

Người dùng có thể đánh dấu một thói quen là "đã hoàn thành" cho ngày hiện tại bằng một thao tác đơn giản (ví dụ: nhấn vào checkbox hoặc nút).

Khi hoàn thành, hệ thống sẽ cập nhật bộ đếm streak.

Người dùng có thể bỏ đánh dấu hoàn thành trong cùng một ngày.

FR2.2: Logic đếm Chuỗi (Streak Logic):

Nếu người dùng hoàn thành thói quen vào ngày N và ngày N-1, chuỗi sẽ tăng lên.

Nếu người dùng không hoàn thành thói quen vào ngày N, chuỗi sẽ bị ngắt và quay về 0 vào ngày N+1.

FR2.3: Lịch sử Thực hiện:

Người dùng có thể xem chi tiết một thói quen và thấy một giao diện lịch.

Lịch phải hiển thị các ngày đã hoàn thành (được đánh dấu màu), ngày bỏ lỡ và ngày hiện tại.

FR3: Thông báo và Nhắc nhở (Notifications & Reminders)
FR3.1: Cài đặt Nhắc nhở:

Khi tạo hoặc chỉnh sửa thói quen, người dùng có thể bật/tắt và cài đặt thời gian nhắc nhở cho thói quen đó.

FR3.2: Gửi Thông báo Đẩy (Push Notification):

Hệ thống phải tự động gửi thông báo đẩy đến điện thoại của người dùng vào thời gian đã cài đặt để nhắc nhở họ thực hiện thói quen.

Nội dung thông báo phải thân thiện và mang tính động viên (ví dụ: "Đã đến giờ đọc sách rồi! Tiếp tục chuỗi ngày tuyệt vời của bạn nhé!").

FR4: Thống kê và Báo cáo (Statistics & Reporting)
FR4.1: Thống kê Chi tiết Thói quen:

Khi xem chi tiết một thói quen, người dùng có thể thấy các thông số sau:

Chuỗi hiện tại (Current Streak).

Chuỗi dài nhất (Longest Streak).

Tổng số lần hoàn thành.

Tỷ lệ hoàn thành (%).

FR5: Quản lý Người dùng (User Account)
FR5.1: Đăng ký/Đăng nhập:

Người dùng có thể tạo tài khoản bằng Email và mật khẩu.

Hỗ trợ đăng nhập nhanh qua tài khoản Google hoặc Apple để tăng tính tiện lợi.

FR5.2: Đồng bộ hóa Dữ liệu:

Tất cả dữ liệu về thói quen và tiến độ của người dùng phải được đồng bộ hóa trên đám mây.

Điều này cho phép người dùng đăng nhập trên nhiều thiết bị mà không bị mất dữ liệu.

FR5.3: Quản lý Tài khoản:

Người dùng có thể thay đổi mật khẩu và xóa tài khoản của mình.
