# Hướng dẫn sử dụng
Download về  máy tính repo này tại vị trí thư mục  muốn sử dụng
```
git@github.com:todo1991/dev-wordpress-local.git
```

Tạo file .env và thay thế các giá trị nếu muốn
```
cd dev-wordpress-local
mv env-file .env
```
Khởi động docker compose và  kiểm tra truy cập
```
docker compose up -d
```
Để truy cập  với tên miền thì có thể thêm dòng sau vào file /etc/hosts
```
127.0.0.1 domain.com
```
Sau khi lưu lại có thể truy cập domain.com trên trình duyệt, do không có cấu hình ssl nên  chú ý truy cập qua http:// chứ không phải https://
Để chỉnh sửa code, do  file được docker ghi dưới user khác với user sử dụng nên cách đơn giản nhất là chmod 777 toàn bộ thử mục chứa code
```
sudo su
chmod -R 777 public_html/
```
# Hướng dẫn backup database của webiste
```
source .env && docker compose  exec mariadb mariadb-dump --databases ${MARIADB_DATABASE} -u${MARIADB_USER} -p${MARIADB_PASSWORD} > mariadb-dump-$(date +%F_%H-%M-%S).sql
```
