# Hiểu về EEOS

## Hướng dẫn bằng ngôn ngữ dễ hiểu cho 2026 Foundation Edition

Tài liệu này là bản hướng dẫn đồng hành giúp người đọc tiếp cận dễ hơn với **Saafree EEOS White Paper — 2026 Foundation Edition**.

Tài liệu tương ứng với bản công bố khoa học công khai:

**ERC-007 — `7.0.1-public-release-derivative-2`**

Mục tiêu của tài liệu là giải thích vấn đề cốt lõi, chuỗi lập luận và đề xuất của Enterprise Evolution Operating System (EEOS) bằng ngôn ngữ ít học thuật hơn.

Đây không phải là một ấn bản khoa học, không thay thế sách trắng và cũng không phải một đặc tả độc lập. Khi cần độ chính xác về định nghĩa, mệnh đề, bằng chứng hay điều kiện khoa học, bản công bố khoa học chính thức vẫn là tài liệu có thẩm quyền.

Các ví dụ trong tài liệu này chỉ nhằm minh họa khái niệm. Chúng không phải bằng chứng khoa học cho phạm trù EEOS.

---

## 1. Vì sao vấn đề này trở nên quan trọng

Phần mềm doanh nghiệp truyền thống thường được xây dựng trên một ranh giới tương đối rõ: con người quyết định, còn hệ thống thực thi.

Ranh giới đó đang trở nên kém rõ ràng.

AI agent ngày nay có thể quan sát thông tin, diễn giải tình huống, đưa ra đề xuất, lựa chọn giữa nhiều phương án, sử dụng công cụ, phối hợp quy trình và trong một số trường hợp trực tiếp gây ra những thay đổi thực trong hệ thống doanh nghiệp.

Vì vậy, câu hỏi quan trọng không còn chỉ là:

**AI có làm được việc này hay không?**

Mà còn phải trả lời những câu hỏi khó hơn:

**Nó có được phép gây ra thay đổi cụ thể này hay không?**

**Thay đổi dự kiến có thực sự xảy ra không?**

**Hành động và kết quả có đúng với điều đã được cho phép hay không?**

**Doanh nghiệp có đủ bằng chứng để kiểm chứng chuyển đổi đó hay không?**

**Chuyển đổi cuối cùng có hợp lệ ở cấp doanh nghiệp hay không?**

**Nếu không hợp lệ thì phải xử lý như thế nào?**

Các câu hỏi này không hoàn toàn mới. Doanh nghiệp đã có hệ thống định danh và phân quyền, quy trình công việc, kiểm soát bảo mật, cơ chế phê duyệt, nhật ký kiểm toán, quản trị rủi ro và các quy tắc nghiệp vụ riêng của từng ứng dụng.

EEOS bắt đầu từ một quan sát cụ thể: khi con người và máy ngày càng cùng tham gia vào một hoạt động doanh nghiệp, việc chỉ kiểm soát từng chủ thể hoặc từng hệ thống riêng lẻ có thể chưa đủ. Doanh nghiệp còn cần quản trị chính những **chuyển đổi trạng thái doanh nghiệp** xảy ra xuyên qua chúng.

Sách trắng gọi hiện tượng đó là **Enterprise State Transition — EST**, tức một chuyển đổi trọng yếu từ trạng thái doanh nghiệp này sang trạng thái doanh nghiệp khác.

**EEOS tồn tại để làm cho sự thay đổi trạng thái doanh nghiệp trở nên có thể quản trị được.**

Nói đơn giản, một chuyển đổi trọng yếu trở nên có thể quản trị khi doanh nghiệp có thể xác định trước ý nghĩa và phạm vi được phép, ràng buộc nó bằng thẩm quyền phù hợp, thực thi trong phạm vi đó, kiểm tra tác động thực tế, kiểm chứng toàn bộ chuyển đổi ở cấp hệ điều hành và có thể giải trình đầy đủ những gì đã xảy ra.

---

## 2. Bắt đầu từ điều thực sự thay đổi: chuyển đổi trạng thái doanh nghiệp

Hãy hình dung một doanh nghiệp thay đổi điều khoản thanh toán của một nhà cung cấp từ 30 ngày thành 60 ngày.

Thay đổi đó có thể đi qua nhiều bước:

- một nhu cầu kinh doanh được xác định;
- một thay đổi được đề xuất và cấu trúc;
- ý nghĩa, phạm vi và các giới hạn của thay đổi được xác lập;
- thẩm quyền thực thi được cấp theo đúng quy định;
- hành động được thực thi;
- tác động thực tế xảy ra;
- hành động và kết quả được kiểm tra với điều đã được ràng buộc trước;
- toàn bộ chuyển đổi được kiểm chứng ở cấp hệ điều hành.

Từ góc nhìn doanh nghiệp, điều quan trọng không chỉ là một API đã được gọi hay một quy trình đã báo hoàn thành.

