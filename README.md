# 🖥️ Remote Command System

Hệ thống điều khiển và giao tiếp từ xa được xây dựng theo mô hình **Client–Server**, sử dụng **TCP Socket** để truyền dữ liệu giữa máy chủ và nhiều máy khách trong cùng hệ thống mạng.

Đây là **dự án nhóm** trong quá trình học lập trình mạng. Trong dự án, tôi phụ trách chính phần **Server**, bao gồm tiếp nhận kết nối, quản lý Client và xử lý dữ liệu gửi đến từ các máy khách.

---

## 📌 Giới thiệu dự án

Remote Command System là ứng dụng mô phỏng quá trình giao tiếp giữa một máy chủ trung tâm và nhiều máy khách.

Máy chủ có nhiệm vụ:

* Khởi tạo kết nối mạng.
* Chờ Client kết nối.
* Tiếp nhận dữ liệu từ Client.
* Xử lý yêu cầu.
* Gửi phản hồi về Client.
* Quản lý nhiều kết nối cùng lúc.

Mô hình tổng quát:

```text
                 ┌─────────────────┐
                 │                 │
                 │      SERVER     │
                 │                 │
                 └────────┬────────┘
                          │
                    TCP Socket
                          │
          ┌───────────────┼───────────────┐
          │               │               │
          ▼               ▼               ▼
    ┌──────────┐    ┌──────────┐    ┌──────────┐
    │ Client 1 │    │ Client 2 │    │ Client 3 │
    └──────────┘    └──────────┘    └──────────┘
```

---

## 🎯 Mục tiêu dự án

Dự án được thực hiện nhằm:

* Hiểu cách hoạt động của mô hình Client–Server.
* Làm quen với lập trình mạng bằng TCP Socket.
* Biết cách tạo Server và tiếp nhận kết nối từ Client.
* Thực hành gửi và nhận dữ liệu qua mạng.
* Hiểu cách quản lý nhiều Client.
* Rèn luyện kỹ năng xử lý lỗi kết nối.
* Làm quen với việc phát triển dự án theo nhóm.

---

## ✨ Chức năng chính

### Phía Server

* Khởi tạo Server bằng TCP Socket.
* Thiết lập địa chỉ IP và cổng kết nối.
* Lắng nghe yêu cầu kết nối từ Client.
* Chấp nhận kết nối từ nhiều Client.
* Nhận dữ liệu hoặc lệnh được gửi từ Client.
* Xử lý nội dung nhận được.
* Gửi phản hồi trở lại Client.
* Theo dõi trạng thái kết nối.
* Xử lý trường hợp Client ngắt kết nối.

### Phía Client

* Kết nối đến Server.
* Gửi dữ liệu hoặc yêu cầu đến Server.
* Nhận phản hồi từ Server.
* Hiển thị kết quả giao tiếp.

> Phần Client được thực hiện bởi thành viên khác trong nhóm. Phần đóng góp chính của tôi nằm ở phía Server.

---

## 🏗️ Kiến trúc hệ thống

Dự án sử dụng kiến trúc Client–Server.

```text
Client gửi yêu cầu kết nối
             ↓
Server chấp nhận kết nối
             ↓
Client gửi dữ liệu hoặc lệnh
             ↓
Server nhận và xử lý
             ↓
Server gửi phản hồi
             ↓
Client nhận kết quả
```

Trong mô hình này:

* **Server** là trung tâm tiếp nhận và xử lý dữ liệu.
* **Client** là phía gửi yêu cầu và nhận kết quả.
* **TCP Socket** đảm bảo dữ liệu được truyền theo kết nối ổn định và đúng thứ tự.

---

## 🔄 Luồng hoạt động

Quy trình hoạt động cơ bản của hệ thống:

```text
1. Khởi động Server
        ↓
2. Server mở cổng và bắt đầu lắng nghe
        ↓
3. Client gửi yêu cầu kết nối
        ↓
4. Server chấp nhận kết nối
        ↓
5. Client gửi dữ liệu hoặc lệnh
        ↓
6. Server nhận dữ liệu
        ↓
7. Server xử lý yêu cầu
        ↓
8. Server gửi phản hồi
        ↓
9. Client nhận kết quả
```

---

## 🛠️ Công nghệ sử dụng

| Công nghệ                  | Mục đích sử dụng                     |
| -------------------------- | ------------------------------------ |
| C#                         | Ngôn ngữ lập trình chính             |
| .NET                       | Nền tảng phát triển ứng dụng         |
| TCP Socket                 | Giao tiếp mạng giữa Server và Client |
| Client–Server Architecture | Kiến trúc hệ thống                   |
| Visual Studio              | Môi trường lập trình                 |
| Git                        | Quản lý phiên bản                    |
| GitHub                     | Lưu trữ mã nguồn                     |

---

## 📂 Cấu trúc dự án

```text
Remote-Command-System/
│
├── Server/
│   ├── Mã nguồn khởi tạo Server
│   ├── Quản lý kết nối Client
│   ├── Nhận dữ liệu
│   ├── Xử lý yêu cầu
│   └── Gửi phản hồi
│
├── Client/
│   ├── Kết nối đến Server
│   ├── Gửi dữ liệu
│   └── Nhận phản hồi
│
├── images/
│   ├── server-running.png
│   ├── client-connected.png
│   └── multiple-clients.png
│
└── README.md
```

> Cấu trúc thực tế có thể khác tùy theo cách tổ chức source code trong dự án.

---

## 🚀 Hướng dẫn chạy dự án

### Yêu cầu

Cần cài đặt:

* .NET SDK.
* Visual Studio hoặc IDE hỗ trợ C#.
* Git nếu muốn tải dự án từ GitHub.

### Bước 1: Tải dự án

