Pentester xác định mục tiêu kiểm thử hệ thống:

<img width="915" height="384" alt="image" src="https://github.com/user-attachments/assets/157509a0-8de6-4e77-9c10-988a6dbdec27" />

<img width="915" height="356" alt="image" src="https://github.com/user-attachments/assets/0be66540-d1c4-402a-907a-3b3ddd0ed5ac" />

<img width="915" height="402" alt="image" src="https://github.com/user-attachments/assets/50e0c5d6-ad89-4b75-96b2-672445bec070" />

Pentester kiểm thử với WhatWeb ( công cụ phân tích website)
Lệnh whatweb http://192.168.100.242 sẽ xác định các thông tin về website như
công nghệ sử dụng, framework, máy chủ web, và các ứng dụng chạy trên web.

<img width="911" height="215" alt="image" src="https://github.com/user-attachments/assets/7f439fb8-4a16-4e5c-a17d-8316bfd70a89" />

Pentester kiểm thử với Nmap (Quét cổng và dịch vụ)
Dùng lệnh nmap -sV -O -p- 192.168.100.242 quét tất cả các cổng trên một hệ thống, xác định phiên bản dịch vụ các cổng mở và nhận diện hệ điều hành của hệ thống đích.

<img width="911" height="583" alt="image" src="https://github.com/user-attachments/assets/c78266fe-b3ad-4e8f-bfd8-8774e2e2da88" />

Pentester kiểm thử với BurpSuite Pro (Kiểm thử bảo mật web):
Quét lỗ hổng web đồng thời kiểm tra và phân tích các lưu lượng HTTP và tìm các lỗ hổng bảo mật web như SQL Injection, XSS, hoặc các vấn đề với xác thực.

Bước 1: Mở Burp Suite Pro

<img width="915" height="428" alt="image" src="https://github.com/user-attachments/assets/4682e179-dcff-41cb-965c-3fc3eca9cb0e" />

Bước 2: Khởi Tạo New Scan
Chọn địa chỉ cần quét: http://192.168.100.242

<img width="914" height="661" alt="image" src="https://github.com/user-attachments/assets/59142343-3ef8-4ba6-8620-fafa9da39a6c" />

Chọn Balanced:
Ưu điểm: Cân bằng giữa tốc độ và độ bao phủ, phát hiện nhiều loại lỗ hổng phổ biến.
Nhược điểm: Thời gian quét có thể lâu hơn so với Lightweight và Fast

<img width="909" height="737" alt="image" src="https://github.com/user-attachments/assets/d9ca3bed-aeaa-4e51-803d-745e62d8335f" />

Bước 3: Xem kết quả quét

<img width="915" height="396" alt="image" src="https://github.com/user-attachments/assets/14bf9dcd-2b00-48a2-80cb-8b015a7469a5" />

<img width="913" height="312" alt="image" src="https://github.com/user-attachments/assets/421491d0-9cdd-4024-ad74-5c56f4f68418" />

<img width="915" height="429" alt="image" src="https://github.com/user-attachments/assets/2802a791-22a6-4606-8f26-6cb243bf302c" />

<img width="912" height="524" alt="image" src="https://github.com/user-attachments/assets/80fd68f4-5af9-4b37-ae80-ddb0d7140810" />

Pentester phát hiện được các lỗ hổng nghiêm trọng:

<img width="904" height="574" alt="image" src="https://github.com/user-attachments/assets/01340e23-c292-402a-9a4a-191e0f55b1df" />

<img width="908" height="328" alt="image" src="https://github.com/user-attachments/assets/80ceaa2d-0301-4103-b462-a2b5468ccebb" />

Đây là lỗ hổng xảy ra khi một hệ thống truyền mật khẩu mà không mã hóa (cleartext) trong các yêu cầu mạng, chẳng hạn như qua HTTP mà không có HTTPS, hoặc qua các kết nối không bảo mật. Điều này có thể khiến mật khẩu bị rò rỉ trong quá trình truyền tải và dễ bị nghe trộm hoặc tấn công Man-in-the-Middle (MITM).
Giải pháp khắc phục:
-	Đảm bảo tất cả các kết nối truyền tải mật khẩu sử dụng giao thức HTTPS thay vì HTTP. Điều này bảo vệ dữ liệu khi truyền tải qua mạng.
-	Xác thực hai yếu tố.
-	Sử dụng các giao thức bảo mật an toàn như SSH để truyền tải thông tin.
Pentester xác định thêm 1 lỗ hổng là File path traversal

<img width="909" height="464" alt="image" src="https://github.com/user-attachments/assets/8ef1292d-3fe1-402a-85d2-ae8b486feb77" />

