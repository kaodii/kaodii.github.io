---
title: Cách sử dụng prompt trong Stable Diffusion
categories:
- Hướng dẫn
- Newbie
- Quick tips
feature_image: "https://i.imgur.com/vdDA7JO.png"
indexing: false
comments: true
---
<style>
r { color: Red }
o { color: Orange }
g { color: Green }
b { color: Blue }
</style>

# Lời nói đầu
{:.no_toc}

Prompt là một trong những thứ quan trọng nhất khi dùng các Generative AI như Stable Diffusion hay Chat GPT. Vậy thông thường Stable Diffusion sẽ hiểu prompt theo kiểu nào, viết prompt như thế nào cho hiệu quả, các prompt mẫu cho Stable Diffusion là gì? Hãy cùng tìm hiểu qua bài viết này nhé!

# Mục lục
* toc
{:toc}

# Prompt và Negative prompt

Prompt và [**Negative prompt**](https://docs.google.com/document/d/1EcMuz_vDYQhg6a4rjV35Y8uZQsS5GHymSJ69T8Gz5uA/edit#bookmark=id.8tyyl2e6hw3v) là 2 loại prompt dùng trong Stable Diffusion. **Prompt (lời nhắc)** là nơi mà bạn hướng dẫn cho Stable Diffusion tạo ra ảnh theo ý muốn. Còn **Negative prompt (lời nhắc ngược)** là nơi mà bạn điền những thứ không muốn Stable Diffusion tạo ra. 

Ví dụ bạn không thích có màu tím trong ảnh của mình, hãy viết ***“purple”*** vào Negative prompt.

**Negative prompt thật sự rất quan trọng, sử dụng Negative prompt hợp lý có thể tăng chất lượng của bức ảnh một cách mạnh mẽ.** 😋

{ví dụ bằng hình}

# Nhấn mạnh prompt

Nhấn mạnh prompt là một phương pháp phổ biến, và cũng rất hiệu quả để tạo ra các kết quả mong muốn. Muốn nhấn mạnh một từ hay cụm từ nào đó trong Stable Diffusion, hãy thêm **`()`** , còn muốn giảm nhẹ một từ, hãy dùng **`[]`**. Mỗi lần chồng một cặp ngoặc vào, từ đó sẽ được tăng/giảm 1.1 lần.

Bên cạnh đó, ta cũng có thể chủ động đặt trọng số cho từng từ bằng cách thêm trọng số bên trong ngoặc tròn, ví dụ `(human:1.4)` sẽ tăng trọng số của từ `human` lên 1.4 lần.

- `a (dog)` - tăng độ mạnh của từ `dog` lên 1.1 lần
- `a ((dog))` - tăng độ mạnh của từ `dog` lên (1.1 * 1.1) = 1.21 lần
- `a [dog]` - giảm độ mạnh của từ `dog` đi 1.1 lần
- `a (dog:1.5)` - tăng độ mạnh của từ `dog` lên 1.5 lần
- `a (dog:0.5)` - giảm độ mạnh của từ `dog` đi một nửa

Một lưu ý nhỏ là việc đánh trọng số trong ngoặc chỉ hữu dụng với ngoặc tròn () và không có tác dụng với ngoặc vuông `[]` . Do đó nếu muốn giảm trọng số với chỉ số cố định, hãy dùng cấu trúc như bên trên `a (dog:0.5)`

# Quy trình tạo ra một prompt “chuẩn”

## Hãy miêu tả có quy trình và kỹ lưỡng

Bạn muốn vẽ một ngôi nhà, nhưng nếu bạn chỉ nhập một keyword duy nhất là “house”, Stable Diffusion sẽ không biết được nó nên vẽ thế nào, ở góc nào, ngôi nhà kiểu Âu hay Á, ở làng quê hay thành thị. Từ đó sẽ tạo ra rất nhiều phiên bản ngẫu nhiên. Do đó muốn tạo ra một hình ảnh như thế nào, bạn hãy suy nghĩ và miêu tả nó rõ ràng nhất có thể, và tất nhiên là theo một trình tự cụ thể để làm cho việc viết prompt dễ dàng hơn!

Để build prompt chuẩn thì có nhiều cách, mỗi sách mỗi khác, nhưng mình hay dùng 5 thứ này để dễ nhớ:

### Thể loại

Bạn muốn vẽ tranh hay ảnh chụp, hay một bức tranh?

> professional digital painting of…
> 

### Chủ thể

Bạn muốn vẽ gì, hãy suy nghĩ và miêu tả bằng một câu ngắn và đầy đủ

> professional digital painting of **a beautiful girl wearing gorgeous wedding dress**
> 

### Thêm chi tiết

Bạn hãy nghĩ thêm các chi tiết cần thiết cho bức ảnh của bạn nào, bạn muốn cô ấy tạo dáng như thế nào, cười hay khóc, chi tiết trang phục như thế nào, background thế nào,…

> professional digital painting of a beautiful girl wearing a gorgeous wedding dress, **happy face, tears in eyes, full body, dress made of light fabric, standing in the studio**
> 

### Phong cách

Bạn cần bức ảnh theo phong cách gì, hay sử dụng style của họa sĩ hay nhiếp ảnh gia nào? Hãy thêm nó vào đây

> professional digital painting of a beautiful girl wearing a gorgeous wedding dress, happy face, tears in eyes, full body, dress made of light fabric, standing in the studio, **anime style, movie poster,** by Jeremy Lipking, by Alphonse Mucha
> 

### Chất lượng và Ánh sáng

Cuối cùng là thêm các chi tiết về chất lượng hình ảnh, mức độ tập trung chi tiết cũng như ánh sáng 

> professional digital painting of a beautiful girl wearing a gorgeous wedding dress, happy face, tears in eyes, full body, dress made of light fabric, standing in the studio, anime style, movie poster, **highly detailed, sharp focus, face focus, detailed eyes, studio lighting, backlighting**
> 

## Nhấn mạnh thứ bạn muốn

Bạn đã có một prompt chứa những điều bạn muốn rồi, nhưng kết quả vẫn chưa được hài lòng lắm, ví dụ như bạn muốn miêu tả khuôn mặt với `tears on eyes` nhưng vẫn không thấy nước mắt đâu, thế thì hãy nhấn mạnh cụm từ đó nhé!

> professional digital painting of a beautiful girl wearing a gorgeous wedding dress, happy face, **(tears in eyes:1.4)**, full body, dress made of light fabric, standing in the studio, anime style, movie poster, highly detailed, sharp focus, face focus, detailed eyes, studio lighting, backlighting
> 

Ừm có vẻ có nước mắt hơn rồi, nhưng do ta tạo ảnh với độ phân giải thấp quá nên nhìn hơi không đẹp lắm =))