Điều quan trọng là doanh nghiệp đã thực sự chuyển từ một trạng thái có ý nghĩa sang một trạng thái khác.

EEOS gọi một thay đổi **trọng yếu** như vậy là **Enterprise State Transition — EST**, hay chuyển đổi trạng thái doanh nghiệp.

Ở đây, “trọng yếu” nghĩa là thay đổi đó tác động đến một thứ mà doanh nghiệp coi là thuộc phạm vi cần quản trị, chẳng hạn thẩm quyền, nghĩa vụ, rủi ro, năng lực hoặc bằng chứng, theo một quy tắc đã được xác định trước. Một lần thực thi bị chặn và không tạo ra tác động trọng yếu như vậy thì tự nó chưa phải EST.

Một EST có thể là chủ ý hoặc ngoài dự kiến, được phép hoặc không được phép, có lợi hoặc có hại.

Khái niệm EST chỉ nói rằng một thay đổi trọng yếu thực sự đã xảy ra. Nó chưa tự nói rằng chuyển đổi đó hợp lệ.

Sách trắng vì vậy phân biệt EST nói chung với **Authorized Enterprise State Transition — AEST**.

AEST không đơn giản là một hành động đã được phê duyệt.

Để một chuyển đổi được coi là AEST, ba điều phải cùng đúng:

- có **thẩm quyền hợp quy**, tức thẩm quyền được xác lập và giới hạn theo hệ quy định có hiệu lực;
- tác động trọng yếu thực sự đã xảy ra;
- tác động đó vẫn nằm trong **ý nghĩa, phạm vi và các ràng buộc đã được cho phép**.

Có thẩm quyền nhưng không có tác động thì chưa đủ.

Có tác động nhưng không có thẩm quyền hợp quy cũng chưa đủ.

Và nếu một thay đổi ban đầu được cho phép nhưng sau đó vượt khỏi phạm vi ý nghĩa hoặc các giới hạn đã được cho phép, phần vượt quá đó vẫn là EST nhưng không phải AEST.

Ví dụ, một chủ thể được phép cập nhật một hồ sơ khách hàng nhưng lại cập nhật 200 hồ sơ.

Thẩm quyền có tồn tại. Tác động thực tế cũng đã xảy ra.

Nhưng 199 hồ sơ còn lại vượt ngoài phạm vi được cho phép. Những thay đổi đó vẫn là EST, nhưng không phải AEST.

### Đường chính của một chuyển đổi được EEOS quản trị

Đối với một chuyển đổi có chủ đích và nằm trong phạm vi kiểm soát của EEOS, có thể hình dung đường chính như sau:

```text
Mục đích / ý định đã được cấu trúc
                ↓
     Hợp đồng chuyển đổi ràng buộc
                ↓
          Phê duyệt thẩm quyền
                ↓
          Thực thi có quản trị
                ↓
           Tác động thực tế
                ↓
 Kiểm tra hành động và kết quả
    so với hợp đồng chuyển đổi
                ↓
     Kiểm chứng ở cấp hệ điều hành
                ↓
 Xác định chuyển đổi hợp lệ / không hợp lệ
                ↓
           Học từ kết quả
                ↓
        Tổng hợp và báo cáo
                ↓
        Phê duyệt thu hồi quyền
                ↓
 Đóng vòng / xác lập vị thế tiếp theo
```

**Phê duyệt thẩm quyền** là ranh giới phê duyệt của con người kích hoạt phạm vi thẩm quyền có giới hạn mà chuyển đổi đã được lựa chọn được phép tiến hành trong đó. Bước này không có nghĩa **Hợp đồng chuyển đổi ràng buộc** tự nó cấp thẩm quyền thực thi; việc cho phép thực thi theo thẩm quyền vẫn là một bước riêng (xem mục 4).

Đây là đường chính của một chuyển đổi có chủ đích nằm trong phạm vi kiểm soát của EEOS.

Các EST ngoài dự kiến, trái phép hoặc phát sinh ngoài đường điều khiển vẫn có thể xảy ra. Những thay đổi đó phải được đưa trở lại phạm vi quản trị thông qua quan sát và **nhận thức thực tại**, nhưng **quan sát không phải là một bước hậu-thực-thi bắt buộc của đường chuyển đổi được quản trị nói trên**.

---

## 3. Có khả năng làm không đồng nghĩa với có thẩm quyền làm

Một trong những cách dễ nhất để hiểu sai AI agent là đánh đồng điều nó **có thể làm** với điều nó **được phép làm**.

Giả sử một AI agent phụ trách mua sắm về mặt kỹ thuật có thể tạo đơn mua hàng, gửi cho nhà cung cấp, cập nhật hệ thống ERP và kích hoạt bước chuẩn bị thanh toán.

Những năng lực kỹ thuật đó không trả lời được liệu agent có **thẩm quyền hợp quy** để thực hiện từng hành động trong từng hoàn cảnh cụ thể hay không.

