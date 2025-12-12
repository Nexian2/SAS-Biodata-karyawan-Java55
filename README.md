import java.util.ArrayList;
import java.util.Scanner;

public class Main {
    public static void openingAnimation() throws InterruptedException {
        String title = "██╗      ██████╗  █████╗ ██████╗ ██╗███╗   ██╗ ██████╗     ███████╗████████╗ █████╗ ██████╗ ████████╗███████╗██████╗ \r\n" + //
                        "██║     ██╔═══██╗██╔══██╗██╔══██╗██║████╗  ██║██╔════╝     ██╔════╝╚══██╔══╝██╔══██╗██╔══██╗╚══██╔══╝██╔════╝██╔══██╗\r\n" + //
                        "██║     ██║   ██║███████║██║  ██║██║██╔██╗ ██║██║  ███╗    ███████╗   ██║   ███████║██████╔╝   ██║   █████╗  ██║  ██║\r\n" + //
                        "██║     ██║   ██║██╔══██║██║  ██║██║██║╚██╗██║██║   ██║    ╚════██║   ██║   ██╔══██║██╔══██╗   ██║   ██╔══╝  ██║  ██║\r\n" + //
                        "███████╗╚██████╔╝██║  ██║██████╔╝██║██║ ╚████║╚██████╔╝    ███████║   ██║   ██║  ██║██║  ██║   ██║   ███████╗██████╔╝\r\n" + //
                        "╚══════╝ ╚═════╝ ╚═╝  ╚═╝╚═════╝ ╚═╝╚═╝  ╚═══╝ ╚═════╝     ╚══════╝   ╚═╝   ╚═╝  ╚═╝╚═╝  ╚═╝   ╚═╝   ╚══════╝╚═════╝ \r\n" + //
                        "                                                                                                                     \r\n" + //
                        "";

        for (char c : title.toCharArray()) {
            System.out.print(c);
            Thread.sleep(25);
        }
        System.out.println("\n");
        String bar = "";
        for (int i = 0; i <= 20; i++) {
            bar += "█";
            System.out.print("\rLoading: " + bar);
            Thread.sleep(80);
        }
        System.out.println("\nSistem siap digunakan!\n");
        Thread.sleep(500);
    }

    interface Kinerja {
        void deskripsiKerja();
    }

    static class Pegawai {
        private static int counter = 1000;
        private int id;
        private String nama;
        private int usia;
        private String jabatan;
        private int kontrak;

        public Pegawai(String nama, int usia, String jabatan,int kontrak ) {
            this.id = counter++;
            this.nama = nama;
            this.usia = usia;
            this.jabatan = jabatan;
            this.kontrak = kontrak;
        }

        public int getId() { return id; }
        public String getNama() { return nama; }
        public int getUsia() { return usia; }
        public String getJabatan() { return jabatan; }
        public int getKontrak() { return kontrak; }

        public void tampilkanData() {
            System.out.println("ID Pegawai : " + id);
            System.out.println("Nama       : " + nama);
            System.out.println("Usia       : " + usia); 
            System.out.println("Jabatan    : " + jabatan);
            System.out.println("Masa Kontrak :" + kontrak);
        }
    }

    static class PegawaiTetap extends Pegawai implements Kinerja {
        public PegawaiTetap(String nama, int usia, String jabatan, int Kontrak) {
            super(nama, usia, jabatan, Kontrak);
        }

        @Override
        public void deskripsiKerja() {
            System.out.println("Pegawai tetap bekerja full-time dan memiliki tunjangan");
        }
    }
    
    static class PegawaiKontrak extends Pegawai implements Kinerja {
        public PegawaiKontrak(String nama, int usia, String jabatan, int Kontrak) {
            super(nama, usia, jabatan, Kontrak);
        }

        @Override
        public void deskripsiKerja() {
            System.out.println("Pegawai kontrak bekerja sesuai durasi perjanjian");
        }
    }