Nếu bạn muốn tìm hiểu rõ hơn về cách viết prompt chuẩn, hãy tham khảo cuốn ebook này nhé: Prompt book Tiếng Anh hoặc Tiếng Việt (bản dịch bởi Hà Hải Nam).

## Hãy dùng Negative prompt

Negative prompt rất quan trọng!

Negative prompt rất quan trọng!

Negative prompt rất quan trọng!

Điều quan trọng phải nhắc 3 lần!

Nhiều người thường nghĩ chỉ cần prompt tốt và chi tiết là được, nhưng với các model Stable Diffusion, đặc biệt là model có base 1.5 hoặc 2 thì Negative prompt là một điều không thể thiếu nếu bạn muốn có được một bức ảnh đẹp!

Và thực ra thì bạn có thể dùng một negative prompt cho bất kì ảnh gì cũng được!

Khác với prompt mỗi ảnh mỗi khác, nếu bạn tìm được một negative prompt ưng ý, bạn có thể dùng nó để tạo ra bất kì bức ảnh nào mà không cần phải chỉnh sửa nhiều.

Và có một cách rất hiệu quả để dùng Negative prompt, đó chính là dùng Negative embedding. Bạn hãy tải các Negative embedding về và sử dụng chúng để đem lại hình ảnh đẹp hơn.

