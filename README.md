# TTTH Analyzer
## _Mô tả thư viện_

[![logo](https://github.com/liemvt2008/mds5-analyzer/tree/master/analyzer/.images/logo.jpeg)](https://csc.edu.vn/data-science-machine-learning)

TTTH_Analyzer là gói thư viện hỗ trợ HV môn MDS5 thực hiện các bước phân tích đơn biến và đa biến 

- Phân tích đơn biến (phân loại và liên tục )
- Phân tích đa biến (phân loại vs phân loại, phân loại vs liên tục )

## Tính năng cung cấp:

- Phân tích đơn biến  với biến phân loại  thông qua : 
    * Count values  
    * Barchart
- Phân tích đơn biến với biến liên tục  thông qua :
    * Các thông tin thống kê: Mean, Median, Mode, Min, Max và Range 
    * Các thông tin thống kê liên quan đến sự phân tán dữ liệu như : Range, Q1, Q3 , IQR, phương sai, độ lệch, độ nhọn của phân phối 
    * Trực quan hóa bằng histogram và boxplot 
- Phân tích đa biến phân loại vs phân loại thông qua:
    * Xây dựng bảng 2 chiều (two-way table)
    * Trực quan hóa bằng biểu đồ cột chồng (stacked columns bar )
    * Thực hiện phân tích thống kê bằng chi2
- Phân tích đa biến liên tục vs phân loại thông qua:
    * Xây dựng bảng ANOVA và phân tích thống kê 
    * Trực quan hóa bằng box plot

## Installation

```sh
pip install ttth-mds5-analyzer
```

## Cách sử dụng
- Khởi tạo thư viện 
```sh
from from analysis.analyzer import TTTH_Analyzer
_analyzer = TTTH_Analyzer()
```
- Phân tích đơn biến phân loại
```
_analyzer.analyze_category_variable(variable_name='Pclass', df=df_titanic_input_category)
Trong đó:
variable_name: tên biến phân loại cần phân tích - kiểu  chuỗi (string)
df: dataframe chứa biến phân loại cần phân tích  - kiểu dataframe pandas 
Kết quả: 
```
![result](/images/ket_qua_pt_category.png)
- Phân tích đơn biến liên tục
```
_analyzer.analyze_numeric_variable(variable_name='Age', df=df_titanic_input_continuous)
Trong đó:
variable_name: tên biến liên tục cần phân tích - kiểu  chuỗi (string)
df: dataframe chứa biến liên tục cần phân tích  - kiểu dataframe pandas  
Kết quả: 
```
![result](https://github.com/liemvt2008/mds5-analyzer/tree/master/analyzer/.images/ket_qua_pt_numeric.png)
- Phân tích đa biến phân loại vs phân loại
```
_analyzer.analyze_category_vs_category(var1=var1, var2=var2, df=df_titanic_input_category)
Trong đó:
var1: tên biến phân loại 1 cần phân tích - kiểu  chuỗi (string)
var2: tên biến phân loại 2 cần phân tích - kiểu  chuỗi (string)
df: dataframe chứa cả 2 biến phân loại cần phân tích  - kiểu dataframe pandas  
Kết quả: 
```
![result](https://github.com/liemvt2008/mds5-analyzer/tree/master/analyzer/.images/ket_qua_pt_cate_vs_cate.png)

- Phân tích đa biến liên tục vs phân loại 
```
_analyzer.analyze_continous_vs_categories(continous_var='Age', category_vars=['Sex', 'Pclass'], 
                                          df=df_titanic_input)
Trong đó:
continous_var: tên biến liên tục cần phân tích - kiểu  chuỗi (string)
category_vars: danh sách hoặc tên biến phân loại cần phân tích - kiểu danh sách (list)  hoặc kiểu  chuỗi (string)
df: dataframe chứa biến phân loại và biến liên tục cần phân tích  - kiểu dataframe pandas  
Kết quả: 
```
![result](https://github.com/liemvt2008/mds5-analyzer/tree/master/analyzer/.images/ket_qua_pt_numeric_vs_cates.png)
## License

MIT

**Nhanh tay đăng ký các khóa học Data Science/ Machine Learning ở TTTH Đại học KHTN để có thêm nhiều kiến thức thú vị cùng những cuộc hành trình khai phá dữ liệu **
