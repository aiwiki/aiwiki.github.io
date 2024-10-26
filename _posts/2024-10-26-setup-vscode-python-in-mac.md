---
layout: post
title: Hướng dẫn cài đặt visual studio code lập trình python trên macbook chip apple silicon (M1/M2/M3)
categories: [data engineer]
author: qxnam
tags: [setup, vscode, python, macOS]
date: 2024-09-19
usemathjax: true
description: 'Bài viết này sẽ cung cấp từng bước cụ thể để bạn có thể thiết lập môi trường phát triển Python hoàn chỉnh và hiệu quả trên máy Mac của mình.'
published: true
---

## Giới thiệu
**Visual Studio Code** là một trình soạn thảo mã nguồn miễn phí, mạnh mẽ và linh hoạt, được phát triển bởi Microsoft. Nó hỗ trợ nhiều ngôn ngữ lập trình, trong đó có Python, và cung cấp nhiều tiện ích mở rộng giúp tăng năng suất làm việc.

**MacBook** sử dụng chip Apple Silicon (M1, M2, M3) mang lại hiệu suất vượt trội và tiết kiệm năng lượng. Tuy nhiên, một số bước cài đặt có thể khác so với các máy Mac sử dụng chip Intel. Hướng dẫn này sẽ giúp bạn cài đặt VS Code và thiết lập môi trường Python một cách dễ dàng trên MacBook Apple Silicon.

## Yêu cầu hệ thống
Trước khi bắt đầu, hãy đảm bảo rằng bạn đáp ứng các yêu cầu sau:
- Máy MacBook chạy macOS (10.9 trở lên)
- Kết nối internet ổn định.

## Cài đặt thủ công
Cài đặt python trực tiếp từ trang chính thức của <a href="https://www.python.org/">python.org</a>.

### Bước 1: Cài đặt python 3.10.8 (khuyến khích)
Mở trình duyệt web và truy cập <a href="https://www.python.org/downloads/release/python-3108">https://www.python.org/downloads/release/python-3108/</a>

Bạn cuộn trang xuống dưới sẽ thấy được các loại nền tảng để cài python và click vào version dành cho macOS như hình để tải xuống.
![python-version](/assets/images/setup-python-on-mac/files-python.png)

File sau khi tải xong, đúp chuột vào biểu tượng để mở file cài đặt.
![python-download](/assets/images/setup-python-on-mac/python-download.png)

Step 1: Introduction, click `Continue`.
![install-1](/assets/images/setup-python-on-mac/install-1.png)

Step 2: Read Me, click `Continue`.
![install-2](/assets/images/setup-python-on-mac/install-2.png)

Step 3: License, click `Continue` > `Agree`.
![install-3-1](/assets/images/setup-python-on-mac/install-3-1.png)

![install-3-2](/assets/images/setup-python-on-mac/install-3-2.png)

Step 4: Khi bạn đồng ý cấp phép xong sẽ được chuyển thẳng qua `Installation Type`. Click vào `Install` để cài đặt.
![install-4-1](/assets/images/setup-python-on-mac/install-4-1.png)

Bạn cần nhập password hoặc xác thực vân tay để cấp phép cài đặt.
![install-4-2](/assets/images/setup-python-on-mac/install-4-2.png)

Bạn mở messenger check xem có em gái nào nhắn tin cho không còn rep kịp là nó cài xong 🤗.
![install-4-3](/assets/images/setup-python-on-mac/install-4-3.png)

Step 5: Oke nó cài xong sẽ tự mở nơi nó cài lên nha (bạn có thể tắt đi nếu muốn).
![install-5-1](/assets/images/setup-python-on-mac/install-5-1.png)

Khi bạn chọn `close` thì sẽ có 2 option để bạn chọn:
- `Keep` giữ lại gói cài đặt ở màn hình desktop.
- `Move to Trash` ném vào thùng rác cho bớt ngứa mắt 😏 (mình chọn cái này nha).
![install-5-2](/assets/images/setup-python-on-mac/install-5-2.png)

Vậy là mình cài xong python 3.10.8 rồi, giờ mình thử kiểm tra xem đã thật sự cài được chưa bằng lệnh này trên terminal nhé:
```bash
python3.10 -V # hoặc python3.10 --version
```
Kết quả như hình là okela nhé!
![check-python](/assets/images/setup-python-on-mac/check-python.png)

### Bước 2: Cài đặt visual studio code (vscode)
Bạn cũng tải và cài đặt VS Code trực tiếp từ trang chủ của Microsoft.
Mở trình duyệt web và truy cập https://code.visualstudio.com/Download. Click `Apple sillicon` như hình.
![vscode-home](/assets/images/setup-python-on-mac/vscode-home.png)