## Check keyword lạ

Một số keyword có thể bạn nghĩ nó hữu dụng nhưng thực ra thì không. Bạn có thể check trước bằng cách tạo ảnh chỉ có mỗi từ đó thôi và check xem nó có tạo ra thứ mình muốn không.

Ví dụ dùng perry platypus

Vì dụ dùng spiderman

Do đó, nếu bạn muốn biết keyword đó có được model hiểu không, hay độ mạnh của keyword đó như thế nào, cách đơn giản nhất là thử nghiệm. Một lần tạo ảnh không có keyword đó và một lần khác thêm nó vào, cộng với việc tăng giảm độ mạnh của (keyword:1.4).

## Tầm quan trọng của model (checkpoint)

Model khác biệt sẽ tạo nên kết quả khác biệt, và đôi khi là chẳng giống nhau tí nào. Do đó hãy chọn checkpoint với phong cách mà bạn muốn để đạt được kết quả ưng ý nhất nhé.

# Một số cách dùng prompt nâng cao

## BREAK

Bạn có biết rằng giới hạn số lượng từ trong prompt của Stable Diffusion là bao nhiêu không?

Ngắn gọn mà nói thì: VÔ HẠN

Nhưng thật tình mà nói thì prompt dài chưa chắc đã tốt, mà đa phần còn ảnh hưởng đến chất lượng của bức ảnh.

Stable Diffusion chia prompt (và cả Negative prompt) thành từng phần một, mỗi phần (chunk) bao gồm 75 tokens (hoặc bạn có thể hiểu là 75 từ cũng được). Do đó nếu bạn nhập nhiều hơn 75 tokens, Stable Diffusion sẽ chia nó thành nhiều chunk khác nhau và mỗi chunk có 75 tokens.

Ví dụ bạn prompt 100 tokens, prompt của bạn sẽ được chia ra làm 2 chunk, chunk 1 chứa 75 tokens và chunk 2 chứa 25 tokens.

Vậy tại sao ta cần phải hiểu điều đó?

Bởi vì trong mỗi phần, từ càng nằm ở đầu thì tác dụng của nó lên kết quả càng mạnh. Do đó nếu bạn prompt một từ nằm ở đầu chunk 2, nó sẽ có tác dụng mạnh hơn nằm cuối chunk 1.

Do ta không thể khống chế prompt sao cho từ ta muốn luôn nằm ở đầu chunk được, nên ta sử dụng một phương pháp đó là dùng từ BREAK (viết hoa y như thế này nhé) để tách ra một chunk mới.

Ví dụ nếu prompt bình thường với 100 token sẽ được chia thành 2 phần lần lượt là 75 và 25 tokens, nếu ta đặt từ BREAK phía sau từ thứ 60, prompt sẽ được tách thành 2 chunk, chunk 1 60 tokens, chunk 2 40 token. Từ đó ta có thể đảm bảo được từ ta cần luôn nằm ở đầu chunk để đem lại hiệu quả mạnh nhất.

Thế nhưng, lời khuyên của mình là hãy viết prompt thật kĩ và ngắn gọn là tốt nhất. Đúng là việc dùng BREAK sẽ giúp cho từ đầu của chunk sẽ có tác dụng mạnh hơn, nhưng nếu sử dụng quá nhiều BREAK sẽ làm cho prompt của bạn bị tách thành rất nhiều chunk, và càng về sau, prompt của bạn càng mất tác dụng.

Do đó bình thường cứ quăng các từ quan trọng lên đầu là được, đừng lạm dụng BREAK làm chi!

