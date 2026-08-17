# Báo cáo nộp bài Lab 17 - Multi-Memory Agent với Zep

## 1. Ba câu hỏi cốt lõi
- **Layer quan trọng nhất:** Long-term Memory là layer quan trọng nhất trong bộ test vì chiếm nhiều case nhất (E02, E03, E08, E09) và trực tiếp quản lý tính bền vững qua nhiều session, preferences, open-loops và user isolation.
- **Trade-off Zep Context Block vs Redis/Qdrant:** Zep tự động hóa việc trích xuất tri thức, xây dựng User Graph, xử lý conflict theo thời gian (recency wins) và tổng hợp Context Block theo ngữ cảnh. Tự xây bằng Redis + Qdrant đòi hỏi tự phát triển toàn bộ pipeline chunking, embedding, đồ thị liên kết, quản lý TTL và suy luận conflict phức tạp.
- **Guardrail chống Memory Poisoning:** Áp dụng xác thực consent (`consent.json`), lọc và làm sạch PII (`minimize_pii`), heartbeat chỉ de-duplicate/expire chứ không tự ý nâng quyền hay ghi đè policy, đồng thời yêu cầu human-in-the-loop duyệt các thay đổi trạng thái có ảnh hưởng lớn.

## 2. Bốn câu phân tích Benchmark
1. **Layer hit rate thấp nhất:** Ở baseline no-memory, cả Long-term, Episodic và Semantic đều đạt 0% (chỉ short-term đạt 100%). Với Student Memory, cả 4 layer đều đạt 100% (11/11 PASS).
2. **Query retrieve nhiều token nhất:** Các case Long-term (E02: 1410 tokens, E03: 1407 tokens, E08: 1391 tokens) do Context Block tổng hợp toàn diện tóm tắt người dùng và các facts liên quan.
3. **Case mixed (E07):** Cần kết hợp Long-term Memory (sở thích cá nhân của Minh là `Python`) và Semantic Memory (chính sách retry `Idempotency-Key` từ domain KB).
4. **Token reduction vs Hit rate:** Baseline no-memory đạt 81.8% token reduction nhưng hit rate chỉ 18.2% (2/11) vì không truy xuất gì; điều này chứng minh token reduction chỉ có giá trị khi đi cùng evidence hit rate cao (Student đạt 100% hit rate, token reduction 14.2%).

## 3. Phân tích Recency (E08) & Compaction (E10)
- **E08 (Recency):** Khi Minh đổi yêu cầu cho dự án `BLUEBIRD-42` sang `TypeScript` + `NestJS`, hệ thống ưu tiên fact mới nhất thay vì `Python`, đồng thời duy trì nguồn gốc (provenance).
- **E10 (Compaction):** Cơ chế Sliding Window kết hợp `DURABLE_NOTES` bảo toàn nguyên vẹn ràng buộc cứng `REVIEW-DEADLINE-1600 (Friday 16:00)` dù các lượt hội thoại thô đã bị nén.
