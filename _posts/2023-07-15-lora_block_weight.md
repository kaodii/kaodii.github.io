---
title: Dùng LoRA hiệu quả với LoRA Block Weight
categories:
- LoRA
- Hướng dẫn
- Extension hay
feature_image: "https://i.imgur.com/ICcTPmH.png"
indexing: false
comments: true
---
# Lời nói đầu

Bạn train cho mình một LoRA nhưng không đẹp như người ta? Bạn thấy người khác cũng dùng cùng LoRA như mình nhưng hình tạo ra lại đẹp hơn? 

Một LoRA Sư nào đó đã từng nói: 

> “Chỉ có người dùng phế, không có LoRA phế!”

Trong bài viết này, mình sẽ giới thiệu với các bạn một công cụ không thể thiếu để sử dụng hết toàn bộ khả năng của một LoRA, đó là LoRA Block Weight.

# LoRA là gì

Trong thời gian gần đây, LoRA đã trở thành một công cụ mạnh mẽ không thể thiếu khi sử dụng Stable Diffusion vì nó có thể giúp bạn tạo ra những hình ảnh với phong cách ảo diệu mà model gốc không thể mang tới, hay tạo ra những nhân vật yêu thích mà model chưa được train với kích thước chỉ bằng 1/10 so với model hoàn chỉnh.

LoRA (LowRank-Adaptation of Large Language Model), có thể hiểu đơn giản như một mini model được train trên một tập dữ liệu nhất định. Khi hoạt động, nó sẽ trở thành các layer được "chèn" vào các layer của model gốc, khiến Stable Diffusion tạo ra nhân vật hay phong cách mà LoRA đó được train.

Có thể nói, LoRA đem đến cho bạn sức mạnh của một model với chi phí lưu trữ ít hơn so với một model chính hiệu.

