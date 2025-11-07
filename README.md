# 🌍 Mini Travel App — Hướng dẫn chạy trên Google Colab

Ứng dụng web này được viết bằng **Streamlit** và public qua **ngrok**, giúp bạn chạy trực tiếp từ Google Colab mà **không cần thiết lập môi trường thủ công**.

---

## 🚀 Mục tiêu
- Chạy từng cell trong notebook `mini-travel.ipynb` trên Google Colab.
- Tự động tạo web app (Streamlit).
- Nhận **link public** để truy cập app (qua ngrok).

---

## 📋 Yêu cầu
- Có tài khoản [Google](https://accounts.google.com/) để sử dụng **Google Colab**.
- Có tài khoản [ngrok](https://ngrok.com/) (miễn phí).  
  Sau khi đăng ký, vào **Dashboard → Your Authtoken**, sao chép authtoken cá nhân.

---

## 🧩 Cách chạy
1. Mở **Google Colab** tại [https://colab.research.google.com](https://colab.research.google.com).
2. Tạo **notebook mới** (File → New notebook).
3. Mở file `mini-travel.ipynb` gốc của dự án này.
4. **Copy từng cell** từ notebook gốc vào Colab, **theo đúng thứ tự** (cell 1 → cell 2 → cell 3 → ...).

---

## ⚙️ Cách chạy từng cell
| Thứ tự cell | Nội dung | Ghi chú |
|--------------|-----------|---------|
| **Cell 1** | Cài đặt môi trường & thư viện | Không cần chỉnh sửa gì. |
| **Cell 2** | Tạo / setup code chính của ứng dụng Streamlit | Không cần chỉnh sửa gì. |
| **Cell 3** | Kết nối ngrok & chạy Streamlit app | ⚠️ **Thay dòng authtoken bằng token của bạn.** |
| **Cell 4** | (nếu có) xử lý logic hoặc thông báo kết thúc | Tuỳ nội dung notebook. |

### 🔧 Cụ thể cho cell 3:
Trong cell 3 sẽ có đoạn như sau:
```python
ngrok.set_auth_token("YOUR_NGROK_AUTHTOKEN")
