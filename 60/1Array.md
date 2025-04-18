
1. Dữ liệu là gì và máy tính lưu trữ nó như thế nào?
 * Dữ liệu: Là thông tin mà máy tính cần xử lý. Đó có thể là con số (như 5, 100), văn bản (như "Xin chào", "Apple"), sự thật (đúng/sai),...
 * Lưu trữ dữ liệu: Hãy tưởng tượng máy tính có rất nhiều "chiếc hộp" nhỏ để cất giữ thông tin. Mỗi chiếc hộp có thể chứa một mẩu thông tin (một con số, một chữ cái...).
 * Biến (Variable): Khi lập trình, chúng ta cần đặt tên cho những "chiếc hộp" này để dễ quản lý. Một "biến" giống như một chiếc hộp có dán nhãn, và nhãn đó là tên của biến. Bạn có thể bỏ một giá trị vào hộp đó và sau này dùng cái nhãn để lấy giá trị ra hoặc thay đổi nó.
   * Ví dụ: Bạn có một chiếc hộp dán nhãn "tuoi" và bỏ số 20 vào đó. Sau này bạn có thể nói "tăng tuoi lên 1" và máy tính sẽ hiểu là lấy giá trị trong hộp "tuoi" (là 20), cộng thêm 1 và cất số 21 trở lại vào hộp đó.
2. Khi cần lưu trữ nhiều dữ liệu CÓ THỨ TỰ: Mảng (Array)
 * Vấn đề: Nếu bạn cần lưu trữ danh sách điểm của 10 học sinh, bạn có thể tạo 10 biến riêng lẻ (diem1, diem2, ..., diem10). Nhưng nếu là 1000 học sinh thì sao? Rất bất tiện!
 * Giải pháp: Mảng: Mảng giống như một "dãy hộp" được xếp thẳng hàng, có đánh số thứ tự. Tất cả các hộp trong dãy này thường chứa cùng loại dữ liệu (ví dụ: tất cả đều là số nguyên, hoặc tất cả đều là văn bản).
   * Hãy hình dung một mảng điểm của 5 học sinh:
     [  8.5  |  7.0  |  9.0  |  6.5  |  8.0  ]
  (hộp 0) (hộp 1) (hộp 2) (hộp 3) (hộp 4)

 * Chỉ số (Index): Mỗi hộp trong mảng được xác định bằng một số thứ tự, gọi là chỉ số (index). Thường thì chỉ số bắt đầu từ 0.
 * Truy cập: Bạn có thể dễ dàng lấy giá trị trong một hộp hoặc thay đổi giá trị đó bằng cách sử dụng tên mảng và chỉ số của hộp.
   * Ví dụ: Để lấy điểm của học sinh thứ 3 (là 9.0 trong ví dụ trên, vì chỉ số bắt đầu từ 0), bạn dùng chỉ số 2. Việc lấy hoặc thay đổi giá trị tại một chỉ số bất kỳ trong mảng là rất nhanh (độ phức tạp thời gian O(1) - bạn không cần đi qua các hộp khác để đến được hộp mình cần).
 * Hạn chế: Tìm kiếm một giá trị cụ thể trong mảng có thể chậm. Nếu bạn muốn biết "có học sinh nào được điểm 10 không?", bạn có thể phải đi qua từng hộp một từ đầu đến cuối mảng để kiểm tra (tìm kiếm tuyến tính - độ phức tạp thời gian O(n), với n là số lượng phần tử).
