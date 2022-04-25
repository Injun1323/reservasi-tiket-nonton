import java.util.LinkedList;
import java.util.Scanner;
import java.util.InputMismatchException;


public class javaLinkedList {
    
	
	private static LinkedList<String> dataStorage = new LinkedList<String>();
	private static Scanner extracted() {
		return new Scanner(System.in);
	}
	
	private static void displayData(){
				
		System.out.println("\nJumlah Customer :" + dataStorage);
		System.out.println("\nJumlah Kursi yang Terisi     : " + dataStorage.size());
	}
	
	private static void addData() {
		System.out.println("\n 1.Studio Original "
		                 + "\n 2.Studio Primer "
					     + "\n 3.Studio VIP ");
		System.out.print("jumlah Tiket yang dibeli : ");
		String tempData = extracted().nextLine();
		dataStorage.add(tempData);
		displayData();
		System.out.print("Pilih Studio : ");
		int indexMenu1 = extracted().nextInt();
		switch(indexMenu1){
			case 1:
			System.out.println(" " );
			System.out.println(" \nSTUDIO REGULER "
				             + " \nJudul : Dilan 1990 "
			                 + " \nJam Tayang : Jum'at, 15.30 WITA "
							 + " \nHarga Tiket : Rp45.000 ");
			System.out.println(" \n1.Ya"
			                 + " \n2.Tidak");
			System.out.print(" Pilih : ");
			int Pilih = extracted().nextInt();
			while(Pilih != 1){
				System.out.println(" RESERVASI TIKET DIBATALKAN..!!!");
				programMenu();
			}	
			System.out.print(" Masukkan Nama : ");
			String nama = extracted().next();
			dataStorage.add(nama);
			System.out.print(" Masukkan Jenis Kelamin : ");
			String gender = extracted().next();
			dataStorage.add(gender);
			System.out.print(" No Kursi : ");
			String kur = extracted().next();
			dataStorage.add(kur);
			System.out.println(" RESERVASI TIKET BERHASIL");
			break;
			case 2:
			System.out.println(" \nSTUDIO PREMIERE "
				             + " \nJudul : BOBOIBOY MOVIE 3 "
			                 + " \nJam Tayang : Sabtu, 14.30 WITA "
							 + " \nHarga Tiket : Rp45.000 ");
			System.out.println(" \n1.Ya"
			                 + " \n2.Tidak");
			System.out.print(" Pilih : ");
			Pilih = extracted().nextInt();
			while(Pilih != 1){
				System.out.println(" RESERVASI TIKET DIBATALKAN..!!!");
				programMenu();
			}
			System.out.print(" Masukkan Nama : ");
            nama = extracted().next();
            dataStorage.add(nama);
            System.out.print(" Masukkan Jenis Kelamin : ");
            gender = extracted().next();
            dataStorage.add(gender);
            System.out.print(" No Kursi : ");
            kur = extracted().next();
            dataStorage.add(kur);
            System.out.println(" RESERVASI TIKET BERHASIL");
			break;
			case 3:
			System.out.println(" \nSTUDIO IMAX "
				             + " \nJudul : AVANNGERS END GAME "
			                 + " \nJam Tayang : Minggu, 18.30 WITA "
							 + " \nHarga Tiket : Rp50.000 ");
			System.out.println(" \n1.Ya"
			                 + " \n2.Tidak");
			System.out.print(" Pilih : ");
			Pilih = extracted().nextInt();
			while(Pilih != 1){
				System.out.println(" RESERVASI TIKET DIBATALKAN..!!!");
				programMenu();
			}
			System.out.print(" Masukkan Nama : ");
            nama = extracted().next();
            dataStorage.add(nama);
            System.out.print(" Masukkan Jenis Kelamin : ");
            gender = extracted().next();
            dataStorage.add(gender);
            System.out.print(" No Kursi : ");
            kur = extracted().next();
            dataStorage.add(kur);
            System.out.println(" RESERVASI TIKET BERHASIL");
			break;
		}
	}
	
	private static void removeData() {
		boolean status = true;
		int indexData = 0;
		displayData();
		while(status) {
			System.out.print("Pilih Index Data yang ingin dihapus: [0-" + (dataStorage.size() - 1) + "]: ");
			try {
				status = false;
				indexData = extracted().nextInt();
			}
			catch(InputMismatchException e) {
				System.out.println("Data harus berupa Angka!");
				status = true;
			}
		}
		dataStorage.remove(indexData);
		displayData();
	}
	
	private static void programExit() {
		System.exit(0);
	}
	
	private static void programTitle() {
		System.out.println(" ..:: BIOSKOP SISTEM INFORMASI ::..");
	}
	
	private static void programSwitcher() {
		boolean status = true;
		int indexMenu = 0;
		while(status) {
			try {
				status = false;
				System.out.print("Pilih Menu [1~4]: ");
				indexMenu = extracted().nextInt();
			}
			catch(InputMismatchException e) {
				System.out.println("Masukan harus berupa Angka!");
				status = true;
			}
		}
		
		switch(indexMenu) {
			case 1: addData();break;
			case 2: removeData();break; 
			case 3: displayData();break;
			case 4: programExit(); break;
			case 5: programTitle(); break;
		}
		programMenu();
	}
	
	private static void programMenu() {
		System.out.println("\n MENU RESERVASI TIKET:"
				         + "\n 1. Studio"
				         + "\n 2. Hapus Daftar Pembeli"
				         + "\n 3. Daftar Pembeli"
				         + "\n 4. Exit");
		programSwitcher();
	}
	
	public static void main(String[] args) {
		programTitle();
		programMenu();
	}
}