Ngồi check tin nhắn tiếp đi, hơn 100MB lận 🙃.

Oke xong rồi bạn nhấn đúp vào file để giải nén.
![vscode-app](/assets/images/setup-python-on-mac/vscode-app.png)

Di chuyển file vừa giải nén đó vào `Applications` bằng cách kéo thả. Vì mình đã làm trước đó nên lần này nó hiểu thị 2 cái (1 cái là shortcut)
![vscode-move](/assets/images/setup-python-on-mac/vscode-move.gif)

Bạn đúp chuột vào icon `.app` để mở `vscode` lên, đây là màn hình đầu tiên.
![vscode-ui](/assets/images/setup-python-on-mac/vscode-ui.png)

Nếu có thông báo như thế này thì cứ tick vào `Trust` > `Yes` nhé
![trust_author](/assets/images/setup-python-on-mac/trust_author.png)

Oke vậy là bạn đã hoàn thành việc cài đặt vscode.



### Bước 3: Cài đặt môi trường lập trình python lên vscode
Mình tạo 1 folder rồi mở không gian làm việc đó trên vscode nhé!
1. Tạo folder có tên `python-learning`
2. Phải chuột vào thư mục chọn `New Terminal at Folder`
3. Chạy lệnh mở folder trên vscode:
```bash
code .
```
![vscode-open-ws](/assets/images/setup-python-on-mac/vscode-open-ws.gif)

Hoặc bạn cũng có thể mở bằng cách mở folder trên `vscode`
![vscode-open-ws](/assets/images/setup-python-on-mac/open-ws-2.gif)

Cài đặt gói mở rộng hỗ trợ lập trình `python` bằng `extensions`
![extensions](/assets/images/setup-python-on-mac/extension.png)

Bạn tạo file `*.py` để thử chương trình đầu tiên nhé!
![vscode-create-file](/assets/images/setup-python-on-mac/create-file.gif)

Khi chạy file có 2 cách để chạy: 
1. Dùng lệnh như hướng dẫn trên (Khuyến khích dùng cách này nhé, vừa ngầu vừa dễ điều khiển phiên bản chạy)
```bash
python3.10 lession_01.py # hoặc python3 lession_01.py
```
Việc bạn dùng `python3.10` là để chỉ định đúng version 3.10 để chạy, nếu để `python3` vẫn chạy được nhưng nếu bạn cài nhiều version khác như 3.8, 3.9 thì có thể phiên bản mặc định là các version đó có thể gây lỗi do phiên bản cũ. (Ví dụ từ phiên bản 3.10 trở lên python hỗ trợ thêm `match - case` chức năng giống `switch - case` bên **c/c++**)

2. Dùng extensions `code runner`.
bạn cài extensions này vào giống cách cài extensions `python`.
![code-runner](/assets/images/setup-python-on-mac/code-runner.png)
Nhưng để chạy được thì cần phải config thêm 1 số thứ linh tinh nữa:
- Mặc định code runner chạy trên terminal
![code-runner-config-01.png](/assets/images/setup-python-on-mac/code-runner-config-01.png)

- Thay đổi cách gọi file python: Search từ khóa `Executor Map` > `Edit in settings.json`, thay đổi thông tin tại dòng chứa python như hình.
![code-runner-config-02.png](/assets/images/setup-python-on-mac/code-runner-config-02.png)

- Khi chạy chỉ cần ấn vào biểu tượng run như hình
![code-runner-run.png](/assets/images/setup-python-on-mac/code-runner-run.png)

## Cài đặt bằng homebrew
<a href="https://brew.sh/">Homebrew</a> là một trình quản lý gói (package manager) phổ biến trên macOS, giúp bạn dễ dàng cài đặt và quản lý các phần mềm, thư viện cần thiết cho phát triển phần mềm.

1. Mở Terminal
- Nhấn `Cmd + Space` để mở Spotlight Search.
- Gõ Terminal và nhấn Enter để mở ứng dụng Terminal.

2. Cài Đặt `Homebrew`
Trong cửa sổ Terminal, nhập lệnh sau và nhấn Enter:
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
![Homebrew](/assets/images/setup-python-on-mac/homebrew.png)

3. Cấu Hình PATH cho Homebrew
Sau khi cài đặt xong, bạn cần thêm Homebrew vào biến môi trường PATH để có thể sử dụng các lệnh của Homebrew từ bất kỳ đâu trong Terminal.

Nếu bạn sử dụng zsh (mặc định trên macOS Catalina trở lên), thêm dòng sau vào file `~/.zprofile`:
```bash
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv)"
```

Nếu bạn sử dụng bash, thêm dòng sau vào file `~/.bash_profile`:
```bash
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.bash_profile
eval "$(/opt/homebrew/bin/brew shellenv)"
```