Đây là một lỗ hổng cho phép kẻ tấn công lợi dụng trong việc xử lý đường dẫn tệp để truy cập vào các tệp tin hoặc thư mục mà hệ thống không cho phép.

<img width="908" height="519" alt="image" src="https://github.com/user-attachments/assets/5bf6a12b-5c17-4603-9b97-40b81cdabfd5" />

Nhưng khi Burpsuite Pro gửi kiểm thử thì phản hồi từ hệ thống là 500 Internal Server Error nghĩa là mã lỗi HTTP cho biết rằng phía máy chủ web gặp sự cố khi cố gắng xử lý yêu cầu từ phía người dùng.

<img width="910" height="504" alt="image" src="https://github.com/user-attachments/assets/8bfc9788-6ffa-4297-9870-acb73897b612" />

Có thể thấy thì lỗ hổng không thể bị khai thác

<img width="909" height="423" alt="image" src="https://github.com/user-attachments/assets/05eb435a-416a-415a-a82e-eff3ed74c933" />

Tương tự như thế thì các lỗ hổng File path traversal đều không thể khai thác được, ngoài ra thì công cụ Burpsuite Pro cũng quét ra được 1 lỗ hổng khá nghiêm trọng là SQL Injection

<img width="916" height="645" alt="image" src="https://github.com/user-attachments/assets/ab74856d-f9d8-49ef-997d-15f45d1d255e" />

Pentester tiến hành vào Proxy sử dụng Open browser để kiểm thử

<img width="913" height="427" alt="image" src="https://github.com/user-attachments/assets/6c46fc0f-d670-4a6b-b66d-70524b5b7bc2" />

Đăng nhập vào trang login và nhập thử tài khoản admin và mật khẩu admin

<img width="915" height="570" alt="image" src="https://github.com/user-attachments/assets/d6288ead-5102-43a3-83bb-eb0ba40d2d95" />

Quay lại Proxy nhấp vào HTTP history chọn gói tin vừa kiểm thử

<img width="909" height="547" alt="image" src="https://github.com/user-attachments/assets/6c641ad8-5c40-4d67-8563-2daf2ac1f841" />

Đưa gói tin vào Intruder để tự động dò lỗ hổng dựa trên danh sách được đề xuất

<img width="911" height="615" alt="image" src="https://github.com/user-attachments/assets/8fa7fe36-6800-401d-840e-3c2ae930dffe" />

Add $ vào mật khẩu để tiến hành quét

<img width="915" height="488" alt="image" src="https://github.com/user-attachments/assets/0feec4e8-359d-486a-ad9b-18385faa24a2" />

Tương tự đưa vào $ vào tài khoản

<img width="911" height="482" alt="image" src="https://github.com/user-attachments/assets/35bc0063-d889-4c12-9d98-7176c53c8c96" />

Sử dụng Battering Ram 
Cơ chế hoạt động: 
-	Tấn công này sử dụng một tập hợp các payload (dữ liệu đầu vào) đã được chuẩn bị sẵn, đặt payload vào tất cả các vị trí. Khác với các kỹ thuật khác chỉ thay đổi một vị trí trong yêu cầu, “Battering Ram” sẽ đặt cùng một payload vào tất cả các vị trí payload đã được xác định trong cấu hình của cuộc tấn công.

<img width="906" height="310" alt="image" src="https://github.com/user-attachments/assets/12c02fb8-5a0e-41dd-9eef-31db03a48204" />

Vào Payloads chọn Payloads settings [Simple list] Load file sql_injection_payloads .txt kiểm thử Sql injection từ danh sách pentester đưa ra kiểm thử

<img width="908" height="470" alt="image" src="https://github.com/user-attachments/assets/99397ce5-80ce-4ac8-a992-e595cdaabf96" />

<img width="916" height="577" alt="image" src="https://github.com/user-attachments/assets/baf6999d-d923-4ce2-a752-acc3520cb36b" />

Thêm thành công file Load file sql_injection_payloads.txt vào Payloads settings kiểm thử
Click vào Start attack để tiến hành quét

<img width="915" height="386" alt="image" src="https://github.com/user-attachments/assets/b622d900-f8b2-4ff7-8c60-69f8314be792" />

Phát hiện Response received có thời gian phản hồi bất thường chỉ ra hệ thống đã xử lý các payload đặc biệt
Bên cạnh đó độ dài phản hồi Length cũng phản hồi khác biệt chỉ ra rằng payload đã thành công trong việc thay đổi logic của câu truy vấn SQL hoặc gây ra lỗi bất thường

<img width="912" height="471" alt="image" src="https://github.com/user-attachments/assets/92642e6e-6fb5-49eb-bb62-75463bf0df3a" />