```bash
git clone DUONG_DAN_REPOSITORY
```

### Bước 2: Mở dự án

Mở file solution bằng Visual Studio.

### Bước 3: Chạy Server

Chạy project Server trước.

Server sẽ:

* Khởi tạo Socket.
* Mở cổng kết nối.
* Chờ Client kết nối.

### Bước 4: Chạy Client

Chạy một hoặc nhiều Client.

Mỗi Client sẽ kết nối đến Server thông qua địa chỉ IP và cổng đã được cấu hình.

### Bước 5: Kiểm tra giao tiếp

Gửi dữ liệu hoặc lệnh từ Client và quan sát phản hồi từ Server.

---

## 📸 Hình ảnh minh họa

### Server đang hoạt động

```markdown
![Server đang hoạt động](images/server-running.png)
```

Ảnh nên thể hiện:

* Server đã khởi động.
* Địa chỉ IP hoặc cổng đang lắng nghe.
* Trạng thái chờ Client kết nối.

---

### Client kết nối thành công

```markdown
![Client kết nối thành công](images/client-connected.png)
```

Ảnh nên thể hiện:

* Client kết nối đến Server.
* Server thông báo có Client mới.
* Dữ liệu kết nối hoặc địa chỉ Client.

---

### Nhiều Client hoạt động cùng lúc

```markdown
![Nhiều Client kết nối](images/multiple-clients.png)
```

Ảnh nên thể hiện:

* Server đang quản lý nhiều Client.
* Các Client gửi dữ liệu.
* Server nhận và phản hồi.

---

## 👨‍💻 Vai trò của tôi

Đây là dự án được thực hiện theo nhóm.

Vai trò chính của tôi là:

**Server-side Developer**

Các phần tôi đã tham gia:

* Đóng góp ý tưởng xây dựng hệ thống.
* Tham gia phân tích mô hình Client–Server.
* Xây dựng phần Server.
* Khởi tạo TCP Socket phía Server.
* Thiết lập Server lắng nghe kết nối.
* Tiếp nhận kết nối từ Client.
* Nhận dữ liệu từ Client.
* Xử lý yêu cầu phía Server.
* Gửi phản hồi về Client.
* Hỗ trợ quản lý nhiều kết nối.
* Kiểm thử và sửa lỗi phần Server.
* Phối hợp với thành viên phụ trách Client.

Tôi không phụ trách toàn bộ hệ thống và không tự phát triển toàn bộ phần Client.

---

## 🧠 Kiến thức học được

Sau khi hoàn thành dự án, tôi hiểu rõ hơn về:

### TCP Socket

Quy trình phía Server:

```text
Tạo Socket
    ↓
Bind địa chỉ IP và cổng
    ↓
Listen
    ↓
Accept kết nối
    ↓
Receive dữ liệu
    ↓
Xử lý
    ↓
Send phản hồi
```

Quy trình phía Client:

```text
Tạo Socket
    ↓
Connect đến Server
    ↓
Send dữ liệu
    ↓
Receive phản hồi
```

### Mô hình Client–Server

Tôi hiểu được cách một Server trung tâm tiếp nhận và xử lý yêu cầu từ nhiều Client.

### Quản lý kết nối

Tôi có thêm kinh nghiệm xử lý:

* Client kết nối.
* Client ngắt kết nối.
* Lỗi truyền dữ liệu.
* Sai địa chỉ IP hoặc cổng.
* Server chưa được khởi động.
* Nhiều Client hoạt động đồng thời.

### Làm việc nhóm

Dự án giúp tôi rèn luyện:

* Chia nhỏ nhiệm vụ.
* Phân công phần Server và Client.
* Phối hợp khi tích hợp chức năng.
* Kiểm tra lỗi giữa hai phía.
* Trao đổi cách truyền và định dạng dữ liệu.

---

## ⚠️ Hạn chế hiện tại

Phiên bản hiện tại chủ yếu phục vụ mục đích học tập nên vẫn còn một số hạn chế:

* Chưa có cơ chế xác thực người dùng.
* Chưa mã hóa dữ liệu truyền qua mạng.
* Chưa có hệ thống ghi log hoàn chỉnh.
* Khả năng xử lý lỗi còn cơ bản.
* Giao diện chưa được tối ưu.
* Chưa triển khai trên môi trường Internet thực tế.
* Chưa có cơ chế giới hạn quyền thực thi lệnh.

---

## 🔮 Hướng phát triển

Trong tương lai, dự án có thể được phát triển thêm:

* Xác thực tài khoản trước khi kết nối.
* Phân quyền người dùng.
* Mã hóa dữ liệu truyền qua mạng.
* Bổ sung logging.
* Cải thiện giao diện.
* Quản lý Client theo danh sách.
* Hiển thị trạng thái online hoặc offline.
* Thêm lịch sử gửi và nhận dữ liệu.
* Cải thiện xử lý nhiều Client.
* Bổ sung cơ chế bảo mật khi thực thi lệnh từ xa.

---

## 📚 Mục đích học tập

Dự án được xây dựng nhằm thực hành các kiến thức:

* Lập trình mạng.
* TCP Socket.
* Mô hình Client–Server.
* Giao tiếp giữa các tiến trình.
* Lập trình phía Server.
* Quản lý kết nối mạng.
* Làm việc nhóm trong phát triển phần mềm.

---

## 👤 Thông tin cá nhân

**Trương Tuấn Dũng**

Sinh viên Công nghệ Thông tin
Trường Đại học Giao thông Vận tải Thành phố Hồ Chí Minh

**Vai trò trong dự án:** Server-side Developer

---

## 📄 Giấy phép

Dự án được xây dựng phục vụ mục đích học tập và nghiên cứu.
