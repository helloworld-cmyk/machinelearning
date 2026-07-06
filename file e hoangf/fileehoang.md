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
C. GRANT SELECT, INSERT ON QLSV.* TO 'user1'@'localhost';
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

Câu 11: Cho sơ đồ quan hệ R gồm các thuộc tính: A, B, C, D, E, G, H, K.
Tập phụ thuộc hàm:
CEG → B, H
EG → C, H
DG → B, E, K
ABG → C, K
Hãy xác định một khóa tối thiểu của R (viết theo thứ tự từ điển, không dấu không cách)
ans: ADG [suy luận]

Câu 12: Một CSDL gồm các quan hệ sau: (Các thuộc tính in đậm, gạch chân là khóa chính; NV và DA là khóa ngoài của ThamGia; các ràng buộc khóa chính, khóa ngoài được khai báo đầy đủ )
NhanVien({pk}NV{/pk} , HoTen, NamSinh)
DuAn({pk}DA{/pk} , TenDA, KinhPhi)
ThamGia({pkfk}NV{/pkfk}, {pkfk}DA{/pkfk} , MucLuong)
Cho câu lệnh SQL sau:
SELECT NV, HoTen FROM NhanVien WHERE
(SELECT count(DA) FROM DuAn) =
(SELECT count(DA) FROM ThamGia WHERE NhanVien.NV = ThamGia.NV);
Nhận định nào dưới đây là đúng?
A. Câu truy vấn cho phép đưa ra danh sách nhân viên tham gia nhiều dự án nhất
B. Câu truy vấn cho phép đưa ra danh sách nhân viên tham gia tất cả các dự án
C. Câu truy vấn luôn cho kết quả rỗng
D. Câu truy vấn cho phép đưa ra danh sách nhân viên tham gia ít nhất 1 dự án
ans: B [suy luận]

Câu 13: Cho sơ đồ quan hệ R gồm các thuộc tính: A, B, C, D.
Tập phụ thuộc hàm:
AB → C; BC → A; AC → B; BC → D Biết rằng khóa chính của R là AB.
Hãy cho biết quan hệ R đang ở dạng chuẩn cao nhất nào trong các chuẩn sau?
A. Không đạt 1NF
B. 1NF
C. 2NF
D. 3NF
ans: D [suy luận]

Câu 14: Cho một cơ sở dữ liệu gồm các quan hệ:
NhanVien({pk}MaNV{/pk} , TenNV, DiaChi, NamSinh, {fk}MaPh{/fk} , {fk}MaCV{/fk})
Phong({pk}MaPh{/pk} , TenPh, DiaChi, Tel)
CongViec({pk}MaCV{/pk} , TenCV, Cap, KinhPhi)
Trong đó, khóa chính được in đậm và gạch chân, khóa ngoài được in nghiêng.
Chọn biểu diễn SQL của yêu cầu: Đưa ra tên của các phòng mà không có một nhân viên nào có địa chỉ ở 'Hà Nội'.
A. SELECT TenPh FROM Phong NATURAL JOIN NhanVien WHERE DiaChi = 'Hà Nội'
B. SELECT TenPh FROM Phong WHERE MaPh IN (SELECT MaPh FROM NhanVien WHERE DiaChi = 'Hà Nội')
C. SELECT TenPh FROM Phong WHERE MaPh NOT IN (SELECT MaPh FROM NhanVien WHERE DiaChi = 'Hà Nội')
D. SELECT TenPh FROM Phong WHERE MaPh NOT IN (SELECT MaPh FROM NhanVien WHERE DiaChi 'Hà Nội')
ans: C [suy luận]

Câu 15: (TỰ LUẬN) Cho hai quan hệ R và S khả hợp. Hãy viết một biểu thức đại số quan hệ KHÔNG chứa phép giao, nhưng cho kết quả tương đương với biểu thức:
(R ∪ S) \ (R ∩ S)
ans: (R \ S) ∪ (S \ R) [suy luận]

Câu 16: Chính sách nào giúp tăng hiệu quả tổng thể của hệ thống khi viết một giao dịch?
A. Truy cập vào lượng dữ liệu lớn bên trong thân một giao dịch
B. Thu hẹp phạm vi của giao dịch
C. Yêu cầu người dùng nhập dữ liệu bên trong thân của một giao dịch
D. Sử dụng mức cách ly bất kì cho một giao dịch
ans: B [suy luận]

Câu 17: Cho cơ sở dữ liệu gồm các quan hệ sau:
KhachHang({pk}IdKH{/pk} , HoTen, DiaChi)
MathHang({pk}IdMH{/pk} , TenHang, ChungLoai, GiaBan)
DatHang({pk}IDDonHang{/pk} , {fk}IdKH{/fk} , {fk}IdMH{/fk} , NgayMua, SoLuong)
Câu lệnh SQL nào sau đây đưa ra tổng số khách hàng khác nhau mua hàng trong ngày '31/05/2017'?
Lưu ý, mỗi khách hàng có thể đặt nhiều mặt hàng khác nhau.
A. SELECT COUNT(IdKH) FROM KhachHang WHERE IdKH IN (SELECT IdKH FROM DatHang WHERE NgayMua = '31/05/2017');
B. SELECT COUNT(IdKH) FROM DatHang WHERE NgayMua = '31/05/2017'
C. SELECT MAX(IdKH) FROM DatHang WHERE NgayMua = '31/05/2017';
D. SELECT COUNT(idMH) FROM DatHang WHERE NgayMua = '31/05/2017';
ans: A [suy luận]

Câu 18: Cho các quan hệ R1(ABCD), R2(CDE), R3(BC), hãy cho biết biểu thức nào khả hợp với biểu thức **σ<sub>A≠11</sub>((R1 ∗ R2) ÷ R3)**
A. σ<sub>A≠11</sub>(π<sub>A,C,D,E</sub>((R1 ÷ R3) ∗ R2))
B. (σ<sub>A≠11</sub>(R1) ∗ R2) ÷ R3
C. (σ<sub>A≠11</sub>(R1) ÷ R3) ∗ R2
D. σ<sub>A≠11</sub>((R1 ÷ R3) ∗ R2)
ans: B [suy luận]

Câu 19: REVOKE đi kèm RESTRICT/CASCADE có khác biệt như thế nào?
A. RESTRICT sẽ hủy quyền của người được lan truyền, CASCADE thì không
B. RESTRICT sẽ không hủy quyền của người được lan truyền, CASCADE thì có
C. Trong MySQL, hai lệnh trên không có sự khác biệt
ans: B [suy luận]

Câu 20: Giả sử có chỉ mục trên thuộc tính A của quan hệ R, phát biểu nào sau đây đúng?
A. Chỉ mục này không làm phát sinh không gian lưu trữ của hệ thống
B. Khi thực hiện câu lệnh truy vấn trên thuộc tính A, chỉ mục này có thể không được sử dụng
C. Không thể tạo thêm 1 chỉ mục khác trên quan hệ R
D. Mọi phép so sánh áp dụng trên thuộc tính A đều có thể sử dụng chỉ mục này
ans: B [suy luận]

Câu 21: Lược đồ R(A, B, C), F = {A --> B; B --> C; C --> A} được tách thành R1(AB), R2(BC). Phép tách này có tính chất gì?
A. Bảo toàn tập phụ thuộc hàm và không làm mất mát thông tin
B. Không bảo toàn tập phụ thuộc hàm
C. Làm mất mát thông tin
ans: A [suy luận]

Câu 22: Cho sơ đồ S(U,F), với U = {A, B, C, D, E}, với tập phụ thuộc hàm F = {AE->D, A->E, D->C}. Sau khi chuẩn hóa S về dạng chuẩn 3 bảo toàn thông tin và phụ thuộc hàm, gọi X là số sơ đồ con và gọi Y là số lần xuất hiện của A trong tất cả sơ đồ con đó. Hỏi X + Y = ?
A. 6
B. Đáp án khác
C. 7
D. 9
E. 8
ans: B [suy luận]

Câu 23: Cho lược đồ quan hệ R(A, B, C) với tập phụ thuộc hàm F = {A->B; B->C}. R ở dạng chuẩn cao nhất nào trong số các chuẩn sau:
A. 1
B. 2
C. 3
ans: B [suy luận]

Câu 24: Hãy cho biết có quy tắc tương tự với phép chọn và phép giao không?
A. Có
B. Không
ans: A [suy luận]

Câu 25: Những phát biểu nào sau đây đúng về vật chất hóa và đường ống ?
A. Phương pháp đường ống không thể dùng trong mọi trường hợp để thay thế cho vật chất hóa
B. Đây là 2 hướng tiếp cận để thực hiện đánh giá trực tiếp câu truy vấn viết bằng ngôn ngữ bậc cao
C. Phương pháp vật chất hóa sẽ sử dụng các quan hệ trung gian để sử dụng cho các phép toán kế
ans: A,B,C [suy luận]

Câu 26: Cho sơ đồ quan hệ R có m thuộc tính, sơ đồ quan hệ S có n thuộc tính. Hãy cho biết bậc của biểu thức đại số quan hệ: R x S
A. min(m,n)
B. m*n
C. Chưa đủ thông tin
D. max(m,n)
ans: B [suy luận]

Câu 27: Cho schema của một DB như sau:
SINHVIEN(MASV, TENSV, EMAIL, SDT, NGAYSINH)
HOCPHAN(MAHP, TENHP, LOAIHP, SOTINCHI)
LOPHOCPHAN(MALHP, MAHP, HOCKY, NAMHOC)
DANGKY(MASV, MALHP)

Cho câu lệnh sau:
SELECT COUNT(SDT) FROM SINHVIEN;

Kết quả của câu lệnh trên là gì?
A. Tổng số sinh viên
B. Số sinh viên có số điện thoại khác NULL
C. Giống COUNT(*)
D. Số cột trong bảng SINHVIEN
ans: B [suy luận]