    public static void main(String[] args) {
        try {
            openingAnimation(); 
        } catch (Exception e) {}

        Scanner input = new Scanner(System.in);
        ArrayList<Pegawai> daftarPegawai = new ArrayList<>();

        System.out.println("██████╗  █████╗ ████████╗ █████╗     ██████╗ ███████╗ ██████╗  █████╗ ██╗    ██╗ █████╗ ██╗\r\n" + //
                        "██╔══██╗██╔══██╗╚══██╔══╝██╔══██╗    ██╔══██╗██╔════╝██╔════╝ ██╔══██╗██║    ██║██╔══██╗██║\r\n" + //
                        "██║  ██║███████║   ██║   ███████║    ██████╔╝█████╗  ██║  ███╗███████║██║ █╗ ██║███████║██║\r\n" + //
                        "██║  ██║██╔══██║   ██║   ██╔══██║    ██╔═══╝ ██╔══╝  ██║   ██║██╔══██║██║███╗██║██╔══██║██║\r\n" + //
                        "██████╔╝██║  ██║   ██║   ██║  ██║    ██║     ███████╗╚██████╔╝██║  ██║╚███╔███╔╝██║  ██║██║\r\n" + //
                        "╚═════╝ ╚═╝  ╚═╝   ╚═╝   ╚═╝  ╚═╝    ╚═╝     ╚══════╝ ╚═════╝ ╚═╝  ╚═╝ ╚══╝╚══╝ ╚═╝  ╚═╝╚═╝\r\n" + //
                        "                               Created By Tsar Luthfi                                                                                     \r\n" + //
                        "");

        while (true) {
            System.out.println("\n=== MENU APLIKASI PEGAWAI PT MAJU BERSAMA ===");
            System.out.println("1. Tambah Pegawai Tetap Pada Database");
            System.out.println("2. Tambah Pegawai Kontrak Pada Database");
            System.out.println("3. Lihat Semua Pegawai Yang Terdaftar");
            System.out.println("4. Keluar Dari Aplikasi");
            System.out.print("Pilih menu : ");
            int pilih = input.nextInt();
            input.nextLine();

            switch (pilih) {
                case 1:
                    System.out.println("\n--- Input Pegawai Tetap ---");
                    System.out.print("Masukkan Nama Pegawai     : ");
                    String nama1 = input.nextLine();
                    System.out.print("Masukkan Usia Pegawai    : ");
                    int usia1 = input.nextInt();
                    input.nextLine();
                    System.out.print("Masukkan Jabatan Pegawai : ");
                    String jabatan1 = input.nextLine();
                    System.out.print("Masukkan Kontrak Pegawai : ");
                    int Kontrak1 = input.nextInt();
                    input.nextLine();

                    PegawaiTetap pt = new PegawaiTetap(nama1, usia1, jabatan1, Kontrak1);
                    daftarPegawai.add(pt);
                    System.out.println("Pegawai tetap berhasil ditambahkan dengan ID: " + pt.getId());
                    break;

                case 2:
                    System.out.println("\n--- Input Pegawai Kontrak ---");
                    System.out.print("Masukkan Nama Pegawai  : ");
                    String nama2 = input.nextLine();
                    System.out.print("Masukkan Usia Pegawai   : ");
                    int usia2 = input.nextInt();
                    input.nextLine();
                    System.out.print("Masukkan Jabatan Pegawai : ");
                    String jabatan2 = input.nextLine();
                    System.out.print("Masukkan Kontrak Pegawai : ");
                    int kontrak2 = input.nextInt();
                    input.nextLine();

                    PegawaiKontrak pk = new PegawaiKontrak(nama2, usia2, jabatan2, kontrak2);
                    daftarPegawai.add(pk);
                    System.out.println("Pegawai kontrak berhasil ditambahkan dengan ID: " + pk.getId());
                    break;

                case 3:
                    System.out.println("\n==== DATA SEMUA PEGAWAI ===");
                    if (daftarPegawai.isEmpty()) {
                        System.out.println("Belum ada data pegawai");
                    } else {
                        for (Pegawai p : daftarPegawai) {
                            p.tampilkanData();
                            if (p instanceof Kinerja) {
                                ((Kinerja) p).deskripsiKerja();
                            }
                            System.out.println("-----------------------------");
                        }
                    }
                    break; 

                case 4:
                    System.out.println("Program selesai");
                    return;

                default:
                    System.out.println("Menu Pendaftaran tidak tersedia");
            }
        }
    }
}
