# Update sau khi bảo vệ
Các thay đổi đã được thực hiện sau khi bảo vệ

### Sửa lại nghiệp vụ cho đúng yêu cầu
- Công thức tính tiền thuê xe phụ thuộc vào cả thời gian thuê và loại xe
	- `RentalFeeCalculatorInterface` yêu cầu thêm tham số kiểu `BikeCategory` khi tính tiền thuê
	- Lớp `BikeCategory` có thêm thuộc tính hệ số nhân (`coefficient`) khi tính tiền thuê
	- Bảng `BikeCategory` trong CSDL được thêm trường hệ số nhân (`coefficient`) khi tính tiền thuê

### Cải thiện về mặt thiết kế và hiệu năng
- Lớp `DockHasBike` được đổi tên thành `Bike` để tránh hiểu nhầm
- Thay đổi thiết kế package `Entity`: thêm các quan hệ association sau
	- Lớp `Bike` chứa thêm 2 thuộc tính kiểu `Dock` và `BikeCategory` (thay vì chỉ chứa ID của 2 entity này như trước)
	- Lớp `BikeRent` chứa thêm thuộc tính có kiểu `DepositTransaction` (thay vì chỉ chứa ID tương ứng)
	- Lớp `BikeReturn` chứa thêm 2 thuộc tính có kiểu `PaymentTransaction` và `BikeRent` (thay vì chỉ chứa ID tương ứng)
- Các phương thức của các lớp `Service` nhận tham số đầu vào là các đối tượng `Bike`, `Dock`, `BikeRent`, `BikeReturn`,... thay vì chỉ là ID của chúng như trước
- Giảm số lời gọi tới các lớp DAO và truy vấn tới CSDL, từ đó cải thiện tốc độ chương trình
- Refactor và lược bỏ các phần code bị lặp

### Cập nhật tài liệu thiết kế
- Software Design Document mới được cập nhật ở file `FinalProject/ECOBIKE SDD.pdf`
- Các biểu đồ trình tự ở mức thiết kế được cập nhật ở `FinalProject/DesignSeqDiagrams/`
- Các file Astah trong `FinalProject/Astah` được cập nhật tương ứng

---

# TKXDPM.20211.KSTN-12

Repo này bao gồm cả document cho Phần mềm thuê xe EcoBikeRental. Để clone về toàn bộ document
```
git clone --recurse-submodules https://github.com/hieutran-coder/Ecobike_Rental_HUST_20221.git
```
hoặc
```
git clone https://github.com/hieutran-coder/Ecobike_Rental_HUST_20221.git
git submodule init
git submodule update
```

## Tài liệu 

Các tài liệu hoàn chỉnh được đặt trong `FinalProject`, bao gồm:
- SRS 
- SDD 
- Test plan 
- Slide trình bày

Các file Astah được đặt trong `FinalProject/Astah`

## Source code 
Source code nằm ở một github repo riêng và được thêm vào repo này như một submodule. 

Repo này nằm trong thư mục `ecobikerental`.

Javadoc được đặt trong `ecobikerental/doc`

Hướng dẫn cài đặt được nằm trong `ecobikerental/README.md`

Chú ý: Để lấy source code hãy liên hệ với mình.

## Demo 
[Link video demo phần mềm EcoBikeRental](https://www.youtube.com/watch?v=sdjd5-2IzDY)