Câu 28: Cho lược đồ quan hệ R(U,F) với U = {A,B,C,D,E,G,H,I} và tập phụ thuộc hàm F = {BG->E;I->H;BC->IH;A->CD}. Hãy xác định một khóa tối thiểu của lược đồ quan hệ R
A. BGICA
B. BGIA
C. ABC
D. BGA
ans: D [suy luận]

Câu 30: Phát biểu nào sau đây về tính chất ACID của giao dịch là **đúng**? (Chọn tất cả đáp án đúng)
A. Isolation đảm bảo giao dịch không bị ảnh hưởng bởi giao dịch khác
B. Isolation có nghĩa là chỉ cho phép một giao dịch chạy tại một thời điểm
C. Atomicity đảm bảo giao dịch thực hiện toàn bộ hoặc không thực hiện gì.
D. Durability đảm bảo dữ liệu không bị mất sau khi COMMIT, kể cả khi hệ thống crash
E. Consistency đảm bảo dữ liệu luôn đúng ngay cả khi mất điện.
ans: A,C,D [suy luận]

Câu 31: Khẳng định nào sau đây là đúng ?
A. Trong quan hệ ở dạng chuẩn 2, các thuộc tính không khóa phụ thuộc vào tập con thực sự của khóa chính
B. Trong quan hệ ở dạng chuẩn 2, cần ít nhất một thuộc tính không khóa phụ thuộc hàm đầy đủ vào khóa chính
C. Trong quan hệ ở dạng chuẩn 2, tất cả các thuộc tính không khóa đều phụ thuộc đầy đủ vào khóa chính
D. Trong quan hệ ở dạng chuẩn 2, các thuộc tính không khóa không phụ thuộc bắc cầu vào khóa chính
ans: C [suy luận]

Câu 32: Cho sơ đồ quan hệ R(ABCDE) và tập phụ thuộc hàm F = {AB->E; B->C; ABC->D; A->C}, hỏi phủ tối thiểu của F có bao nhiêu lần B xuất hiện ở vế trái?
ans: 3 [suy luận]

Câu 33: Cho bảng: Customers(ID, name, phone). Câu lệnh nào sau đây chắc chắn sai ?
A. SELECT name FROM Customers as TenKH;
B. INSERT Customers (ID, name, phone) VALUES ('141288', 'Nguyen Van An', '039864092');
C. DELETE FROM Customers WHERE ID = '14168';
D. UPDATE Customers SET phone = '033 3 456789' where ID = '14168';
ans: B [suy luận]

Câu 34: Cho sơ đồ quan hệ R(U) với tập thuộc tính U = {A, B, C, D, E, G, H, K} và tập phụ thuộc hàm F = {AB -> CGH, DG->CH, AD->BGH, BG ->CK}. Hãy tính một khóa tối thiểu của R. (Viết đáp án là các thuộc tính liền nhau, không cách không phẩy)
ans: ADE [suy luận]

Câu 35: Cho U = {A, B, C, D, E, G, H} và tập phụ thuộc hàm F = {A->D, AB ->DE, CE->F, E->H, D->E} Hãy cho biết, phụ thuộc hàm nào không thuộc vào phủ tối thiểu Fc của F
A. E->H
B. A->D
C. D->E
D. E->F
ans: D [suy luận]

Câu 36: Đâu là biểu diễn tối ưu nhất cho lệnh: SELECT sname FROM S, SP WHERE S.sid = SP.sid?
A. π<sub>sname</sub>( S ⋈<sub>{sid}</sub> SP )
B. π<sub>sname</sub>( π<sub>{sid, sname}</sub>(S) ⋈<sub>{sid}</sub> π<sub>{sid}</sub>(SP) )
C. π<sub>sname</sub>( σ<sub>S.sid = SP.sid</sub>( S × SP ) )
D. σ<sub>S.sid = SP.sid</sub>( π<sub>{sname}</sub>(S) × SP )
ans: B [suy luận]

Câu 37: Cho quan hệ và các phụ thuộc hàm: LOPHOC(SinhVien, MonHoc, GiangVien) FD:
1) (SinhVien, MonHoc) → GiangVien
2) GiangVien → MonHoc
Quan hệ này ở dạng chuẩn cao nhất là chuẩn nào trong số các chuẩn sau?
A. Không đạt 1NF
B. 3NF
C. 2NF
D. 1NF
ans: B [suy luận]

Câu 38: Cho sơ đồ quan hệ s(U) với:
U = {A, B, C, D, E}
F = {A --> BC, CD --> E}.
Phép tách về dạng chuẩn 3 không làm mất mát thông tin và bảo toàn tập phụ thuộc hàm là:
A. r1(AB), r2(AC), r3(CDE), r4(AD)
B. r1(ABC), r2(CDE), r3(ADE)
C. r1(ABC), r2(CDE), r3(AD)
D. r1(ABC), r2(CDE)
ans: C [suy luận]

Câu 39: Cho 1 bảng R(A1, A2, A3). Giả sử câu truy vấn " select * from R where A3 >= 5 and A3 <= 15 " được thực hiện thường xuyên trên R có số lượng bản ghi lớn. Lựa chọn nào dưới đây là có thể giúp cải tiến thời gian thực thi câu truy vấn?
A. Chỉ cần đánh chỉ mục trên khóa chính (A1, A2)
B. Đánh chỉ mục trên A3 dùng B-tree
C. Đánh chỉ mục trên A3 dùng hàm băm
D. Dùng tệp đống
ans: B [suy luận]

Câu 40: Cho schema của một DB như sau:
SINHVIEN(MASV, TENSV, EMAIL, SDT, NGAYSINH)
HOCPHAN(MAHP, TENHP, LOAIHP, SOTINCHI)
LOPHOCPHAN(MALHP, MAHP, HOCKY, NAMHOC)
DANGKY(MASV, MALHP)
Cho câu lệnh sau:
SELECT MASV, COUNT(*) AS SL
FROM DANGKY
WHERE SL > 1
GROUP BY MASV;
A. Trả về sinh viên đăng ký > 1 lớp
B. Chạy đúng
C. Sai logic nhưng chạy được
D. Lỗi cú pháp
ans: D [suy luận]

Câu 41: Phát biểu nào sau đây là đúng nhất?
A. BCNF --> 3NF
B. 3NF --> BCNF
C. Hehe
D. Hai dạng chuẩn này không liên quan tới nhau
E. BCNF <-> 3N
ans: A [suy luận]

Câu 42: Cho lược đồ quan hệ Q(A, B, C, D), với phụ thuộc hàm F = {AB->C; D->B; C->ABD} ở dạng chuẩn cao nhất nào trong số các chuẩn sau
A. 3NF
B. Các phương án khác sai
C. 2NF
D. 1NF
ans: A [suy luận]

Câu 43: Hãy cho biết nhận định đúng về khung nhìn (view)
A. Có thể sử dụng trigger để cập nhật giá trị của các bản ghi trong khung hình
B. Không thể định nghĩa khung nhìn thông qua một khung nhìn khác
C. Khung nhìn sẽ không còn tồn tại trong CSDL sau khi người dùng đóng kết nối
D. Không thể cập nhật giá trị của bản ghi trong khung nhìn
ans: A [suy luận]

Câu 44: Khi cấp quyền READ, người sử dụng chỉ được quyền
A. Truy vấn, không được phép sửa đổi, bổ sung
B. sửa đổi, bổ sung và cập nhật dữ liệu
C. sử dụng các câu truy vấn và cập nhật, lưu trữ dữ liệu
D. đọc và ghi
ans: A [suy luận]

Câu 45: Cho quan hệ R(A, B, C, D, E) với tập phụ thuộc hàm F = {AB --> E, E --> C, ABC --> D, D --> B}. Cho biết các khóa tối thiểu của lược đồ?
A. AB
B. AD
C. AC
D. ED
ans: A,B [suy luận]

Câu 46: Cho sơ đồ S(U), U = {A, B, C, D, E, F, G, H}, tập phụ thuộc hàm F={AB->CDE, CD->E, ABC->FG}. Sau khi chuẩn hóa S về dạng chuẩn 3 với phép tách bảo toàn thông tin và phụ thuộc hàm, ta được bao nhiêu sơ đồ con?
A. 1
B. 2
C. 4
D. 3
ans: D [suy luận]

Câu 47: DonHang( {pk}DonID{/pk} , NgayMua, TenKhach, TongTien); Khóa chính: DonID
SanPham ( {pk}SanPhamID{/pk} , TenSP, Gia); Khóa chính: SanPhamID
ChitietDonHang( {pkfk}ChitietDonID{/pkfk}; {fk}DonID{/fk} , {fk}SanPhamID{/fk} , quantity, NgayMua); Khóa chính: ChitietDonID; Hai khóa ngoài: DonID và SanPhamID tham chiếu đến các thuộc tính cùng tên của DonHang và SanPham. Hãy chọn các câu lệnh truy vấn đúng để thực hiện yêu cầu sau:"Đưa ra danh sách mã đơn hàng (DonID) mà có mua cả 2 sản phẩm có tên 'ADAPTATION SECRETS' và 'AFFAIR GENTLEMENT' ".
A. SELECT DonID FROM ChitietDonHang WHERE SanPhamID IN (SELECT SanPhamID FROM SanPham WHERE TenSP = 'ADAPTATION SECRETS') INTERSECT SELECT DonID FROM ChitietDonHang WHERE SanPhamID IN (SELECT SanPhamID FROM SanPham WHERE TenSP = 'AFFAIR GENTLEMENT')
B. SELECT DonID FROM ChitietDonHang WHERE SanPhamID IN (SELECT SanPhamID FROM SanPham WHERE TenSP IN ('ADAPTATION SECRETS', 'AFFAIR GENTLEMENT'))
C. SELECT DonID FROM ChitietDonHang d, SanPham s WHERE d.SanPhamID = s.SanPhamID AND (s.TenSP = 'ADAPTATION SECRETS' AND s.TenSP = 'AFFAIR GENTLEMENT')
D. SELECT DonID FROM ChitietDonHang d JOIN SanPham s ON d.SanPhamID = s.SanPhamID WHERE s.TenSP = 'ADAPTATION SECRETS' OR s.TenSP = 'AFFAIR GENTLEMENT'
ans: A [suy luận]

