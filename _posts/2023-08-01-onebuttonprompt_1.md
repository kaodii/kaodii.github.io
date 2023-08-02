---
title: Vô tận prompt chỉ với một cú click với OneButtonPrompt (P1)
categories:
- Hướng dẫn
- Extension hay
feature_image: "https://i.imgur.com/ICcTPmH.png"
indexing: false
comments: true
---

# Lời nói đầu
{:.no_toc}

Bạn quá lười viết prompt? Bạn muốn tạo ra thật nhiều prompt đa dạng mà không cần phải ngồi suy nghĩ? Bạn muốn test một model nhanh chóng bằng cách sử dụng đa dạng các prompt nhưng quá mất thời gian?

> Có làm thì mới có ăn, không muốn viết prompt mà còn muốn có ảnh đẹp thì chỉ có…

**ẤY VẬY MÀ CÓ THẬT ĐẤY!!!**

Nếu bạn muốn tạo prompt một cách tự động, nhanh chóng, đa dạng và **có thể kiểm soát ở một mức độ vừa phải**, hãy sử dụng extension **OneButtonPrompt** ✨

**NHẤP MỘT CÁI, RA MỘT PROMPT, NHẤP CÀNG NHIỀU, PROMPT CÀNG NHIỀUUUUU** 🤩

# Mục lục
* toc
{:toc}

# Tải extension

Như bao extension khác, extension này có sẵn trong kho của Automatic1111, bạn chỉ đơn giản là vào **Extensions** → Search **One Button Prompt** rồi cài đặt thôi! 😋

{% include figure.html image="https://i.imgur.com/QdFf2iK.png" caption="Cứ cài đặt bình thường như bao Extension khác" %}

# Dùng Extension

Ở Blog lần này, chúng ta sẽ chỉ nhắm tới chức năng cơ bản và hữu ích nhất của Extension, đó chính là **tạo prompt cho text2image**!

Sau khi cài đặt xong, để sử dụng được extension, bạn hãy vào mục **Script** rồi chọn **One Button Prompt**.

{% include figure.html image="https://i.imgur.com/SqJLZoQ.png" caption="Nó nằm ở phía dưới cùng của trang" %}

## Điều chỉnh độ phức tạp của prompt

Ở trên cùng, ta sẽ thấy thanh điều chỉnh độ phức tạp. Số càng lớn thì prompt sẽ càng phức tạp và chi tiết hơn, tất nhiên là cũng càng dài hơn. Nhưng theo như kinh nghiệm dùng của mình thì thấy cứ để độ phức tạp từ 5-7 là okay nhất, quá dài hay quá ngắn đều tạo ra những kết quả không tốt lắm. (Riêng tác giả của extension thì đề xuất dùng từ 3-7).

{% include figure.html image="https://i.imgur.com/VMPV8o0.png" caption="Số càng lớn, prompt càng phức tạp" %}

Khi độ phức tạp quá lớn, extension hay thêm những cụm từ ngẫu nhiên, và thậm chí là không liên quan gì vào prompt khiến kết quả không được đồng nhất và hỗn loạn:

{% include figure.html image="https://i.imgur.com/FlxCa0L.png" caption="fantasy Pastels artwork, intricate background, knee level shot of a Untidy Intense Bauhaus [Interstellar gas:Vine:3] of Mythology, Marble patterns, detailed with Crystal patterns, infused with ethereal color fairy tale, Giant Wasp den in background, [roots lake], at Twilight, equirectangular 360, Ultra Detailed, Cosy, Minimalism Art, natural lighting, Depth of field 100mm, Kodak portra, underpainting, sloppy strokes, High quality, pixiv, (art by Frank Auerbach:1.2) , (art by Terese Nielsen:0.8) , (art by Maruja Mallo:1.1)" %}

còn complexity quá bé thì. Ừm,… thì prompt nó ngắn gọn vầy nè 🤣

{% include figure.html image="https://i.imgur.com/ZFq0wq1.png" caption="art by Peter Elson, The Aura of Life" %}

Nếu bạn muốn tạo một bức ảnh bất kì, không kể thể loại, họa sĩ, phong cách, chủ đề,… nói chung là ngẫu nhiên hết mức thì đến đây là được rồi, ấn Generate là được. 

Nhưng nếu bạn muốn thêm thắt, điều chỉnh một chút cho prompt thì hãy tiếp tục nào!  (*￣3￣)╭

## Điều chỉnh nội dung prompt

Ở phía dưới thanh chỉnh độ phức tạp, bạn sẽ thấy các ô để chọn chủ đề. Bạn cứ việc chọn lần lượt từ trên xuống dưới.

