Câu 1: X là một khóa tối thiểu của lược đồ quan hệ S = khi và chỉ khi
A. (X->U) ∈ F+, ∀ Z ⊂ X: (Z->U) ∈ F+
B. (X->U) ∈ F+, ∀ Z ⊂ X: (Z->U) ∉ F+
C. ∀ Z ⊂ X: (Z->U) ∈ F+
D. (X->U) ∈ F+
ans: B [suy luận]

Câu 2: Giả sử một bảng được tạo với lệnh sau:
CREATE TABLE sinhvien(
MSSV char(8) NOT NULL PRIMARY KEY,
Hoten varchar(50) NOT NULL,
Gioitinh boolean NOT NULL);
Những câu lệnh nào dưới đây chắc chắn KHÔNG cho phép thêm thành công bản ghi vào bảng trên?
A. INSERT INTO sinhvien VALUES ('20220101', 'Nguyen Van An')
B. INSERT INTO sinhvien(Hoten, MSSV, Gioitinh) VALUES ('20220101', 'N.V.An', true);
C. INSERT INTO sinhvien(MSSV, Gioitinh, Hoten) VALUES ('20220101', 2, 'Nguyen Van An')
D. INSERT INTO sinhvien(MSSV, Hoten) VALUES ('20220101', 'Nguyen Van An')
ans: A,C,D [suy luận]

Câu 3: Cho CSDL gồm các quan hệ:
Kháchhàng( MãKH , Họtên, Sốđiệnthoại, Cơquan)
Nhàchothuê(MãN , Địachỉ, Giáthuê, Tênchủnhà)
Hợpđồng(MãN ,MãKH , Ngàybắtđầu , Ngàykếtthúc)
Chỉ ra câu lệnh tạo khung nhìn tên là KH chứa thông tin gồm Mã khách hàng, họ tên và số điện thoại của những khách hàng thuê nhà có giá thuê cao hơn 50 triệu đồng (giá thuê nhà, đơn vị tính là triệu đồng)
A. CREATE VIEW KH(Mã, Họvàtên, Điệnthoại) SELECT MãKH, Họtên, Sốđiệnthoại FROM Kháchhàng WHERE MãKH IN(SELECT MãKH FROM Hợpđồng, Nhàchothuê WHERE Hợpđồng.MãN = Nhàchothuê.MãN AND Giáthuê > 50)
B. CREATE VIEW KH(Mã, Họvàtên, Điệnthoại) AS SELECT MãKH, Họtên, Sốđiệnthoại FROM Kháchhàng WHERE MãKH IN(SELECT MãKH FROM Hợpđồng, Nhàchothuê WHERE Giáthuê > 50)
C. CREATE VIEW KH(Mã, Họvàtên, Điệnthoại) AS SELECT MãKH, Họtên, Sốđiệnthoại FROM Kháchhàng WHERE MãKH IN(SELECT MãKH FROM Hợpđồng, Nhàchothuê WHERE Hợpđồng.MãN = Nhàchothuê.MãN AND Giáthuê > 50)
D. CREATE VIEW KH(MãKH, Họtên, Sốđiệnthoại) FROM Kháchhàng WHERE MãKH IN (SELECT MãKH FROM Hợpđồng, Nhàchothuê WHERE Hợpđồng.MãN = Nhàchothuê.MãN AND Giáthuê > 50)
ans: C [suy luận]

Câu 4: Một CSDL gồm các quan hệ sau:
NhanVien(NV , HoTen, NamSinh)
DuAn(DA , TenDA, KinhPhi)
ThamGia( NV, DA , MucLuong)
Cho câu lệnh SQL sau:SELECT NV, HoTen FROM NhanVien, ThamGiaWHERE NhanVien.NV = ThamGia.NV AND DA = 'P01' INTERSECT SELECT NV, HoTen FROM NhanVien, ThamGia WHERE NhanVien.NV = ThamGia.NV AND DA = 'P02'; Nhận định nào dưới đây là đúng?
A. Câu truy vấn luôn cho kết quả rỗng
B. Lỗi cú pháp
C. Câu truy vấn cho phép đưa ra danh sách nhân viên đã tham gia ít nhất 1 trong hai dự án có mã 'P01', 'P02'
D. Câu truy vấn cho phép đưa ra danh sách nhân viên đã tham gia cả hai dự án có mã 'P01' và 'P02'
ans: D [suy luận]

Câu 5: Câu lệnh nào sau đây dùng để cấp quyền SELECT và INSERT trên cơ sở dữ liệu QLSV cho người dùng user1?
A. GRANT SELECT, INSERT ON QLSV TO 'user1'@'localhost';
B. REVOKE SELECT, INSERT ON QLSV FROM 'user1'@'localhost';
自由. GRANT SELECT, INSERT ON QLSV.* TO 'user1'@'localhost';
D. GRANT ALL PRIVILEGES QLSV.* TO user1;
ans: C [suy luận]

Câu 6: Sử dụng khung nhìn (view) có ưu điểm nào? Chọn 1 phương án phù hợp nhất
A. Bảo mật, đơn giản, nhất quán
B. Đơn giản, nhất quán
C. Bảo mật, đơn giản, nhất quán, tăng hiệu năng
D. Bảo mật, đơn giản
ans: A [suy luận]

Câu 7: Phát biểu nào dưới đây là ĐÚNG?
A. Một trường trong bảng có thể tham gia vừa vào khóa chính và vừa vào khóa ngoài của bảng đó.
B. Mỗi bảng chỉ có 1 khóa ngoài.
C. Mỗi khóa ngoài chỉ có 1 thuộc tính.
D. Các thuộc tính nằm trong khóa ngoài phải có tên trùng với tên của các thuộc tính mà nó tham chiếu đến.
ans: A [suy luận]

Câu 8: Cho câu lệnh truy vấn SQL sau, nhận định nào sau đây đúng ?
SELECT s.*
FROM Sinhvien s, DangKy d
WHERE s.MaSV = d.MaSV AND MaLop = 'NN01' AND TenMH = 'Database';
A. Câu truy vấn đưa ra thông tin sinh viên cũng như điểm số của sinh viên thuộc lớp có mã số 'NN01' mà đã từng đăng ký môn Database
B. Câu truy vấn đưa ra thông tin sinh viên thuộc lớp có mã số 'NN01' mà đã từng đăng ký môn Database
C. Câu lệnh vẫn được thực thi nhưng kết quả khác 2 phương án được đưa ra trong đáp án
D. Câu truy vấn không thực thi được
ans: B [suy luận]

Câu 9: Phát biểu nào dưới đây là SAI ?
A. Giao dịch là một tập các thao tác được xử lí như một đơn vị không thể chia cắt được
B. Các tính chất của giao dịch (ACID) được đảm bảo bởi môđun quản trị giao dịch của hệ quản trị CSDL
C. Định nghĩa tốt giao dịch cho phép đảm bảo tính nhất quán và đúng đắn của dữ liệu
D. Một giao dịch cụ thể do hệ quản trị CSDL tự phát hiện và định nghĩa
ans: D [suy luận]

Câu 10: Lựa chọn nào đầy đủ nhất về các kiểu ràng buộc của kết nối ?
A. 1-n;n-m; đệ quy; 1-1
B. n-m; n-1
C. 5-n; đệ quy
D. 1-n; n-2; n-m
ans: A [suy luận]