Câu 48: Một nhà máy sản xuất ô-tô sản xuất nhiều mẫu xe khác nhau. Mỗi mẫu xe được lắp ráp từ nhiều linh kiện khác nhau và một linh kiện có thể sử dụng được trong nhiều mẫu xe khác nhau. Mỗi mẫu xe được sản xuất tại một phân xưởng được đặt tại 1 thành phố, mỗi thành phố chỉ có 1 phân xưởng. Mỗi linh kiện chỉ được sản xuất tại một phân xưởng. Trong các sơ đồ ER sau, sơ đồ nào phù hợp nhất với mô tả trên ? (ko co so do)
A. Tùy chọn 2
B. Tùy chọn 3
C. Các đáp án trên sai
D. Tùy chọn 1
ans: C [suy luận]

Câu 49: Cho lược đồ quan hệ: Hoc(ma_sv, ma_lop, hoc_ky, diemthi)
Cho biết tác động của lệnh sau lên dữ liệu của lược đồ sau:
Update Hoc set diemthi = 0 where NOT (NULL = 1);
A. Trường diem_thi của bản ghi cuối cùng trong bảng bị cập nhật thành 0
B. Trường diem_thi của bản ghi đầu tiên trong bảng bị cập nhật thành 0;
C. Trường diem_thi của tất cả các bản ghi bị cập nhật thành 0
D. Không bản ghi nào bị thay đổi
ans: D [suy luận]

Câu 50: Phát biểu nào dưới đây là SAI ?
A. Các xử lý trong trigger không làm thay đổi dữ liệu ở các hàng
B. Trigger được tự động kích hoạt khi có sự kiện xảy ra
C. Trigger được thực thi ở phía hệ quản trị CSDL (server)
D. Trigger là xử lí được gắn với các bảng dữ liệu
ans: A [suy luận]

Câu 51: Cho cơ sở dữ liệu gồm các bảng sau (Khóa ngoài in nghiêng, Khóa chính in đậm và gạch chân):
Acc({pk}AccID{/pk}, Password, {fk}AccID_parent{/fk}), Object({pk}ObjectID{/pk}, name, type, {fk}AccID{/fk}), Permission({pkfk}AccID{/pkfk}, {pkfk}ObjectID{/pkfk}, {pk}type{/pk}, {pk}expired_date{/pk}) Trong đó:
* Acc: lưu thông tin tài khoản; AccID_parent là khóa ngoài tham chiếu đến AccID của bảng Acc
* Object: lưu thông tin về các đối tượng, miền giá trị của type : DOM(type) = {'table', 'view'}
* Permission: lưu thông tin về quyền hạn của các tài khoản trên các đối tượng, với miền giá trị của type : DOM(type) = {'r', 'w'}
Cho biết kết quả câu lệnh sau:
Delete from Acc where not exists(select * from Permission p where Acc.AccID = p.AccID);
A. Xóa các tài khoản (trên bảng Acc) mà đã được trao quyền trên 1 đối tượng (Object) nào đó
B. Lỗi cú pháp
C. Không bao giờ có bản ghi nào được xóa
D. Xóa các tài khoản (trên bảng Acc) mà chưa được trao quyền trên đối tượng (Object) nào
ans: D [suy luận]

Câu 52: Cho quan hệ R(A,B,C,D,E) với tập phụ thuộc hàm F = {AB->E, B->C, ABC->D, A->C}. Một khóa tối thiểu của R là
A. AB
B. A
C. ABC
D. BC
ans: A [suy luận]

Câu 53: Trong các phép toán sau trong đại số quan hệ sau, phép toán nào không có tính kết hợp?
A. Cả 3 đều có tính kết hợp
B. Phép tích Đề - các
C. Phép kết nối tự nhiên
D. Phép kết nối
ans: A [suy luận]

Câu 54: Cho quan hệ R(A,B,C,D,E) với tập phụ thuộc hàm F = {AB->E, B->C, ABC->D, A->C}. Cho biết dạng chuẩn cao nhất của lược đồ, giả sử các thuộc tính đều chỉ nhận giá trị nguyên tố ?
A. 1NF
B. không đạt chuẩn 1
C. 2NF
D. 3NF
ans: A [suy luận]

Câu 55: Cho câu lệnh SQL sau: SELECT sname FROM S, SP WHERE S.sid = SP.sid AND pid = 'P1' Hãy chọn Cây toán tử (Query Tree) biểu diễn đúng nhất quy trình thực thi logic của câu lệnh trên:
A. (Gốc) π<sub>sname</sub> (Nhánh) S ⋈<sub>{sid}</sub> (σ<sub>pid = 'P1'</sub>(SP))
B. (Gốc) π<sub>sname</sub> (Nhánh) σ<sub>pid = 'P1'</sub> (Lá) S ∪ SP
C. (Gốc) σ<sub>pid = 'P1'</sub> (Nhánh) S ⋈<sub>{S.sid = SP.sid}</sub> SP (Lá) sname
D. (Gốc) π<sub>sname</sub> σ<sub>S.sid = SP.sid AND pid = 'P1'</sub> (Lá) S × SP
ans: A [suy luận]

Câu 56: Cho sơ đồ quan hệ R gồm các thuộc tính: A, B, C, D, E, G, H, K.
Tập phụ thuộc hàm:
* A → D
* AB → D, E
* CE → G
* AE → H
* AD → E

Cho các bao đóng sau:
* V1 = bao đóng của (B, C, K)
* V2 = bao đóng của (A, B)
* V3 = bao đóng của (A, C)
* V4 = bao đóng của (A, D)

Hãy sắp xếp các tập V1, V2, V3, V4 theo số lượng thuộc tính tăng dần.
ans: V1 V4 V2 V3 [suy luận]

Câu 57: Trong các phát biểu sau về Clustered Index và Non-Clustered Index, phát biểu nào là đúng?
A. Clustered index yêu cầu cột khóa phải là khóa chính (PRIMARY KEY).
B. Một bảng chỉ có thể có tối đa một clustered index, nhưng có thể có nhiều non-clustered
C. Nếu bảng không có clustered index, thì dữ liệu sẽ được lưu theo cấu trúc heap, và non- clustered index sẽ trỏ trực tiếp đến RID (Row Identifier).
D. Nếu bảng có clustered index, thì non-clustered index sẽ trỏ trực tiếp đến dữ liệu vật lý của bảng, không thông qua clustered index.
E. Clustered index quyết định thứ tự vật lý của dữ liệu trong bảng, trong khi non-clustered index chỉ lưu con trỏ đến dữ liệu.
F. clustered index luôn nhanh hơn non-clustered index trong mọi trường hợp truy vấn.
ans: B,C,E [suy luận]

Câu 58: Cho CSDL gồm các quan hệ sau:
* NhanVien(NV , HoTen, NamSinh)
* DuAn(DA , TenDA, KinhPhi)
* ThamGia(NV, DA , MucLuong) -- (NV, DA) là khoá chính, NV và DA là khoá ngoài.

Câu lệnh SQL nào sau đây đưa ra HoTen nhân viên và Số dự án họ tham gia
A. SELECT Hoten, COUNT(NV) FROM NhanVien, ThamGia WHERE NhanVien.NV = ThamGia.NV GROUP BY NhanVien.DA
B. SELECT HoTen, Count(DA) FROM NhanVien, Thamgia WHERE NhanVien.NV = ThamGia.NV GROUP BY NhanVien.NV
C. SELECT HoTen, COUNT(DA) FROM NhanVien, ThamGia WHERE NhanVien.NV = ThamGia.NV GROUP BY NV
D. SELECT HoTen, SUM(DA) FROM NhanVien, ThamGia WHERE NhanVien.NV = ThamGia.NV GROUP BY NhanVien.NV
ans: B [suy luận]

Câu 59: Cho CSDL gồm các quan hệ sau:
* NhaHang ( MaNH, TenNH, DiaChi, SoDienThoai)
* NguoiDung ( MaNSD, HoTen, SDT, Email)
* DanhGia ( MaNSD, MaNH, DiemSo, YeuThich)

Biểu thức đại số nào mô tả yêu cầu: Liệt kê số điện thoại những nhà hàng được khách hàng có tên 'Monte Carlos' đánh giá từ 8 điểm trở lên (trường DiemSo).
A. π<sub>SoDienThoai</sub> (σ<sub>DiemSo>=8</sub> (DanhGia) ∗ π<sub>MaNSD</sub> (σ<sub>HoTen='Monte Carlos'</sub>(NguoiDung)))
B. σ<sub>SoDienThoai</sub> (NhaHang ∗ σ<sub>DiemSo>=8</sub> (DanhGia) ∗ π<sub>MaNSD</sub> (σ<sub>HoTen='Monte Carlos'</sub>(NguoiDung)))
C. π<sub>SoDienThoai</sub> ((NhaHang ∗ π<sub>MaNSD</sub> (σ<sub>HoTen='Monte Carlos'</sub> (NguoiDung))) ∗ σ<sub>DiemSo>=8</sub> (DanhGia))
D. π<sub>SoDienThoai</sub> (NhaHang ∗ σ<sub>DiemSo>=8</sub> (DanhGia) ∗ π<sub>MaNSD</sub> (σ<sub>HoTen='Monte Carlos'</sub>(NguoiDung)))
ans: D [suy luận]