Thẩm quyền có thể phụ thuộc vào:

- giá trị giao dịch;
- đơn vị kinh doanh;
- loại nhà cung cấp;
- khu vực pháp lý;
- mức độ rủi ro;
- phê duyệt của con người;
- thời điểm;
- mục đích;
- chính sách và quy định đang có hiệu lực.

Vì vậy, một hệ thống có thể gọi được API không có nghĩa hệ thống đó tự động có thẩm quyền gây ra tác động doanh nghiệp đứng phía sau API đó.

EEOS vì vậy tách biệt khả năng suy luận và khả năng thực thi của một chủ thể khỏi thẩm quyền của chủ thể đó.

Một chủ thể có thể suy luận, đề xuất hoặc về mặt kỹ thuật có thể thực thi. Không điều nào trong số đó, tự thân, trao cho chủ thể thẩm quyền gây ra một thay đổi trọng yếu trong doanh nghiệp.

---

## 4. Quyết định trước khi hành động: hợp đồng chuyển đổi ràng buộc

Năng lực và thẩm quyền vẫn chưa đủ để giải thích một thay đổi có chủ đích phải được ràng buộc như thế nào **trước khi tác động xảy ra**.

Trước một thay đổi trọng yếu đã được dự kiến và được giao cho một chủ thể thực hiện trên một con đường có thể kiểm soát, doanh nghiệp cần một biểu diễn bền vững và có thể kiểm tra về chính thay đổi đã được lựa chọn.

Sách trắng gọi biểu diễn đó là **Hợp đồng chuyển đổi ràng buộc (authoritative transition contract)**.

Đây là biểu diễn của một chuyển đổi đã được xác định, được doanh nghiệp xác lập làm **nguồn tham chiếu chính thức có giá trị ràng buộc** đối với chuyển đổi đó.

Nó xác lập và ràng buộc:

- mục đích và ý nghĩa đã được cho phép;
- phạm vi;
- thẩm quyền;
- các giới hạn không được vượt qua;
- tác động dự kiến;
- yêu cầu về bằng chứng;
- chuỗi truy nguyên cần thiết.

Thực thi phải tuân theo những ràng buộc đó.

Từ **“ràng buộc”** ở đây diễn đạt chức năng kiểm soát của hợp đồng đối với chuyển đổi. Nó không có nghĩa bản thân hợp đồng tự cấp thẩm quyền thực thi.

“Hợp đồng” ở đây là một khái niệm ở cấp phạm trù. Nó không nhất thiết phải là một hợp đồng pháp lý, một schema phần mềm cụ thể hay một artifact riêng của Saafree.

Việc hình thành hợp đồng chuyển đổi ràng buộc **không tự nó cho phép thực thi**.

Việc cho phép thực thi theo thẩm quyền (**authorization**) là một bước riêng.

Chỉ khi thẩm quyền thích hợp đã được xác lập và có hiệu lực thì thực thi mới được phép hiện thực hóa hợp đồng.

Sau đó, mọi thực thi tạo tác động phải nằm trong **phạm vi ý nghĩa và các ràng buộc đã được cho phép (authorized semantic and constraint envelope)**.

Nếu ý nghĩa, thẩm quyền của chủ thể, các ràng buộc được bảo vệ hoặc phạm vi tác động bị mở rộng hay thay thế, thì phải có thẩm quyền mới **trước khi tác động liên quan xảy ra**.

Nếu không, phần sai lệch vẫn là EST nhưng không phải AEST đối với phần không phù hợp.

Thẩm quyền cũng không nhất thiết phải được cấp lại cho từng hành động nhỏ.

Doanh nghiệp có thể thiết lập **thẩm quyền thường trực** hoặc thẩm quyền được định sẵn theo các tham số cho một lớp lựa chọn đã được giới hạn trước. Khi đó máy có thể tự chọn hành động cụ thể mà không cần con người phê duyệt lại từng bước nhỏ, miễn là lựa chọn đó vẫn có thể được quy kết và kiểm tra với phạm vi đã được cho phép.

Nguyên tắc này áp dụng cho cả chủ thể là con người lẫn chủ thể là máy.

---

## 5. Thực thi không đồng nghĩa với tác động thực tế

Hệ thống doanh nghiệp thường sử dụng trạng thái thực thi thành công như một đại diện thuận tiện cho thành công của hoạt động kinh doanh.

Ví dụ:

- API trả về HTTP 200;
- quy trình báo `COMPLETED`;
- agent thông báo nhiệm vụ đã thành công;
- một thông điệp được hàng đợi tiếp nhận.

Những tín hiệu này hữu ích.

Nhưng chúng không phải lúc nào cũng chứng minh rằng trạng thái thực tế của doanh nghiệp đã thay đổi đúng như dự kiến.

Hãy hình dung một agent gửi yêu cầu cập nhật tài khoản khách hàng.

API chấp nhận yêu cầu.

Quy trình đánh dấu bước đó hoàn thành.

