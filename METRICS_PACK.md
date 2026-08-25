# 00 — Dự án, Persona, Core Job

* **Dự án:** **MatchCraft AI** — Trợ lý AI May đo CV & Tối ưu hóa hồ sơ ứng tuyển theo từng Mô tả công việc (AI Tailored Resume & ATS Optimization Agent).
* **Persona:** **Ứng viên đang tích cực tìm việc / Người chuyển ngành (Active Job Seeker / Career Switcher)**.
* **Core job:** *"Tôi cần tùy biến hồ sơ ứng tuyển (CV & Cover Letter) khớp chuẩn xác với từng bản mô tả công việc (JD) trong vòng dưới 3 phút để vượt qua hệ thống lọc tự động (ATS) và tăng tối đa tỷ lệ được gọi phỏng vấn mà không phải mất hàng giờ chỉnh sửa thủ công từng câu chữ cho mỗi công ty."*

---

# 01 — Core Action Card & Tự Kiểm 5 Tiêu Chí

### 1. Bảng phân biệt 4 khái niệm
| Khái niệm | Định nghĩa | Áp dụng vào MatchCraft AI |
| :--- | :--- | :--- |
| **Core job** | User đang cố hoàn thành việc gì? | Tùy biến CV khớp với yêu cầu của nhà tuyển dụng để nộp đơn ứng tuyển hiệu quả. |
| **Core action** | User làm gì trong sản phẩm để tiến tới giá trị? | Rà soát gợi ý của AI và **Xuất bản/Tải xuống bản CV đã được may đo theo JD (Export Tailored Resume)**. |
| **Core value** | User nhận được lợi ích gì? | Sở hữu bản CV có độ khớp từ khóa ATS cao ($\ge 85\%$), làm nổi bật kinh nghiệm phù hợp nhất chỉ sau 2 phút. |
| **Core value event** | Sự kiện nào chứng minh value đã xảy ra? | `tailored_resume_exported` |

### 2. Thẻ Core Action Card
| Thành phần | Chi tiết |
| :--- | :--- |
| **Target user** | Ứng viên đang tìm việc (Active Job Seeker). |
| **Core job** | Tạo ra bản CV may đo chuẩn ATS cho từng vị trí tuyển dụng cụ thể để sẵn sàng nộp đơn. |
| **Core action** | Dán JD, duyệt các gợi ý chỉnh sửa từ khóa/bullet points của AI và bấm **Tải xuống bản CV đã may đo (Export Tailored Resume)**. |
| **Object** | Bản CV cá nhân hóa gắn liền với một tin tuyển dụng (Job Description) cụ thể. |
| **Preconditions** | Người dùng đã upload CV gốc (Master CV) và dán link/nội dung JD mục tiêu; AI đã phân tích khoảng trống kỹ năng và đề xuất tối ưu. |
| **Completion rule** | Người dùng bấm "Tải xuống CV (PDF/DOCX)", hệ thống render thành công và file được tải về máy của người dùng. |
| **Core value** | CV chuẩn ATS, ngôn từ chuyên nghiệp, khớp kỹ năng yêu cầu trong thời gian ngắn nhất. |
| **Evidence of value** | File CV định dạng PDF/DOCX được tải về máy thành công; bản ghi được lưu tự động vào bảng theo dõi ứng tuyển (Job Tracker). |
| **Candidate event** | `tailored_resume_exported` |

### 3. Tự kiểm 5 tiêu chí
1. **Gần core value (ĐẠT):** Tải được file CV may đo là user đã có sẵn tài liệu tốt nhất để nộp đơn ngay.
2. **Có thể lặp lại (ĐẠT):** Lặp lại mỗi khi user tìm thấy một vị trí tuyển dụng mới ưng ý.
3. **Có thể quan sát (ĐẠT):** Hệ thống ghi nhận chính xác thời điểm tải file, User ID, Job ID, định dạng tải và điểm ATS Match Score.
4. **Có ý nghĩa (ĐẠT):** Số lượng CV may đo tải về tăng phản ánh trực tiếp việc user đang tích cực ứng tuyển bằng sản phẩm.
5. **Có thể tác động (ĐẠT):** Team có thể tối ưu thuật toán đối sánh từ khóa, cải thiện giao diện chỉnh sửa nhanh để tăng tỷ lệ hoàn tất export.
* **Kết quả:** Đạt **5/5 tiêu chí**.

---

# 02 — Action Nature Card & Kết Luận Cadence