3. Khi cần lưu trữ dữ liệu và TÌM KIẾM/KIỂM TRA sự tồn tại CỰC NHANH: Băm (Hashing) và Bảng Băm (Hash Table/Map/Set)
 * Vấn đề: Như đã nói ở trên, tìm kiếm trong mảng có thể chậm. Làm thế nào để kiểm tra "có số X trong tập hợp dữ liệu này không?" hoặc "giá trị liên quan đến khóa Y là gì?" một cách nhanh chóng, gần như ngay lập tức?
 * Ý tưởng Băm (Hashing): Hãy tưởng tượng bạn có rất nhiều đồ vật (dữ liệu) và bạn muốn cất chúng vào các ngăn kéo tủ (các vị trí lưu trữ) sao cho khi cần tìm một món đồ nào đó, bạn biết ngay nó nằm ở ngăn kéo nào mà không cần lục tung cả tủ. Băm là kỹ thuật giúp bạn "biến" tên món đồ (hoặc một đặc điểm của nó) thành "số ngăn kéo" hoặc "địa chỉ" để cất/lấy.
 * Hàm Băm (Hash Function): Là "công thức" hoặc "quy tắc" mà bạn dùng để biến thông tin về món đồ (gọi là khóa - key) thành một con số (gọi là mã băm - hash code). Dựa vào mã băm này, bạn sẽ biết món đồ nên được cất/lấy ở đâu trong "tủ đồ" của mình. Một hàm băm tốt sẽ phân bố các món đồ vào các ngăn kéo khác nhau một cách đều đặn.
 * Bảng Băm (Hash Table): Đây là cấu trúc "tủ đồ thông minh" sử dụng kỹ thuật băm. Nó giống như một dãy các ngăn kéo (gọi là các "bucket" hoặc "slot"). Khi bạn muốn cất một món đồ với tên (khóa), bạn dùng hàm băm để tính ra mã băm, từ đó biết nó sẽ được cất vào ngăn kéo nào. Khi bạn muốn tìm lại món đồ đó, bạn làm tương tự: dùng tên món đồ, tính mã băm, và biết ngay cần mở ngăn kéo nào để lấy.
   * Bảng băm thường lưu trữ dữ liệu dưới dạng cặp Khóa - Giá trị (Key - Value). Khóa là cái bạn dùng để tìm kiếm (tên món đồ), Giá trị là thông tin bạn muốn lưu trữ cùng với khóa đó.
   * Ví dụ: Lưu thông tin học sinh. Khóa có thể là Mã số sinh viên (là duy nhất), Giá trị là tên, điểm số, v.v.
 * Ưu điểm: Việc thêm một món đồ mới, lấy một món đồ ra, hoặc kiểm tra xem một món đồ có tồn tại trong bảng băm hay không là cực kỳ nhanh trong hầu hết các trường hợp (độ phức tạp thời gian trung bình là O(1)), không phụ thuộc vào số lượng món đồ bạn đang có. Đây là điểm khác biệt lớn so với mảng khi tìm kiếm.
 * Nhược điểm:
   * Cần bộ nhớ phụ để tạo ra cấu trúc bảng băm.
   * Thỉnh thoảng có thể xảy ra "va chạm" (collision): hai món đồ khác nhau lại có cùng mã băm và muốn vào cùng một ngăn kéo. Bảng băm có các kỹ thuật để xử lý va chạm, nhưng nếu va chạm xảy ra quá nhiều (do hàm băm không tốt hoặc dữ liệu đầu vào có vấn đề), tốc độ có thể bị chậm đi (trong trường hợp xấu nhất có thể về O(n)).
 * Các dạng Bảng Băm thường dùng trong lập trình:
   * Hash Map / Dictionary / Map: Sử dụng để lưu trữ các cặp Khóa - Giá trị. Khóa là duy nhất. Rất tiện khi bạn cần "ánh xạ" từ một thứ này sang một thứ khác (ví dụ: từ tên sản phẩm sang giá, từ mã nhân viên sang tên).
   * Hash Set / Set: Chỉ lưu trữ các phần tử duy nhất. Nó giống như một danh sách mà bạn chỉ quan tâm là một món đồ có "có mặt" trong danh sách đó hay không, không quan tâm đến giá trị đi kèm hay thứ tự. Rất tiện để kiểm tra nhanh sự tồn tại hoặc loại bỏ trùng lặp.