Nhưng một nhà cung cấp dịch vụ ở phía sau sau đó từ chối thay đổi vì thiếu một trường dữ liệu bắt buộc.

Thực thi đã xảy ra.

**Tác động thực tế mà doanh nghiệp dự kiến thì chưa xảy ra.**

EEOS vì vậy tách:

**bằng chứng rằng thực thi đã xảy ra**

khỏi

**bằng chứng rằng tác động dự kiến thực sự tồn tại trong thực tế doanh nghiệp**.

Báo cáo của chính chủ thể thực thi cũng không đủ, tự thân, để chứng minh rằng tác động trọng yếu thực sự đã xảy ra.

---

## 6. Sau tác động: kiểm tra, kiểm chứng và xác định tính hợp lệ

Khi tác động thực tế đã xảy ra, EEOS không dừng ở việc biết rằng “có một thay đổi”.

Đối với một **chuyển đổi được quản trị**, đường chính sau tác động là **kiểm tra chủ động** theo trình tự sau:

1. **Kiểm tra hành động và kết quả so với hợp đồng chuyển đổi ràng buộc** — hành động có đúng điều đã được cho phép hay không; chủ thể thực thi có đúng thẩm quyền hay không; các ràng buộc có được giữ hay không; tác động thực tế có đúng phạm vi và ý nghĩa đã được xác lập hay không; bằng chứng có đủ để chứng minh những điều đó hay không.

2. **Kiểm chứng ở cấp hệ điều hành** — mục tiêu không chỉ là xác nhận một bước kỹ thuật đã chạy đúng, mà là kiểm chứng toàn bộ chuyển đổi trong trật tự vận hành EEOS.

3. **Xác định tính hợp lệ của chuyển đổi** — trong phạm vi áp dụng: thẩm quyền là hợp quy; thực thi tuân theo hợp đồng chuyển đổi ràng buộc; tác động thực tế nằm trong phạm vi ý nghĩa và các ràng buộc đã được cho phép; bằng chứng và kiểm chứng cần thiết đáp ứng yêu cầu. “Hợp lệ” ở đây không chỉ có nghĩa một lệnh đúng cú pháp, một API thành công hay một quy trình chạy hết bước. Một chuyển đổi có thể thực thi thành công về kỹ thuật nhưng vẫn **không hợp lệ** ở cấp hệ điều hành.

4. **Học từ kết quả** — giữ lại hoặc loại bỏ điều đã học được từ chuyển đổi vừa qua.

5. **Tổng hợp và báo cáo** — gom kết quả, bằng chứng và đánh giá để chuẩn bị đóng vòng.

6. **Phê duyệt thu hồi quyền** — ranh giới phê duyệt của con người ở cuối vòng đời được quản trị: phê duyệt đóng vòng và thu hồi cùng một phạm vi thẩm quyền có giới hạn đã được kích hoạt trước đó, sau khi đã thực thi, có tác động thực tế, đối chiếu với hợp đồng, kiểm chứng ở cấp hệ điều hành, xác định tính hợp lệ, học từ kết quả và tổng hợp báo cáo. Bước này không tự thay thế cho việc hình thành hợp đồng chuyển đổi ràng buộc và cũng không tạo một “thẩm quyền” thứ hai tách rời.

7. **Đóng vòng đời và xác lập vị thế tiếp theo** có quản trị — điểm xuất phát cho chu kỳ chuyển đổi kế tiếp.

Đường này **không** thay thế bằng chuỗi thụ động quan sát → ghi nhận → phán xét nên được chấp nhận như các bước bắt buộc mặc định của lộ trình được kiểm soát.

### Còn quan sát và nhận thức thực tại ở đâu?

EEOS vẫn cần khả năng nhận thức thực tại.

Đặc biệt, một EST có thể xảy ra ngoài đường đã được điều khiển: ngoài dự kiến, trái phép, ngoài phạm vi kiểm soát hoặc chỉ được phát hiện sau đó.

Trong những tình huống như vậy, quan sát và **nhận thức thực tại** là điều kiện để đưa trạng thái thực tế trở lại phạm vi quản trị.

Nhưng đó là một vấn đề khác với đường chuyển đổi được quản trị phía trên.

**Không nên biến quan sát rồi ghi nhận thành các bước mặc định sau thực thi có quản trị** trong một chuyển đổi vốn đã được EEOS điều khiển chủ động theo trình tự kiểm tra và kiểm chứng.

---

## 7. Vì sao từng hệ thống đúng riêng lẻ vẫn có thể để lại một khoảng trống xuyên suốt

Doanh nghiệp hiện đại đã có rất nhiều hệ thống kiểm soát.

Quản lý định danh và truy cập xác định ai được truy cập cái gì.

Hệ thống quy trình điều phối công việc.

Các hệ thống quản trị, rủi ro và tuân thủ mã hóa chính sách và nghĩa vụ.