### 1. Thẻ Action Nature Card
| Thành phần | Chi tiết |
| :--- | :--- |
| **Actor** | Cá nhân người tìm việc (Individual Job Seeker). |
| **Intent** | Cần một bản CV hoàn hảo để nộp cho một công việc vừa tìm thấy trên LinkedIn/TopCV. |
| **Trigger** | Người dùng lướt thấy một tin tuyển dụng phù hợp ngoài đời thực (External Trigger). |
| **Effort** | 2 – 4 phút để dán JD, lướt kiểm tra các điểm chỉnh sửa do AI gợi ý và bấm xuất file. |
| **Value timing** | Giá trị xuất hiện tức thì (Instant) — cầm ngay file CV chuẩn đẹp để apply. |
| **State** | Lưu trữ Master CV, các phiên bản CV đã may đo, điểm ATS Score, và danh sách công ty đã nộp trong Job Tracker. |
| **Dependency** | Phụ thuộc vào việc người dùng tìm thấy job mới trên thị trường tuyển dụng. |
| **Repeat condition** | Người dùng tiếp tục tìm thấy các cơ hội việc làm khác trong đợt tìm việc của mình. |

### 2. Kết luận Cadence
> *"Đối với **Ứng viên đang tích cực tìm việc**, core action **xuất bản CV đã may đo theo JD (`tailored_resume_exported`)** thường xuất hiện **2–5 lần/tuần trong đợt chiến dịch tìm việc kéo dài từ 4–8 tuần** vì **nhu cầu nộp đơn diễn ra liên tục theo từng đợt ứng tuyển cá nhân cho đến khi nhận được offer**. Do đó, nhịp đo phù hợp là **Weekly Bracket trong giai đoạn Active Campaign (chu kỳ 30–60 ngày)** ở cấp **User Account**."*

---

# 03 — Metric System

### 1. Activation Metric
* **Start event:** `master_cv_uploaded` (Người dùng hoàn tất tải lên CV gốc đầu tiên).
* **Activation event:** `tailored_resume_exported` lần đầu tiên với điểm tương thích ATS Match Score $\ge 80\%$.
* **Time window:** Trong vòng **24 giờ** kể từ khi tải lên Master CV.

### 2. Engagement Metric
* **Frequency:** Số lượng bản CV may đo được xuất (`tailored_resume_exported`) / tuần trong chiến dịch tìm việc.
* **Depth:** Điểm tương thích ATS trung bình (Average ATS Match Score) của các bản CV được xuất ($\ge 85\%$).

### 3. North Star Metric (NSM), Leading & Counter-metrics
* **North Star Metric (NSM):**
  $$\text{Weekly High-Match Tailored Applications}$$
  *(Số lượng bản CV may đo đạt điểm tương thích ATS $\ge 85\%$ được xuất bản thành công mỗi tuần).*
  * *Unit of Value:* Bản CV may đo được tải về (`tailored_resume_exported`).
  * *Quality Threshold:* Điểm ATS Match $\ge 85\%$, thời gian tạo $< 3$ phút/bản, tỷ lệ người dùng xóa bỏ chỉnh sửa của AI $< 20\%$.
  * *Frequency:* Hàng tuần (Weekly trong chu kỳ chiến dịch tìm việc).

* **Leading Indicators:**
  1. **JD Gap Analysis Completion Rate:** Tỷ lệ người dùng thực hiện dán JD và xem phân tích đối chiếu kỹ năng thiếu hụt $\ge 75\%$.
  2. **AI Suggestion Acceptance Rate:** Tỷ lệ từ khóa/bullet points do AI gợi ý được người dùng giữ lại trong bản CV cuối $\ge 80\%$.

* **Counter-metrics:**
  1. **Hallucination / AI Fabrication Rate (Tỷ lệ bốc phét kinh nghiệm):** Tỷ lệ người dùng phải xóa bỏ hoàn toàn đoạn văn bản do AI tự ý bịa thêm thông tin không có trong Master CV $\le 2\%$.
  2. **Zero-Review Fast Export Rate:** Tỷ lệ tải CV trong vòng $< 10$ giây sau khi AI tạo mà không đọc/chỉnh sửa (dấu hiệu spam CV rác, không kiểm soát chất lượng) $\le 5\%$.

---

# 04 — Retention Definition (Đủ 6 thành phần)

| Thành phần | Định nghĩa chi tiết |
| :--- | :--- |
| **1. Unit** | Active Job Seeker Account (Tài khoản người tìm việc cá nhân). |
| **2. Cohort entry** | Người dùng xuất bản CV may đo đầu tiên (`first_tailored_resume_exported`) trong tuần $W_0$. |
| **3. Return event** | Thực hiện hành vi `tailored_resume_exported`. |
| **4. Window** | **Weekly Bracket trong chu kỳ chiến dịch 6 tuần** ($W_1 \rightarrow W_6$ Active Campaign). |
| **5. Threshold** | Xuất $\ge 2$ bản CV may đo đạt chuẩn ATS trong tuần theo dõi. |
| **6. Segment** | Ứng viên đang ở trạng thái tích cực tìm việc (Active Job Hunting Segment). |