Câu 60: Yêu cầu truy vấn: Đưa ra danh sách sinh viên đã đăng ký môn 'Hệ phân tán', sắp xếp theo học kỳ đăng ký. Hãy chọn câu lệnh SQL cho phép thực hiện yêu cầu trên
A. SELECT s.* FROM Sinhvien s, Dangky d, Monhoc m WHERE m.MaMH = d.MaMH AND TenMH = 'He phan tan' ORDER BY Hocky;
B. SELECT s.* FROM Sinhvien s, Dangky d, Monhoc m WHERE s.MaSV = d.MaSV AND TenMH = 'He phan tan' ORDER BY Hocky;
C. SELECT s.* FROM Sinhvien s, Dangky d WHERE s.MaSV = d.MaSV AND TenMH = 'He phan tan' ORDER BY Hocky;
D. SELECT s.* FROM Sinhvien s, Dangky d, Monhoc m WHERE s.MaSV = d.MaSV AND m.MaMH = d.MaMH AND TenMH = 'He phan tan' ORDER BY Hocky;
ans: D [suy luận]

Câu 61: Cho CSDL gồm các quan hệ sau:
* NhanVien( MaNV , HoTen, NamSinh)
* DuAn( MaDA , TenDA, KinhPhi)
* ThamGia( MaNV, MaDA , MucLuong) -- (MaNV, MaDA) là khoá chính, MaNV và MaDA là khoá ngoài
Giả sử các bảng trên có đầy đủ các ràng buộc khóa chính, khóa ngoài. Trong đó, khóa chính được in đậm và gạch chân, khóa ngoài in nghiêng
Phương án nào dưới đây đảm bảo luôn xóa được nhân viên có tên là 'Nguyễn Văn A' ?
A. DELETE * FROM NhanVien WHERE HoTen = 'Nguyễn Văn A';
B. DELETE * FROM ThamGia WHERE MaNV in (SELECT MaNV FROM NhanVien WHERE HoTen = 'Nguyễn Văn A');
C. DELETE FROM NhanVien WHERE HoTen = 'Nguyễn Văn A';
D. DELETE FROM ThamGia WHERE MaNV in (SELECT MaNV FROM NhanVien WHERE HoTen = 'Nguyễn Văn A');
ans: D [suy luận]

Câu 62: Có tổng cộng bao nhiêu chiến lược tối ưu tổng quát?
A. 4
B. 5
C. 6
D. 7
E. 8
ans: D [suy luận]

Câu 63: Cho quan hệ R(A, B, C, D, E) với tập phụ thuộc hàm F = {AB->E, B->C, ABC->D,A->C}Cho biết dạng chuẩn cao nhất của lược đồ, giả sử các thuộc tính đều chỉ nhận giá trị nguyên tố?
A. 2NF
B. Không đạt chuẩn 1
C. 1NF
D. 3NF
ans: C [suy luận]

Câu 64: Cho cơ sở dữ liệu gồm các bảng sau (Khóa ngoài in nghiêng, Khóa chính in đậm và gạch chân): Acc( AccID, Password, AccID_parent), Object( ObjectID, name, type, AccID),Permission( AccID, ObjectID, type, expired_date). Trong đó:
* Acc: lưu thông tin tài khoản; AccID_parent là khóa ngoài tham chiếu đến AccID của bảng Acc
* Object: lưu thông tin về các đối tượng, miền giá trị của type : DOM(type) = {'table', 'view'}
* Permission: lưu thông tin về quyền hạn của các tài khoản trên các đối tượng, với miền giá trị của type : DOM(type) = {'r', 'w'}
Giả sử các cột trong các bảng và các khóa chính đã được tạo. Lệnh nào dưới đây để tạo ràng buộc khóa ngoài cho bảng Acc?
A. alter table Object add constraint fk_acc foreign key (Accid) references Acc(AccID_parent);
B. alter table object add constraint kf_acc foreign key (AccID_parent) references Acc(AccID);
C. alter table Acc add constraint fk_acc foreign key (AccID_parent) references Acc(AccID);
D. alter table Acc add constraint fk_acc foreign key (AccID) references Acc(AccID_parent);
ans: C [suy luận]

Câu 65: Cho schema của một DB như sau:
* SINHVIEN(MASV, TENSV, EMAIL, SDT, NGAYSINH)
* HOCPHAN(MAHP, TENHP, LOAIHP, SOTINCHI)
* LOPHOCPHAN(MALHP, MAHP, HOCKY, NAMHOC)
* DANGKY(MASV, MALHP)

