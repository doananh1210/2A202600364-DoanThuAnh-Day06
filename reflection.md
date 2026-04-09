# Individual reflection — Đoàn Thư Ánh (2A202600364)

## 1. Role
- **AI Product Canvas**: spec/spec-final.md (phần 1)
- **Thu thập data**
- **Prompt Engineering**: system_prompt.txt
- **Tools**: tools.py

## 2. Đóng góp cụ thể
- Thiết kế AI Product Canvas, xác định các failure modes và mitigation.
- Thu thập dữ liệu 
- Viết và tối ưu hóa system prompt.
- Viết các hàm trong `tools.py` 


## 3. SPEC mạnh/yếu
- **Mạnh nhất:**
  - Luồng tư vấn rõ ràng: AI luôn giải thích vì sao gợi ý model đó phù hợp với ngân sách và nhu cầu của khách hàng, giúp user dễ hiểu và tin tưởng quyết định hơn.
  - Quy tắc ưu tiên dữ liệu chặt chẽ: PDF chính thức của VinFast được đặt làm nguồn “source of truth”, giảm nguy cơ trả sai giá/specs khi database hard-code lỗi thời.
- **Yếu nhất:**
  - Assumption về nhu cầu người dùng chưa đủ sâu: hiện mới dựa vào budget, tên xe, hoặc yêu cầu so sánh; chưa tách rõ các nhóm nhu cầu như đi gia đình, chạy dịch vụ, đi xa thường xuyên.
  - Rủi ro bias gợi ý: nếu dữ liệu trong database không cân bằng, AI có thể ưu tiên một số model phổ biến hơn dù chưa chắc tối ưu nhất cho user.

## 4. Đóng góp khác


## 5. Điều học được
Trước hackathon, em nghĩ các khái niệm như accuracy, precision hay recall chỉ là những chỉ số kỹ thuật để đánh giá model.
Sau quá trình làm việc, nhóm nhận ra rằng đằng sau mỗi metric là một quyết định sản phẩm: chọn tối ưu tiêu chí nào sẽ ảnh hưởng trực tiếp đến trải nghiệm người dùng và giá trị mà hệ thống mang lại.

Trong thực tế, có những lúc phải đứng giữa hai lựa chọn đều quan trọng: cái nào cũng có lý do để giữ lại, cái nào bỏ đi cũng thấy tiếc. Nhưng xây dựng AI cũng giống như làm sản phẩm — không thể ôm tất cả mọi thứ cùng lúc. Điều quan trọng là phải hiểu mục tiêu cuối cùng để chọn điều phù hợp hơn, dù biết rằng lựa chọn nào cũng có mặt được và mất.



## 6. Nếu làm lại
Nhóm sẽ bắt đầu kiểm thử prompt và luồng hội thoại sớm hơn thay vì tập trung quá lâu vào phần SPEC ban đầu.
Trong quá trình làm, còn không đủ time test nhiều case hơn để biết rõ AI lỗi ở đâu, vì vừa build xong đã đến time demo.
Nếu thử nghiệm sớm ngay từ ngày đầu, nhóm có thể cải thiện thêm nhiều vòng để chatbot tự nhiên và mượt hơn.

## 7. AI giúp gì / AI sai gì
- **Giúp:**
  - Dùng Claude để brainstorm failure modes — nó gợi ý được "drug interaction" mà nhóm không nghĩ ra.
  - Dùng Gemini để test prompt nhanh qua AI Studio.
  - AI phát huy hiệu quả nhất khi đóng vai trò phản biện và mở rộng trên chính ý tưởng ban đầu của nhóm. Từ concept chatbot tư vấn xe mà nhóm đưa ra, AI giúp brainstorm thêm các hướng triển khai như chia flow theo ngân sách, theo model cụ thể, hay thêm nhánh so sánh xe và tính chi phí sở hữu. Với mỗi prompt xuất phát từ ý tưởng của nhóm, AI hỗ trợ biến những ý tưởng còn mơ hồ thành kế hoạch rõ ràng hơn về workflow và giao diện.
  - Claude còn hỗ trợ sinh code giao diện nhanh cho prototype, giúp nhóm tiết kiệm đáng kể thời gian dựng UI ban đầu và có thể tập trung nhiều hơn vào logic hệ thống.
- **Sai/mislead:**
  - Vì AI chỉ phát triển dựa trên prompt đầu vào, đôi khi nó mở rộng ý tưởng theo hướng quá phức tạp hoặc xa nhu cầu thực tế. Có lúc AI đề xuất thêm nhiều bước trong flow tư vấn khiến trải nghiệm trở nên rườm rà, trong khi mục tiêu ban đầu của nhóm chỉ là tạo một chatbot đơn giản, dễ demo.
  - Dù sinh code rất nhanh, giao diện AI tạo ra vẫn còn lỗi như bố cục lệch, icon chồng lên nhau và spacing chưa hợp lý, nên vẫn cần con người chỉnh sửa để hoàn thiện trải nghiệm người dùng.