---
các bài tập 

Okay, sau khi đã nắm được khái niệm cơ bản về Mảng và Băm (Hash Table/Map/Set), đây là hướng tiếp cận ngắn gọn cho từng bài toán trong những ngày đầu tiên, tập trung vào cách sử dụng các cấu trúc dữ liệu này:
 * Contains Duplicate (Easy):
   * Vấn đề: Kiểm tra xem có bất kỳ phần tử nào xuất hiện nhiều hơn một lần trong mảng không.
   * Hướng làm: Dùng một Hash Set. Duyệt qua mảng, với mỗi số:
     * Kiểm tra xem số đó đã có trong Set chưa.
     * Nếu có rồi -> Tìm thấy số trùng lặp, trả về true.
     * Nếu chưa có -> Thêm số đó vào Set.
   * Nếu duyệt hết mảng mà không tìm thấy số trùng lặp -> Trả về false.
   * Vì sao dùng Set? Kiểm tra sự tồn tại trong Set rất nhanh (trung bình O(1)).
 * Valid Anagram (Easy):
   * Vấn đề: Kiểm tra xem hai chuỗi có phải là hoán vị của nhau không (chứa cùng các ký tự với cùng số lượng).
   * Hướng làm: Dùng một Hash Map (hoặc một mảng có kích thước 26 nếu chỉ có ký tự thường) để đếm tần suất xuất hiện của mỗi ký tự trong chuỗi thứ nhất. Sau đó, duyệt qua chuỗi thứ hai, giảm tần suất của các ký tự tương ứng trong Map.
     * Nếu gặp một ký tự không có trong Map hoặc tần suất của nó đã hết (về 0) nhưng vẫn gặp ký tự đó -> Hai chuỗi không phải anagram.
   * Cuối cùng, kiểm tra xem tất cả các tần suất trong Map còn lại có bằng 0 hết không. Nếu có -> Hai chuỗi là anagram.
   * Vì sao dùng Map/Mảng tần suất? Đếm và theo dõi số lượng ký tự rất hiệu quả.
 * Two Sum (Easy):
   * Vấn đề: Tìm hai số trong mảng có tổng bằng một số mục tiêu (target). Trả về chỉ số của chúng.
   * Hướng làm: Dùng một Hash Map để lưu trữ các số đã duyệt qua và chỉ số của chúng (số -> chỉ số). Duyệt qua mảng. Với mỗi số num hiện tại:
     * Tính "số cần tìm" (complement) bằng target - num.
     * Kiểm tra xem complement có tồn tại như một khóa trong Map không.
     * Nếu có -> Tìm thấy cặp số! Trả về chỉ số hiện tại của num và chỉ số của complement lưu trong Map.
     * Nếu chưa có -> Thêm num và chỉ số hiện tại của nó vào Map.
   * Vì sao dùng Map? Giúp kiểm tra nhanh (trung bình O(1)) xem "số cần tìm" đã xuất hiện trước đó trong mảng chưa và lấy được chỉ số của nó.
 * Group Anagrams (Medium):
   * Vấn đề: Nhóm các chuỗi là hoán vị của nhau lại với nhau.
   * Hướng làm: Dùng một Hash Map. Khóa của Map là một "định danh" duy nhất cho một nhóm anagram (ví dụ: chuỗi đã được sắp xếp theo thứ tự bảng chữ cái), Giá trị của Map là một danh sách các chuỗi gốc thuộc nhóm đó.
     * Duyệt qua từng chuỗi đầu vào.
     * Với mỗi chuỗi, tạo ra "định danh" bằng cách sắp xếp các ký tự trong chuỗi đó.
     * Sử dụng "định danh" này làm khóa để truy cập Map. Thêm chuỗi gốc vào danh sách giá trị tương ứng với khóa này trong Map.
   * Kết quả là các danh sách giá trị trong Map chính là các nhóm anagram.
   * Vì sao dùng Map? Cho phép nhóm các chuỗi dựa trên cùng một "định danh" được tạo ra từ nội dung của chúng một cách hiệu quả.
 * Top K Frequent Elements (Medium):
   * Vấn đề: Tìm K phần tử xuất hiện nhiều nhất trong mảng.
   * Hướng làm:
     * Bước 1 (Hashing): Dùng một Hash Map để đếm tần suất xuất hiện của mỗi số trong mảng (số -> số lần xuất hiện).
     * Bước 2 (Lấy Top K): Có nhiều cách, phổ biến là dùng Priority Queue (Heap) hoặc Bucket Sort (mảng tần suất).
       * Cách dùng Heap: Dùng Min-Heap kích thước K. Duyệt qua Map tần suất. Thêm cặp (số, tần suất) vào Heap. Nếu Heap quá K phần tử, loại bỏ phần tử có tần suất nhỏ nhất (đỉnh Heap). Sau khi duyệt hết Map, Heap chứa K phần tử có tần suất lớn nhất.
       * Cách dùng Bucket Sort (hiệu quả hơn): Tạo một mảng các danh sách, chỉ số của mảng là tần suất. Đặt các số vào danh sách tương ứng với tần suất của chúng. Duyệt mảng này từ cuối lên (tần suất cao xuống thấp) để thu thập đủ K phần tử.
   * Vì sao dùng Map ở bước 1? Đếm tần suất của tất cả các phần tử một cách hiệu quả (O(n)).
 * Encode and Decode Strings (Medium):
   * Vấn đề: Biến danh sách chuỗi thành một chuỗi duy nhất và ngược lại.
   * Hướng làm: (Chủ yếu là thao tác chuỗi và xử lý phân tách). Chọn một ký tự đặc biệt (ví dụ: # hoặc /) làm ký tự phân tách. Để xử lý trường hợp chuỗi gốc chứa ký tự phân tách, hãy thêm độ dài của chuỗi gốc vào phía trước, theo sau là ký tự phân tách, rồi mới đến chuỗi gốc.
     * Encode: Với mỗi chuỗi trong danh sách, nối: độ_dài_chuỗi + ký_tự_phân_tách + chuỗi_gốc. Ghép tất cả lại thành một chuỗi lớn. Ví dụ: ["hello", "world"] -> "5#hello5#world".
     * Decode: Duyệt chuỗi đã encode. Đọc các ký tự số ở đầu để biết độ dài của chuỗi gốc tiếp theo. Bỏ qua ký tự phân tách. Đọc số lượng ký tự theo độ dài vừa tìm được để lấy lại chuỗi gốc. Lặp lại cho đến khi hết chuỗi đã encode.
   * Bài này không dùng Hashing theo nghĩa Map/Set, mà là kỹ thuật xử lý chuỗi để serialization/deserialization.
 * Product of Array Except Self (Medium):
   * Vấn đề: Tạo mảng kết quả sao cho mỗi phần tử là tích tất cả các số trong mảng gốc trừ chính nó, không dùng phép chia, thời gian O(n).
   * Hướng làm: Dùng kỹ thuật tính tích tiền tố (prefix product) và tích hậu tố (suffix product).
     * Bước 1: Tạo mảng answer. Duyệt mảng gốc từ trái sang phải. Tại mỗi vị trí i, lưu vào answer[i] tích của tất cả các số bên trái nó. Giữ một biến tích lũy tiền tố.
     * Bước 2: Duyệt mảng gốc từ phải sang trái. Giữ một biến tích lũy hậu tố. Tại mỗi vị trí i, nhân giá trị đã có trong answer[i] (vốn là tích tiền tố) với tích lũy hậu tố hiện tại (tích của tất cả các số bên phải nó). Biến tích lũy hậu tố được cập nhật sau mỗi bước.
   * Không dùng Hashing, chủ yếu là thao tác mảng và tính toán tích lũy.
 * Valid Sudoku (Medium):
   * Vấn đề: Kiểm tra xem bảng Sudoku 9x9 có hợp lệ không (không có số trùng lặp trong mỗi hàng, mỗi cột, mỗi ô 3x3).
   * Hướng làm: Dùng Hash Set (hoặc mảng boolean) để theo dõi các số đã thấy cho từng hàng, từng cột và từng ô 3x3. Cần ba bộ theo dõi riêng biệt:
     * Một tập hợp các Set cho 9 hàng (ví dụ: rows[9]).
     * Một tập hợp các Set cho 9 cột (ví dụ: cols[9]).
     * Một tập hợp các Set cho 9 ô 3x3 (ví dụ: boxes[9]). Để xác định ô 3x3 mà ô (i, j) thuộc về, bạn có thể dùng công thức chỉ số ô: (i / 3) * 3 + (j / 3).
     * Duyệt qua từng ô (i, j) trên bảng. Nếu ô đó có số (không phải ô trống '.'):
       * Kiểm tra xem số đó đã có trong rows[i] chưa. Nếu có -> sai. Thêm số vào rows[i].
       * Kiểm tra xem số đó đã có trong cols[j] chưa. Nếu có -> sai. Thêm số vào cols[j].
       * Tính chỉ số ô 3x3 là box_index = (i / 3) * 3 + (j / 3). Kiểm tra xem số đó đã có trong boxes[box_index] chưa. Nếu có -> sai. Thêm số vào boxes[box_index].
   * Nếu duyệt hết bảng mà không tìm thấy lỗi nào -> bảng hợp lệ.
   * Vì sao dùng Set? Giúp kiểm tra nhanh (trung bình O(1)) xem một số đã xuất hiện trong phạm vi cần kiểm tra (hàng/cột/ô 3x3) hay chưa.
 * Longest Consecutive Sequence (Medium):
   * Vấn đề: Tìm độ dài của dãy các số liên tiếp dài nhất trong mảng không sắp xếp (ví dụ: [100, 4, 200, 1, 3, 2] -> dãy liên tiếp dài nhất là [1, 2, 3, 4], độ dài 4). Yêu cầu thời gian O(n).
   * Hướng làm: Dùng một Hash Set để lưu tất cả các số trong mảng. Điều này cho phép kiểm tra sự tồn tại của một số bất kỳ trong tập hợp ban đầu một cách nhanh chóng (trung bình O(1)).
     * Duyệt qua từng số num trong mảng gốc (hoặc trong Set).
     * Kiểm tra xem num - 1 có tồn tại trong Set không.
     * Nếu num - 1 không tồn tại -> num là điểm bắt đầu của một dãy liên tiếp tiềm năng. Bắt đầu đếm độ dài dãy từ đây: kiểm tra sự tồn tại của num + 1, num + 2, num + 3, ... trong Set và tăng biến đếm độ dài hiện tại.
     * Nếu num - 1 có tồn tại -> num không phải điểm bắt đầu, nó là phần của một dãy đã bắt đầu từ num - 1 hoặc sớm hơn. Bỏ qua số num này (vì dãy liên tiếp chứa nó sẽ được xử lý khi gặp điểm bắt đầu thật sự).
   * Theo dõi và cập nhật độ dài dãy liên tiếp dài nhất tìm được.
   * Vì sao dùng Set và logic kiểm tra điểm bắt đầu? Set cho phép kiểm tra nhanh O(1). Logic kiểm tra num-1 giúp đảm bảo mỗi dãy liên tiếp chỉ được "đếm" một lần duy nhất, bắt đầu từ phần tử nhỏ nhất của dãy đó, đảm bảo tổng thời gian là O(n).
Đây là những hướng tiếp cận cốt lõi sử dụng mảng và kỹ thuật băm cho từng bài. Khi thực hành code, bạn sẽ thấy rõ cách các khái niệm này được áp dụng. Chúc bạn luyện tập hiệu quả!

 