Cho câu lệnh sau:
```sql
SELECT SV.MASV
FROM SINHVIEN SV
JOIN DANGKY DK ON SV.MASV = DK.MASV
WHERE YEAR(NGAYSINH) = '2006';
```
Kết quả của câu lệnh trên là gì?
A. Sinh viên đã đăng ký ít nhất một lớp học phần có năm sinh 2006
B. Sinh viên chưa đăng ký học phần nào có năm sinh 2006
C. Lỗi cú pháp
D. Tất cả sinh viên có năm sinh 2006
ans: A [suy luận]
Câu 66: Thứ tự đúng khi viết câu lệnh truy vấn trong ngôn ngữ SQL là gì?
A. SELECT, FROM, GROUP BY, HAVING, WHERE, ORDER BY
B. SELECT, FROM, WHERE, GROUP BY, HAVING, ORDER BY
C. SELECT, GROUP BY, HAVING, FROM, ORDER BY
D. SELECT, GROUP BY, HAVING, WHERE, ORDER BY
ans: B [suy luận]
Câu 67: Câu hỏi: cho quan hệ R được xác định trên {A,B,C,D}, S được xác định trên {B,D,E,G}, T được xác định trên {A,C, H, K}. Hãy cho biết sơ đồ quan hệ của phép toán (S ∗ T) ÷ R.
A. {E,G,H,K}
B. {B,D,H,K}
C. {A,C,E,G}
D. {A,B,C,D}
ans: A [suy luận]
Câu 68: Một hệ cơ sở dữ liệu KHÔNG gồm thành phần nào sau đây?
A. Hệ quản trị CSDL
B. Phần mềm ứng dụng
C. Người dùng
D. Tất cả đều là thành phần của hệ CSDL
E. Phần cứng
ans: D [suy luận]
Câu 69: Chọn câu truy vấn SELECT trả về tất cả các mặt hàng mà tên bắt đầu bởi chuỗi kí tự 'choco'
A. SELECT * FROM items WHERE name LIKE 'choco_'
B. SELECT * FROM items WHERE name = 'choco%';
C. SELECT * FROM items WHERE name LIKE '%choco%'
D. SELECT * FROM items WHERE name LIKE 'choco%'
ans: D [suy luận]
Câu 70: CongDan(CCCD, HoTen, Tuoi, DiaChi)
Tiem(CCCD, MaV, NgayTiem, MuiTiem)
Vaccine(MaV, TenVaccine)
Trong các biểu thức đại số quan hệ dưới đây mô tả yêu cầu liệt kê họ tên những công dân dưới 11 tuổi đã tiêm vaccine Pfizer ở mũi tiêm thứ hai, thì biểu thức đại số nào KHÔNG đúng:
A. πHoTen(σTuoi < 11(CongDan) ∗ σMuiTiem = 2(πMuiTiem(Tiem)) ∗ σTenVaccine = 'Pfizer'(Vaccine))
B. πHoTen(πCCCD, HoTen(σTuoi < 11(CongDan)) ∗ σMuiTiem = 2(Tiem) ∗ σTenVaccine = 'Pfizer'(Vaccine))
C. πHoTen(σTuoi < 11(CongDan) ∗ σMuiTiem = 2(Tiem) ∗ πMaV(σTenVaccine = 'Pfizer'(Vaccine)))
D. πHoTen(σTuoi < 11(CongDan) ∗ σMuiTiem = 2(Tiem) ∗ σTenVaccine = 'Pfizer'(Vaccine))
ans: A [suy luận]
Câu 71: Cho lược đồ quan hệ R(U,F) Với U = {A, B, C, D, E} và F = {AB -> CD; E -> C; D -> CE; A -> E}. Tính (AD)+
A. ACE
B. ABD
C. ACED
D. ABCDE
ans: C [suy luận]
Câu 72: (TỰ LUẬN) Cho lược đồ quan hệ R(U,F) Với U = {A, B, C, D, E} và F = {AB -> CD; E -> C; D -> CE; A -> E}. Tính (AD)+. Tính tổng các phần tử trong đáp án cuối cùng?
ans: 4 [suy luận]
Câu 73: Phát biểu nào dưới đây là ĐÚNG về khóa ngoài ?
A. Một bảng chỉ có nhiều nhất 1 khóa ngoài
B. Khóa ngoài của một bảng có thể tham chiếu đến khóa chính của chính bảng đó
C. Khóa ngoài luôn tham gia vào khóa chính
D. Một bảng luôn có ít nhất 1 khóa ngoài
ans: B [suy luận]
Câu 74: Cho sơ đồ quan hệ R(U) với: U = {A, B, C, D, E} F = {A -> BC, B -> C, CD -> E} Bao đóng của BDE với sơ đồ này là?
A. ABCDE
B. BCD
C. BCDE
D. BDE
ans: C [suy luận]
Câu 76: Cho CSDL gồm các quan hệ sau:
NhanVien(NV, HoTen, NamSinh)
DuAn(DA, TenDA, KinhPhi)
ThamGia(NV, DA, MucLuong)
(NV, DA) là khóa chính, NV và DA là khóa ngoài.
Câu lệnh SQL nào sau đây đưa ra HoTen nhân viên làm việc tại dự án có tên là '007'?
A. Select HoTen FROM NhanVien, DuAn, ThamGia WHERE NhanVien.NV = ThamGia.NV, DuAn.DA = ThamGia.DA AND TenDA = '007'
B. Select HoTen FROM NhanVien, DuAn, ThamGia WHERE TenDA = '007'
C. Select HoTen FROM NhanVien, ThamGia WHERE NhanVien.NV = ThamGia.NV AND DuAn.DA = ThamGia.DA AND TenDA = '007'
D. Select HoTen FROM NhanVien, DuAn, ThamGia WHERE NhanVien.NV = ThamGia.NV AND DuAn.DA = ThamGia.DA AND TenDA = '007'
ans: D [suy luận]
Câu 77: Cho sơ đồ quan hệ R có lực lượng m, sơ đồ quan hệ S có lực lượng n. Hãy cho biết lực lượng của biểu thức đại số quan hệ: R x S
A. min(m, n)
B. Chưa đủ thông tin
C. m + n
D. max(m, n)
E. m*n
ans: E [suy luận]
Câu 78: Phát biểu nào sau đây về PRIMARY KEY là đúng? (Chọn tất cả đáp án đúng)
A. PRIMARY KEY tự động tạo chỉ mục (index).
B. Một bảng chỉ có thể có tối đa một PRIMARY KEY, nhưng có thể gồm nhiều cột.
C. PRIMARY KEY có thể được tham chiếu bởi nhiều FOREIGN KEY ở bảng khác.
D. Một bảng có thể có nhiều PRIMARY KEY nếu chúng ở các cột khác nhau.
E. PRIMARY KEY cho phép giá trị NULL.
ans: A,B,C [suy luận]
Câu 79: Xét các phát biểu về SAVEPOINT:
Phát biểu nào đúng? (Chọn tất cả đáp án đúng)
A. Có thể tạo nhiều SAVEPOINT trong một giao dịch.
B. SAVEPOINT cho phép rollback một phần giao dịch.
C. SAVEPOINT chỉ có thể dùng trong chế độ autocommit = 1.
D. SAVEPOINT bị xóa khi COMMIT.
E. Sau khi ROLLBACK TO SAVEPOINT, giao dịch vẫn tiếp tục được.
ans: A,B,D,E [suy luận]
Câu 80: Lệnh nào giúp một giao dịch quay trở về trạng thái trước khi các thay đổi được lưu vào CSDL ?
A. ABORT
B. COMMIT
C. RELEASE
D. ROLLBACK
ans: D [suy luận]
Câu 81: Sau khi thực hiện: GRANT UPDATE ON QLSV.SINHVIEN TO 'user2'@'%'; REVOKE UPDATE ON QLSV.SINHVIEN FROM 'user2'@'%'; Phát biểu nào sau đây là đúng nhất?
A. user2 vẫn có quyền UPDATE vì GRANT được thực hiện trước
B. user2 bị mất tất cả các quyền trên CSDL QLSV
C. user2 bị xóa khỏi hệ thống MySQL
D. user2 không còn quyền UPDATE trên bảng SINHVIEN
ans: D [suy luận]
Câu 82: GRANT x ON y TO z WITH GRANT OPTION Phát biểu nào đúng về x, y, z?
A. x là một hoặc một nhóm người sử dụng, y là một hoặc nhiều thao tác, z là một hoặc nhiều đối tượng
B. x là một hoặc nhiều đối tượng, y là một hoặc nhiều thao tác, z là một hoặc một nhóm người sử dụng
C. x là một hoặc nhiều thao tác, y là một hoặc một nhóm người sử dụng, z là một hoặc nhiều đối tượng
D. x là một hoặc nhiều thao tác, y là một hoặc nhiều đối tượng, z là một hoặc một nhóm người sử dụng
ans: D [suy luận]
Câu 83: Một giao dịch đọc cùng một tập bản ghi hai lần, lần thứ hai xuất hiện thêm bản ghi mới do giao dịch khác INSERT và COMMIT. Hiện tượng này là gì?
A. Dirty Read
B. Phantom Read
C. Non-repeatable Read
D. Lost Update
ans: B [suy luận]
Câu 84: Cho sơ đồ quan hệ R gồm các thuộc tính: A, B, C, D, E, G, H
Tập phụ thuộc hàm:
A -> D
AB -> D, E
CE -> G
AE -> H
AD -> E
Cho phép tách:
ρ = (ADEH, CEG, ABC)
Khi kiểm tra tính bảo toàn dữ liệu, hỏi hàng số mấy có toàn bộ giá trị là a?
A. 1
B. 3 đáp án trên sai
C. 2
D. 3
ans: D [suy luận]
Câu 85: Mọi giao dịch không ảnh hưởng đến các giao dịch khác là phải có tính chất nào?
A. Tính nhất quán
B. Tính nguyên tố
C. Tính cách ly
D. Tính bền vững
ans: C [suy luận]
Câu 86: Cho quan hệ: R(A, B, C, D, E)
với tập phụ thuộc hàm:
F = {AB -> E; B -> C; ABC -> D; A -> C}
Cho biết F tương đương với tập phụ thuộc hàm nào dưới đây?
A. {AB -> ED, B -> C, A -> C}
B. {B -> ED, B -> C, A -> C}
C. {AB -> ED, AB -> C}
D. {A -> ED, B -> C, A -> C}
ans: A [suy luận]
Câu 87: Cho lược đồ quan hệ R(A, B, E, I, J, G, H) và tập phụ thuộc hàm F = {AB --> E; AC --> J; BH --> I; B --> G; GA --> HB} Có thể suy ra những phụ thuộc hàm nào? (Chọn tất cả đáp án đúng)
A. AB --> EHIC
B. ABG --> EHI
C. B --> GE
D. AB --> EI
E. Tùy chọn 2
ans: B,D [suy luận]

Câu 88: Cho các quan hệ: R(A, B, C, D)
S(B, D, E, G)
T(A, C, H, K)
Và các quan hệ trung gian:
V1 = (S * T) ÷ R
V2 = R * S
V3 = S * chiếu trên các thuộc tính C, H, K của T
V4 = chiếu trên A, B của R * chiếu trên B, D của S * chiếu trên C, H của T
Hãy sắp xếp các quan hệ V1, V2, V3, V4 theo thứ tự tăng dần về bậc. Ví dụ: V4 V3 V2 V1
ans: V1 V4 V2 V3 [suy luận]

Câu 89: Phát biểu nào chưa chính xác về biểu thức đại số quan hệ (ĐSQH)
A. Kết quả thực hiện biểu thức ĐSQH là 1 hay nhiều quan hệ
B. Đầu vào là một hay nhiều quan hệ
C. Gồm các phép toán tương ứng với các thao tác trên quan hệ
D. Đầu ra là 1 quan hệ
ans: A [suy luận]

Câu 90: Cho quan hệ R(A,B,C,D,E) với tập phụ thuộc hàm F = {AB->E, B->C, ABC->D, A->C} Một khóa tối thiểu của R là
A. AB
B. A
C. ABC
D. BC
ans: A [suy luận]

Câu 91: Trong các phép toán sau trong đại số quan hệ sau, phép toán nào không có tính kết hợp?
A. Cả ba đều có tính kết hợp
B. Phép kết nối tự nhiên
C. Phép lấy tích descartes
D. Phép kết nối
ans: A [suy luận]

Câu 92: (TỰ LUẬN) Cho cơ sở dữ liệu gồm các quan hệ như ở Câu 129. Hãy viết biểu thức đại số quan hệ đưa ra danh sách các bộ (MãMH, TênMH, SốTínChỉ) được giảng viên “Nguyễn Văn A” giảng dạy trong học kỳ 20241. (Hình dưới là đáp án tham khảo, hãy làm trước khi xem)(tự tưởng tượng hình:))))
ans: π<sub>MãMH, TênMH, SốTínChỉ</sub>(σ<sub>TênGV = 'Nguyễn Văn A' ∧ HọcKỳ = '20241'</sub>(GIANGVIEN ⋈ LOPHOCPHAN ⋈ HOCPHAN)) [suy luận]

Câu 93: Cho sơ đồ quan hệ R(U) với tập thuộc tính U = {A, B, C, D, E, G, H, K} và tập phụ thuộc hàm F = {AB -> CGH, DG->CH, AD->BGH, BG->CK}. Hỏi trong phủ tối thiểu của F thì thuộc tính A xuất hiện bao nhiêu lần ở vế trái?
ans: 3 [suy luận]

Câu 94: Cho lược đồ quan hệ R(ABCDEGH) và tập phụ thuộc hàm: F = {AB->C; D->EG; C->A; BE->C; ACD->B; CE->AG; BC->D; CG->BD; G->H}. Tính (BE)+
A. ABCDEGH
B. ACDGH
C. ABCDEH
D. BDEGH
ans: A [suy luận]

Câu 95: Trong mô hình cơ sở dữ liệu 3 tầng (khi trừu tượng hóa dữ liệu), gồm có 3 mức: mức trong (lưu trữ), mức khái niệm (logic) và mức ngoài (các khung nhìn). Điều khẳng định nào sau đây đúng ?
A. Người thiết kế CSDL thường chỉ xử lý với sơ đồ trong
B. Hầu hết người dùng CSDL không bao giờ xem sơ đồ trong (không cần)
C. Người dùng cuối thông thường, không phải là chuyên gia CNTT thường chỉ xử lý ở mức khái niệm
D. Người quản trị CSDL, người thiết kế CSDL và người dùng cuối thường chỉ xử lý ở mức khung nhìn bên ngoài
ans: B [suy luận]

Câu 96: Cho lược đồ quan hệ R(ABCDE) và tập phụ thuộc hàm F = {A->BC; BD->E; B->C}. Phép tách lược đồ R thành các lược đồ con R1(ABD), R2(BC), R3(ADE) sẽ:
A. Bảo toàn thông tin, không bảo toàn tập phụ thuộc hàm
B. Không bảo toàn thông tin, không bảo toàn tập phụ thuộc hàm
C. Bảo toàn thông tin, bảo toàn tập phụ thuộc hàm
D. Không bảo toàn thông tin, bảo toàn tập phụ thuộc hàm
ans: A [suy luận]

