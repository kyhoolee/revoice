Rất tốt. Dưới đây là phần cập nhật chi tiết cho **use-case của user (người bệnh)** – làm rõ mục tiêu sử dụng, loại user, hành vi tương tác, và các tình huống cụ thể sẽ gặp.

---

## 🧑‍🦽 **USE CASE CHO USER (NGƯỜI BỆNH MẤT GIỌNG / LẠC GIỌNG)**

---

### 🎯 **MỤC TIÊU SỬ DỤNG**

Hệ thống được thiết kế để:

1. **Thu thập dữ liệu giọng nói của người mất tiếng/lạc tiếng** (sau tai biến, hoặc các bệnh về phát âm)
2. **Giúp người bệnh luyện phát âm dần dần theo hướng dẫn có sẵn**
3. **Phân tích dữ liệu giọng nói để cá nhân hóa nhận diện âm thanh** (bằng AI)
4. **Tạo giao diện giao tiếp đơn giản để người bệnh truyền đạt ý muốn với người thân hoặc nhân viên y tế**

---

### 👥 **PHÂN LOẠI NGƯỜI DÙNG**

| Loại user                                | Mô tả                                                          | Khả năng tương tác                                            |
| ---------------------------------------- | -------------------------------------------------------------- | ------------------------------------------------------------- |
| 👴 **Người bệnh không tự thao tác**      | Người cao tuổi sau tai biến, liệt, yếu tay, khó phối hợp       | Cần **người thân/người hỗ trợ thao tác hộ** (collector mode)  |
| 🧓 **Người bệnh có thể thao tác cơ bản** | Người mới mất giọng, có thể bấm nút hoặc sử dụng máy tính bảng | Có thể dùng app ở **chế độ đơn giản**, 1 chạm để ghi âm       |
| 🧑‍⚕️ **Người hỗ trợ/collector**         | Con/cháu, y tá, điều dưỡng                                     | Dùng giao diện chuyên biệt để thu âm, gắn nhãn, xác nhận file |

---

### 📱 **TÌNH HUỐNG SỬ DỤNG ĐIỂN HÌNH**

#### 📌 Use-case 1: **Thu âm giọng nói mẫu**

* 🧠 Mục tiêu: thu 10–20 âm đơn/câu mẫu
* 🧍 Người thao tác: người hỗ trợ
* 📲 Quy trình:

  1. Giao diện hiện "âm cần đọc" hoặc "từ mẫu"
  2. Bấm **\[Start]**, người bệnh phát âm
  3. Bấm **\[Stop]**, file được lưu với label + thời gian

#### 📌 Use-case 2: **Luyện tập phát âm hằng ngày**

* 🧠 Mục tiêu: giúp người bệnh luyện lại khả năng nói
* 🧍 Người thao tác: người bệnh (hoặc hỗ trợ)
* 📲 Quy trình:

  1. Chọn bài luyện hôm nay (ví dụ: 5 âm A-I-U-E-O)
  2. Giao diện bật mẫu đọc → người bệnh lặp lại
  3. Ghi lại giọng, cho phép nghe lại và lưu

#### 📌 Use-case 3: **Giao tiếp bằng âm thanh**

* 🧠 Mục tiêu: khi người bệnh chỉ phát ra âm "bê bê", hệ thống giúp suy luận ra câu muốn nói
* 📲 Mô hình:

  * Tạo ra các **mẫu phát âm thường lặp lại** theo thời gian
  * Gắn nhãn (ví dụ: “bê bê bê” ứng với “tôi khát nước”)
  * Cho phép người bệnh phát âm → hệ thống gợi ý
* Đây là mục tiêu dài hơi (về sau fine-tune Whisper + mapping semantic)

---

### ✅ **Tóm tắt nhiệm vụ theo vai trò**

| Vai trò                          | Tác vụ chính                                                                                                    |
| -------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| 🧑‍🦽 Người bệnh                 | - Lặp lại âm thanh hiển thị<br>- Thực hiện luyện tập mỗi ngày<br>- Giao tiếp bằng âm đặc trưng                  |
| 👨‍👩‍👧 Người thân / điều dưỡng | - Hỗ trợ thu âm mẫu<br>- Đảm bảo môi trường yên tĩnh<br>- Chọn từ/câu mẫu, bấm Start/Stop                       |
| 👨‍💻 Hệ thống                   | - Hiển thị bài luyện tập<br>- Ghi lại âm thanh<br>- Gắn label + timestamp<br>- Tự động lưu trữ + chuẩn hóa file |

---

Nếu bạn muốn, mình có thể:

* Viết luôn các `JSON schema` mẫu cho `session.json` (ghi lại 1 buổi thu âm)
* Mockup giao diện `3 màn hình đầu tiên`: thu âm – luyện tập – xem lại dữ liệu
* Chuẩn hóa danh sách các âm cần thu (việt hóa theo tiếng Việt luôn)

Bạn muốn triển khai phần nào tiếp theo?