Hệ thống bảo mật phát hiện và ngăn chặn các mối đe dọa.

Nền tảng ứng dụng thực thi các quy tắc nghiệp vụ cục bộ.

Cơ chế kiểm soát agent giới hạn hành vi AI.

Hệ thống quan sát ghi lại các sự kiện kỹ thuật.

Mỗi hệ thống có thể hoạt động hoàn toàn đúng trong phạm vi của mình.

Câu hỏi khó hơn là: khi các **kiểm soát cục bộ** được ghép lại với nhau, liệu chúng có bảo toàn ý nghĩa, thẩm quyền, các ràng buộc, bằng chứng và trách nhiệm giải trình của cùng một **chuyển đổi trạng thái doanh nghiệp** từ đầu đến cuối hay không?

Hãy xem xét một chuyển đổi đi qua:

agent AI  
→ tầng điều phối  
→ dịch vụ định danh  
→ ứng dụng nghiệp vụ  
→ nhà cung cấp bên ngoài  
→ thực tế doanh nghiệp.

Mỗi thành phần có thể báo thành công theo quy tắc cục bộ của mình.

Nhưng toàn doanh nghiệp vẫn có thể không có một **trật tự vận hành** có trách nhiệm giải trình đủ khả năng trả lời xuyên suốt cả chuyển đổi:

Điều gì được dự kiến?

Ai hoặc cái gì đã đề xuất?

Dựa trên thẩm quyền nào?

Những ràng buộc nào được áp dụng?

Thực thi thực tế là gì?

Tác động thực tế là gì?

Tác động đó được ghi nhận như thế nào?

Trạng thái kết quả có **tính hợp lệ** hay không?

**Phương án xử lý** sau đó là gì?

Sau này doanh nghiệp có thể dựng lại đầy đủ chuỗi truy nguyên đó hay không?

Một ví dụ dễ thấy hơn là **nguyên tắc phân tách nhiệm vụ**. Một hệ thống có thể đúng khi cho phép một người tạo nhà cung cấp. Một hệ thống khác cũng có thể đúng khi cho chính người đó phê duyệt thanh toán. Mỗi kiểm soát cục bộ đều đạt. Nhưng cách ghép hai hệ thống vẫn có thể vi phạm quy tắc doanh nghiệp rằng cùng một người không được thực hiện cả hai việc.

Một trong những lập luận cốt lõi của sách trắng, **N1**, là một luận điểm về tính không suy ra được (non-entailment): tính đúng của từng phần riêng lẻ không tự bảo đảm việc bảo toàn các thuộc tính cần thiết xuyên suốt toàn bộ chuyển đổi trạng thái doanh nghiệp.

> Tính đúng cục bộ không bảo đảm về mặt logic các thuộc tính xuyên suốt cần thiết (end-to-end properties).

N1 tự nó không chứng minh một trật tự thuộc lớp EEOS là cần thiết. Đó là một mệnh đề khác: **N2**.

**N2** hỏi liệu, đối với một lớp doanh nghiệp và nghĩa vụ đã được khai báo, có thực sự cần một **chủ thể hoặc trật tự vận hành chịu trách nhiệm giải trình xuyên các điểm nối**, được xác định **trước** — tức **E0** — để bảo toàn các kết quả xuyên suốt cần thiết hay không. Sách trắng giữ N2 ở trạng thái **mở, chưa được chứng minh và có thể bị bác bỏ (falsifiable)**. Một cách sắp xếp không có E0 mà vẫn đạt được các kết quả đã nêu sẽ là một phản ví dụ. N1 không chứng minh N2.

---

## 8. EEOS đề xuất điều gì

EEOS đề xuất coi chính **chuyển đổi trạng thái doanh nghiệp** là một đối tượng hạng nhất của kiểm soát vận hành.

Đề xuất này không đơn giản là thêm một màn hình phê duyệt, một khung agent, một sản phẩm bảo mật hay một bảng điều khiển quản trị. Nó cũng không yêu cầu mọi doanh nghiệp phải vận hành một nền tảng tập trung khổng lồ.

Bước nền tảng đầu tiên là **E0**: một **chủ thể hoặc trật tự vận hành chịu trách nhiệm giải trình xuyên các điểm nối**.

Nói bằng ngôn ngữ thông thường, E0 có nghĩa là **trước khi biết kết quả**, doanh nghiệp có thể xác định ai hoặc trật tự vận hành nào chịu trách nhiệm bảo toàn một chuyển đổi trọng yếu xuyên suốt toàn bộ đường đi. Ít nhất chủ thể hoặc trật tự đó phải có:

- phạm vi được khai báo;
- thẩm quyền thực sự để sửa hoặc phân xử xuyên qua các điểm nối liên quan;
- nghĩa vụ thu thập bằng chứng về tác động thực tế;
- trách nhiệm nhận thức thực tại, sửa hoặc xử lý thực tế không phù hợp;
- trách nhiệm giải trình đối với chuyển đổi được quản trị như một toàn thể, chứ không chỉ với một hệ thống cục bộ.

