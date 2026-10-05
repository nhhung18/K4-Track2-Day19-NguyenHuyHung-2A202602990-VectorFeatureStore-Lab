# Reflection — Lab 19

**Tên:** Nguyen Huy Hung
**Cohort:** A20-K4
**Path đã chạy:** lite

---

## Câu hỏi (≤ 200 chữ)

> Trên golden set 50 queries, mode nào thắng ở loại query nào (`exact` /
> `paraphrase` / `mixed`), và tại sao? Khi nào bạn **không** dùng hybrid
> (i.e. khi nào pure BM25 hoặc pure vector là lựa chọn đúng)?

- **Exact queries:** BM25 hòa/thắng Hybrid (96.7%) vì thuật ngữ verbatim khớp trực tiếp từ khóa.
- **Paraphrase queries:** Vector search giúp bắt ngữ nghĩa không cần từ khóa trùng khớp (sẽ vượt trội hơn hẳn khi dùng model đa ngữ như `bge-m3`).
- **Mixed queries:** Hybrid thắng tuyệt đối (100.0% vs BM25 97.0%, Vector 98.5%) nhờ RRF (k=60) tổng hợp ưu điểm cả hai.

**Khi KHÔNG dùng hybrid:**
- *Pure BM25:* Tra cứu mã định danh/SKU/tên riêng/mã lỗi log exact match, hoặc khi hạn chế tài nguyên CPU/latency.
- *Pure Vector:* Search đa phương tiện (image/audio), cross-language, hoặc mô tả ý tưởng không chứa từ khóa trùng.

---

## Điều ngạc nhiên nhất khi làm lab me

RRF (k=60) kết hợp cực kỳ hiệu quả mà không cần chuẩn hóa scale điểm số giữa BM25 và Vector.

---

## Bonus challenge

- [ ] Đã làm bonus (xem `bonus/`)
- [ ] Pair work với: _N/A_
