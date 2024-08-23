---
layout: post
title: Một vài công cụ train mô hình
categories: [data science]
author: qxnam
tags: [pytorch, tensorflow, IDE]
date:   2024-04-23
usemathjax: true
image: assets/images/docker/intro.png
description: 'Khi train mô hình deeplearning các bạn sẽ phải chuẩn bị dữ liệu và xây dựng mô hình, bài viết này mình sẽ chia sẻ 1 vài công cụ hữu ích giúp bạn tiết kiệm thời gian và dễ dàng train mô hình.'
published: true
---

Nếu các bạn đã từng train mô hình deeplearning thì chắc các bạn đã từng copy $1$ model về và tất nhiên model đó đã được tác giả vẽ nên kiến trúc. Vậy nếu các bạn tự tạo nên $1$ kiến trúc (hoặc `finetune`) bằng code thì sao? Có thể bạn sẽ khó để hình dung ra kiến trúc dạng biểu đồ từ những dòng code đúng không. Và để thực hiện train mình cũng phải viết pipeline và các hàm `loss`, thuật toán `optimizer` để tạo được bộ tham số tốt nhất. Hôm nay mình sẽ chia sẻ $1$ vài công cụ khá tốt để giúp các bạn dễ dàng thực hiện $1$ mô hình cho riêng mình mà không cần phải code quá nhiều. Oke, let's go!

À chờ chút, pipeline thường để train $1$ mô hình deep gồm:
- Load dataset, split ra thành bộ `train`/`validation`/`test`
- Load model, config hyperparameters
- Train model
- Plot biểu đồ đánh giá (`loss`, `accuracy`) trong quá trình train (có thể có hoặc không)

# <a href="https://www.torchstudio.ai/">TorchStudio</a>
<a id="torch_studio"></a>

Tìm hiểu $1$ chút thì đây là $1$ phần mềm open source được ông này <img src="/assets/tool_deep/photo_robin_lobel.jpg" alt="robin lobel" width="30" height="40
"> và dùng framework chính là <a href="https://pytorch.org/">pytorch</a>. Có thể xem đây như là giao diện đồ hoạ của pytorch.

Việc cài đặt các bạn cứ theo hướng dẫn của họ là được.

Mình sẽ thử demo $1$ đoạn xem thử như nào.

Đầu tiên vào giao diện sẽ là:
![load data](/assets/tool_deep/first.png)

Trông cũng xịn phết 😆

## Load dataset
<a id="load_dataset"></a>

Đầu tiên mình thấy chọn dataset, trên đó đều là những dataset mà pytorch cài sẵn, mình chỉ cần việc load về và dùng thôi. Ngoài ra mình cũng có thể tự custom dataset (GenericLoader) cho project. Các bạn cứ lên trang chủ đọc hướng dẫn là được. Nếu check chọn `code` kế bên thì hệ thống tự sinh ra source code load dataset này, việc còn lại là thêm đường dẫn đến data mình để trên máy. Và thực hiện tiếp 1 vài config thì dataset của mình đã được analysis như hình.
![custom dataset](/assets/tool_deep/load_data.png)

## Chọn và train mô hình
<a id="train"></a>

Sau khi xong phần dataset, bấm nút New Model (có hình dấu cộng trong hình lục giác) ở bên phải tab Dataset để thêm tạo một model mới.
TorchStudio có cung cấp vài model mẫu và cũng cho phép chọn các model có sẵn của torchvision.

Sau đó chỉnh lại `parameters` rồi train thôi. Kết quả sẽ được biểu diễn ở hình bên.

![custom dataset](/assets/tool_deep/train.png)

Sau khi train xong, có thể export model ra dưới dạng `TorchScript` hoặc `ONNX` nếu muốn.

# <a href="https://teachablemachine.withgoogle.com/train">TeachableMachine</a>
<a id="teachable_machine"></a>
Khác với `TorchStudio` chạy trên phần mềm tải về thì `TeachableMachine` chạy trên `drive`. Dữ liệu của bạn sẽ được tải lên drive để thực hiện.

Công cụ này dùng framework `tensorflow` để build mô hình.

Oke, giờ mình cũng thử thực hiện train 1 mô hình phân loại ảnh gồm 3 lớp `cat`, `dog`, `lion`.

## Load dataset
<a id="load_dataset_teach"></a>
Công cụ này cần bạn phải tự cho data vào có thể là dùng `camera` hoặc các file ảnh.
![custom dataset](/assets/tool_deep/teachable_load.png)

## Chọn và train mô hình
<a id="train_teach"></a>
Sau khi chuẩn bị dữ liệu xong, thì mình sẽ chỉnh 1 số `parameters` rồi thực hiện train.

Theo mình biết thì công cụ này sử dụng thuật
toán `KNN` (K-Nearest Neighbors) để
phân loại hình ảnh.

![custom dataset](/assets/tool_deep/train_teach.png)

ồ 🤓! con này vẫn ra `dog` và chính xác tuyệt đối luôn, quá đỉnh.

## Deploy model
<a id="save_teach"></a>
Cuối cùng là lưu model và lấy code triển khai bằng cách chọn `Export Model`

![custom dataset](/assets/tool_deep/save_teach.png)

#  Tổng kết

Vậy là mình đã giới thiệu cho các bạn biết đến $2$ công cụ hỗ trợ các bạn train nhanh $1$ mô hình deep với $2$ framework khác nhau trên $2$ nền tảng. 

Nó sẽ giúp các bạn phần nào thời gian để tạo cho mình $1$ mô hình nhanh chóng. Nhưng mình vẫn khuyến khích các bạn tự code pipeline train từ đầu đến cuối để nâng cao skill code cho mình và khả năng đọc code.

Chúc các bạn thành công!!!