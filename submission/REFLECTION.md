# Reflection — Lab 19

**Tên:** Hoàng Thị Thanh Tuyền  
**Cohort:** A20-K1  
**Path đã chạy:** lite

---

## Câu hỏi (≤ 200 chữ)

Trên golden set 50 queries, `exact` thường thắng bằng BM25 vì query có từ khóa khớp trực tiếp với tài liệu. `paraphrase` thường thắng bằng vector search vì mô hình bắt được ngữ nghĩa dù không trùng từ. `mixed` thường là nơi hybrid thắng rõ nhất vì nó vừa giữ được tín hiệu keyword của BM25 vừa tận dụng semantic matching của embeddings, nên ổn định hơn trên nhiều kiểu truy vấn.

Tôi không dùng hybrid khi cần latency cực thấp, khi truy vấn rất ngắn và đã có từ khóa rõ ràng, hoặc khi corpus nhỏ và khá chuẩn hóa. Trong các trường hợp đó, pure BM25 thường đủ tốt và rẻ hơn. Ngược lại, pure vector phù hợp hơn khi người dùng hay diễn đạt lại ý, dùng tiếng Việt tự nhiên, code-switching, hoặc gõ sai nhẹ.

---

## Điều ngạc nhiên nhất khi làm lab này

Điều ngạc nhiên nhất là cùng một query có thể cho kết quả rất khác giữa exact keyword và paraphrase, nên lựa chọn mode ảnh hưởng trực tiếp đến trải nghiệm tìm kiếm.

---
