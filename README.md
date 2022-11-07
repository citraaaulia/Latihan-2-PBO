# Latihan-2-PBO
public class Elemen{
    public String nama;

    public Elemen(String nama){
        this.nama = nama;
    }    
}

public class Mahasiswa extends Elemen{
    //Mahasiswa merupakan kelas turunan dari class elemen
    private int sks;
    public int JamSibuk;
    
    public Mahasiswa(String nama, int sks){
        super(nama);
        JamSibuk = sks * 3;
    }

    public int getJamSibuk(){ //overridding
        return JamSibuk;
    }

    public void show(){
        System.out.println(nama + " adalah seorang mahasiswa dengan jam sibuk " + JamSibuk);
    }
}
class Asdos extends Mahasiswa{
    //class asdos merupakan kelas turunan dari kelas mahasiswa
    private int jamNgasdos;

    public Asdos(String nama, int sks, int jamNgasdos){
        super(nama, sks);
        // this.JamNgasdos = JamNgasdos;
        JamSibuk = JamSibuk + jamNgasdos;

    }
    
    public void show(){
        System.out.println(nama + " adalah seorang asdos dengan jam sibuk " + JamSibuk);
    }
    public int getJamSibuk(){ //overridding (menggunakan method yang ada pada class parentnya, class mahasiswa)
        return JamSibuk;
    }
}

class Dosen extends Elemen{
    private int JumlahHariKerja;
    public int JamSibuk;
    
    public Dosen(String nama,int JumlahHariKerja){
        super(nama);
        JamSibuk = JumlahHariKerja*8;
    }

    public int getJamSibuk(){
        return JamSibuk;
    }

    public void show(){
        System.out.println(nama + "adalah seorang dosen dengan jam sibuk "+ JamSibuk);
    }
}
public class Driver {
    public static void main(String[] args) {
        Asdos asdos1 = new Asdos("Fairuzikun",24,1);//polymorphism
        Asdos asdos2 = new Asdos("Angel-chan", 19, 7);//polymorphism
        Dosen dosen1 = new Dosen("Raja OP Damanik",5);//polymorphism
        Dosen dosen2 = new Dosen("Nivotko", 3);//polymorphism
        Mahasiswa mahasiswa1 = new Mahasiswa("Firman", 20);//polymorphism
        Mahasiswa mahasiswa2 = new Mahasiswa("Nid to pass this sem", 23);//polymorphism

        asdos1.show();
        dosen1.show();
        asdos2.show();
        mahasiswa1.show();
        mahasiswa2.show();
        dosen2.show();

        int total = asdos1.getJamSibuk() + dosen1.getJamSibuk() +
         asdos2.getJamSibuk() + mahasiswa1.getJamSibuk() + mahasiswa2.getJamSibuk() + dosen2.getJamSibuk();

        System.out.println("Total : "+ total);

    }
}
    
