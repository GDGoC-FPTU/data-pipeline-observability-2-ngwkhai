# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** 2A202600671
**Name:** Nguyen Dinh Khai
**Date:** 2026-06-10

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Agent: Based on my data, the best choice is Laptop at $1200.0. | 9 | Du lieu da duoc validate, category da chuan hoa thanh Title Case, gia khong hop le va category rong da bi loai. |
| Garbage Data (`garbage_data.csv`) | Agent: Based on my data, the best choice is Nuclear Reactor at $999999. | 2 | Agent bi anh huong boi outlier cuc lon va khong nhan ra day la record bat thuong, nen cau tra loi sai ve ngu canh. |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Agent tra loi sai khi dung Garbage Data vi logic cua agent tin truc tiep vao
du lieu dau vao va chon san pham electronics co gia cao nhat. Trong
`garbage_data.csv`, record Nuclear Reactor co gia 999999 la mot outlier rat lon,
nen no lap tuc vuot qua Laptop mac du khong phai goi y phu hop cho nguoi dung.
Ngoai ra, bo du lieu rac con co duplicate ID, price sai kieu nhu "ten dollars",
record co null value va category thieu. Nhung van de nay lam agent kho tong hop
thong tin dang tin cay, co the sap xep sai, loc sai hoac dua ra ket luan dua
tren nhung record khong nen duoc su dung. Clean Data giup agent tra loi on dinh
hon vi du lieu da duoc loc theo rule ro rang truoc khi dua vao mo phong.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** Dong y. Prompt tot co the giup agent hieu cau
hoi, nhung neu knowledge base chua du lieu sai, thieu, trung lap hoac co outlier,
agent van se dua ra cau tra loi kem chat luong. Vi vay can uu tien lam sach,
validate va quan sat pipeline du lieu truoc khi toi uu prompt.
