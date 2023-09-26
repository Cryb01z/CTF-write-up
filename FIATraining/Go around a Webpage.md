# Go around a Webpage
# Author: nquangit
![Capture](https://github.com/Cryb01z/CTF-write-up/assets/144227142/6cbdee47-968e-4a31-8096-e6299226b41e)

# Link: https://hackerpage.fiahackingisfun.id.vn/

Coi source nhưng không có gì hết thế nên vào robots.txt coi xem sao

![2](https://github.com/Cryb01z/CTF-write-up/assets/144227142/06a89736-90fd-48ff-888e-81b0ff988780)

Thấy được 1 dir trông ổn áp. Trang này bắt phải login mới cho view nên tiếp tục view source

![5](https://github.com/Cryb01z/CTF-write-up/assets/144227142/bd7ba25a-2e0d-4992-a90d-7e4ffa54ff94)



![1](https://github.com/Cryb01z/CTF-write-up/assets/144227142/7078a5b3-8be6-480a-9798-45c34ad37d0a)


Ở source trang này có đề cập đến việc trang index.html đã được backup, thường thì trang backup sẽ thêm đuôi .bak

![6](https://github.com/Cryb01z/CTF-write-up/assets/144227142/6e9b864c-8df8-470f-8d6e-592af4b37257)

Sau khi view source cũng không thấy gì cả nhưng để ý số dòng của file source vẫn còn rất nhiều nên kéo dọc kéo ngang tìm tới tìm lui sẽ thấy được user/pass

![3](https://github.com/Cryb01z/CTF-write-up/assets/144227142/2b35892c-22ae-4b3c-8ddb-b14a4bc03dd9)

Nhưng pass đã bị hash mất tiu :(( nên xài crackstation để ra pass: https://crackstation.net/

![4](https://github.com/Cryb01z/CTF-write-up/assets/144227142/c6878c40-883d-4353-bb96-987d34a5140b)

Tìm được user/pass nhưng lại không thấy login ở đâu nên từ dir /Super_Secret_Page/ ta sẽ tìm thêm coi có những dir con nào của nó nữa không bằng cách xài tool: gobuster(https://www.kali.org/tools/gobuster/)

![8](https://github.com/Cryb01z/CTF-write-up/assets/144227142/2d3b1aef-42a7-434c-9f7a-58084e768c31)

Thấy có dir development. Truy cập vào và chỉnh value cookies thành enable sẽ thấy khung login
![10](https://github.com/Cryb01z/CTF-write-up/assets/144227142/9b298074-65ab-4bd9-9159-f318645702e6)
![14](https://github.com/Cryb01z/CTF-write-up/assets/144227142/9e33a38e-5f33-466f-adf7-6b0301c75858)
Ở phần Network ta sẽ có nửa flag


Chỉ FIA_Member mới có thể truy cập vào trang này nên ta sẽ xài 1 extension trên firefox: https://addons.mozilla.org/en-US/firefox/addon/user-agent-string-switcher/ để đổi user agent thành FIA_Member

![13](https://github.com/Cryb01z/CTF-write-up/assets/144227142/b363072f-6722-4514-89f9-41134cabdc3d)

Và đây là phần còn lại của flag, đem đi decode 
# Flag: FIA{G0_@round_@_web_s3rv3r_@nd_f1nd_the_S3cr3t}




