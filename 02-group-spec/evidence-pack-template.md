# Đặc tả Sản phẩm — Evidence Pack (Phiên bản Q&A)

Tài liệu thu thập bằng chứng và phân tích hành vi người dùng cho dự án Chatbot hỏi đáp thông tin tích hợp trên ứng dụng Techcombank Mobile.

---

## 1. Nhóm và track

* **Tên nhóm:** Nhóm 2 - Batch 02 (AI Product Labs)
* **Track:** AI Finance / Banking Q&A Assistant
* **Product/app đã chọn:** Ứng dụng di động Techcombank (Techcombank Mobile App)
* **Build slice đang nghĩ:** Chatbot AI chuyên biệt hỗ trợ hỏi đáp, phản hồi các câu hỏi tra cứu thông tin của khách hàng (lãi suất tiết kiệm, biểu phí giao dịch, thủ tục dịch vụ) trực tiếp trong ứng dụng.

---

## 2. Self-use evidence (Bằng chứng tự trải nghiệm)

Nhóm đã trực tiếp trải nghiệm ứng dụng Techcombank hiện tại và ghi nhận điểm gãy liên quan đến tra cứu thông tin:

| Quan sát thực tế (Observation)                                                                                                           | Ảnh chụp màn hình / Link                                                                                                                 | Luồng liên quan (Path)        | Điều học được (Insight học được)                                                                            |
| :-----------------------------------------------------------------------------------------------------------------------------------------| :-----------------------------------------------------------------------------------------------------------------------------------------| :------------------------------| :------------------------------------------------------------------------------------------------------------|
| Không có ô tìm kiếm hay chatbot hỗ trợ tra cứu thông tin nhanh trên màn hình chính.                                                      | [Screenshot 1](file:///C:/Users/giang/Desktop/New%20folder/Batch02-Day05-AI-Product-Labs/02-group-spec/evidence-images/home_screen.png)  | Happy Path (Khởi đầu tra cứu) | Người dùng không có cách nào để đặt câu hỏi trực tiếp khi cần biết thông tin nhanh.                         |
| Menu hỗ trợ dẫn ra trang FAQ tĩnh bên ngoài với quá nhiều chuyên mục và văn bản dài dòng, không hỗ trợ trả lời trực tiếp câu hỏi cụ thể. | [Screenshot 2](file:///C:/Users/giang/Desktop/New%20folder/Batch02-Day05-AI-Product-Labs/02-group-spec/evidence-images/sidebar_menu.png) | Failure / Low-confidence Path | Việc đọc các tài liệu FAQ dài làm người dùng nản lòng, họ muốn gõ câu hỏi và nhận câu trả lời ngay lập tức. |

---

## 3. User / review / social evidence (Bằng chứng từ người dùng)

| Ý kiến / Phản hồi của người dùng                                                                                                                                                                 | Nguồn gốc                    | Người dùng là ai?                    | Điểm đau & Lỗi trải nghiệm (Pain/Failure Mode)                                                      |
| :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------| :-----------------------------| :-------------------------------------| :----------------------------------------------------------------------------------------------------|
| "Mỗi lần muốn xem phí chuyển tiền đi nước ngoài hoặc phí thường niên thẻ là phải lên Google tra cứu, rất mất thời gian. Nhiều lúc Google ra thông tin cũ từ mấy năm trước làm mình bị nhầm lẫn." | Phỏng vấn nhanh khách hàng   | Giang, 28 tuổi (Nhân viên văn phòng) | Mất thời gian tra cứu bên ngoài, rủi ro nhận thông tin sai lệch/lỗi thời từ nguồn không chính thức. |


---

## 4. Competitor / analog evidence (Bằng chứng từ đối thủ cạnh tranh)

| Đối thủ tham khảo | Cách họ xử lý task này thế nào? | Pattern học được | Có thể áp dụng trong 1 ngày không? |
| :--- | :--- | :--- | :--- |
| **Timo (Trợ lý Timo)** | Tích hợp chatbot hỏi đáp FAQ. Người dùng gõ câu hỏi và nhận câu trả lời dạng văn bản ngắn gọn, chính xác kèm nguồn trích dẫn. | **Direct Q&A:** Trả lời trực diện câu hỏi của người dùng ngay trong cửa sổ chat. | **Có:** Xây dựng chatbot trả lời dựa trên cơ sở dữ liệu câu hỏi thường gặp. |
| **MBBank (Trợ lý ảo)** | Hỗ trợ tìm kiếm thông tin dịch vụ, giải đáp thắc mắc về thẻ và tài khoản bằng ngôn ngữ tự nhiên. | **FAQ Retrieval:** Truy xuất thông tin từ tài liệu chính thức của ngân hàng để phản hồi. | **Có:** Sử dụng RAG hoặc Prompt-Engineering nạp ngữ cảnh dữ liệu ngân hàng. |
| **VietinBank (Trợ lý ảo)** | Trợ lý ảo giải đáp chi tiết biểu phí dịch vụ thẻ, lãi suất tiết kiệm và thủ tục mở tài khoản. | **Contextual Q&A:** Phản hồi thông tin có cấu trúc, ngắn gọn, dễ hiểu thay vì trích nguyên văn bản luật. | **Có:** Tinh chỉnh prompt để AI tóm tắt câu trả lời ngắn gọn dưới 3 dòng. |

---

## 5. Từ Bằng chứng (Evidence) sang Thấu hiểu (Insight)

```text
Bằng chứng nổi bật nhất:
Người dùng phải liên tục thoát ứng dụng Techcombank để lên Google tra cứu các thông tin cơ bản như lãi suất tiết kiệm, biểu phí giao dịch và thủ tục dịch vụ, sau đó đối mặt với rủi ro thông tin lỗi thời và việc phải đăng nhập lại app từ đầu.

Thấu hiểu (Insight):
Khách hàng không muốn đọc các tài liệu văn bản FAQ dài dòng hay tự tìm kiếm thủ công. Họ thực sự cần một kênh "Hỏi đáp tức thì" (Instant Q&A) đáng tin cậy ngay trong app để trả lời chính xác thắc mắc của họ, giúp họ yên tâm thực hiện các quyết định tài chính.

Cơ hội sản phẩm (Opportunity):
Sử dụng AI Chatbot để nhận diện câu hỏi tự nhiên của khách hàng về dịch vụ ngân hàng, tự động đối chiếu với cơ sở tri thức chính thức của Techcombank để phản hồi câu trả lời ngắn gọn, chính xác 100% ngay lập tức.
```

---

## 6. Bằng chứng thay đổi tài liệu đặc tả (SPEC) như thế nào?

* [x] Đổi pain statement.
* [x] Đổi build slice.
* [x] Đổi 4 paths.
* [ ] Đổi Auto/Aug decision.

**Ghi rõ thay đổi quan trọng:**

```text
Trước khi thu thập bằng chứng, nhóm định:
Tích hợp cả các luồng giao dịch tự động và nút điều hướng thao tác phức tạp trong chatbot.

Sau khi thu thập bằng chứng và nhận phản hồi, nhóm quyết định đổi thành:
Tập trung 100% vào tính năng Hỏi đáp (Q&A), phản hồi các câu hỏi tra cứu thông tin của khách hàng một cách chính xác và nhanh chóng nhất.

Lý do:
Khách hàng cốt lõi cần giải quyết vấn đề tìm kiếm thông tin nhanh để thay thế việc tra cứu Google. Tập trung vào Q&A giúp tối ưu hóa độ chính xác của câu trả lời từ AI, tránh ảo giác và xây dựng lòng tin cao nhất đối với khách hàng về mặt thông tin tài chính.
```