Câu 97: Xét các mức cô lập giao dịch (Isolation Levels). Phát biểu nào sau đây là đúng? (Chọn tất cả đáp án đúng)
A. READ COMMITTED loại bỏ dirty read nhưng vẫn có thể xảy ra non-repeatable read.
B. READ UNCOMMITTED có thể xảy ra dirty read.
C. REPEATABLE READ đảm bảo không xảy ra phantom read.
D. SERIALIZABLE đảm bảo kết quả tương đương thực thi tuần tự các giao dịch.
E. SERIALIZABLE là mức cô lập cao nhất.
ans: A,B,D,E [suy luận]

Câu 98: Khi một bảng đã được tạo, nếu muốn bổ sung thêm cột hoặc loại bỏ cột cho bảng này thì chúng ta sử dụng câu lệnh bắt đầu với từ khóa nào dưới đây ?
A. ALTER TABLE
B. ADD COLUMN
C. DROP COLUMN
D. ALTER COLUMN
ans: A [suy luận]

Câu 99: Cho biết phát biểu nào dưới đây là đúng ?
A. Trigger được gọi tường minh bởi người phát triển hệ thống
B. Trigger được thực thi ở phía ứng dụng (client)
C. Các xử lý trong trigger không làm thay đổi dữ liệu ở các bảng
D. Trigger được tự động kích hoạt khi có sự kiện xảy ra
ans: D [suy luận]

Câu 100: Cho lược đồ quan hệ r(ABCDEGH) và tập phụ thuộc hàm F = {BG->E; I->H; BC->IH; A->CD}. Các phụ thuộc hàm nào sau đây KHÔNG suy diễn được từ F ?
A. B->E
B. B->I
C. BGC->I
D. C->I
ans: A,B,D [suy luận]

Câu 101: Tính phủ tối thiểu của tập phụ thuộc hàm F = {A->BC; A->B; B->C; AB->C}
A. A->B; B->C
B. AB->C
C. A->BC
D. A->B; AB->C
ans: A [suy luận]

Câu 102: Cho biết phát biểu nào dưới đây là không chính xác về khóa chính (primary key) của 1 bảng ?
A. Khóa chính có thể có nhiều hơn 1 thuộc tính
B. Bảng có thể không cần khóa chính
C. Hai bản ghi bất kì không được có giá trị trên khóa chính trùng nhau
D. Trong 1 bảng có thể có nhiều hơn 1 khóa chính
ans: D [suy luận]

Câu 103: Cho schema của một DB như sau:
SINHVIEN(MASV, TENSV, EMAIL, SDT, NGAYSINH)
HOCPHAN(MAHP, TENHP, LOAIHP, SOTINCHI)
LOPHOCPHAN(MALHP, MAHP, HOCKY, NAMHOC)
DANGKY(MASV, MALHP)
Cho câu lệnh sau:
SELECT MASV FROM SINHVIEN
WHERE MASV NOT IN (SELECT MASV FROM DANGKY);
Điều gì có thể xảy ra nếu bảng DANGKY.MASV chứa NULL?
A. Lỗi runtime
B. Truy vấn trả về sai một vài dòng
C. Truy vấn chạy bình thường
D. Không trả về dòng nào
ans: D [suy luận]

Câu 104: Cho schema của một DB như sau:
SINHVIEN(MASV, TENSV, EMAIL, SDT, NGAYSINH)
HOCPHAN(MAHP, TENHP, LOAIHP, SOTINCHI)
LOPHOCPHAN(MALHP, MAHP, HOCKY, NAMHOC)
DANGKY(MASV, MALHP)
Cho câu lệnh sau:
SELECT * FROM SINHVIEN
WHERE YEAR(NGAYSINH) = 2006;
Hãy lựa chọn nhận định đúng?
A. Có thể làm mất hiệu quả index
B. Không chạy được
C. Chạy nhanh hơn so với BETWEEN
D. Sai cú pháp
ans: A [suy luận]

Câu 105: Cho lược đồ quan hệ R(ABCDE) và tập phụ thuộc hàm: F = {AB->D; C->B; CB->E; E->DC}
Phép tách lược đồ R thành các lược đồ con R1(ABC), R2(CBE), R3(DE) thỏa mãn các tiêu chí nào dưới đây ?
A. Không bảo toàn thông tin, bảo toàn tập phụ thuộc hàm
B. Bảo toàn thông tin, không bảo toàn tập phụ thuộc hàm
C. Không bảo toàn thông tin, không bảo toàn tập phụ thuộc hàm
D. Bảo toàn thông tin, bảo toàn tập phụ thuộc hàm
ans: B [suy luận]

Câu 106: Cho cơ sở dữ liệu gồm các quan hệ:
KhánGiả (MãKG, HọTên, Tuổi, ĐịaChỉ);
Phim (MãPh, TênPhim, ThểLoại, NămSảnXuất);
XemPhim (MãXem, MãKG, MãPh, ĐiểmĐánhGiá),
hãy viết biểu thức đại số quan hệ để đưa ra danh sách các (MãKG, HọTên, ĐịaChỉ) của những người đã từng xem phim thể loại 'hoạt hình' và cho điểm đánh giá lớn hơn hoặc bằng 9.
ans: π<sub>MãKG, HọTên, ĐịaChỉ</sub>(σ<sub>ThểLoại = 'hoạt hình' ∧ ĐiểmĐánhGiá ≥ 9</sub>(KhánGiả ⋈ XemPhim ⋈ Phim)) [suy luận]

Câu 107: Chuyển đổi phát biểu sau sang logic vị từ: "All boys are cool".
A. Với mọi x: boy(x) -> cool(x)
B. Với mọi x: boy(x) <-> cool(x)
C. Với mọi x: boy(x) -> (cool, x)
D. Với mọi x: boy(x) ^ cool(x)
ans: A [suy luận]

Câu 108: Trong logic mệnh đề, mệnh đề (P ^ Q) ^ -R -> Q là:
A. đúng đắn (valid)
B. không thỏa mãn được (unsatisfiable)
C. không đúng đắn (not valid)
ans: A [suy luận]

Câu 109: Tìm kiếm nào tương tự như tìm kiếm minimax (trong duyệt cây tìm kiếm)?
A. Tìm kiếm theo chiều rộng (Breadth-First Search - BFS)
B. Tất cả các câu trả lời trên (dưới) đây
C. Tìm kiếm theo chiều sâu (Depth-First Search - DFS)
D. Tìm kiếm leo đồi (Hill Climbing Search)
ans: C [suy luận]

Câu 110: Trong bài toán thỏa mãn ràng buộc, biến ràng buộc nhiều nhất là gì?
A. Biến còn lại ít giá trị hợp lệ nhất có thể gán.
B. Biến còn lại nhiều giá trị hợp lệ nhất có thể gán.
C. Biến ràng buộc ít biến khác nhất (chưa được gán giá trị).
D. Biến bị ràng buộc bởi số lượng các biến khác nhiều nhất (chưa được gán giá trị).
ans: D [suy luận]

Câu 111: Hành động của tác tử phản xạ đơn giản (simple reflex agent) hoàn toàn dựa vào:
A. Nhận thức hiện tại (Current perception)
B. Lịch sử nhận thức (Perception history)
C. Lý thuyết học
D. Các hàm tiện ích
ans: A [suy luận]

Câu 112: Câu nào sau đây là dạng logic vị từ của câu "All students study at least one branch"?
ans: ∀x(Student(x) → ∃y(Branch(y) ∧ Study(x, y))) [suy luận]

Câu 113: Một thủ tục suy diễn từ cơ sở tri thức KB được gọi là hoàn chỉnh nếu nó có thể:
A. suy diễn ra một số mệnh đề được bao hàm từ KB
B. suy diễn ra bất kỳ mệnh đề được bao hàm từ KB
C. suy diễn ra bất kỳ mệnh đề nào từ KB
ans: B [suy luận]

Câu 114: Trong giải thuật Alpha-Beta Pruning, các giá trị Alpha và Beta được cập nhật lúc nào (ở đâu)?
A. Dọc theo đường đi tìm kiếm (trong cây tìm kiếm)
B. Tại nút gốc
C. Tại bước tìm kiếm cuối cùng (kết thúc của quá trình tìm kiếm)
D. Tại nút có giá trị ước lượng lớn hơn Beta và nhỏ hơn Alpha
ans: A [suy luận]

Câu 115: Tìm kiếm theo chiều rộng là (có thể chọn nhiều đáp án):
A. Hoàn chỉnh
B. Tối ưu (nếu chi phí mỗi bước bằng nhau)
C. Độ phức tạp về thời gian lớn hơn tìm kiếm theo chiều sâu
D. Độ phức tạp về bộ nhớ nhỏ hơn tìm kiếm theo chiều sâu
ans: A,B [suy luận]

Câu 116: Suy diễn tiến là quá trình (), suy diễn lùi là quá trình ()
A. Hướng đích, hướng đích
B. Hướng dữ liệu, hướng dữ liệu
C. Hướng dữ liệu, hướng đích
D. Hướng đích, hướng dữ liệu
ans: C [suy luận]

Câu 117: Tìm kiếm với chi phí tối thiểu mở rộng các node với:
A. Chi phí đường đi ngắn nhất (từ node gốc)
B. Chi phí ước lượng tới nút đích ngắn nhất
C. Chi phí đường đi trung bình
D. Chi phí đường đi lớn nhất
ans: A [suy luận]

Câu 118: Môi trường như thế nào được gọi là bán động?
A. Môi trường không thay đổi khi thời gian trôi đi
B. Môi trường bị thay đổi
C. Môi trường không thay đổi khi thời gian trôi đi, nhưng hiệu năng của tác tử thay đổi
D. Hiệu năng của tác tử thay đổi
ans: C [suy luận]