### Subject Types

![aa](https://i.imgur.com/G0zbxBK.png)

Chủ đề chính của prompt sẽ được chọn ở đây, bạn có thể chọn một trong các thể loại có sẵn:

- **object**: Một vật thể ngẫu nhiên sẽ xuất hiện, có thể là nhà cửa, xe cộ,…
- **animal**: Động vật, có thể là những con vật thông thường hoặc con quái thú gì đấy
- **humanoid**: Người, nhân vật, khi chọn thì nó cũng ngẫu nhiên thêm các từ về trang phục luôn
- **landscape**: Phong cảnh thiên nhiên hoặc thành thị,…
- **concept**: Bối cảnh, ví dụ như bối cảnh cho một bộ phim, hoặc có thể là một trích dẫn từ một bài thơ hay bài hát nào đấy
- **all**: Ngẫu nhiên tất cả các thể loại trên

Khi chọn những thể loại như **object, humanoid** hay **concept** thì bên dưới sẽ ra thêm nhiều ô khác nhau để bạn tùy chỉnh cho chủ đề, ví dụ nếu bạn chọn **Humanoid** thì sẽ có thêm ô để chọn giới tính,…

### Artists

![aa](https://i.imgur.com/qqVfCLV.png)

Bạn muốn ảnh của mình được vẽ theo phong cách của họa sĩ nào? Hãy chọn phong cách và extension sẽ giúp bạn chọn ngẫu nhiên một hoặc vài họa sĩ theo phong cách ấy. 

Nếu không biết mình muốn gì, hãy chọn **all**. 

Nếu bạn biết phong cách mình cần là gì, hãy chọn phong cách bạn muốn.

Còn nếu bạn không cần thêm tên họa sĩ vào prompt, hãy chọn **none**.

### Type of image

![aa](https://i.imgur.com/YsCIpGp.png)

Bạn quá chán với các **từ chỉ kiểu ảnh** thông thường như **painting, photoshoot, picture**,… hãy tận dụng phần này để tạo ra vô vàn các style khác nhau. Nếu giải thích hết thì blog này sẽ thành cuốn Wiki mất nên mình điểm qua một vài cái thú vị nhé:

- **all**: ngẫu nhiên toàn bộ style đang có và thỉnh thoảng ra mấy cái dị lắm
- **all - force multiple**: ngẫu nhiên lấy ra 2-3 style
- **only other types**: cũng là chọn ngẫu nhiên nhưng mà là những style độc lạ
- **only templates mode**: lấy từ các prompt mẫu chuẩn chỉ, được lấy từ nhiều nguồn khác nhau như các promptbook, civitai,…
- **massive madness mode**: nồi lẩu thập cẩm, những style vừa độc lại dị
- …

Và còn khá nhiều style khác với vô vàn prompt kèm theo hứa hẹn đủ cho bạn mò mẫm cả ngày trời. 😁

Nếu muốn biết thêm về các style, bạn chỉ cần tải extension về và kéo xuống bên dưới xem hướng dẫn. Hay bạn cũng có thể xem hình mẫu của các style ở [**chỗ này**](https://github.com/AIrjen/OneButtonPrompt/blob/main/user_guides/prompt_generation_modes.md){:target="_blank"}.

### **One in X chance to use special image type mode (cứ X ảnh được tạo ra thì có một ảnh sẽ dùng prompt đặc biệt)**

![aa](https://i.imgur.com/9Jk2JRK.png)

Ủa cái gì đây ta. Bạn đang tạo ảnh và bùm, một lời nhắn xuất hiện: 

> Chúc mừng, bạn đã trúng thưởng vài cụm từ độc lạ và nó sẽ được thêm vào prompt của bạn!
> 

Đây là một kiểu gây bất ngờ của tác giả để thêm các cụm từ độc đáo cho prompt. Túm lại thanh này dùng để điều chỉnh xác suất mà bạn ~~trúng số~~, à nhầm, trúng prompt độc lạ. 

**Số càng lớn là xác suất càng nhỏ**, ví dụ số 3 nghĩa là trung bình 3 prompt được tạo ra mới có một prompt độc lạ. Còn 100 nghĩa là 100 prompt mới có 1 tấm chứa prompt độc lạ.

### **Overwrite subject (Ghi đè lên chủ đề)**

![aa](https://i.imgur.com/HN1eN5V.png)

Bạn thấy chủ đề quá ít và thứ bạn cần không có trong đó? Hãy sử dụng bất kì chủ đề mình muốn và điền vào phần Overwrite subject, nó sẽ ghi đè lên phần subject mà bạn đã chọn.

Nhưng để đạt được hiệu quả tốt nhất, bạn hãy điền vào những thứ gần với thể loại được chọn.

Ví dụ bạn muốn chọn chủ đề ghi đè là 

> “a long black hair girl wearing aodai” (một cô gái với mái tóc đen dài đang mặc áo dài)
> 

, hãy chọn subject là **humanoid** để prompt được tạo ra phù hợp hơn.

Và với ví dụ bên trên, nếu bạn tick vào ô **Smart subject**, nó sẽ có tính năng phân biệt những gì bạn nhập vào để không tạo ra sự trùng lặp. 

Ví dụ bên trên chúng ta có thêm **thông tin về mái tóc và trang phục**, extension sẽ tự nhận ra và không tạo ra thêm prompt về trang phục và tóc nữa.

![aa](https://i.imgur.com/fkCwtiF.jpg)

### Các ô còn lại

Khi dùng extension này thì ô prompt và negative prompt của Automatic1111 sẽ bị bỏ qua, Automatic1111 sẽ **chỉ sử dụng prompt và negative prompt được tạo ra bởi extension**. Do đó, các ô tiếp theo này rất quan trọng.

![aa](https://i.imgur.com/sAbo1QR.png)

- **Place this in front of generated prompt (prefix)**: những gì trong ô này sẽ được đặt lên phía trước của prompt. Ví dụ bạn muốn thêm các cụm như (masterpiece), (highquality:1.2),… vào trước prompt, hãy đặt nó ở đây!
- **Place this at back of generated prompt (suffix)**: ngược lại, những gì trong ô này sẽ được đặt phía sau prompt. Nếu bạn muốn thêm một vài prompt về phong cách nghệ thuật, ánh sáng, hay thậm chí là LoRA,… hãy thêm vào đây.
- **Use this negative prompt**: đây là nơi bạn đặt negative prompt vào!
- **Overwrite type of image**: ghi đè style hình ảnh.

Phối hợp các phần bên trên lại với nhau, bạn sẽ có được một câu prompt ưng ý đấy! ヾ(≧▽≦*)o

Ngoài ra còn có thêm ô để bạn **lọc ra các từ không mong muốn**

![aa](https://i.imgur.com/KlzFqZG.png)

- **Filter out following properties (comma seperated)**: lọc ra những từ bạn không muốn nó xuất hiện, ví dụ như nsfw, ugly, dog, horror,… Hãy ngăn cách chúng bằng dấu phẩy là được.

# Thực hành một chút nào 🥳

Giới thiệu toàn bộ cho mọi người biết thôi chứ thông thường mình cũng chả để tâm chỉnh nhiều như vậy đâu, vì tác dụng lớn của extension này là sự ngẫu nhiên mà đúng không, mặc dù đúng là nếu bạn nắm vững hơn thì sẽ dễ dàng tạo được prompt mình muốn hơn 😁

Rồi, vậy thì giờ bắt đầu nào! Mình đang muốn vẽ một bức ảnh “**một cô gái tóc xoăn ngắn mặc áo dài”** nhưng chưa biết prompt thêm cái gì nữa, hãy sử dụng extension!

Base prompt: 

> girl with curly short hair wearing aodai
> 

Đầu tiên hãy chỉnh sửa các thông số tạo ảnh. Sau khi chọn model, mình chỉnh size ảnh, sampler và step.

![aa](https://i.imgur.com/hxGqtmM.png)

Kế đó, hãy kéo xuống phần extension **OneButtonPrompt** của chúng ta!

**Độ phức tạp**, mình chọn tầm 5 là đủ.

**Chủ đề** mình muốn là ảnh nhân vật, nên mình chọn **humanoid**.

Mình không chắc chắn muốn dùng style của họa sĩ nào lắm, nhưng mà để tên họa sĩ vào sẽ hơi bị khó khống chế style khi random nên mình không chọn luôn.

**Type of humanoids** mình không biết nên chọn gì nên để **all**

Gender, tất nhiên là **female** rồi!

**type of image**: mình thích nên chọn digital art

 ![aa](https://i.imgur.com/Cb0S46v.png)

**Overwrite subject**: hãy điền base prompt của mình vào nào: ***“girl with curly short hair wearing aodai”***

**(prefix)**: cứ điền những gì bạn **muốn nó nằm ở phía trước prompt**. Mình thường hay dùng loRA theo cách **để trigger words ở phía trước và tên loRA ở phía sau**. Do model thường không hiểu áo dài nên mình **dùng thêm loRA áo dài** ở đây

**(suffix)**: điền những gì ở đằng sau prompt

**negative prompt**: tất nhiên là nếu bạn có sử dụng negative prompt thì hãy thêm vào nào!

![aa](https://i.imgur.com/QnoovEb.png)

**TẤT CẢ ĐÃ SẴN SÀNG, THỬ NGAY THÔI (/≧▽≦)/**

Và đây là kết quả của chúng ta!!!

{% include figure.html image="https://i.imgur.com/x3ZD7AA.png" caption="((best quality)) , ((masterpiece)) , (detailed) , (memorable picture:1.2) , (half body) , aodai, HDR, Cathode tube, underpainting, acrylic painting, Cold girl with curly short hair wearing aodai, Sepia filter, Accent lighting, Best quality, Arts and Crafts Movement,It's all coming back to me now, Monochromatic Rust filter, (nostalgia:1.2) , <lora:a0d4ivn:0.5>" %} 

{% include figure.html image="https://i.imgur.com/L5u1YPG.png" caption="(masterpieces:1.2) , (memorable picture:1.2) , (half body) , aodai, digital art, Unexpected Bantu girl with curly short hair wearing aodai, Junglecore, studio lighting, Light streaks, (nostalgia:1.2) , <lora:a0d4ivn:0.6>" %}

{% include figure.html image="https://i.imgur.com/z9T1S22.png" caption="((best quality)) , ((masterpiece)) , (detailed) , (memorable picture:1.2) , (half body) , aodai, Fuchsia background, Lightcore, Frilled girl with curly short hair wearing aodai, (nostalgia:1.2) , <lora:a0d4ivn:0.5>" %}

{% include figure.html image="https://i.imgur.com/cHdosfT.png" caption="((best quality)) , ((masterpiece)) , (detailed) , (memorable picture:1.2) , (half body) , aodai, Dollpunk, dripping White, High quality, inktober drawing, Grayscale, Health Goth Art, Bloom light, girl with curly short hair wearing aodai, Neogothic Art, otherworldly, (nostalgia:1.2) , <lora:a0d4ivn:0.5>" %}

# Một vài lưu ý khi sử dụng Extension OneButtonPrompt

- Đây là một extension khá “hòa đồng”, nó có thể sử dụng chung với rất nhiều tính năng và extension khác như highres fix, batch, ADetailer, ControlNet,…
- Nếu bạn sử dụng **batch size lớn hơn 1**, các hình ảnh được tạo ra **sẽ có chung prompt.** Do đó, nếu bạn muốn tạo nhiều ảnh với các prompt khác nhau, hãy **tăng batch count** hoặc dùng tính năng **Generate Forever**
- Không phải kết quả trả ra lúc nào cũng tốt, vì là ngẫu nhiên nên đôi khi Extension này hơi thêm thắt những thứ không cần thiết hoặc không liên hệ gì với nhau vào prompt. Nhưng theo mình thấy nó vẫn đáng giá để thử, biết đâu kết hợp các thứ tưởng chừng không liên quan đến nhau lại tạo ra siêu phẩm thì sao! Theo lời tác giả thì 1/5 lần sẽ tạo ra một prompt chất lượng.

# Lời kết

Extension này là một công cụ hữu ích cho chúng ta, những người không muốn dành thời gian quá nhiều cho việc viết prompt, thích sự ngẫu nhiên và sáng tạo. Chỉ với vài setting ban đầu, chúng ta đã có ngay công cụ “**Một nút ra một prompt**”, cứ cần tạo prompt thì nhấn một nút là được.

Extension này có có rất nhiều điều thú vị cũng như tùy chỉnh hay ho, như kết hợp run và upscale, hay thủ thuật áp dụng vào img2img và control net, hay tùy chỉnh wildcard để tạo ra prompt phù hợp với bản thân hơn,… Nhưng đó là quá dài để chúng ta có thể tìm hiểu vỏn vẹn trong một bài Blog. Hẹn mọi người bài viết phần tiếp theo cho extension này nhé!

Hoặc nếu bạn muốn tự mày mò nhiều hơn, hãy ghé thăm github và xem các bài hướng dẫn tận tình của tác giả!

# Tham khảo
- [Github Extension OneButtonPrompt](https://github.com/AIrjen/OneButtonPrompt){:target="_blank"}

**Như mọi khi, nếu thấy bài viết là hữu ích hãy chia sẻ nó với mọi người, cũng như nếu bạn có điều kiện có thể ủng hộ mình trong mục Donate để có thêm động lực viết thêm nhiều bài viết nữa.**

**Một lần nữa cám ơn mọi người đã ủng hộ Blog Stable Diffusion Cơ Bản. Hẹn gặp lại mọi người trong các bài viết tới!!!**