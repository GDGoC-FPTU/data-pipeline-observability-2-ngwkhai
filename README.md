[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=24112842&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student ID:** 2A202600671
**Name:** Nguyen Dinh Khai

---

## Mo ta

Bai lab nay xay dung mot pipeline ETL don gian cho du lieu san pham trong
`raw_data.json`. Pipeline thuc hien cac buoc: extract du lieu JSON, validate de
loai record khong hop le, transform category va gia giam 10%, sau do load ket
qua ra `processed_data.csv`. Phan observability duoc the hien bang log so record
duoc doc, so record hop le, so record bi loai va timestamp `processed_at`.

---

## Cach chay (How to Run)

### Prerequisites
```bash
pip install pandas pytest
```

### Chay ETL Pipeline
```bash
python solution.py
```

### Chay Agent Simulation (Stress Test)
```bash
python generate_garbage.py
python agent_simulation.py
```

---

## Cau truc thu muc

```
├── solution.py              # ETL Pipeline script
├── processed_data.csv       # Output cua pipeline
├── garbage_data.csv         # Du lieu rac dung cho stress test
├── experiment_report.md     # Bao cao thi nghiem
└── README.md                # File nay
```

---

## Ket qua

Pipeline doc 5 records tu `raw_data.json`, giu lai 3 records hop le va loai 2
records loi. Cac loi bi loai gom `price <= 0` va `category` rong. File output
`processed_data.csv` co cac cot `id`, `product`, `price`, `category`,
`discounted_price`, va `processed_at`.

Ket qua stress test cho thay agent tra loi dung hon voi clean data: voi
`processed_data.csv`, agent chon Laptop la san pham electronics co gia cao nhat.
Voi `garbage_data.csv`, agent bi anh huong boi outlier va chon Nuclear Reactor
gia 999999, day la ket qua sai ve mat ngu canh kinh doanh.
