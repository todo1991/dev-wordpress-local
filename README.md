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
