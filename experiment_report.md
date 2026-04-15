# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** AI20K-2A202600004
**Name:** Bùi Lâm Tiến
**Date:** 15/4/2026

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Based on my data, the best choice is Laptop at $1200. | 9/10 | Dữ liệu đã được chuẩn hóa và loại bỏ điểm dị thường |
| Garbage Data (`garbage_data.csv`) | Based on my data, the best choice is Nuclear Reactor at $999999. | 1/10 | Dữ liệu chứa Outliers nghiêm trọng làm Agent tính toán sai |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Khi sử dụng dữ liệu rác, AI Agent dễ dàng bị cung cấp những thông tin sai lệch dẫn đến "ảo giác" hoặc tính toán sai lầm. Cụ thể trong dữ liệu lỗi:

1. **Outliers**: Có những sản phẩm không đúng thực tế như "Nuclear Reactor" với giá ảo ($999999). Agent không có kiến thức mặc định để tự từ chối mà dễ tin tưởng trỏ đến kết quả bất thường nhất.
2. **Null Values & Wrong Data Types**: Gây lỗi cho quá trình extract và tính toán logic, dẫn đến các thông tin quan trọng bị bỏ sót hoặc gộp sai.
3. **Duplicate IDs**: Gây trùng lặp vector và làm sai lệch thứ tự xếp hạng (retrieval ranking) khi đưa context vào Prompt.

Với nguyên lý "Garbage In, Garbage Out", một AI Agent có mạnh mẽ đến đâu nhưng truy xuất dựa trên dữ liệu dơ thì cũng sẽ sinh ra phản hồi vô nghĩa và không an toàn.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** Đồng ý.

Tôi hoàn toàn đồng ý. Prompt Engineering chỉ giống như một "bộ hướng dẫn", trong khi dữ liệu là "kiến thức lõi". Cho dù prompt có xuất sắc đến đâu, nếu dữ liệu nền tảng nhồi vào AI (thông qua RAG, context injection, hay training dataset) là những tài liệu chứa lỗi, trùng lặp và cực đoan, AI sẽ dùng chính dữ liệu sai đó để tổng hợp và hồi đáp lấp liếm sự thật. Chất lượng dữ liệu quyết định giới hạn trần của độ chính xác mà một AI Agent có thể đạt tới.
