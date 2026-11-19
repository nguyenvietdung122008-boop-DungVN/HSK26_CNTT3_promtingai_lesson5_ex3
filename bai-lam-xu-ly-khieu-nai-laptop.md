# Thiết kế prompt AI xử lý khiếu nại về laptop

## 1. Prompt hoàn chỉnh

```text
Bạn là chuyên viên chăm sóc khách hàng của một cửa hàng laptop.

Khiếu nại của khách hàng
“Tôi mua laptop cách đây 10 ngày. Máy thường xuyên bị nóng, quạt kêu to và pin chỉ sử dụng được khoảng 2 tiếng. Tôi đã mang đến cửa hàng kiểm tra nhưng nhân viên chỉ vệ sinh máy và trả lại. Sau 2 ngày, tình trạng vẫn tiếp diễn. Tôi muốn đổi máy hoặc hoàn tiền.”

Áp dụng kỹ thuật Chain-of-Thought bằng cách phân tích theo trình tự sau. Trong báo cáo, trình bày kết quả của từng bước cùng căn cứ ngắn gọn, có thể kiểm tra.

1. Liệt kê từng vấn đề theo lời khách, kết quả xử lý lần đầu và yêu cầu hiện tại.
2. Đánh giá sơ bộ mức độ ảnh hưởng của từng vấn đề và giải thích căn cứ. Đánh giá riêng mức ưu tiên xử lý khiếu nại.
3. Phân biệt dữ kiện do khách cung cấp, giả thuyết có thể kiểm tra và thông tin chưa xác định.
4. Liệt kê thông tin cần xác minh từ khách hàng, nội dung cần kiểm tra kỹ thuật và hồ sơ cửa hàng cần đối chiếu.
5. Đề xuất đúng hai phương án. Với mỗi phương án, nêu điều kiện áp dụng, cách thực hiện, ưu điểm và hạn chế.
6. Soạn phản hồi lịch sự để nhân viên gửi khách. Ghi nhận cả ba triệu chứng, lần tiếp nhận trước và yêu cầu đổi máy hoặc hoàn tiền. Nêu bước tiếp theo và thông tin tối thiểu cần khách cung cấp.

Không tự đặt chính sách, thời hạn đổi trả hoặc điều kiện bảo hành của cửa hàng. Không suy ra khách đủ điều kiện đổi máy hay hoàn tiền chỉ vì mới mua 10 ngày. Không khẳng định máy có lỗi, quy trách nhiệm hoặc cam kết kết quả khi chưa có căn cứ.

Đầu ra gồm báo cáo phân tích theo từng bước, danh sách thông tin cần xác minh, hai phương án kèm ưu điểm và hạn chế, và phản hồi gửi khách hàng.
```

## 2. Báo cáo phân tích theo từng bước

### Bước 1. Xác định vấn đề

Theo lời khách, laptop mua cách đây 10 ngày thường xuyên nóng, quạt kêu to và pin dùng được khoảng hai giờ. Khách đã mang máy đến cửa hàng và cho biết nhân viên chỉ vệ sinh máy trước khi trả lại. Hai ngày sau, các triệu chứng vẫn tiếp diễn. Khách muốn đổi máy hoặc hoàn tiền.

### Bước 2. Đánh giá mức độ sơ bộ

| Vấn đề | Mức ảnh hưởng hoặc ưu tiên | Căn cứ |
| --- | --- | --- |
| Máy thường xuyên nóng | Trung bình, cần kiểm tra sớm | Triệu chứng lặp lại. Chưa có số đo nhiệt độ và thông tin về tác vụ đang chạy. |
| Quạt kêu to | Trung bình | Ảnh hưởng đến trải nghiệm. Cần biết tiếng quạt xuất hiện khi chạy tác vụ nhẹ hay khi tải cao. |
| Pin dùng khoảng hai giờ | Trung bình | Hạn chế thời gian sử dụng khi rời nguồn điện. Cần đối chiếu đúng mẫu máy và điều kiện sử dụng. |
| Triệu chứng tiếp diễn sau lần tiếp nhận đầu | Ưu tiên chăm sóc khách hàng cao | Khách đã mang máy đến một lần và phải phản ánh lại vì vấn đề tiếp diễn. |

