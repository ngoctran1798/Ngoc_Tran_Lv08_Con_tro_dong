**Trần Thị Ngọc**  
##Báo cáo học con trỏ động  
  
---  
   
[I.Biến Động](#Biến_động)  
[II. Cấp phát và giải phóng bộ nhớ động](#Bộ_nhớ_động)  
  
---  
  
<a name Biến_động><a\>  
###I.Biến Động 
**1.Khái niệm**  
  - Biến động là các biến được tạo ra lúc chạy chương trình, tùy nhu cầu.  
  - Không được xác định từ trước.   
  - Không có tên xác định mà chỉ là gán cho nó một địa chỉ xác định.  
  
**2.Cách tạo và truy nhập biến động:**  
  - Việc tạo và thu hồi( giải phóng) biến động dưa vào hàm *malloc()* và *free()* trong thư viện `stdlib.h`  
  - Việc truy nhập dựa vào các biến con trỏ được khai báo ở đầu chương trình dùng để lưu trữ địa chỉ biến động.  
        *Ví dụ:*  
      ```  
      int *a;  
      a= (int*)malloc(10);
      free(a);  
      ```    
  
<a name Bộ_nhớ_động><a\>  
###II.Cấp Phát Và Giải Phóng Bộ Nhớ Động  
**1.Cấp phát bộ nhớ động bằng hàm malloc()**  
    *Cú pháp:*  
    `void *malloc(kiểu _dl size)`  
    trong đó:  
      Size là một giá trị kiểu size_t (đã được định nghĩa sẵn)  
    *Chức năng:*    
  - Cấp phát một vùng nhớ có kích thước size, trả về con trỏ kiểu void chứa địa chỉ ô nhớ đầu của vùng nhớ được cấp phát.    
  - Nếu không đủ vùng nhớ nó sẽ trả lại giá trị null.    
  
**2.Cấp phát bộ nhớ động bằng hàm calloc()**      
    *Cú pháp:*  
    ` (datatype*)calloc(n,sizeof(object));`  
    trong đó:  
      Datatype là kiểu con trỏ tới kiểu dữ liệu datatype, n là số lượng object cần cấp phát bộ nhớ.    
    *Chức năng:*  
  - Cấp phát bộ nhớ động cho các kiểu dữ liệu.    
  
**3Cấp phát bộ nhớ đông bằng hàm relloc()**  
    *Cú pháp:*  
    `(datatype*)relloc(buf_p,newsize);`  
    trong đó:  
    buf_p là con trỏ trỏ tới ùng nhớ được cấp phát từ trước, newsize là kích thước mới cần cấp phát.  
    *chức năng:*  
  - Cấp phát lại bộ nhớ cho con trỏ đã được cấp phát bộ nhớ trước đó.  
  
**4.Giải phóng bộ nhớ bằng hàm free()**  
    *Cú pháp:*  
    `void free( void *prt)`  
    *Chức năng:*  
  - Hàm free giải phóng vùng nhớ được trỏ đến bởi con trỏ ptr.
  - Nếu con trỏ ptr = NULL thì hàm free không làm gì cả.
