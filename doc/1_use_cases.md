## 🧠 **Cập nhật mục tiêu sử dụng hệ thống**

### 🎯 **2 hướng chính của sản phẩm:**

| Hướng                                      | Mục tiêu chính                                                                | Mô tả ngắn                                                          |
| ------------------------------------------ | ----------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| **1. Tập giao tiếp lại (phục hồi)**        | **Phục hồi khả năng phát âm** sau tai biến, đột quỵ hoặc tổn thương thần kinh | Giúp người bệnh luyện âm từ cơ bản đến nâng cao, tracking quá trình |
| **2. Hỗ trợ giao tiếp vĩnh viễn (bù trừ)** | **Thay thế hoặc hỗ trợ** giao tiếp cho người không thể hồi phục khả năng nói  | Dựa trên âm thanh đặc trưng, gesture, hoặc touch để truyền đạt ý    |

---

## 👥 **Cập nhật nhóm người dùng chính**

| Loại người dùng                                | Hướng phù hợp         | Đặc điểm                                                             |
| ---------------------------------------------- | --------------------- | -------------------------------------------------------------------- |
| 🧓 Người mới mất tiếng (khả năng hồi phục cao) | **Tập giao tiếp lại** | Phát âm méo nhưng còn điều khiển được lưỡi, miệng, hơi thở           |
| 👴 Người mất tiếng lâu dài / vĩnh viễn         | **Hỗ trợ giao tiếp**  | Không nói rõ được hoặc không thể phục hồi do tổn thương nghiêm trọng |
| 👨‍👩‍👧 Người thân                            | Cả 2                  | Hỗ trợ vận hành app, thu âm, sử dụng tính năng giao tiếp hộ          |

---

## 📱 **Chi tiết use-case theo từng hướng**

---

### 🟢 **1. Tập giao tiếp lại (Hướng phục hồi)**

> Mục tiêu: **giúp người bệnh luyện tập theo giáo trình tăng dần**, từ âm đơn đến từ đơn và câu ngắn.

#### ✅ Các use-case chính:

| Use-case                         | Mô tả                                              | Ghi chú                                                 |
| -------------------------------- | -------------------------------------------------- | ------------------------------------------------------- |
| **Luyện âm cơ bản**              | Người bệnh nghe âm mẫu → cố phát âm theo → ghi lại | Gợi ý: 5 nguyên âm, 5 phụ âm dễ nhất                    |
| **Luyện từ**                     | Người bệnh đọc theo từ đơn ("ba", "cá", "mẹ")      | Có thể chia theo nhóm nghĩa (gia đình, đồ vật, cảm xúc) |
| **Theo dõi tiến trình phục hồi** | Ghi nhận audio hằng ngày → biểu đồ so sánh         | Cần thiết cho bác sĩ/người thân                         |

---

### 🟡 **2. Hỗ trợ giao tiếp (Hướng bù trừ)**

> Mục tiêu: **giúp người mất tiếng giao tiếp với người khác qua âm thanh đặc trưng hoặc thao tác đơn giản.**

#### ✅ Các use-case chính:

| Use-case                                       | Mô tả                                                  | Ghi chú                                                    |
| ---------------------------------------------- | ------------------------------------------------------ | ---------------------------------------------------------- |
| **Phát âm đặc trưng → xác định ý nghĩa**       | Ví dụ: “bê bê bê” → “tôi khát nước”                    | Dùng mô hình nhận diện mẫu âm cá nhân                      |
| **Bảng giao tiếp cảm ứng (Touch UI)**          | Bấm biểu tượng: nước, toilet, đói, đau... → đọc ra câu | Giải pháp bù hoàn toàn khi không thể phát âm               |
| **Hệ thống tự học và gợi ý câu nói quen dùng** | Dựa vào lịch sử & tần suất → gợi ý câu nói phù hợp     | Ví dụ: mỗi sáng hay nói “chào con” → đưa lên đầu danh sách |

---

## 🔧 Phân biệt kỹ thuật giữa 2 hướng

| Thành phần    | Tập giao tiếp lại                             | Hỗ trợ giao tiếp                                   |
| ------------- | --------------------------------------------- | -------------------------------------------------- |
| 🎤 Thu âm mẫu | Bắt buộc – để luyện & đo tiến bộ              | Chỉ cần để khởi tạo mô hình cá nhân                |
| 🧠 AI xử lý   | Fine-tune Whisper hoặc nhận diện cải tiến dần | Mapping từ âm cá nhân → ý nghĩa                    |
| 📲 Giao diện  | Dẫn dắt bài tập luyện, ghi log                | Giao diện cảm ứng đơn giản, có biểu tượng, câu mẫu |

---

## ✅ Kết luận đề xuất

Với định hướng rõ ràng này, bạn có thể:

* ✅ Thiết kế kiến trúc hệ thống chia thành 2 mode: `recovery_mode` và `assistive_mode`
* ✅ Khi user đăng ký, chọn mục tiêu: **"Tập luyện hồi phục"** hoặc **"Hỗ trợ giao tiếp"**
* ✅ Cấu trúc lại data & feedback theo từng nhóm

