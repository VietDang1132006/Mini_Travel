# 🌍 Mini Travel App — Hướng dẫn chạy trên Google Colab

Ứng dụng web này được viết bằng **Streamlit** và public qua **ngrok**, giúp bạn chạy trực tiếp từ Google Colab mà **không cần thiết lập môi trường thủ công**.

---

## 🚀 Mục tiêu

* Chạy từng cell trong notebook `mini-travel.ipynb` trên Google Colab.
* Tự động tạo web app (Streamlit).
* Nhận **link public** để truy cập app (qua ngrok).

---

## 📋 Yêu cầu

* Có tài khoản [Google] để sử dụng **Google Colab**.
* Có tài khoản [ngrok] (miễn phí). Sau khi đăng ký, vào **Dashboard → Your Authtoken**, sao chép authtoken cá nhân.

---

## 🧩 Cách chạy

1. Mở **Google Colab** tại [https://colab.research.google.com](https://colab.research.google.com).
2. Tạo **notebook mới** (File → New notebook).
3. Mở file `mini-travel.ipynb` gốc của dự án này.
4. **Copy từng cell** từ notebook gốc vào Colab, **theo đúng thứ tự** (cell 1 → cell 2 → cell 3 → ...).

---

## ⚙️ Cách chạy từng cell

| Thứ tự cell | Nội dung                                      | Ghi chú                                        |
| ----------- | --------------------------------------------- | ---------------------------------------------- |
| **Cell 1**  | Cài đặt môi trường & thư viện                 | Không cần chỉnh sửa gì.                        |
| **Cell 2**  | Tạo / setup code chính của ứng dụng Streamlit | Không cần chỉnh sửa gì.                        |
| **Cell 3**  | Kết nối ngrok & chạy Streamlit app            | ⚠️ **Thay dòng authtoken bằng token của bạn.** |
| **Cell 4**  | (nếu có) xử lý logic hoặc thông báo kết thúc  | Tuỳ nội dung notebook.                         |

### 🔧 Cụ thể cho cell 3:

Trong cell 3 sẽ có đoạn như sau:

```python
ngrok.set_auth_token("YOUR_NGROK_AUTHTOKEN")
```

👉 **Hãy thay** `YOUR_NGROK_AUTHTOKEN` bằng token cá nhân bạn lấy từ trang ngrok dashboard.

---

## 🔐 Đăng nhập (Login bắt buộc)

Khi mở web app (link ngrok public), **ứng dụng sẽ yêu cầu đăng nhập** trước khi truy cập nội dung.

* **Tài khoản mặc định (đã cấu hình sẵn trong notebook):**

  * **Username:** `user`
  * **Password:** `123`
  * **Note:** `Bấm login 2 lần để chuyển trang`
  
Người dùng **bắt buộc** phải nhập đúng username và password để vào app.

> **Lưu ý bảo mật:** Đây chỉ là cấu hình mặc định để demo. Tuyệt đối **không** để thông tin đăng nhập mặc định trên môi trường public lâu dài. Nếu muốn deploy thực tế, thay đổi username/password hoặc tích hợp hệ thống xác thực an toàn (OAuth, secret manager, v.v.).

---

## 🌐 Kết quả

Sau khi chạy **toàn bộ các cell**, ở cuối cùng notebook sẽ in ra URL public của ngrok, ví dụ:

```
Public URL: https://xxxx-xx-xx-xx.ngrok-free.app
```

→ **Bấm vào link đó**, ứng dụng **Mini Travel App** sẽ mở trực tiếp trong trình duyệt. Ứng dụng sẽ hiển thị màn hình đăng nhập yêu cầu nhập `user` / `123`.

---

## 🧠 Lưu ý

* Colab sẽ **tạo lại môi trường sạch** mỗi khi bạn khởi động lại runtime — nên mỗi lần muốn chạy lại, chỉ cần copy notebook và làm lại đúng thứ tự.
* Link ngrok chỉ **tạm thời**, sẽ hết hạn sau khi Colab runtime tắt.
* Không chia sẻ authtoken ngrok hoặc mật khẩu mặc định công khai.
* Nếu gặp lỗi `Streamlit cannot start`, hãy chạy lại từ cell 1.

---

**🎉 Hoàn tất!**
Bạn đã có hướng dẫn rõ ràng: copy cell → chạy → thay authtoken → mở link → đăng nhập bằng `user` / `123` để vào app.