E0 có thể tập trung trong một số môi trường và được tổ chức theo mô hình liên hợp trên nhiều hệ thống trong môi trường khác. Nhiều chủ sở hữu cục bộ nhưng không có thẩm quyền ràng buộc đối với cách ghép thì chưa đủ tạo thành E0. Điều quan trọng không phải mọi thành phần nằm vật lý ở đâu. Điều quan trọng là có một trật tự vận hành nhận trách nhiệm đối với toàn bộ chuyển đổi **trước khi kết quả được biết**.

E0 **không tự nó tạo thành một hệ điều hành**.

**Đặc tính ở cấp hệ điều hành (operating-system character)** là một bước tiếp theo. Trật tự đó phải thực sự **ràng buộc hoặc hạn chế thực thi** ở những nơi có thể làm được về kỹ thuật, chứ không chỉ đưa ra tư vấn, kiểm toán hoặc dựng lại sự việc sau đó. Ở nơi không thể điều phối trực tiếp trước hoặc trong tác động, cùng trật tự đó vẫn phải chịu trách nhiệm: doanh nghiệp có thể quan sát thay đổi tại thời điểm nó xảy ra hoặc tái dựng sau đó. Các cách làm này không tương đương. Tái dựng sau sự kiện tự nó không chứng minh đặc tính hệ điều hành.

Sách trắng mô tả tư cách thành viên của phạm trù thông qua E0 cùng với K1–K12, **đồng thời chịu yêu cầu có thực chất (non-vacuity requirement)**: trật tự đó phải thực sự thực hiện công việc vận hành cần thiết, chứ không chỉ mô tả, tư vấn hay kiểm toán nó. Tài liệu hướng dẫn này không biến các điều kiện đó thành bài tập ghi nhớ.

Ở mức khái quát, những điều kiện đó liên quan đến việc duy trì xuyên suốt vòng đời của chuyển đổi trạng thái doanh nghiệp các yếu tố như:

- mục đích và ý nghĩa đã được cho phép;
- trách nhiệm giải trình doanh nghiệp và thẩm quyền con người được bảo lưu;
- thẩm quyền và các ràng buộc;
- thực thi;
- tác động thực tế;
- bằng chứng và chuỗi truy nguyên;
- nhận thức thực tại;
- tính hợp lệ và phương án xử lý;
- ranh giới được bảo vệ và thẩm quyền đóng khi thiếu điều kiện;
- tái chứng nhận và tiếp tục có quản trị.

Các điều kiện chính xác của phạm trù và các quy tắc đánh giá sự phù hợp (conformance rules) thuộc về bản công bố khoa học.

Đối với người đọc nhập môn, ý quan trọng đơn giản hơn:

**EEOS quan tâm đến việc giữ cho thay đổi trạng thái doanh nghiệp có thể quản trị được xuyên suốt từ ý nghĩa đã được cho phép đến tác động thực tế, rồi từ tác động thực tế quay trở lại hành động doanh nghiệp có trách nhiệm giải trình.**

Đó là lý do sách trắng dùng từ **hệ điều hành** theo nghĩa chức năng. EEOS không khẳng định nó phải giống hệ điều hành máy tính cá nhân hay phải có một kiến trúc phần mềm cụ thể. Lập luận là trật tự vận hành cần thiết phải liên quan đến khả năng liên tục của doanh nghiệp trong việc quản trị chuyển đổi trạng thái xuyên qua nhiều chủ thể và nhiều hệ thống, thay vì chỉ quản trị riêng một ứng dụng, một quy trình hoặc một AI agent.

**Vì sao có từ “Evolution” trong tên gọi?** Sau khi chuyển đổi được lấy bằng chứng và xử lý theo phương án thích hợp, doanh nghiệp có thể giữ lại hoặc loại bỏ điều đã học được, bảo toàn chuỗi truy nguyên thay vì viết lại lịch sử, tái chứng nhận vị thế hiện tại và bắt đầu vòng tiếp theo từ trạng thái đã được cập nhật đó. Đối tượng trung tâm vẫn là chuyển đổi trạng thái doanh nghiệp. “Evolution” trong nghĩa này là điều xuất hiện khi các chuyển đổi được quản trị được lặp lại một cách có kỷ luật theo thời gian. Đây chỉ là cách giải thích tên gọi, không phải một mệnh đề khoa học mới.

---

## 9. EEOS không chỉ là một tên gọi khác của các hệ thống hiện có

EEOS có vùng giao với nhiều lĩnh vực đã tồn tại, nhưng đề xuất này không đơn giản là đổi tên cho bất kỳ một lĩnh vực nào trong số đó.

**Quản trị** quan trọng, nhưng chính sách tự nó không chứng minh ý nghĩa và thẩm quyền của một chuyển đổi đã được bảo toàn xuyên qua thực thi và tác động thực tế.