---

# 05 — Product Loop & Metric Hypothesis

### 1. Sơ đồ Product Loop (2 chu kỳ nộp đơn & theo dõi)
```mermaid
flowchart TD
    A[Tìm thấy JD ưng ý trên mạng\n(Natural Trigger 1)] --> B[Dán JD & duyệt gợi ý may đo CV của AI\n(Core Action 1)]
    B --> C[Tải CV chuẩn ATS nộp đơn ngay trong 2 phút\n(Immediate Value 1)]
    C --> D[Tự động lưu Job vào Bảng theo dõi ứng tuyển & ghi nhớ từ khóa thành công\n(Saved State / Investment)]
    D --> E[Đến lịch follow-up hoặc tìm thấy Job tương tự tiếp theo\n(Next Natural Trigger 2)]
    E --> F[AI tái sử dụng profile tối ưu để tạo CV mới nhanh hơn gấp 2 lần\n(Core Action 2)]
    F --> G[Tăng gấp đôi cơ hội nhận lời mời phỏng vấn\n(Repeat Value 2)]
```

### 2. Metric Hypothesis (Bắt buộc 1 câu)
> *"Nếu loop này hoạt động, metric **Weekly High-Match Tailored Applications (NSM)** sẽ thay đổi theo hướng **tăng 35%** và **W2–W4 Campaign Retention tăng từ 25% lên 50%** trong **chu kỳ 6 tuần**, vì **tính năng Tự động lưu Job Tracker kết hợp bộ nhớ từ khóa tích lũy giúp ứng viên giảm thêm 50% thời gian khi tạo các bản CV tiếp theo**."*

---

# 06 — Tracking Nhanh & Tiêu Chí Nghiệm Thu

### 1. Bảng 5 Core Events
| Tên event (`object_action`) | Ý nghĩa | Thời điểm ghi nhận | Metric sử dụng (ở Phase 3) |
| :--- | :--- | :--- | :--- |
| `master_cv_uploaded` | Người dùng đã tải lên và parse thành công CV gốc | Khi hệ thống phân tích xong các trường dữ liệu của Master CV | Start event của Activation |
| `jd_analysis_completed` | AI hoàn tất so sánh độ tương thích giữa Master CV và JD | Khi màn hình hiển thị điểm ATS ban đầu và danh sách kỹ năng thiếu hụt | JD Gap Analysis Completion Rate |
| `ai_suggestion_accepted` | Người dùng chấp nhận 1 gợi ý sửa đổi bullet point từ AI | Khi người dùng bấm nút áp dụng gợi ý vào bản nháp CV | AI Suggestion Acceptance Rate |
| `tailored_resume_exported` | Người dùng tải xuống bản CV đã may đo hoàn chỉnh | Khi file PDF/DOCX render thành công và browser bắt đầu download | **North Star Metric**, Activation, Weekly Retention |
| `job_tracker_status_updated` | Người dùng cập nhật trạng thái ứng tuyển (Applied / Interview / Offer) | Khi người dùng kéo thẻ công việc sang cột trạng thái mới trong Job Tracker | Đo lường hiệu quả chuyển đổi thực tế |

### 2. Tiêu chí nghiệm thu (Acceptance Criteria)
1. **Tiêu chí 1 (Completion-only):** Event `tailored_resume_exported` chỉ được bắn khi tệp CV (PDF/DOCX) đã được render hoàn tất từ backend và trình duyệt người dùng đã kích hoạt tải xuống thành công (HTTP 200 / Download Triggered). Tuyệt đối không bắn event khi người dùng mới bấm mở modal xem trước (Preview Modal).
2. **Tiêu chí 2 (Deduplication & Idempotency):** Với mỗi bộ định danh `(user_id, job_id, resume_export_version)`, hệ thống chỉ ghi nhận duy nhất 01 event `tailored_resume_exported` trong vòng 5 phút. Việc người dùng bấm nút tải nhiều lần liên tiếp do mạng chậm hoặc tải lại trang không được tạo thêm event tính sai sản lượng.

---

# 07 — Revision (Ghi Nhận Thay Đổi & Rationale)
* **Lý do chuyển đổi chủ đề:** Chuyển từ dự án B2B Automotive QC sang **MatchCraft AI (B2C / Career Tech)** nhằm tạo ra một use case gần gũi, có **Product Loop tự thân rõ ràng (Job Tracker + Keyword Memory)** và định nghĩa **Retention theo chu kỳ chiến dịch (Campaign-based Bracket)** chuẩn xác, tránh rơi vào bẫy ép nhịp Daily sai bản chất.
