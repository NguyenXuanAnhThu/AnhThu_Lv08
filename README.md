# Cấp phát và giải phóng bộ nhớ

[1. Khái niệm biến động](khainiem)

[2. Cấp phát và giải phóng bộ nhớ động (các hàm  thuộc stdlib.h và alloc.h)](capphat)

<a name"khainiem"></a>
##1. Khái niệm biến động:
  
  Là các biến *được tạo ra lúc chạy chương trình*, tùy theo nhu cầu. Số biến này hoàn toàn không được xác định từ trước. Các biến động không có tên( việc đặt tên thực chất là gán cho nó một địa chỉ xác định).
  
  * Cách tạo ra biến động và truy nhập đến biến động: 
   
    - Việc tạo ra các biến động và xóa nó đi được thực hiện nhờ các hàm như **malloc()** hay **free()** được chứa trong thư viện stdlib.h.
    
    - Việc truy cập đến biến động nhờ vào các biến con trỏ.
   
<a name"capphat"></a>
##2. Cấp phát và giải phóng bộ nhớ động ( các hàm thuộc stdlib.h và alloc.h):  
  **Cấp phát bộ nhớ:**  
   a. Hàm **malooc**:  
     - Cú pháp: **void *malloc(kiểu_dữ_liệu size)**  
     - Chức năng: cấp phát một vùng bộ nhớ có kích thước là size. (size là một kiểu dữ liệu được định sẵn trong thư viện **stdlib.h**)  
     - Nếu không đủ vùng nhớ để cấp phát hàm trả về giá trị *NULL*. Cần phải kiểm tra giá trị trả về trước khi sử dụng hàm **malloc**.  
     * Ví dụ:  
       num=(int*)malloc(10);
     
   b. Hàm **calloc**:  
     - Cú pháp: **(datatype *) calloc(n,sizeof(object))**;  
       Trong đó:  
        - (datatype *) là kiểu con trỏ tới kiểu dữ liệu datatype.  
        - n là số lượng object  thộc kiểu datatype cần cấp phát bộ nhớ.  
        - datatype có thể là kiểu dữ liệu cơ sở hoặc kiểu dữ liệu mới.  
      * Ví dụ:  
        num=(int*)calloc(10, sizeof(int));
        
   c. Hàm **relloc**:  
      - Cú pháp: **(datatype *) relloc(buf_p, newsize)**;  
        Trong đó:
         - buf_p là con  trỏ đang trỏ đến vùng ô nhớ đã được cấp phát từ trước.  
         - newsize là kích thước mới cần cấp phát, có thể lớn hơn hoặc nhỏ hơn.  
      * Ví dụ:  
        num=(int*)realloc(num,20);  
 
  **Giải phóng bộ nhớ:**  
    * Hàm **free** :  
      - Cú pháp: **void free(void *prt)**  
      - Ví dụ:  
        free(num);
