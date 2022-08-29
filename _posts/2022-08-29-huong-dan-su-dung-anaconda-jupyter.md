---
layout: post
title:  "Hướng dẫn cài đặt và sử dụng Anaconda & Jupyter notebook"
categories: [ Tutorial ]
tags: [tuturial, python, jupyter, anaconda]
author: goiliace
description: "Anaconda là một nền tảng phân phối miễn phí của ngôn ngữ lập trình Python và R cho tính toán khoa học, nhằm mục đích đơn giản hóa việc quản lý và triển khai gói. Nó có trên cả Windows, MacOS và Linux. 
Trong bài viết này chúng ta sẽ cùng nhau tìm hiểu về cách cài đặt Anaconda và Jupyter notebook trên máy windows"
---

## Nội dung

### 1. Anaconda là gì?

Anaconda là một nền tảng phân phối miễn phí của ngôn ngữ lập trình Python và R cho tính toán khoa học (khoa học dữ liệu, machine learning, xử lý dữ liệu lớn, phân tích dự đoán, v.v.), nhằm mục đích đơn giản hóa việc quản lý và triển khai gói. Nó có trên cả Windows, MacOS và Linux.

**Lợi ích của Anaconda:**

- Dễ dàng tải 1500+ packages về Python/R cho data science
- Quản lý thư viện, môi trường và dependency giữa các thư viện dễ dàng
- Dễ dàng phát triển mô hình machine learning và deep learning với scikit-learn, tensorflow, keras
- Xử lý dữ liệu tốc độ cao với numpy, pandas
- Hiện thị kết quả với Matplotlib, Bokeh
### 2. Hướng dẫn cài đặt Anaconda

Bạn vào <a href ="https://www.anaconda.com/">trang chủ Anaconda</a> hoặc click vào link <a href ="https://repo.anaconda.com/archive/Anaconda3-2022.05-Windows-x86_64.exe">này</a> để download. Sau đó mở file *Anaconda.exe* và chạy:

![](/assets/anaconda/anh_1.png)

Chọn 'Next' hoặc ấn Enter

![](/assets/anaconda/anh_2.png)

Chọn 'I Agree' hoặc ấn Enter

![](/assets/anaconda/anh_3.png)

Chọn Just Me hoặc All Users (nếu bạn muốn sử dụng cho tất cả các user trên máy) (ở đây tôi chọn Just Me) 

![](/assets/anaconda/anh_4.png)

Chọn vị trí cài đặt Anaconda tùy chọn hoặc giữ nguyên và nhấn Next

![](/assets/anaconda/anh_5.png)


Chọn **Add Anaconda 3 to my Path environment variable** nếu bạn muốn sử dụng Anaconda trên các command prompt (git bash, cmder, powershell,...) nhưng sẽ *có thể* ảnh hưởng đến các ứng dụng khác của bạn. Nếu chỉ cần sử dụng Anaconda Navigator hoặc Anaconda Command Prompt thì không chọn (ở đây tôi không chọn). Sau đó click vào 'Install' hoặc ấn Enter

![](/assets/anaconda/anh_5.png)

Đợi 2-3p cho nó cài đặt sau đó click 'Next' hoặc ấn Enter

![](/assets/anaconda/anh_7.png)

Click Finish và hoàn thành!
### 3. Hướng dẫn cài đặt và sử dụng Jupyter Notebook

#### Cài đặt Jupyter Notebook

Bạn có thể cài Jupyter trên Anaconda Navigator hoặc dùng lệnh sau trên command prompt nếu muốn sử dụng ở nhiều thư mục khác nhau:

```cmd
pip install jupyter notebook
```
#### Hướng dẫn sử dụng Jupyter Notebook
 
Nếu sử dụng Anaconda Navigator thì bạn mở ứng dụng và chọn Launch để chạy Jupyter Notebook.

![](/assets/anaconda/anh_8.png)

Nếu sử dụng lệnh `pip` thì bạn chọn thư mục cần mở Jupyter sau đó mở cmd và chạy lệnh sau:

```
jupyter notebook
```
![](/assets/anaconda/anh_9.png)

Giao diện khi mở jupyter notebook:

![](/assets/anaconda/anh_10.png)

Click vào new chọn Python3 để tạo 1 notebook mới

![](/assets/anaconda/anh_11.png)

Chọn Untitled để đổi lại tên khác

![](/assets/anaconda/anh_12.png)

Bạn có thể code trên các cell riêng biệt hoặc chọn Markdown để viết markdown cho code 

![](/assets/anaconda/anh_13.png)

### 4. Tổng kết

Trên đây là toàn bộ hướng dẫn sử dụng và cài đặt Anaconda & Jupyter notebook trên Windows. Nếu có thắc mắc hay góp ý gì bạn vui lòng để lại bình luận hoặc nhắn tin cho tôi tại <a href = "https://www.facebook.com/suzii.bad/"> đây </a>

### Nguồn tham khảo:
- <a href = "https://www.datacamp.com/tutorial/installing-anaconda-windows" >Installing Anaconda on Windows Tutorial - Data camp</a>
- <a href = "https://docs.anaconda.com/anaconda/install/"> Anaconda document installation - anacoda docs</a>
- <a href = "https://nttuan8.com/huong-dan-cai-dat-anaconda/"> Hướng dẫn cài đặt anaconda - nttuan</a>