**Quản lý định danh và truy cập** quan trọng, nhưng việc xác thực chủ thể không xác định **tính hợp lệ** của mọi trạng thái doanh nghiệp mà chủ thể đó về mặt kỹ thuật có thể gây ra.

**Quy trình công việc** quan trọng, nhưng quy trình hoàn thành không nhất thiết chứng minh tác động ngoài đời thực.

**Bảo mật** quan trọng, nhưng ngăn hành động thù địch không đồng nghĩa với việc quản trị mọi **chuyển đổi trạng thái doanh nghiệp trọng yếu**, kể cả chuyển đổi trái phép hoặc bất lợi.

**Khả năng quan sát** quan trọng, nhưng quan sát được một trạng thái không quyết định trạng thái đó có **tính hợp lệ** hay doanh nghiệp phải làm gì tiếp theo.

**Rào cản AI** quan trọng, nhưng kiểm soát hành vi mô hình tự nó không quản trị được toàn bộ chuyển đổi trạng thái doanh nghiệp sau khi agent tương tác với hệ thống bên ngoài và thực tế doanh nghiệp.

EEOS vì vậy đề xuất một **mức quan tâm khác**: trật tự vận hành có trách nhiệm giải trình đối với chuyển đổi trạng thái doanh nghiệp xuyên qua những điểm nối này.

Điều đó không có nghĩa các hệ thống hiện tại phải bị loại bỏ. Một cách ghép gồm các hệ thống định danh, quy trình, bảo mật, quản trị, quan sát, ứng dụng và kiểm soát agent hiện có hoàn toàn có thể đạt lớp EEOS nếu toàn bộ cách sắp xếp thực sự đáp ứng các điều kiện của phạm trù và hoạt động như trật tự vận hành xuyên điểm nối cần thiết.

Không bắt buộc phải dùng phần mềm Saafree.

Không bắt buộc một nhà cung cấp, một sản phẩm hay một kiến trúc cụ thể.

Nguồn gốc hoặc thương hiệu của từng thành phần không phải tiêu chí xác định tư cách thành viên của phạm trù.

---

## 10. Sách trắng hiện đang khẳng định điều gì — và chưa khẳng định điều gì

Một cách hữu ích để đọc EEOS White Paper là phân biệt các loại phát biểu khoa học khác nhau.

Không phải mọi nội dung trong sách trắng đều có cùng trạng thái bằng chứng.

**P0** là mệnh đề tồn tại về hành động máy được ủy quyền. Khi máy hành động dựa trên thẩm quyền được ủy quyền, bốn thứ sau có thể tách khỏi nhau theo thời gian hoặc trạng thái:

- điều thực sự đã xảy ra;
- điều doanh nghiệp quan sát được;
- điều doanh nghiệp chính thức ghi nhận;
- nơi thẩm quyền và trách nhiệm giải trình được quy kết.

Trong ấn bản công khai hiện tại, P0 ở trạng thái **ARGUED**. Các minh họa thực nghiệm bên ngoài có định danh cụ thể đã được chủ động loại khỏi cách diễn đạt công khai. Mô hình trừu tượng được dùng để giải thích; nó không được trình bày như bằng chứng thực nghiệm bên ngoài.

**P1** là giả thuyết định hướng về khả năng vấn đề tăng lên khi khối lượng hành động máy được ủy quyền, tốc độ hoặc độ phức tạp xuyên hệ thống tăng trong điều kiện năng lực kiểm soát có thể so sánh. Đây là giả thuyết, không phải quy luật phổ quát đã được chứng minh.

**N1** lập luận rằng tính đúng cục bộ không tự bảo đảm các thuộc tính xuyên suốt cần thiết khi các phần được ghép lại với nhau (non-compositionality). Việc tồn tại các tổ hợp thành công dưới điều kiện ràng buộc mạnh hơn vẫn hoàn toàn có thể xảy ra và không bác bỏ luận điểm về tính không suy ra được nói chung.

**N2** vẫn **mở, chưa được chứng minh và có thể bị bác bỏ (falsifiable)**. Đối với một lớp doanh nghiệp và nghĩa vụ đã được khai báo, N2 hỏi liệu E0 — chủ thể hoặc trật tự vận hành chịu trách nhiệm giải trình xuyên các điểm nối được xác định từ trước — có thực sự cần thiết để bảo toàn các kết quả xuyên suốt đã nêu hay không. Một cách sắp xếp không có E0 mà vẫn đáp ứng được những kết quả này sẽ là phản ví dụ. N1 không chứng minh N2.

**S** là giả thuyết về khả năng tồn tại kỹ thuật (engineering-existence conjecture): liệu có **ít nhất một** hiện thực khả thi của E0 cùng các điều kiện của phạm trù có thể thực sự vận hành trong giới hạn đã khai báo của nó dưới điều kiện doanh nghiệp thực hay không. Câu hỏi này vẫn chưa được giải quyết. S không phải bảo đảm đối với mọi hiện thực phù hợp và cũng không phải tuyên bố chứng nhận.

