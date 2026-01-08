```mermaid
erDiagram
    PELANGGAN {
        int id_pelanggan PK
        string nama_pelanggan
        string alamat_pelanggan
        string email_pelanggan
    }

    KASIR {
        int id_kasir PK
        string nama_kasir
        string shift
    }

    MENU {
        string kode_menu PK
        string nama_menu
        string kategori
        int harga
    }

    TRANSAKSI {
        int id_transaksi PK
        date tanggal_transaksi
        int total_harga
        int id_pelanggan FK
        int id_kasir FK
    }

    DETAIL_TRANSAKSI {
        int id_detail PK
        int id_transaksi FK
        string kode_menu FK
        int jumlah
        int subtotal
    }

    PELANGGAN ||--o{ TRANSAKSI : melakukan
    KASIR ||--o{ TRANSAKSI : menangani
    TRANSAKSI ||--o{ DETAIL_TRANSAKSI : terdiri_dari
    MENU ||--o{ DETAIL_TRANSAKSI : terdapat_dalam