### Bước 3. Phân loại thông tin

- **Dữ kiện được khách cung cấp** gồm thời điểm mua, ba triệu chứng, lần tiếp nhận trước và yêu cầu đổi máy hoặc hoàn tiền. Cần đối chiếu ngày mua và nội dung tiếp nhận với hồ sơ cửa hàng.
- **Giả thuyết cần kiểm tra** gồm tải tác vụ cao, thiết lập nguồn, tình trạng pin và hoạt động của hệ thống tản nhiệt.
- **Thông tin chưa xác định** gồm nguyên nhân kỹ thuật, kết quả kiểm tra lần đầu và điều kiện đổi trả áp dụng cho giao dịch.

### Bước 4. Danh sách thông tin cần xác minh

- **Hỏi khách hàng** về mã đơn hàng hoặc hóa đơn, mẫu máy, tác vụ đang chạy khi máy nóng và quạt kêu, cùng điều kiện sử dụng khi ghi nhận thời lượng pin khoảng hai giờ.
- **Kiểm tra kỹ thuật** bằng cách tái hiện điều kiện khách mô tả. Ghi nhận nhiệt độ, tải hệ thống và đặc điểm tiếng quạt. Kiểm tra tình trạng pin và đo thời lượng sử dụng trong điều kiện được ghi nhận. Đối chiếu kết quả với tài liệu của đúng mẫu máy nếu có.
- **Đối chiếu hồ sơ cửa hàng** để xác nhận ngày mua, số sê-ri, nội dung xử lý lần đầu và chính sách đổi trả hoặc bảo hành áp dụng cho đơn hàng.

### Bước 5. Hai phương án xử lý

| Phương án | Điều kiện và cách thực hiện | Ưu điểm | Hạn chế |
| --- | --- | --- | --- |
| **1. Tiếp nhận lại để kiểm tra kỹ thuật** | Khi hồ sơ chưa đủ để xác định hướng xử lý, dùng lại thông tin đã có, kiểm tra cả ba triệu chứng và thông báo kết quả cùng hướng xử lý phù hợp. | Có kết quả kiểm tra để giải thích cho khách và làm căn cứ xử lý. | Khách có thể phải bàn giao máy thêm một lần và chờ kết quả. |
| **2. Đổi máy hoặc hoàn tiền nếu đủ điều kiện** | Đối chiếu hồ sơ và chính sách áp dụng. Nếu cần kết quả kỹ thuật để xác nhận điều kiện, sử dụng kết quả từ phương án 1. Sau khi xác nhận, trao đổi với khách về hình thức áp dụng. | Giải quyết trực tiếp yêu cầu của khách khi đã xác nhận đủ điều kiện. | Có thể phải chờ thêm kết quả kiểm tra. Hình thức xử lý phụ thuộc vào điều kiện của giao dịch. |

### Bước 6. Phản hồi mẫu gửi khách hàng

> Chào anh/chị,
>
> Cửa hàng xin lỗi vì tình trạng máy nóng, quạt kêu to và pin chỉ dùng được khoảng hai giờ vẫn tiếp diễn sau lần anh/chị mang máy đến. Bên em đã ghi nhận yêu cầu đổi máy hoặc hoàn tiền của anh/chị.
>
> Anh/chị vui lòng gửi giúp em mã đơn hàng hoặc ảnh hóa đơn để bên em tra cứu hồ sơ lần tiếp nhận trước và đối chiếu điều kiện đổi trả áp dụng cho đơn hàng. Nếu cần kiểm tra lại máy, bên em sẽ liên hệ để thống nhất cách tiếp nhận và kiểm tra cả ba tình trạng anh/chị đã phản ánh.
>
> Sau khi xác minh, bên em sẽ thông báo kết quả và phương án xử lý áp dụng cho trường hợp của anh/chị.