Ở phản hồi của câu truy vấn ‘OR 1=1# xuất hiện chuyển đổi qua qua trang liên kết khác (này là http://192.168.100.242/home) nghĩa là trang câu truy vấn đã đăng nhập thành công vào hệ thống

<img width="906" height="590" alt="image" src="https://github.com/user-attachments/assets/f8072702-3d6f-43c5-9fe5-15a8d63ff1f7" />

<img width="904" height="510" alt="image" src="https://github.com/user-attachments/assets/1cc53703-6d02-40ec-ba35-2299b2784623" />

Dùng câu truy vấn vấn ‘OR 1=1# đăng nhập vào tài khoản mật khẩu

<img width="915" height="504" alt="image" src="https://github.com/user-attachments/assets/71309050-e101-48b3-8028-35e296f638ac" />

Đăng nhập thành công vào trang quản trị của hệ thống

<img width="915" height="305" alt="image" src="https://github.com/user-attachments/assets/b665c0fe-c71e-4417-a74b-96046099b080" />

Lỗ hổng SQL Injection thật sự đã tồn tại và bị khai thác thành công
Pentester tiến hành báo cáo và khắc phục sự cố trên:
Nguyên nhân dẫn đến lỗ hổng:
-	Ứng dụng không kiểm tra kỹ dữ liệu nhập vào từ người dùng
-	Không có quy định rõ ràng về định dạng và giới hạn giá trị của các trường dữ liệu.
Lỗ hổng SQL Injection thật sự đã tồn tại và bị khai thác thành công
Pentester tiến hành báo cáo và khắc phục sự cố trên:
Nguyên nhân dẫn đến lỗ hổng:
-	Ứng dụng không kiểm tra kỹ dữ liệu nhập vào từ người dùng
-	Không có quy định rõ ràng về định dạng và giới hạn giá trị của các trường dữ liệu.

<img width="908" height="656" alt="image" src="https://github.com/user-attachments/assets/08d84cdf-6603-4a8f-b2ae-7236b42d2fd0" />

<img width="913" height="623" alt="image" src="https://github.com/user-attachments/assets/f8add693-466e-48d2-bf45-5200dc0aa307" />

Đoạn code sử dụng dữ liệu đầu vào từ người dùng để tạo truy vấn SQL bằng cách nối chuỗi
$sql = "SELECT * FROM users WHERE email='{$credentials['email']}' AND password='{$credentials['password']}'";
Vấn đề:
Nếu $credentials['email'] hoặc $credentials['password'] chứa các ký tự độc hại (như ' OR 1=1#), truy vấn sẽ bị thao túng.
Dữ liệu từ $request được truyền vào mà không kiểm tra, xác thực. Sử dụng trực tiếp dữ liệu từ truy vấn trả về sau khi lấy dữ liệu từ câu lệnh SQL, đoạn code thực hiện kiểm tra và đăng nhập người dùng
foreach ($user as $userData) {
if ($userData->email === $getemail) { 
$this->guard()->loginUsingId($userData->id); 
return true; } }
Vấn đề:
Nếu hacker chèn payload để truy vấn trả về nhiều người dùng, việc lặp qua danh sách này có thể dẫn đến đăng nhập trái phép.
Sử dụng phương thức DB::select thay vì chuẩn hóa truy vấn
Phương thức DB::select không tự động áp dụng cơ chế bảo mật chống SQL Injection.
Giải pháp khắc phục:

<img width="914" height="698" alt="image" src="https://github.com/user-attachments/assets/bf9b8660-6faa-4af5-b3f9-9a4df7496628" />

Đoạn code hiện tại có khả năng chống SQL Injection nhờ sử dụng prepared statements thông qua DB::select. Các kỹ thuật như ' OR 1=1# sẽ không hoạt động.
Khi sử dụng DB::select với tham số ?, hệ thống sẽ tự động thoát (escape) các giá trị đầu vào.
Điều này ngăn chặn các ký tự đặc biệt như ', --, hoặc # gây ra SQL Injection.
Cách xử lý input:
Biến $getemail và $getpassword được truyền vào câu truy vấn dưới dạng tham số, không trực tiếp chèn vào chuỗi SQL.
Điều này bảo vệ đoạn code khỏi các tấn công kiểu ' OR 1=1# vì câu lệnh sẽ không được thực thi theo ý đồ của kẻ tấn công.
Kiểm tra lại hệ thống:

<img width="915" height="451" alt="image" src="https://github.com/user-attachments/assets/e6170455-4ab4-4ab9-a90b-555d876fed59" />

Đăng nhập thất bại

<img width="915" height="434" alt="image" src="https://github.com/user-attachments/assets/fd7e65e4-e744-4d36-b334-efb167629c54" />

=>	Khắc phục thành công
