# AI Support Log

### 1. AI đã giúp tôi ở đâu?
* Gợi ý cấu trúc 5 bước logic chuẩn chỉnh theo khung bài lab: Core Action → Natural Cadence → Metric System & Retention → Product Loop → Event Tracking.
* Hỗ trợ brainstorm các ý tưởng dự án mới, sáng tạo và gần gũi ngoài các chủ đề mặc định trong đề bài.
* Hỗ trợ chuẩn hóa định dạng tên event dạng `object_action` và xây dựng 2 tiêu chí nghiệm thu (Acceptance Criteria) chặt chẽ cho sự kiện export CV.

### 2. AI sai, hời hợt hoặc đề xuất metric sai nature ở đâu?
* Ban đầu AI có xu hướng đề xuất các chỉ số Retention theo chu kỳ Daily (DAU) hoặc dựa vào notification nhắc nhở nộp đơn hàng ngày.
* Điều này vi phạm nguyên tắc "Nature trước, Nurture sau" vì người tìm việc không nộp đơn dàn trải mỗi ngày mà nộp theo từng đợt chiến dịch (Campaign) khi tìm thấy job phù hợp.

### 3. Tôi đã tự sửa hoặc quyết định lại điều gì?
* **Quyết định chuyển đổi chủ đề sang MatchCraft AI:** Thay vì làm đề tài B2B đặc thù khó kiểm chứng, tôi chọn bài toán may đo CV theo JD — một use case có tính lặp lại tự nhiên và giá trị tức thì rất rõ ràng.
* **Tự định nghĩa Retention theo Campaign Bracket:** Xác lập khung đo lường Retention theo chu kỳ chiến dịch 6 tuần ($W_1 \rightarrow W_6$) với phân khúc *Active Job Seeker*, không ép dùng chung khung thời gian cứng nhắc.
* **Xây dựng Counter-metric chống bốc phét (Hallucination Rate):** Đưa vào counter-metric kiểm soát việc AI tự ý bịa thêm kinh nghiệm để đảm bảo tính trung thực của hồ sơ ứng viên.
