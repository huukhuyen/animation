# CSS Transitions and Transforms

Bài viết giới thiệu về CSS transitions và CSS transforms: được sử dụng như là một cặp kết dính với nhau . Những thuộc tính này dùng chung với nhau thì sẽ giúp  tạo ra animation đơn giản với hiệu ứng, tương tác và chuyển động có thể thấy được cho người xem.
## CSS transitions: 
Transitions được xem như là dầu mỡ trong bánh xe của CSS transforms. Nếu không có transition , một yếu tố được chuyển đổi sẽ thay đổi đột ngột từ một trạng thái này sang trạng thái khác. Bằng cách áp dụng transition, bạn có thể kiểm soát sự thay đổi, làm cho nó mịn hơn.

Có hai thuộc tính được yêu cầu :

* Transition-property
* Transition-duration

Cách viết đầy đủ : 	 	
 	
`div {
  	transition: [property] [duration] [timing-function] [delay]; 	
 	}
`	

### transition-property (required)
Dùng để xác định thuộc tính sẽ được áp dụng hiệu ứng chuyển động.

Giá trị:

* none: không áp dụng cho thuộc tính nào hết
* all: áp dụng cho tất cả các thuộc tính
* (tên thuộc tính): margin, opacity, background,...

### transition-duration (required)

Dùng để xác định khoảng thời gian của hiệu ứng chuyển động.

`div {
  transition: all 3s;
}
`

demo: [http://codepen.io/nguyentb1412/pen/grgmWG](http://codepen.io/nguyentb1412/pen/grgmWG)

### transition-timing (optional)
Dùng để xác định hiệu ứng của quá trình chuyển đổi, bao gồm các hiệu ứng sau :
 ease: hiệu ứng khởi đầu chậm sau đó nhanh dần và kết thúc chậm. ( mặc định là hiệu ứng này )
 
* ease-in: hiệu ứng với một khởi đầu chậm rồi nhanh dần.
* ease-out: hiệu ứng với một khởi đầu nhanh rồi chậm dần.
* ease-in-out: hiệu ứng với khởi đầu chậm, sau đó nhanh dần và kết thúc chậm dần.
* linear: hiệu ứng có cùng một tốc độ từ lúc bắt đầu đến khi kết thúc
* cubic-bezier(n,n,n,n): xác định giá trị của hiệu ứng theo từng giai đoạn, giá trị xác định của từng giai đoạn chỉ có thể từ 0 đến 1.

`div {
  transition: all 3s ease-in-out;
}`

demo : [http://codepen.io/nguyentb1412/pen/BKQboK](http://codepen.io/nguyentb1412/pen/BKQboK)

### transition-delay (optional)

Dùng để xác định độ trễ của hiệu ứng chuyển động. Theo mặc định, transition sẽ bắt đầu ngay sau khi nó được kích hoạt (ví dụ: mouse hover).Tuy nhiên, nếu bạn muốn transition bắt đầu sau khi nó được kích hoạt, bạn có thể sử dụng thuộc tính transition delay.

`div {
  transition: all 3s 1s;
}`

demo: [http://codepen.io/nguyentb1412/pen/GZrWdy](http://codepen.io/nguyentb1412/pen/GZrWdy)

## CSS transforms:
Thuộc tính transform sẽ giúp chúng ta có thể di chuyển, xoay, phóng to... một thành phần trong trang web. Chúng ta có thể biến đổi thành phần đó theo dạng 2D hoặc 3D.
Transforms được kích hoạt khi một yếu tố thay đổi trạng thái, chẳng hạn như được mouse-hover hoặc mouse-click.

### Scale
Giá trị scale của thuộc tính transform cho phép chúng ta phóng to hoặc thu nhỏ đối tượng theo cả chiều ngang và chiều dọc.

`div {
  transition: transform 1s;
}
`

`div:hover {
  transform: scale(2);
}
`	

Demo: [http://codepen.io/nguyentb1412/pen/bpgqmm](http://codepen.io/nguyentb1412/pen/bpgqmm)

###Rotate: 
Rotate là một giá trị của transform, nó có thể làm quay vật thể với một góc được xác định theo chiều 2D hoặc 3D

`div {
  transition: transform 1s;
}`

`div:hover {
  transform: rotate( 1080 deg );
}`

Demo: [http://codepen.io/nguyentb1412/pen/QNdpzo](http://codepen.io/nguyentb1412/pen/QNdpzo)
###Translate
Giá trị translate, cho phép chúng ta dịch chuyển vật thể theo trục x và trục y một khoảng xác định.
div {
   	   transition: transform 1s;
	}
	div:hover {
 	   transform: translate(20px, 20px);
	}
Demo: [http://codepen.io/nguyentb1412/pen/YqNZBr](http://codepen.io/nguyentb1412/pen/YqNZBr)

###Skew
Giá trị skew cho phép chúng ta thực hiện việc quay nghiêng đối tượng theo một góc xác định, theo trục X hoặc trục Y hoặc cả trục X và trục Y.

`div {
  transition: transform 1s;
}`

`div:hover {
  transform: skewX(-20px);
}`

Demo: [http://codepen.io/nguyentb1412/pen/PNWpVa](http://codepen.io/nguyentb1412/pen/PNWpVa)

###Transform-origin
Transform-origin phải được dùng kèm với transform , nó dùng để xác định tâm của đối tượng. Mặc định: transform-origin: center center; ( hoặc 50% 50%).

`div {
 transform-origin: left top;
 transition: transform 1s; }`
		
`div: hover {
	transform: rotate(720deg);
}	`
	
Demo: [http://codepen.io/nguyentb1412/pen/KzaWJL](http://codepen.io/nguyentb1412/pen/KzaWJL)

###Kết hợp transform
Có thể kết hợp lại nhiều transform

`div {
 	 transform: rotate(90deg) scale(2) translateY(-50%) translateX(50%);
	}`
	
Demo: [http://codepen.io/nguyentb1412/pen/eZgvXN](http://codepen.io/nguyentb1412/pen/eZgvXN)

Example: 

[http://codepen.io/nguyentb1412/pen/dGRJee](http://codepen.io/nguyentb1412/pen/dGRJee)

[http://codepen.io/nguyentb1412/pen/mVwJKV](http://codepen.io/nguyentb1412/pen/mVwJKV)

