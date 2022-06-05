# Ödevin Konusu

Labview projem için ortamdaki ışığın şiddetini algılayan ve bu şiddete göre ortamın aydınlık derecesini 4 kademeli bir şekilde gösteren bir sensör yapmayı tercih ettim.

## Kullanılan malzemeler

-   Arduino UNO
-   LDR
-   POT
-   LED

## Uygulamanın İşleyişi

Devre basit bir gerilim bölücü devresi. POT ile ledin ışık şiddetini ayarlayabiliyorum.
![](/devre.jpg)
***
Odamdaki lamba açıkken ve LDR'ye düşen ışığı herhangi bir şekilde engellemezken bilgisayarda seri port üzerinden print ettiğimde böyle bir çıkış alıyorum
![](/cikis.jpg)
***
Lambayı kapattığımda ise çıkışta aldığım değerler *300 - 400* aralığından *900 - 1000* aralığına artıyor
![](/cikis2.jpg)
***
Bu değerleri labviewdeki VISA seri port giriş elemanı ile direk okuyarak labview üzerinde yaptığım diyagram ile odanın aydınlık düzeyini gösterebiliyorum.

Odanın lambası açıkken
![](/labview_1.jpg)
***
LDR'nin önüne koyduğum LED açıkken
![](/labview_2.jpg)
***
Lamba kapalıyken
![](/labview_3.jpg)
##Labview Blok Diyagramı
-   COM4 yazan string arduinonun bağlandığı seri portun ismi olmalıdır
![](/labview_blok_diyagram.png)
##Arduino Programın Kodu
```{r}
int analogPin = A1;
int val = 0;
void setup() {
  Serial.begin(9600);
}

void loop() {
  val = analogRead(analogPin);
  Serial.println(val);
  delay(1000);
}
```
##Ad - Soyad - Numara
Şafak Harun AKKAYA
170519011
