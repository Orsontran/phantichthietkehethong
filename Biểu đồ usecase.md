# Sơ đồ Use Case - Hệ thống quản lý nhân viên

```mermaid
flowchart LR
    %% Định nghĩa các Actor
    NhanVien["👤 Nhân viên"]
    QuanLy["👤 Quản lý chi nhánh"]

    %% Quan hệ Kế thừa (Generalization) giữa các Actor
    QuanLy -- Generalization --> NhanVien

    %% Khung hệ thống (System Boundary)
    subgraph System ["Hệ thống quản lý nhân viên"]
        UC_XemHoSo(["Xem hồ sơ"])
        UC_BoSungNgoaiNgu(["Bổ sung ngoại ngữ..."])
        UC_CapNhatSĐT(["Cập nhật điện thoại..."])
        UC_KiemTraSĐT(["Kiểm tra trùng sđt"])
        
        UC_TraCuu(["Tra cứu nhân viên"])
        UC_TraCuuNangCao(["Tra cứu nhân viên nâng cao"])
        UC_ChuyenDonVi(["Chuyển đơn vị"])
        UC_LapBaoCao(["Lập báo cáo"])

        %% Quan hệ Include và Extend
        UC_CapNhatSĐT -. "<<include>>" .-> UC_KiemTraSĐT
        UC_TraCuuNangCao -. "<<extend>>" .-> UC_TraCuu
    end

    %% Liên kết giữa Actor và Use Case (Association)
    NhanVien --- UC_XemHoSo
    NhanVien --- UC_BoSungNgoaiNgu
    NhanVien --- UC_CapNhatSĐT

    QuanLy --- UC_TraCuu
    QuanLy --- UC_ChuyenDonVi
    QuanLy --- UC_LapBaoCaoExtension