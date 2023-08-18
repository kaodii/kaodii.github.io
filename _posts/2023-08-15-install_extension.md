---
title: Cách cài đặt Extension trong Automatic1111
categories:
- Hướng dẫn
- Extension hay
- Quick tips
feature_image: "https://i.imgur.com/vdDA7JO.png"
indexing: false
comments: true
---

# Mục lục
* toc
{:toc}

# Extension là gì?

Extension là các chương trình được cộng đồng tạo ra và chia sẻ để việc sử dụng Stable Diffusion trở nên thuận tiện hơn. Không những thế, có những extension còn giúp Stable Diffusion khẳng định sức mạnh của mình, khai thác tối đa những gì mà Stable Diffusion có thể mang lại cho người dùng.

|---
| ![hehe](https://i.imgur.com/Cd4Ou2f.png) |  | ![hehe](https://i.imgur.com/7YmrkY3.png)
|:--:|:--:|:--:
| Dùng ControlNet |  | Thành phẩm
|---

💖

# Cách cài đặt Extension

Có 2 cách chính để cài đặt Extension, một là cài đặt thông qua Extensions Store của Automatic1111, hai là cài đặt trực tiếp từ Github

## Cài đặt thông qua Extensions Store

B1: Chọn Tab Extension

B2: Chọn Tab Available

B3: Nhấn nút Load from

B4: Tìm Extension mong muốn trong ô Search

B5: Nhấp Install và chờ đợi

B6: Trở về tab Installed

B7: Nhấn nút Check for update

B8: Nhấn Apply and restart UI

{% include figure.html image="https://i.imgur.com/VOok34F.png" caption="Cài đặt từ Extension Stores" %}

{% include figure.html image="https://i.imgur.com/pZYNpop.png" caption="Reload lại UI" %}

## Cài đặt trực tiếp từ Github

Tất nhiên cách này rủi ro hơn một chút so với việc cài đặt các Extension đã qua kiểm định trong Extensions Store

B1: Chọn Tab Extension

B2: Chọn Tab Install from URL

B3: Copy link github và paste vào ô URL for extension's git repository

B4: Nhấp Install và chờ đợi

B5: Trở về tab Installed

B6: Nhấn nút Check for update

B7: Nhấn Apply and restart UI

{% include figure.html image="https://i.imgur.com/jV0QRUv.png" caption="Cài đặt trực tiếp từ Github" %}

# Cài một số Extension đặc biệt

Sau khi thực hiện những bước trên, một số Extensions yêu cầu ta phải thêm một số bước nữa mới có thể sử dụng

## Cài đặt ControlNet

Sau khi cài đặt theo các bước bên trên, ta phải tải thêm các model weight cho ControlNet thì mới có thể sử dụng nó

B1: Truy cập đường dẫn đến [link các model trên HuggingFace](https://huggingface.co/lllyasviel/ControlNet-v1-1/tree/main){:target="_blank"}

B2: Tải các model files có đuôi ***.pth***

B3: Đặt các model bạn vừa tải vào thư mục ***stable-diffusion-webui\extensions\sd-webui-controlnet\models*** . Lưu ý là các file ***.yaml*** đã có sẵn nên chỉ cần tải các files ***.pth***

B4: Tại Tab ControlNet, nhấn nút Reload để tải các model lên

## Cài đặt Additional Networks

Để sử dụng Additional Networks, bạn phải thêm LoRA cho Extension thì mới có thể sử dụng. Và có 2 cách để làm điều đó.

**Cách 1:** Đặt các LoRA vào trong thư mục ***stable-diffusion-webui\extensions\sd-webui-additional-networks/models/LoRA***. Sau đó nhấn nút Reload để tải LoRA lên

**Cách 2:** Sử dụng thư mục LoRA của chính Automatic1111

- B1: Vào Setting
- B2: Kéo xuống tab Additional Networks
- B3: Tại ô đầu tiên Extra paths to scan for LoRA models, hãy điền đường dẫn của LoRA vào đây, thông thường nó sẽ là ***stable-diffusion-webui\models\Lora***

**Như mọi khi, nếu thấy bài viết là hữu ích hãy chia sẻ nó với mọi người, cũng như nếu bạn có điều kiện có thể ủng hộ mình trong mục Donate để có thêm động lực viết thêm nhiều bài viết nữa.**

**Một lần nữa cám ơn mọi người đã ủng hộ Blog Stable Diffusion Cơ Bản. Hẹn gặp lại mọi người trong các bài viết tới!!!**