# Đặc tả Sản phẩm — Synthesis & Decide Toolkit (Phiên bản Q&A)

Tài liệu phân tích, tổng hợp từ bằng chứng thực tế đến việc lựa chọn phạm vi phát triển (Build Slice) cho Chatbot hỏi đáp thông tin khách hàng Techcombank.

---

## 1. Gom bằng chứng (Evidence) thành cụm nỗi đau

Chúng tôi gom các bằng chứng thu thập được theo các cụm điểm đau của khách hàng khi tra cứu thông tin:

* **Cụm 1: "Mất thời gian và đứt gãy trải nghiệm do tra cứu ngoài ứng dụng"**
  * *Mô tả:* Người dùng phải thoát ứng dụng sang Google để tìm kiếm hạn mức chuyển tiền mặc định, biểu phí giao dịch quốc tế hoặc lãi suất mới nhất.
  * *Hậu quả:* Gây đứt gãy phiên làm việc trong app, quay lại phải đăng nhập lại từ đầu, làm tăng rủi ro tiếp cận thông tin cũ/sai lệch từ các trang không chính thức.
* **Cụm 2: "Nản lòng vì kênh trợ giúp tĩnh quá phức tạp"**
  * *Mô tả:* Trang hỗ trợ (FAQ) hiện tại của app chỉ là liên kết ngoài dẫn tới danh sách câu hỏi tĩnh, văn bản dài dòng.
  * *Hậu quả:* Người dùng phải tự kéo lướt, đọc rất nhiều chữ để tự tìm câu trả lời cho vấn đề cụ thể của mình, thay vì được trả lời trực diện.

---

## 2. Thấu hiểu sâu sắc (Insight)

```text
Khách hàng sử dụng ứng dụng Techcombank Mobile không muốn mất thời gian tự đọc các văn bản FAQ dài dòng hay thoát app tra cứu Google.
Họ thực sự cần một kênh "Hỏi đáp tức thì" (Instant Q&A) thông minh ngay tại cửa sổ chat để nhận được câu trả lời chính xác, ngắn gọn cho thắc mắc cụ thể của mình mà không làm gián đoạn trải nghiệm hiện tại.
```

---

## 3. Cơ hội sản phẩm (Opportunity)

```text
Cơ hội là sử dụng AI để tự động nhận diện ý định của người dùng và truy xuất thông tin từ cơ sở tri thức chính thức của Techcombank,
phản hồi câu trả lời ngắn gọn dưới 3 dòng ngay lập tức,
trong khi vẫn kiểm soát rủi ro thông tin sai lệch (hallucination) bằng cách thiết lập nguồn dẫn rõ ràng và cung cấp lối thoát nhanh sang hỗ trợ viên trực tiếp khi gặp câu hỏi ngoài phạm vi.
```

---

## 4. Đánh giá Build Slice (Phạm vi phát triển tối thiểu)

Chúng tôi đánh giá phạm vi lựa chọn phát triển cho ngày demo (Day 06) qua 5 câu hỏi cốt lõi:

| Câu hỏi kiểm chứng | Trạng thái | Chi tiết đánh giá |
| :--- | :---: | :--- |
| **User cụ thể chưa?** | **Đạt** | Khách hàng cá nhân sử dụng ứng dụng Techcombank Mobile cần tìm hiểu thông tin dịch vụ, lãi suất hoặc biểu phí. |
| **Task đủ hẹp chưa?** | **Đạt** | Tập trung duy nhất vào luồng **Hỏi đáp thông tin (Q&A)** thuộc 2 chủ đề lớn: **Lãi suất tiết kiệm hiện hành** và **Biểu phí dịch vụ thẻ/chuyển tiền**. |
| **AI decision rõ chưa?** | **Đạt** | AI phân loại ý định người dùng (FAQ Intent) và truy xuất câu trả lời chuẩn xác nhất từ cơ sở dữ liệu tri thức của ngân hàng. |
| **Failure path rõ chưa?** | **Đạt** | Khi người dùng hỏi các câu mơ hồ hoặc nằm ngoài cơ sở tri thức, AI nhận diện độ tin cậy thấp và kích hoạt thông điệp chuyển giao sang nhân viên hỗ trợ trực tiếp. |
| **Có bằng chứng (Evidence) không?** | **Đạt** | Đã thu thập bằng chứng từ phỏng vấn người dùng, phản hồi trên App Store và trải nghiệm thực tế của nhóm. |

---

## 5. Quyết định phạm vi (Scope Decision)

* **Quyết định:** **Giữ nguyên và tối ưu hóa chuyên sâu (Focus Scope)**
* **Lý do:** Không phát triển các tính năng điều hướng giao dịch hay thực hiện tác vụ tự động. Nhóm sẽ tập trung 100% vào việc tối ưu hóa khả năng phản hồi thông tin (Q&A) chính xác, ngắn gọn và dẫn nguồn rõ ràng cho khách hàng để giải quyết triệt để vấn đề mất thời gian tra cứu Google.

---

## 6. Câu chốt định hướng phát triển (Core Value Statement)

```text
Dựa trên bằng chứng khách hàng mất thời gian tra cứu ngoài ứng dụng và nản lòng với trang FAQ tĩnh,
nhóm sẽ xây dựng prototype Chatbot AI hỗ trợ hỏi đáp trực diện và phản hồi tức thì thông tin ngân hàng,
cho khách hàng sử dụng ứng dụng di động Techcombank,
để giải quyết nỗi đau đứt gãy đăng nhập và sự chậm trễ khi tự tra cứu biểu phí/lãi suất,
bằng cách AI tự động nhận diện ý định và truy xuất câu trả lời chuẩn xác từ cơ sở tri thức chính thức,
và sẽ kiểm thử kịch bản lỗi (Failure path) khi người dùng hỏi các câu hỏi mơ hồ hoặc ngoài phạm vi ngân hàng.
```

---

## 7. Backlog (Danh sách tính năng tích lũy - Không xây dựng trong Day 06)

Những tính năng dưới đây sẽ **không** được xây dựng trong đợt phát triển nhanh 1 ngày:

1. **Điều hướng nhanh bằng Deep Link:** Nút bấm dẫn tới các màn hình thực hiện tác vụ (chuyển sang phần phát triển tương lai).
2. **Khóa thẻ hoặc đổi hạn mức trực tiếp qua Chatbot:** Các tính năng làm thay đổi trạng thái tài khoản/thẻ của khách hàng.
3. **Hỏi đáp bằng giọng nói (Voice Q&A):** Nhận diện giọng nói để trả lời.
4. **Hỏi đáp các lĩnh vực tài chính phức tạp bên thứ ba:** Bảo hiểm liên kết, sản phẩm chứng khoán đối tác (cần tích hợp nhiều hệ thống dữ liệu ngoại bang).
