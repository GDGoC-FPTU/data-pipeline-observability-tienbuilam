[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=23572347&assignment_repo_type=AssignmentRepo)

# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** <tienbuilam@gmail.com>
**Name:** Bùi Lâm Tiến
**Student ID:** AI20K-0004

---

## Mo ta

Bài lab hướng dẫn xây dựng một ETL Pipeline cơ bản sử dụng Python và Pandas. Pipeline thực hiện việc đọc dữ liệu thô từ file JSON, tiến hành kiểm tra tính hợp lệ của dữ liệu, chuẩn hóa dữ liệu, cuối cùng lưu dữ liệu đã làm sạch vào file CSV. Đồng thời thực hiện báo cáo thí nghiệm mô tả sự ảnh hưởng của garbage data đối với phản hồi của AI Agent.

---

## Cach chay (How to Run)

### Prerequisites

```bash
pip install pandas
```

### Chay ETL Pipeline

```bash
python solution.py
```

### Chay Agent Simulation (Stress Test)

```bash
python agent_simulation.py --data processed_data.csv
python agent_simulation.py --data garbage_data.csv
```

---

## Cau truc thu muc

```
├── solution.py              # ETL Pipeline script
├── processed_data.csv       # Output cua pipeline
├── experiment_report.md     # Bao cao thi nghiem
└── README.md                # File nay
```

---

## Ket qua

Pipeline đã đọc toàn bộ dữ liệu thô từ file `raw_data.json`. Qua quá trình validation, pipeline giữ lại thành công 3 records hợp lệ, loại bỏ 1 record không hợp lệ, thực hiện transform và xuất file thành công ra `processed_data.csv`.
