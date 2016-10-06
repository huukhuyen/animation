
#Animations Keyframes và các framework animation

##Animations Keyframes


Thuộc tính @keyframes dùng để điều khiển diễn biến một hoạt động của thành phần theo nhiều thời điểm khác nhau , được dùng kèm với thuộc tính animation.
@keyframes gồm tên , các thời điểm và thuộc tính của animation.

~~~
@keyframes slide {
  0% {
    left: 0;
    top: 0;
  }
  50% {
    left: 244px;
    top: 100px;
  }
  100% {
    left: 488px;
    top: 0;
  }
}
~~~

Tiền tố @keyframes

@-moz-keyframes  /* Firefox */

@-o-keyframes  /* Opera */

@-webkit-keyframes  /* Safari and Chrome */

* animation-name : Ghi rõ tên của keyframes bạn muốn liên kết với các selector.
* animation-duration : Số giây hoặc mili giây hoàn thành một chuyển động animation.
* animation-timing-function : Loại chuyển động của animation.
* animation-delay : Chỉ định thời gian delay của animation.
* animation-iteration-count : Chỉ định số lần chuyển động của animation(number hoặc infinite | mặc định là 1).
* animation-direction : Chỉ định các animation có chạy theo chu kỳ ngược lại hay không (mặc định normal , ngược lại là alternate).
* animation-fill-mode : Chỉ định giá trị áp dụng cho selector khi animation kết thúc ( none, forwards, backwards, both).
* animation-play-state : Chỉ định các animation là running hoặc paused (mặc định running).

Demo: [http://codepen.io/nguyentb1412/pen/yOgqjv](http://codepen.io/nguyentb1412/pen/yOgqjv)

##Animate.css

[https://daneden.github.io/animate.css/](https://daneden.github.io/animate.css/)

demo : [http://codepen.io/nguyentb1412/pen/mVNLZa](http://codepen.io/nguyentb1412/pen/mVNLZa)

##Magic animation css3

[http://www.minimamente.com/example/magic_animations/](http://www.minimamente.com/example/magic_animations/)

Demo  : 

[http://codepen.io/nguyentb1412/pen/mPbEpr](http://codepen.io/nguyentb1412/pen/mPbEpr)

[http://codepen.io/nguyentb1412/pen/GZvRvY](http://codepen.io/nguyentb1412/pen/GZvRvY)

Example: 

[http://codepen.io/nguyentb1412/pen/BjKwxa](http://codepen.io/nguyentb1412/pen/BjKwxa)

[http://codepen.io/nguyentb1412/pen/gPMrBJ](http://codepen.io/nguyentb1412/pen/gPMrBJ)

[http://codepen.io/nguyentb1412/pen/PNKqqp](http://codepen.io/nguyentb1412/pen/PNKqqp)

[http://codepen.io/nguyentb1412/pen/jqaGLL](http://codepen.io/nguyentb1412/pen/jqaGLL)

##SVG
SVG là viết tắt của Scalable Vector Graphics (đồ họa vector mở rộng)

SVG được dùng để làm nền cho đồ họa vector trên Web

SVG có định dạng XML

Chất lượng ảnh SVG không bị ảnh hưởng khi phóng to, thu nhỏ hoặc thay đổi kích thước ảnh

Mỗi phần tử và thuộc tính trong files SVG đều linh động

SVG được khuyến nghị bởi W3C

###Ưu điểm : 
Vì là định dạng đồ họa vectơ, lợi điểm của SVG là khả năng hiển thị tốt ở mọi kích cỡ và độ phân giải. Với một kích thước tương tự, một tập tin SVG có thể chứa nhiều thông tin hơn là một tập tin định dạng nhị phân khác (GIF, PNG,...).

SVG là một chuẩn mở, nó cho phép việc tùy biến theo mục đích sử dụng một cách dễ dàng. Các hình ảnh SVG có thể được dễ dàng sửa chữa và phát triển sau này, khác với đồ họa mảng thường là sản phẩm cuối cùng của các xử lý ảnh, không chứa mã nguồn các lớp ảnh.

Các tập tin SVG ở dạng văn bảnå, việc chỉnh sửa có thể thực hiện bằng các trình soạn thảo đơn giản nhất.
###Nhược điểm : 
SVG là ngôn ngữ không được thiết kế để sửa chữa trực tiếp trên mã nguồn. Để tạo ra các hình ảnh SVG nói chung, cần dùng các công cụ hỗ trợ.

Dù SVG có thể là một lựa chọn cho hình ảnh của các trang mạng trong tương lai không xa, nó vẫn còn khá mới mẻ và cần sự hỗ trợ từ các trình duyệt mạng. Hiện nay Firefox đã hỗ trợ tương đối đầy đủ cho SVG, tuy nhiên Internet Explorer 8 và một số trình duyệt khác cần có plug-in đặt riêng lẻ.

Demo :

 [http://codepen.io/nguyentb1412/pen/reNbYE](http://codepen.io/nguyentb1412/pen/reNbYE)
 
 [http://codepen.io/nguyentb1412/pen/KzKOPo](http://codepen.io/nguyentb1412/pen/KzKOPo)

##SNAP SVG	
Thư viện JavaScript Snap.svg ra đời giúp cho việc làm việc với các tài sản SVG dễ dàng như jQuery làm việc với DOM.

[http://snapsvg.io/](http://snapsvg.io/)

Demo: 

[http://codepen.io/nguyentb1412/pen/VawJxo](http://codepen.io/nguyentb1412/pen/VawJxo)

[http://codepen.io/nguyentb1412/pen/QNbwrm](http://codepen.io/nguyentb1412/pen/QNbwrm)

[http://codepen.io/nguyentb1412/pen/dMomvj](http://codepen.io/nguyentb1412/pen/dMomvj)

[http://codepen.io/nguyentb1412/pen/dModgV](http://codepen.io/nguyentb1412/pen/dModgV)

[http://codepen.io/nguyentb1412/pen/vGOROa](http://codepen.io/nguyentb1412/pen/vGOROa)

[http://codepen.io/nguyentb1412/pen/grpvvz](http://codepen.io/nguyentb1412/pen/grpvvz)

[http://codepen.io/nguyentb1412/pen/pyJajq](http://codepen.io/nguyentb1412/pen/pyJajq)

