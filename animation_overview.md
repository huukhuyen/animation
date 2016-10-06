

# Tổng quan animation

**Animation** (hay còn gọi là hiệu ứng) là tiến trình thay đổi hình dạng và tạo hiệu ứng di chuyển của các phần tử. 

CSS hỗ trợ rất nhiều hiệu ứng liên quan tới sự kiện chuyển động. Điển hình là transition và key-frames

Transition kết hợp với trigger ( hover, checked hoặc dùng js add/remove class ..) 

[https://css-tricks.com/almanac/properties/t/transition/](https://css-tricks.com/almanac/properties/t/transition/)

Dùng animation/key-frames có nhiều control hơn của các trạng thái khác nhau 

[https://css-tricks.com/snippets/css/keyframe-animation-syntax](https://css-tricks.com/snippets/css/keyframe-animation-syntax)

Ngoài ra, còn rất nhiều thư viện CSS và Javascript hỗ trợ animation để giúp nó trở nên dễ sử dụng, linh hoạt, uyển chuyển hơn. Tùy theo yêu cầu mà chúng ta chọn các thư viện phù hợp.

* Sử dụng animation.css có các function viết sẵn để xác định hiệu ứng của thẻ 
[https://daneden.github.io/animate.css](https://daneden.github.io/animate.css)

* magic animation: cũng tương tự như animation.js nhưng có các hiệu ứng đẹp và phong phú hơn nhiều. [http://www.minimamente.com/example/magic_animations/](http://www.minimamente.com/example/magic_animations/)
* CSShake : cũng tương tự như magic animation mà có các hiệu ứng khác [http://elrumordelaluz.github.io/csshake/#1](http://elrumordelaluz.github.io/csshake/#1)
* Dùng Canvas : sử dụng tọa độ viết bằng js để xác định position và hướng chuyển động. Đây được xem như là nền tảng về animation. Các framework sau này hầu hết kế thừa từ canvas nhưng sử dụng nhanh và tiện dụng hơn.
* SVG : là 1 graphics nổi tiếng được dùng như 1 image hoặc background-image,.. kết hợp với css để làm animation [https://css-tricks.com/using-svg/](https://css-tricks.com/using-svg/)
* CreateJS ( [http://www.createjs.com](http://www.createjs.com) ) : gồm có cái lib sau :
  + easelJS : sử dụng với html5 canvas 1 cách dễ dàng . 
  + tweenjs : là lib đơn giản để sử dụng trong Javascript. Nó được phát triển để tích hợp tốt với các thư viện easelJS, nhưng nó không phụ thuộc . Nó hỗ trợ thuộc tính object và CSS. API  đơn giản nhưng rất mạnh mẽ, làm cho nó dễ dàng để tạo tweens phức tạp bằng các chuỗi lệnh.
  + soundjs : làm việc dễ dàng và hiệu quả với các html audio.
  + preloadjs: quản lý assets
* Move.js: small lib tạo ứng dụng animation đơn giản, dễ dàng sử dụng hơn dùng transition [http://visionmedia.github.io/move.js/](http://visionmedia.github.io/move.js/)
* Collie : là một thư viện javascript giúp tạo ra hình ảnh động tối ưu hóa cao và game sử dụng HTML 5. Collie chạy trên cả PC và smartphone  sử dụng HTML 5  và DOM [http://jindo.dev.naver.com/collie/](http://jindo.dev.naver.com/collie/)
* Rekapi : là một thư viện hình ảnh động keyframe cho JavaScript. Nó cung cấp API cho xác định hình ảnh động keyframe và kiểm soát sự phát lại của hình ảnh động. [http://rekapi.com/](http://rekapi.com/)
* Snap.svg : ứng dụng tuyệt vời tạo ra sự tương tác, đồ họa ở mọi độ phân giải. Không những thế, các thư viện javascript làm việc các tài sản SVG dễ dàng như Jquery làm việc với Dom. [http://snapsvg.io/demos/](http://snapsvg.io/demos/)
* AliceJS: một lib nhỏ dùng để tạo ra chất lượng và hiệu ứng hình ảnh cao [http://blackberry.github.io/Alice/demos/index.html](http://blackberry.github.io/Alice/demos/index.html)
* Motio:  là một thư viện JavaScript nhỏ cho hình ảnh động dựa sprite đơn giản nhưng powerful . Có tùy chọn Motio jQuery plugin phiên bản có sẵn để custom. [http://darsa.in/motio/#!examples](http://darsa.in/motio/#!examples)
* AniJS :  là một thư viện hình ảnh động, cho phép thêm các chuyển động vào các yếu tố với các định dạng sau:If click, On Square, Do wobble animated To .container-box [http://anijs.github.io](http://anijs.github.io)