Vì vậy, EEOS hiện nên được hiểu là một **phạm trù khoa học và kỹ thuật được đề xuất**.

Sách trắng không tuyên bố EEOS đã là một phạm trù được bên ngoài công nhận.

Không tuyên bố đã có bằng chứng khoa học phổ quát.

Không tuyên bố các công nghệ hiện có không thể ghép thành một hiện thực thuộc lớp EEOS.

Không tuyên bố một triển khai cụ thể của Saafree định nghĩa phạm trù cho tất cả mọi người.

Không tuyên bố việc sử dụng tên EEOS đồng nghĩa một doanh nghiệp đã tuân thủ, an toàn hay được quản trị đúng.

### Vị thế của Saafree

Saafree hiện có một **triển khai tham chiếu ứng viên (candidate reference implementation)**.

Vị thế được công bố hiện nay là **tự xác nhận (self-attested)**, dựa trên bằng chứng từ **một tổ chức duy nhất** (`n = 1`) và được thể hiện dưới dạng **hồ sơ phù hợp một phần (partial conformance profile)**.

Saafree **không** tuyên bố tư cách thành viên đầy đủ của phạm trù chỉ dựa trên mức bằng chứng đó.

Những giới hạn đó xác định rõ những gì còn phải được quan sát, thử nghiệm, phản biện hoặc xây dựng để phạm trù trở nên mạnh hơn.

---

## 11. Một cách đơn giản để hình dung EEOS

Trong lần đọc đầu tiên, toàn bộ đề xuất có thể được rút về một câu hỏi:

**Khi trạng thái của doanh nghiệp thay đổi một cách trọng yếu, liệu doanh nghiệp có thể giải trình chuyển đổi đó từ mục đích, hợp đồng và thẩm quyền, xuyên suốt đến thực thi, tác động thực tế, kiểm tra, kiểm chứng tính hợp lệ, đóng vòng và vị thế tiếp theo hay không?**

Nếu câu trả lời phụ thuộc vào nhiều hệ thống rời rạc, nhiều cách hiểu không thống nhất hoặc bằng chứng chỉ dừng ở thực thi thay vì tác động và kiểm chứng, thì một khoảng trống quản trị xuyên các điểm nối có thể đang tồn tại.

EEOS đề xuất coi vấn đề đó là một **vấn đề ở cấp hệ điều hành**.

---

## Thuật ngữ cốt lõi Việt–Anh

| Tiếng Việt dùng trong hướng dẫn | Thuật ngữ tiếng Anh |
|---|---|
| chuyển đổi trạng thái doanh nghiệp | Enterprise State Transition (EST) |
| thẩm quyền | authority |
| thẩm quyền hợp quy | duly constituted / valid authority within the applicable rule system |
| cho phép thực thi theo thẩm quyền | authorization |
| Hợp đồng chuyển đổi ràng buộc | authoritative transition contract |
| tác động thực tế | actual effect |
| tính hợp lệ của chuyển đổi | transition validity (OS-level) |
| Phê duyệt thẩm quyền | approval that activates bounded authority |
| Phê duyệt thu hồi quyền | approval to withdraw or close bounded authority |
| Học từ kết quả | learning from result |
| Tổng hợp và báo cáo | consolidation and reporting |
| nhận thức thực tại | cognitive recognition of reality |
| kiểm tra hành động và kết quả | check action and result against contract |
| Kiểm chứng ở cấp hệ điều hành | operating-system-level verification |
| chuỗi truy nguyên | lineage |
| chuyển đổi được quản trị | governed transition |
| vòng đời | lifecycle |
| trật tự vận hành | operating order |
| đặc tính ở cấp hệ điều hành | operating-system character |
| yêu cầu có thực chất | non-vacuity requirement |

Hai điểm cần nhớ:

**Hợp đồng chuyển đổi ràng buộc không tự cấp thẩm quyền thực thi.**

Và:

**Thực thi thành công về kỹ thuật không đồng nghĩa chuyển đổi đã hợp lệ ở cấp hệ điều hành.**

---

## 12. Đọc tiếp ở đâu

Tài liệu hướng dẫn này chủ động lược bỏ phần lớn cấu trúc hình thức của bản công bố khoa học.

Người đọc muốn xem các định nghĩa chính xác, cấu trúc mệnh đề, trần bằng chứng, điều kiện bác bỏ, điều kiện thành viên của phạm trù, Zones A/B/C, E0, K1–K12 và toàn bộ lập luận khoa học nên đọc:

**Saafree EEOS White Paper — 2026 Foundation Edition**

Sách trắng là tài liệu khoa học có thẩm quyền của edition này.

Tài liệu hướng dẫn này chỉ tồn tại để giúp con đường đi vào sách trắng trở nên dễ tiếp cận hơn.