Chọn từ và viết prompt ngắn gọn vừa đem lại hiệu quả tốt, vừa giảm thời gian xử lý, vừa hạn chế nhiễu cho hình.

## Trộn nhiều keywords

Bạn muốn vẽ một bức tranh lai giữa một con bò và một con ngựa? Thay vì prompt “một con bò lai ngựa” - thứ mà không hẳn Stable Diffusion đã hiểu, có một cách giúp bạn điều khiển sao cho các step đầu model sẽ tạo ra ảnh con bò, sau đó các step sau sẽ tạo ảnh con ngựa ngay trên chính con bò đấy!

<gif>

Có 2 cách để bạn trộn keyword theo kiểu đấy:

### Cách 1: dùng cấu trúc [from:to:when]

Trong đó from và to là thứ bạn muốn thay đổi, và when là step bắt đầu sự thay đổi đó.

Ví dụ:

a picture of a [cow:horse:10] 

Nếu bạn chạy prompt với 20 step:

- 10 step đầu prompt sẽ là:  a picture of a cow
- 10 step sau (step 11 - 20), prompt sẽ là: a picture of a horse

Ngoài ra bạn có thể viết lại câu trên bằng % nếu không muốn nhập chính xác step thứ mấy

a picture of a [cow:horse:0.5]

- 50% step đầu sẽ là: a picture of a cow
- 50% step sau prompt sẽ là: a picture of a horse

Chú ý là cách này không dùng được với LoRA hay LyCORIS.

### Cách 2: dùng cấu trúc [A|B]

Trong đó A và B là các keyword mà bạn muốn trộn. Lưu ý cách này khác cách 1 là nó sẽ không thay đổi keyword ở một step bất kì mà xen kẽ thay đổi chúng.

Ví dụ:

a picture of a [cow|horse]

- Step 1: a picture of a cow
- Step 2: a picture of a horse
- Step 3: a picture of a cow
- …

Chúng sẽ xem kẽ qua lại cho đến khi đến step cuối cùng.

# Tham khảo prompt mẫu

Đây là một cách tối thượng mà chắc ai cũng đã từng làm qua, đó chính là đi tham khảo (copy =))) prompt ở các trang web và diễn đàn về dùng. Từ đó có thể rút ra các viết prompt hay cho chính bản thân mình.

Sau đây là một số trang web bạn có thể dùng để kiếm các prompt mẫu

CivitAI

Nơi đang model số 1 thì không thể thiếu prompt mẫu rồi, bạn hãy chọn model nổi tiếng và tìm hình ảnh mình thích và copy prompt thôi

prompt mẫu

Các keyword, magic word

Prompt Hero

Đây chỉ là ví dụ về một trang prompt nổi tiếng thôi, bạn có thể dùng bất kì trang nào mà bạn thích

Tools

Bạn có thể dùng các tool này để tham khảo về họa sĩ và phong cách vẽ tranh. Cách dùng rất đơn giản, chỉ cần download về và bật lên là được\

Prompt Pallette

[https://civitai.com/models/95839?modelVersionId=102355](https://civitai.com/models/95839?modelVersionId=102355)

SD Cheat Sheet

[https://github.com/SupaGruen/StableDiffusion-CheatSheet](https://github.com/SupaGruen/StableDiffusion-CheatSheet)

[https://stable-diffusion-art.com/prompt-guide/](https://stable-diffusion-art.com/prompt-guide/)

[https://aituts.com/stable-diffusion-prompts/](https://aituts.com/stable-diffusion-prompts/)

[https://prompthero.com/stable-diffusion-prompts](https://prompthero.com/stable-diffusion-prompts)

[https://www.reddit.com/r/StableDiffusion/search/?q=how long can a prompt be&restrict_sr=1](https://www.reddit.com/r/StableDiffusion/search/?q=how%20long%20can%20a%20prompt%20be&restrict_sr=1)