Câu 119: Tìm kiếm tốt nhất trước (Best-First) được triển khai bằng cách sử dụng cấu trúc dữ liệu sau:
A. Ngăn xếp
B. Hàng đợi vòng (phần tử cuối cùng được kết nối với phần tử đầu tiên)
C. Hàng đợi ưu tiên (hàng đợi sắp xếp các phần tử dựa trên giá trị của chúng)
D. Hàng đợi
ans: C [suy luận]

Câu 120: Cho 2 quan hệ R (n bản ghi), S (m bản ghi), số lượng bản ghi sau khi thực hiện phép nối tự nhiên R*S là:
A. Nhỏ hơn min(m, n)
B. m * n
C. Đáp án khác
D. Nhỏ hơn hoặc bằng min(m, n)
ans: C [suy luận]

Câu 121: Cho schema của một DB như sau:
SINHVIEN(MASV, TENSV, EMAIL, SDT, NGAYSINH)
HOCPHAN(MAHP, TENHP, LOAIHP, SOTINCHI)
LOPHOCPHAN(MALHP, MAHP, HOCKY, NAMHOC)
DANGKY(MASV, MALHP)

Cho câu lệnh sau:
SELECT MAHP, COUNT(*)
FROM LOPHOCPHAN;

Kết quả?
A. Đếm tổng số lớp học phần
B. Đếm số lớp học phần cho mỗi học phần
C. Lỗi cú pháp
D. Đếm số học phần
ans: C [suy luận]

Câu 122: Cho lược đồ quan hệ R(ABCDEFG), tập phụ thuộc hàm F = {B->A; D->C; D->EB; DF->G} Tách về dạng chuẩn 3, bảo toàn tập phụ thuộc hàm là:
A. R1(BA), R2(DBCFG)
B. R1(BA), R2(DBCE), R3(DFG)
C. R1(BA), R2(DC), R3(DE), R4(DFG)
ans: B [suy luận]

Câu 123: Cho quan hệ: ThueBao (MaTB, TenTB, SoTB, DiaChi)
Biểu thức đại số quan hệ biểu diễn yêu cầu "Liệt kê thông tin thuê bao có mã thuê bao là 3590" là:
A. Π<sub>COUNT(*)</sub> (σ<sub>MaTB=3590</sub> (ThueBao))
B. σ<sub>MaTB=3590</sub> (ThueBao)
C. Π<sub>SoTB</sub> (σ<sub>MaTB=3590</sub> (ThueBao))
D. Π<sub>TenTB</sub> (σ<sub>MaTB=3590</sub> (ThueBao))
ans: B [suy luận]

Câu 124: Tổ chức tệp dữ liệu nào phải quét toàn bộ tệp khi tìm kiếm một bản ghi
A. Tổ chức tệp đống (heap file)
B. Tổ chức tệp băm (hashed file)
C. Tổ chức tệp chỉ dẫn (indexed file)
D. Tổ chức cây cân bằng (balanced tree)
ans: A [suy luận]

Câu 125: Khi thực hiện một câu lệnh phức tạp có phần (S ⋈ SP) xuất hiện nhiều lần, chiến lược tối ưu tổng quát khuyên chúng ta nên làm gì?
A. Thay thế bằng tích Descartes để đơn giản hóa biểu thức.
B. Thực hiện phép tính (S ⋈ SP) mỗi khi cần để đảm bảo dữ liệu mới nhất.
C. Đẩy phép chiếu vào giữa biểu thức con chung đó.
D. Xác định biểu thức con chung này để đánh giá và lưu kết quả tạm thời, chỉ tính toán một lần
ans: D [suy luận]

Câu 126: Xử lý một truy vấn bao gồm bao nhiêu bước chính:
A. 3
B. 4
C. 5
D. 6
ans: B [suy luận]

Câu 127: Cho sơ đồ quan hệ R gồm các thuộc tính: A, B, C, D, E.
Tập phụ thuộc hàm:
A → E
BC → AD
C → B
E → D

Trong phủ tối thiểu của tập phụ thuộc hàm F, C xuất hiện bao nhiêu lần ở bên trái?
A. 3
B. 0
C. 1
D. 4
E. 2
ans: E [suy luận]

Câu 128: Câu lệnh nào sau đây bị sai?
A. SELECT tenSV as TenSinhVien FROM tblSinhVien;
B. UPDATE tblSinhVien set tenSV = 'Nguyen Van A' where masv = '20122003';
C. INSERT INTO tblSinhVien (masv, tenSV) VALUE ('20122003', 'Nguyen Van A');
D. DELETE FROM tblSinhVien WHERE masv = '20122003';
ans: C [suy luận]

Câu 129: Phát biểu nào sau đây là đúng?
A. Tất cả các phương án lựa chọn chọn khác đều sai
B. Một quan hệ chỉ được có 1 khóa tối thiểu
C. Một quan hệ có thể có nhiều khóa tối thiểu
D. K không là khóa tối thiểu của r nếu K là 1 khóa của r và bất kì tập con thực sự nào của K đều không phải khóa của r
ans: C [suy luận]

Câu 130: Trong một trigger, nhận định nào sau đây là đúng về biến "NEW" và "OLD"? (Chọn tất cả đáp án đúng)
A. "NEW" được sử dụng để chọn bản ghi, trong khi "OLD" được sử dụng để chèn bản ghi
B. "NEW" chỉ áp dụng trong trigger "AFTER", trong khi "OLD" được sử dụng trong trigger "BEFORE".
C. "NEW" và "OLD" là 2 biến có cùng cấu trúc với cấu trúc của bảng/view có sự kiện kích hoạt trigger
D. "NEW" đại diện cho bản ghi sau sửa đổi dữ liệu, trong khi "OLD" là biến đại diện cho bản ghi trước sửa đổi
ans: C,D [suy luận]

Câu 131: Cho sơ đồ quan hệ R(U) với tập thuộc tính U = {A, B, C, D, E, G, H, K} và tập phụ thuộc hàm F = {ABK->EGH, DG->CHK, AD->GH, BK->EC}. Kiểm tra phép tách thành {ABGHK, CDGHK, ADG, ABD, BCEK} có mất mát thông tin hay không? (nên làm tự luận, đây chỉ check đáp án)
A. Có
B. Không
ans: B [suy luận]

Câu 132: Xét quan hệ R(A, B, C) trong hệ quản trị CSDL quan hệ.
Giả sử:
A là khóa chính (PRIMARY KEY)
Có một clustered index trên A
Có một non-clustered index trên B
Phát biểu nào sau đây là đúng?
A. Chỉ mục clustered xác định cách dữ liệu được lưu trữ vật lý trong bảng.
B. Dữ liệu vật lý của bảng được sắp xếp theo thứ tự của chỉ mục non-clustered.
C. Truy vấn trên A luôn nhanh hơn truy vấn trên B
D. Có thể tạo nhiều clustered index trên cùng một bảng.
ans: A [suy luận]

Câu 133: (TỰ LUẬN) Cho cơ sở dữ liệu gồm các quan hệ như ở bảng dưới đây, hãy viết câu lệnh SQL đưa ra tổng số phim có năm sản xuất là 2022.
KhánGiả (MãKG, HọTên, Tuổi, ĐịaChỉ);
Phim (MãPh, TênPhim, ThểLoại, NămSảnXuất);
XemPhim (MãXem, MãKG, MãPh, ĐiểmĐánhGiá);
ans: SELECT COUNT(*) FROM Phim WHERE NămSảnXuất = 2022; [suy luận]

Câu 134: Cho bảng: SP(sid, pid, qty)
Xét truy vấn SQL: SELECT sid FROM SP WHERE pid = 'P1' AND qty > 100;
Biểu thức đại số quan hệ nào dưới đây là tối ưu nhất?
A. π<sub>sid</sub>(σ<sub>pid='P1'</sub>(σ<sub>qty>100</sub>(SP)))
B. π<sub>sid</sub>(σ<sub>pid='P1'</sub>(SP) × σ<sub>qty>100</sub>(SP))
C. σ<sub>pid='P1' ∧ qty>100</sub>(π<sub>sid</sub>(SP))
D. π<sub>sid</sub>(σ<sub>pid='P1' ∧ qty>100</sub>(SP))
ans: D [suy luận]

Câu 135: Cho sơ đồ quan hệ R(ABCDE) với tập phụ thuộc hàm F = {AB->E; B->C; ABC->D; A->C}. Khi tách về dạng chuẩn 3 không làm mất mát thông tin và bảo toàn tập phụ thuộc hàm, ta được bao nhiêu sơ đồ con?
A. 2
B. 3
C. 4
D. 5
ans: B [suy luận]

Câu 136: Cho hai quan hệ R và S khả hợp, biểu thức nào dưới đây cho kết quả đúng bằng kết quả của phép toán: R ∩ S
A. R \ (S \ R)
B. R \ (R \ S)
C. (R ∪ S) \ (R \ S)
D. S \ (R \ S)
ans: B [suy luận]

Câu 137: Phát biểu nào dưới đây là chưa chính xác về khóa ngoài?
A. Mỗi khóa ngoài của bảng này sẽ chỉ tham chiếu đến khóa chính của duy nhất 1 bảng khác.
B. Một trường tham gia vào khóa ngoài thì không thể tham gia vào khóa chính của bảng.
C. Mỗi bảng có thể có nhiều khóa ngoài.
D. Một khóa ngoài có thể có nhiều thuộc tính.
ans: B [suy luận]

Câu 138: Cho bảng Student(Id, Name, Address) Sinh viên có id là '20155041' chuyển đến sống tại địa chỉ 'Hawai'. Chọn câu lệnh cập nhật dữ liệu thích hợp:
A. UPDATE * Set Address = 'Hawai' WHERE id = '20215041'
B. UPDATE Student Set Address = 'Hawai' WHERE id = '20215041'
C. UPDATE Student, * Set Address = 'Hawai' WHERE id = '20215041'
D. UPDATE Student, Address Set Address = 'Hawai' WHERE id = '20215041'
ans: B [suy luận]

