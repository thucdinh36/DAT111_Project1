# Phân tích Thị trường & Xu hướng Lương trong lĩnh vực Data & AI  
Giai đoạn 2020 – 2023  

**Môn học**: Dự án 1 – DAT111  
**Nhóm**: 03  
**Trường**: Cao đẳng FPT Polytechnic  
**GVHD**: Trần Văn Huy  

---

## Mục tiêu dự án
- Phân tích thực trạng lương trong ngành Data & AI toàn cầu và tại một số quốc gia trọng điểm  
- Đánh giá ảnh hưởng của kinh nghiệm, hình thức làm việc (remote/onsite), quy mô công ty đến mức lương  
- Dự báo xu hướng lương 2024–2025  
- Xây dựng dashboard chuyên nghiệp bằng Power BI + SQL Server (DirectQuery)

## Nguồn dữ liệu
- **Tên dataset**: Data Science Job Salaries (2020–2024)  
- **Nguồn**: Kaggle – https://www.kaggle.com/datasets/ruchi798/data-science-job-salaries  
- **Số dòng**: 3.757 bản ghi (sau khi làm sạch)  
- **Thời gian**: 2020 – 2023 (cập nhật đến Q4/2023)

## Công nghệ sử dụng
| Công nghệ                  | Phiên bản                | Mục đích sử dụng                                 |
|----------------------------|--------------------------|--------------------------------------------------|
| Microsoft SQL Server       | Express 2019/2022        | Lưu trữ dữ liệu, DirectQuery                     |
| SQL Server Management Studio (SSMS) | Latest             | Quản trị & import dữ liệu                                |
| Power BI Desktop           | Tháng 12/2025            | Xử lý, mô hình hóa, trực quan hóa, DirectQuery   |
| Power BI Service           | –                        | Publish & chia sẻ dashboard                              |
| GitHub                     | –                        | Lưu trữ mã nguồn, báo cáo, tài liệu dự án        |

## Quy trình dự án (Project Workflow)
1. Thu thập & làm sạch dữ liệu
   - Tải dataset ds_salaries.csv từ Kaggle
   - Import vào SQL Server Express bằng Import Flat File
2. Xây dựng mô hình Star Schema trong SQL Server
   - 1 bảng Fact: fact_salaries
   - 6 bảng Dim: dim_job_title, dim_experience, dim_location, dim_company_size, dim_year, dim_remote
   - Tạo khóa ngoại (ID) và relationship
3. Kết nối Power BI → SQL Server bằng DirectQuery
4. Xây dựng mô hình Star Schema lần 2 trong Power BI (relationship, measure DAX)
5. Thiết kế 5 trang dashboard + bookmark + drill-through
6. Publish lên Power BI Service

## Cài đặt và sử dụng

### Yêu cầu hệ thống
- Windows 10/11  
- Microsoft SQL Server Express (2019 trở lên)  
- Power BI Desktop (phiên bản mới nhất 2025)

### Hướng dẫn cài đặt & chạy dự án
1. **Cài SQL Server Express + SSMS**  
   Link tải: https://go.microsoft.com/fwlink/p/?linkid=2216018

2. **Import dữ liệu**
   - Mở SSMS → chuột phải database DS_Salaries_DB → Tasks → Import Flat File → chọn file ds_salaries.csv

3. **Mở file Power BI**
   - Tải file .pbix trong repo về máy  
   - Mở bằng Power BI Desktop → sẽ tự động kết nối DirectQuery tới SQL Server localhost

4. **Xem dashboard online (không cần cài gì)**
   Link Power BI Service (đã public):  
   https://app.powerbi.com/view?r=xxx (nhóm sẽ cập nhật link sau khi publish)
