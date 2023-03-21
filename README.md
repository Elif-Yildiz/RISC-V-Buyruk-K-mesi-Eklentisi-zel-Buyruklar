# RISC-V-Buyruk-Kumesi-Eklentisi-Ozel-Buyruklar

Farklı değerler denemek için  tb_yildiz dosyasını güncelleyin.

Buyruk Buyruğun İşlevi ve Formatı
KAREAL.TOPLA rs1 ve rs2 yazmaçlarındaki değerlerin karelerinin toplamını rd yazmacına yazar.
Assembly formatı: kareal.topla rd, rs1, rs2
CARP.CIKAR rs1 ve rs2 yazmaçlarındaki değerleri çarpar, çıkan sonuçtan rs1 yazmacındaki değeri çıkarıp
rd yazmacına yazar.
Assembly formatı: carp.cikar rd, rs1, rs2
SIFRELE rs1 yazmacındaki değer ile işaretle genişletilmiş anlık değeri "xor"layıp rd yazmacına yazar.
Assembly formatı: sifrele rd, rs1, imm
TASI Sıfırla genişletilmiş anlık değeri, rs1 yazmaç değeriyle toplar ve rd yazmacına yazar.
(rs1 RISC-V’de her zaman 0 olması gereken x0 yazmacıdır.)
Assembly formatı: tasi rd, rs1, imm
IKIKAT.ATLA İşaretle genişletilmiş anlık değerin 2 katına atlar (program sayacını günceller) ve program sayacının
bir sonraki buyruk için olan değerini (ps + 4) rd yazmacına kaydeder. (ayrıca imm[0] = 0 )
Assembly formatı: ikikat.atla rd, imm
BITSAY s1 (1 bitlik seçim) bitine bakarak rs1 yazmacındaki değerde bulunan "0" ya da "1" sayısını sayıp
rd yazmacına yazar. Seçim biti "1" ise "1", "0" ise "0" sayısını sayar.
Assembly formatı: bitsay rd, rs1, s1
SEC.DALLAN s2 (2 bitlik seçim) bitine bakarak rs1 ve rs2 yazmaç değerlerini işaretli olarak karşılaştırıp ilgili koşulu
sağlıyorsa, işaretle genişletilmiş anlık değerle dallanır. (program sayacını günceller) (ayrıca imm[0] = 0 )
Seçim bitlerine göre denk gelen buyruklar ve yapılması gereken karşılaştırmalar aşağıdaki şekildedir:
s2 = 00 ise nop buyruğu gibi davranacak, yani karşılaştırma ve dallanma işlemi yapılmayacak,
sadece, program sayacı bir sonraki buyruk için güncellenecek. (ps + 4)
s2 = 01 ise beq buyruğu gibi davranacak, yani rs1_deger == rs2_deger koşulu doğruysa dallanacak.
s2 = 10 ise blt buyruğu gibi davranacak, yani rs1_deger <rs2_deger koşulu doğruysa dallanacak.
s2 = 11 ise bge buyruğu gibi davranacak, yani rs1_d