Trong ví dụ bên dưới, 2 hình ảnh này được tạo bởi cùng một prompt để miêu tả một cô gái mặc áo dài. Nhưng một ảnh không dùng LoRA và một ảnh có dùng [LoRA áo dài](https://civitai.com/models/16766):

|---
| ![hehe](https://i.imgur.com/9tpdYu1.png) | | ![hehe](https://i.imgur.com/pRQBxz1.png)
|:--:|:--:|:--:
| Không dùng LoRA, model không hiểu áo dài là gì | | Có dùng LoRA áo dài
|---


|---
| {% include figure.html image="https://i.imgur.com/7f4bt1m.png" caption="QR Momo 🧧" width="300" height="300" %} |  | {% include figure.html image="https://i.imgur.com/OiX5aP0.png" caption="QR Ngân Hàng 🧧" width="300" height="300" %}
|:--:|:--:|:--:
|  |  |  
|---

# Cách khống chế LoRA theo từng Block

## Cách dùng thông dụng

Trước giờ cách thông thường khi dùng LoRA là gì? Đó chính là dùng cú pháp như sau:

***<lora:lora_name:weight>***

Nhưng nếu đi sâu hơn một chút về LoRA, bạn sẽ thấy LoRA - một mini model - không phải chỉ có một cục weight như thế. Thực tế, LoRA được chia thành 17 phần (block), bao gồm:

|---
| 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 | 17 
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-
| BASE | IN01 | IN02 | IN04 | IN05 | IN07 | IN08 | MID | OUT03 | OUT04 | OUT05 | OUT06 | OUT07 | OUT08 | OUT09 | OUT10 | OUT11 
|---
{:.mbtablestyle}

Và với LyCoris thì còn nhiều hơn nữa, tận 26 blocks.

Điều đó có nghĩa gì?  

> Chúng ta không chỉ có thể điều chỉnh một **weight chung**, mà có thể điều chỉnh toàn bộ 17 blocks của LoRA theo các weight khác nhau, và trên lý thuyết, mỗi một cách phối đều có thể cho ra một kết quả riêng biệt.

## Tại sao cần quan tâm đến các block?

> Ừm thì cũng ghê gớm đấy, nhưng ai quan tâm chứ, cứ dùng LoRA như bình thường thôi không được sao?

![ye.jpg](https://i.imgur.com/AUAU7HF.jpg)

Đối với LoRA, các block khác nhau có chức năng khác nhau, chẳng hạn như block khởi tạo thường ảnh hưởng đến cấu trúc các thành phần của LoRA, trong khi block cuối thường ảnh hưởng đến chế độ màu (color hue), hay block giữa thường ảnh hưởng đến tông màu (color tone). Do đó việc điều chỉnh weight của từng block sẽ quyết định đến kết quả.

Ví dụ như việc thay đổi weight của các block về cấu trúc có thể giúp bạn tạo ra nhân vật giống mẫu hơn, hoặc tăng giảm độ sắc nét của làn da, thay đổi nét vẽ, hoặc thay đổi weight của các block về màu sắc giúp thay đổi độ sáng, tối của ảnh, tông màu đậm nhạt,…

## Cách thay đổi weight từng block

Với bản LoRA mặc định trên AUTO1111, bạn hoàn toàn có thể điều chỉnh tay toàn bộ các weight theo cú pháp sau:

***<lora:lora_name:weight chung:weight riêng cho từng block>***

vd: ***<lora:Doraemon_lora:0.7:0,0,1,0,0,1.3,0.7,1,0,0.1,1,0.4,1,0,0,0,0>***

Hmm, có vẻ hơi nhức đầu rồi!     o(￣┰￣*)ゞ

Trên thực tế, điều chỉnh như thế là không ổn vì điều chỉnh chi tiết từng block một như thế không đem lại hiệu quả rõ rệt. Nếu bạn để ý thì 17 block của LoRA được chia thành 3 nhóm chính là BASE, IN, OUT. Do đó, để có hiệu quả rõ rệt, chúng ta phải điều chỉnh toàn một cụm các block chứ không nên điều chỉnh lẻ tẻ từng block như thế.

ví dụ: để chỉ sử dụng các **block IN** và không dùng các block khác, ta sẽ set 7 block đầu với weight là 1 và tắt toàn bộ các block khác bằng cách gán weight là 0. Ví dụ:

***<lora:Doraemon_lora:0.7:1,1,1,1,1,1,1,0,0,0,0,0,0,0,0,0,0>***

Tuy nhiên, cách làm này vẫn quá rườm rà và đau não rồi! Do đó mình sẽ giới thiệu một extension giúp bạn làm công việc trên một cách gọn gàng hơn!

# Extension LoRA Block Weight

## Cài đặt

Extension **LoRA Block Weight** giúp bạn thay đổi thông số block của LoRA một cách hiệu quả hơn.

Để cài đặt extension này, bạn vào mục Extension của AUTO1111, tìm kiếm **LoRA Block Weight** sau đó cài đặt. 

## Cách dùng

Để sử dụng extension, bạn chỉ cần chọn Active và thêm các alias (thường thì extension sẽ load các alias mặc định lên nên không cần quan tâm lắm)

![Untitled](https://i.imgur.com/UKOsBVb.png)

Cấu trúc của LoRA khi dùng extension vẫn là

***<lora:"lora name":weight chung:weight riêng cho từng block>***

nhưng lúc này thay vì phải gán từng weight một cho từng block, extension này hỗ trợ bạn set tham số dễ dàng hơn bằng cách đặt “biệt danh (alias)” cho từng nhóm weight. Hiện tại, extension có sẵn các nhóm sau:

> NONE:0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0 \\
ALL:1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1 \\
INS:1,1,1,1,0,0,0,0,0,0,0,0,0,0,0,0,0 \\
IND:1,0,0,0,1,1,1,0,0,0,0,0,0,0,0,0,0 \\
INALL:1,1,1,1,1,1,1,0,0,0,0,0,0,0,0,0,0 \\
MIDD:1,0,0,0,1,1,1,1,1,1,1,1,0,0,0,0,0 \\
OUTD:1,0,0,0,0,0,0,0,1,1,1,1,0,0,0,0,0 \\
OUTS:1,0,0,0,0,0,0,0,0,0,0,0,1,1,1,1,1 \\
OUTALL:1,0,0,0,0,0,0,0,1,1,1,1,1,1,1,1,1 \\
ALL0.5:0.5,0.5,0.5,0.5,0.5,0.5,0.5,0.5,0.5,0.5,0.5,0.5,0.5,0.5,0.5,0.5,0.5
> 

Khi đó bạn chỉ cần thêm alias vào là được. Ví dụ

***<lora:Doraemon_lora:0.7:MIDD>***

Ngoài những alias có sẵn, bạn cũng có thể tự tạo cho mình các alias yêu thích và lưu lại chúng vào extension này và sử dụng.

![melma.png](https://i.imgur.com/c0VQGKY.png)

## XYZ Plot cho LoRA Block Weight

Như mọi khi, để có thể so sánh các kết quả một cách tiện lợi nhất vẫn là XYZ plot. Extension này hỗ trợ sẵn một XYZ Plot cho riêng mình. 

Để sử dụng nó, bạn hãy mở mục **XYZ Plot của Extension (Không phải XYZ Plot của AUTO1111)**, chọn XYZ plot và điền các thông số vào để chạy.

![Untitled](https://i.imgur.com/bZZc5MV.png)

Ở phần LoRA, bạn chỉ cần thêm XYZ vào sau weight là được

<lora:Doraemon_lora:0.7:**XYZ**>

Riêng mình chủ yếu chỉ so sánh Original Weights thôi vì nó giúp ta nắm bắt nhanh nhất ở Block nào thì LoRA hoạt động như ý nhất. Tất nhiên ngoài ra còn có nhiều thông số khác mà bạn có thể tự tìm hiểu thêm (thực ra thì nó cũng có giới thiệu sơ trong [github của extension](https://github.com/hako-mikan/sd-webui-lora-block-weight)).

Ví dụ, khi sử dụng Extension trên cho LoRA áo dài, ta có kết quả sau:

![Untitled](https://i.imgur.com/Wb8g7gQ.jpg)

Có thể thấy rõ ràng rằng khi sử dụng các weight khác nhau cho các block sẽ ảnh hưởng đến chất lượng của bức ảnh. Ví dụ trên cho ta thấy có những nhóm block hoạt động tốt hơn các nhóm còn lại.

Sử dụng kĩ thuật này, ta hoàn toàn có thể tự tin khi sử dụng bất kì LoRA nào. 

> Nếu chỉ dùng weight không cho ra được kết quả ưng ý, ta hoàn toàn có thể tìm những block mà LoRA hoạt động tốt nhất và sử dụng chúng!

## Một số lưu ý khi sử dụng LoRA Block Weight

- Nhớ check nút Active để enable extension nhé
- Không dùng dấu cách, dấu ngoặc, dấu hai chấm,… giữa các phần trong dấu ngoặc < >. Nói chung cứ dùng mẫu như trên, đừng thêm các phần dư thừa, nếu không sẽ bị lỗi.
- Nếu Bạn bật cả XYZ Plot mặc định của AUTO1111 lẫn XYZ Plot của extension, nó sẽ ưu tiên của AUTO1111
- Hires. fix chưa được hỗ trợ trên extension này nên nếu bạn bật Hires. fix thì extension sẽ không hoạt động
- Khi dùng XYZ Plot của extension, bạn còn có thể sử dụng ZYX thay vì XYZ, điều này sẽ đảo ngược weight lại

> Dùng XYZ: 1,0,0,0,1,1,1,1,1,1,1,1,0,0,0,0,0 \\
> Dùng ZYX: 0,1,1,1,0,0,0,0,0,0,0,0,1,1,1,1,1

- Đừng set batch size lớn hơn 1, nếu không extension sẽ không hoạt động
- Hiện tại extension này bị lỗi nếu dùng chung với Composable Lora và Additional Networks. Do đó khi dùng extension này, hãy tắt 2 cái kia đi.

# Lời kết

LoRA là một bước tiến tuyệt vời đối với Stable Diffusion vì sức mạnh mà nó mang lại. Thế nhưng để sử dụng nó một cách tốt nhất thì Extension này là một cứu tinh giúp ta có thể nắm được hoàn toàn sức mạnh của LoRA. Hi vọng qua bài viết này bạn có thể có cho mình những kiến thức hữu ích để sử dụng LoRA mà không lo kết quả không ưng ý!

Như mọi khi, nếu thấy bài viết là hữu ích hãy chia sẻ nó với mọi người, cũng như nếu bạn có điều kiện có thể ủng hộ mình trong mục Donate để có thêm động lực viết thêm nhiều bài viết hay.

**Một lần nữa cám ơn mọi người đã ủng hộ Blog Stable Diffusion Cơ Bản. Hẹn gặp lại mọi người trong các bài viết tới!!!**