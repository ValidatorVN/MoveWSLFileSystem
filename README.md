# MoveWSLFileSystem

Dành cho bạn nào dùng WSL2 trên Windown 10.

1/ Check xem mình đã cài thành công WSL2 bằng CMD:

    wsl -l -v
    
    Name: Ubuntu
    Version: 2
    
2/ Tắt WSL đang chạy trước khi chuyển dữ liệu:
  
    wsl --shutdown
    
3/ Tạo 1 Folder backup bên ổ D, xuất dữ liệu ra theo đường dẫn:

    mkdir D:\backup
    wsl --export Ubuntu D:\backup\ubuntu.tar
    
4/ Chờ một lúc cho dữ liệu chuyển qua xong, phải chắc chắn đã thấy trong ổ D có folder Backup\ubuntu.tar

    wsl --unregister Ubuntu

Di chuyển dữ liệu:

    mkdir D:\WSL
    wsl --import Ubuntu D:\WSL\ D:\backup\ubuntu.tar
    
5/ Chuyển mặc định sử dụng root:

    cd $env:USERPROFILE\AppData\Local\Microsoft\WindowsApps
    ubuntu config --default-user equiman
    
Khởi động lại WSL:

    wsl --distribution Ubuntu
    
Chúc thành cơm....
