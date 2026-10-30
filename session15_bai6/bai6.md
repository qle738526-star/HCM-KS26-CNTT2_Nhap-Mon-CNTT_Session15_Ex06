## Folder
- 01_sensors_code: code cảm biến
- 02_reports_investor: báo cáo
- 03_partner_feedback: góp ý đối tác
- 04_private_env: file .env, chỉ trưởng dự án

## Hybrid workflow
- code ở máy local, push lên github, cloud backup thêm
- .env ghi vào .gitignore

## Channel
- #dev-sensors: code
- #bug-sensors: báo lỗi
- #investor-update: báo cáo
- #partner-device: đối tác

## Phân quyền
- trưởng dự án: Owner
- dev: Editor
- nhà đầu tư: Viewer
- đối tác: Commenter
- .env: không share, chỉ trưởng dự án

## Lỗi thành task
- lỗi ở #bug-sensors thì tạo task có người phụ trách và deadline

## Bàn giao
- đổi mật khẩu .env rồi Transfer Ownership

## Lỡ xóa folder sensors
1. Trash, Restore
2. không được thì nhờ admin khôi phục
3. vẫn không được thì git clone từ remote

## Code

### 1. hybrid workflow (git)
```bash
git init
git remote add origin https://github.com/greentech/sensors.git
git add .
git commit -m "them code cam bien"
git push -u origin main
```

### 2. .gitignore (không đưa .env lên git)
```
.env
```
# Bài 6 : Thiết lập Môi trường Làm việc Số cho Doanh nghiệp
### 3. .env.example (không có mật khẩu thật)
```
SENSOR_USER=
SENSOR_PASSWORD=
```

### 4. đọc mật khẩu từ .env (python)
```python
import os
from dotenv import load_dotenv

load_dotenv()
user = os.getenv("SENSOR_USER")
password = os.getenv("SENSOR_PASSWORD")

print("dang nhap cam bien voi", user)
```

### 5. khôi phục khi lỡ xóa folder sensors
```bash
git clone https://github.com/greentech/sensors.git
```
hoặc nếu máy local còn repo
```bash
git checkout -- sensors/
``` 