4. Kiểm Tra Homebrew
![homebrew-ver](/assets/images/setup-python-on-mac/homebrew-ver.png)

5. Cài Đặt Python
Trong Terminal, nhập lệnh sau:
```bash
brew install python
```
Lệnh này cài đặt phiên bản Python mới nhất thông qua Homebrew.

## Môi trường ảo (venv)
Môi trường ảo là một công cụ để duy trì không gian riêng biệt cho một dự án với các phụ thuộc và các thư viện của nó ở một nơi. Môi trường này thì riêng biệt cho một dự án cụ thể và không ảnh hưởng đến các phụ thuộc của các dự án khác. Hiểu đơn giản thì nó như 1 bản sao từ python gốc mà mình cài đặt và mọi thay đổi trên `venv` sẽ không ảnh hưởng đến python gốc (nếu nhỡ cài thư viện sai gây lỗi trên venv thì xóa đi tạo lại để cài lại tránh bị hỏng trên python gốc)

Việc sử dụng môi trường ảo giúp bạn quản lý các thư viện và phụ thuộc cho từng dự án một cách hiệu quả, tránh xung đột giữa các dự án.

1. Sử dụng `venv` để tạo môi trường ảo:
```bash
python3[version] -m venv [name]
```
- [version] là version python muốn tạo venv
- [name] là tên venv tự đặt

2. Bật venv
```bash
source [name]/bin/activate
```

3. Tắt venv
```bash
deactivate
```

Việc bạn ghi rõ version sẽ tạo venv đúng với version đó (rất quan trọng trong việc triển khai hệ thống)
![venv-python](/assets/images/setup-python-on-mac/venv-python.png)

Cách chạy file khi dùng venv như bình thường
![venv-run](/assets/images/setup-python-on-mac/venv-run.png)

Vì `venv` là bản sao của python nên nó cũng khá nặng ký, nếu không dùng nữa có thể xóa đi, nếu push code lên github cũng nhớ dùng `.gitignore` để ẩn `venv` trước khi push

## Jupyter notebook
Jupyter Notebook là một ứng dụng web mã nguồn mở cho phép bạn tạo và chia sẻ tài liệu có chứa mã nguồn trực tiếp, phương trình, hình ảnh và chú thích văn bản. Nó là công cụ tuyệt vời cho việc phân tích dữ liệu, trực quan hóa, và xây dựng mô hình máy học.

Để cài đặt `jupyter notebook` thì bạn phải cài `python` trước đó. Và để tốt cho việc sử dụng mình nên tạo `venv` và dùng như 1 kernel chuyên biệt.

Mỗi cell trong notebook là 1 chương trình `python`.

1. Cài `extensions` 
![jupyter](/assets/images/setup-python-on-mac/jupyter.png)

2. Tạo file với phần mở rộng *.ipynb

3. Chọn kernel, nếu chưa config thì phải để venv tại cấp cao nhất (level 1) folder đang mở, hoặc cài đặt:
```bash
pip install ipykernel
python -m ipykernel install --user --name=my_jupyter_project --display-name "Python (my_jupyter_project)"
```

![jupyter](/assets/images/setup-python-on-mac/jupyter.gif)

Có 2 thành phần chính trong notebook:
- `code`: khối code python
- `markdown`: viết note định dạng <a href="https://www.ibm.com/docs/en/db2-event-store/2.0.0?topic=notebooks-markdown-jupyter-cheatsheet">markdown</a> (*.md) 

## Một số cài đặt thêm cho vscode
1. Login tài khoản github để lưu các cài đặt extensions mỗi khi reset vscode.
![vscode-signin](/assets/images/setup-python-on-mac/vscode-signin.png)

2. Cài đặt chế độ tự động lưu file mà không cần lưu trước khi run code.
![auto-save](/assets/images/setup-python-on-mac/auto-save.png)

## Một số phím tắt thường dùng
![Keyboard](/assets/images/setup-python-on-mac/Keyboard.png)

## Một số extension hay ho
1. background: dành cho mấy đứa wibu vừa code vừa ngắm loli
![bg](/assets/images/setup-python-on-mac/bg.png)

2. vscode-pdf: Vừa đọc paper vừa code
![pdf](/assets/images/setup-python-on-mac/pdf.png)

3. Material Icon Theme: Thêm biểu tượng cho file/folder cho dễ nhìn
![mater](/assets/images/setup-python-on-mac/mater.png)
![mater-icon.png](/assets/images/setup-python-on-mac/mater-icon.png)

cập nhật sau chứ buồn ngủ quá rồi ...

Vậy là mình đã hướng dẫn bạn cách thiết lập môi trường học lập trình rồi nhé. Chúc bạn thành công!