Câu 139: Trong trigger của SQL Server, bảng nào chứa dữ liệu mới sau thao tác INSERT/UPDATE?
A. new
B. inserted
C. old
D. deleted
ans: B [suy luận]

Câu 140: Cho schema của một DB như sau:
SINHVIEN(MASV, TENSV, EMAIL, SDT, NGAYSINH)
HOCPHAN(MAHP, TENHP, LOAIHP, SOTINCHI)
LOPHOCPHAN(MALHP, MAHP, HOCKY, NAMHOC)
DANGKY(MASV, MALHP)

Cho câu lệnh sau:
```sql
SELECT SV.MASV
FROM SINHVIEN SV
LEFT JOIN DANGKY DK ON SV.MASV = DK.MASV
AND YEAR(NGAYSINH) = '2006';
```
Kết quả của câu lệnh trên là gì?
A. Tất cả sinh viên có năm sinh 2006
B. Sinh viên đã đăng ký ít nhất một lớp học phần có năm sinh 2006
C. Sinh viên chưa đăng ký học phần nào có năm sinh 2006
D. Lỗi cú pháp
ans: D [suy luận]
Câu 141: Phát biểu nào sau đây về FOREIGN KEY là đúng? (Chọn tất cả đáp án đúng)
A. FOREIGN KEY bắt buộc phải có cùng tên với PRIMARY KEY được tham chiếu.
B. FOREIGN KEY có thể tham chiếu chính nó (self-reference).
C. FOREIGN KEY không thể chứa giá trị NULL.
D. FOREIGN KEY có thể tham chiếu đến PRIMARY KEY hoặc UNIQUE KEY.
E. Một bảng chỉ có thể có một FOREIGN KEY.
ans: B,D [suy luận]
Câu 142: Cho sơ đồ quan hệ R gồm các thuộc tính: A, B, C, D, E, G, H.
Tập phụ thuộc hàm:
AB → H
BC → D
CD → H
AE → D
AB → E
BD → G
Hãy tính bao đóng của tập thuộc tính CD. (viết theo thứ tự từ điển, không dấu không cách)
ans: CDH [suy luận]
Câu 143: Cho sơ đồ S(U,F) với U = {A, B, C, D, E, F, G, H}, F = {A->BC, B->DE, DE->F, AD->G}. Hỏi sơ đồ trên có tất cả bao nhiêu khóa tối thiểu?
ans: 1 [suy luận]
Câu 144: Cho sơ đồ S(U,F), với U = {A, B, C, D, E, F, G, H}, F = {A->BC, B->DE, DE->F, AD->G}. Sau khi chuẩn hóa S về dạng chuẩn 3 bảo toàn thông tin và phụ thuộc hàm, gọi X là số sơ đồ con và gọi Y là số lần xuất hiện của A trong tất cả các sơ đồ con đó. Hỏi X + Y = ?
A. 6
B. 7
C. Đáp án khác
D. 9
E. 8
ans: A [suy luận]
Câu 145: Cho sơ đồ quan hệ s(U) với:
U = {A, B, C, D, E, F}
F = {A->B, C->D, CD->EF}
Phủ tối thiểu của F là:
A. FC = {A->B, C->D, CD->E, CD->F}
B. FC = {A->B, C->D, C->EF}
C. FC = {A->B, C->D, C->E, C->F}
D. FC = {A->B, C->E, C->F}
ans: C [suy luận]
Câu 146: Cho U = {A, B, C, D, E, G, H}, và tập phụ thuộc hàm F = {A->D, AB->DE, CE->G, E->H}
Hãy cho biết, phụ thuộc hàm nào không được dẫn xuất từ F?
A. AB->H
B. AB->D
C. AB->G
D. AB->E
ans: C [suy luận]
Câu 147: (TỰ LUẬN) Cho quan hệ R và quan hệ S khả hợp. Hãy viết một biểu thức không chứa phép kết nối, mà cho kết quả đúng bằng kết quả của phép toán: R ⋈F S
ans: σF(R × S) [suy luận]
Câu 148: SELECT * FROM fruit ?
A. Chọn tất cả dữ liệu hiện có trong bảng fruit
B. Chọn bảng * từ bảng fruit
C. Chọn bảng fruit từ bảng *
D. Chọn cột * từ bảng fruit
ans: A [suy luận]
Câu 149: Trường hợp nào không nên đánh chỉ mục cho bảng dữ liệu
A. Tất cả các phương án chọn khác của câu hỏi này
B. Các bảng được cập nhật và thêm dữ liệu thường xuyên
C. Các bảng có kích thước nhỏ
D. Các cột được cập nhật dữ liệu thường xuyên, các cột có kiểu giá trị là NULL
ans: A [suy luận]
Câu 150: Đảm bảo tính không thể chia cắt là tính chất nào của 1 giao dịch ?
A. Tính nguyên tố
B. Tính nhất quán
C. Tính bền vững
D. Tính cách ly
ans: A [suy luận]

Câu 151: Cho sơ đồ R(ABCDE), tập phụ thuộc của hàm F = {AB -> CD; A -> B; C -> E; E -> DC}. Phép tách R thành các sơ đồ con R1(ABC), R2(CE), R3(DE) sẽ:
A. Không bảo toàn thông tin, không bảo toàn tập phụ thuộc hàm
B. Bảo toàn thông tin, không bảo toàn tập phụ thuộc hàm
C. Không bảo toàn tập tin, bảo toàn tập phụ thuộc hàm
D. Bảo toàn thông tin, bảo toàn tập phụ thuộc hàm
ans: D [suy luận]

Câu 152: Cho SQL:
```sql
SELECT P.pname FROM P, SP WHERE P.pid = SP.pid AND SP.sid = 'S1'
```
Phương án nào tối ưu nhất ?
A. πpname( σsid='S1'( P ⋈pid SP ) )
B. πpname( σP.pid = SP.pid AND SP.sid='S1'( P × SP ) )
C. πpname( πpid, pname(P) ⋈pid πpid( σsid='S1'(SP) ) )
D. πpname( P ⋈pid SP )
ans: C [suy luận]
Câu 153: Cho sơ đồ quan hệ R(U) với U = {A, B, C, D, E, F} và 2 tập phụ thuộc hàm:
F = {AB -> CE; D -> EF; C -> D; E -> F}
G = {AB -> CD; D -> EF; C -> DF}
Phát biểu nào đúng ?
A. Bổ sung phụ thuộc hàm C -> F vào tập F thì F <=> G
B. Bổ sung phụ thuộc hàm E -> F vào tập G thì F <=> G
C. Bổ sung phụ thuộc hàm AB -> E vào tập G thì F <=> G
D. F <=> G
ans: B [suy luận]
Câu 154: Chỉ những dữ liệu hợp lệ được lưu trữ là tính chất nào của 1 giao dịch ?
A. Tính nhất quán
B. Tính nguyên tố
C. Tính bền vững
D. Tính cô lập
ans: A [suy luận]
Câu 155: Kiến trúc của 1 Hệ quản trị CSDL bao gồm:
A. Bộ xử lý câu hỏi, bộ quản trị giao dịch, bộ quản lý lưu trữ
B. Bộ xử lý câu hỏi, các truy vấn, bộ quản lý lưu trữ
C. Bộ xử lý câu hỏi, sơ đồ dữ liệu, bộ quản lý lưu trữ
D. Bộ xử lý câu hỏi, ngôn ngữ dữ liệu, bộ quản lý lưu trữ
ans: A [suy luận]
Câu 156: Cho các quan hệ R1(ABCD), R2(DCE), R3(BC), hãy cho biết trong các biểu thức dưới đây, biểu thức nào cho quan hệ kết quả khả hợp quan hệ S(ACDE) ?
A. ( R1 ÷ R3 ) * R2
B. ( R1 * R2 ) ÷ R3
C. πACDE( R1 * R2 ) * R3
D. R1 * πCDE( R2 * R3 )
ans: A [suy luận]
Câu 157: Cho cơ sở dữ liệu gồm các quan hệ như ở Câu 129. Hãy cho biết liên kết giữa thực thể GiảngDạy và thực thể GiảngViên là loại liên kết gì
A. N - N
B. Đệ quy
C. 1 - 1
D. 1 - N
ans: D [suy luận]
Câu 158: Trong mô hình thực thể liên kết, các thuộc tính có thể là:
A. thuộc tính tham chiếu ( đến thực thể khác )
B. thuộc tính phức
C. thuộc tính suy diễn ( tính toán được từ thuộc tính khác )
D. thuộc tính tổng hợp
ans: B,C [suy luận]
Câu 159: Cho cơ sở dữ liệu gồm các quan hệ như ở Câu 135, hãy cho biết liên kết giữa thực thể KhánGiả và thực thể XemPhim là loại liên kết gì
A. 1 - 1
B. N - N
C. 1 - N
D. Đệ quy
ans: C [suy luận]
Câu 160: Cho cơ sở dữ liệu gồm các quan hệ:
KhánGiả({pk}MãKG{/pk}, HọTên, Tuổi, ĐịaChỉ);
Phim({pk}MãPhim{/pk}, TênPhim, ThểLoại, NămSảnXuất);
XemPhim({pkfk}MãXem{/pkfk}, {fk}MãKG{/fk}, {fk}MãPh{/fk}, ĐiểmĐánhGiá),
Hãy viết câu lệnh SQL tính số lượng các bộ phim chưa có ai xem.
ans: SELECT COUNT(*) FROM Phim WHERE MãPhim NOT IN (SELECT DISTINCT MãPh trừ khi có quy định khác trong câu 135) [suy luận]