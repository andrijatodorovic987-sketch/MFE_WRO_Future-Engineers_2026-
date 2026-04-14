# MFE_WRO_Future-Engineers_2026-
Dokumentacija 
MFE – WRO Future Engineers 2026
Zvanična GitHub dokumetacija za WRO Future Engineers tim MFE 2026. Sav kod, dokumentacija i fajlovi nalaze se ovdje.

•	Hardverski dizajn

•	Fotografije

•	Detaljna dokumentacija algoritma

•	Uputstvo za sklapanje i podešavanje

•	Lista djelova


•	Podešavanje Raspberry PI uređaja

•	Pokretanje programa

•	Demonstracioni video snimci


•	Naučene lekcije

•	Bezbjednost LI-PO baterije

Hardverski dizajn
MFE koristi šasiju od LEGO kockica sa dodatnim štampanim dijelovima sa 3D štampačai osnovnim komponentama poput motora, kamera i kontrolnih ploča.

Šasija se sastoji od:

•	donje baze 

•	zadnje osovine

•	gornje platforme za elektroniku

•	prednji branik sa senzorima


Karakteristike:

•	prostor za bateriju i ESC ispod

•	prednji dio za upravljanje

•	laka dostupnost komponenti


Napajanje i kontrola
Napajanje:
•	3S LiPo baterija (~11.1V)

Distribucija:

•	ESC (direktno 12V) 

•	5V regulator (Raspberry PI) 

•	7.0V regulator (servo) 

•	Kontrola:

•	Raspberry PI + PWM kontroler 

•	komunikacija preko I2C



Motori

•	Pogon: zadnji (RWD) 

•	Brushless motor sa senzorom 

•	ESC kontrola

Servo:

•	model: MG995

Senzori

•	FaceCam 1000X

•	HC-SR04 ultra sonični senzori x2 : postavljene pod 30°

•	Mi koristimo inegrisani žiroskop na ARDUINO NANO BLE 33

SLIKE ROBOTA


<img width="322" height="429" alt="image" src="https://github.com/user-attachments/assets/e6c334da-9d9c-40e5-9158-36c56c97dbe3" />
<img width="322" height="429" alt="image" src="https://github.com/user-attachments/assets/488a0a22-6619-4ac1-8a3b-f37ac66a80a6" />
<img width="322" height="429" alt="image" src="https://github.com/user-attachments/assets/b735fb5c-6b0e-45d5-bc84-21443998390e" />
<img width="322" height="429" alt="image" src="https://github.com/user-attachments/assets/5d25f5ee-cc4e-497f-9857-bf9ad2ee3c64" />
<img width="322" height="429" alt="image" src="https://github.com/user-attachments/assets/b50cc8a0-67ad-4930-80c4-17db11757e66" />
<img width="322" height="429" alt="image" src="https://github.com/user-attachments/assets/8d492adc-0e01-4207-b2bb-bf2cc6c898d3" />

               
                                              

Build & Setup

 Potrebni alati

•	3D štampač 

•	Imbus ključevi 

•	Lemilica 

•	LEGO set


Dijelovi (skraćeno)

•	Raspberry PI

•	2x HC-SR04 senzora

•	PWM driver 

•	ESC + motor 

•	Servo 

•	LiPo baterija

•	LEGO set

Podešavanje Raspberry Pi uređaja
Raspberry Pi predstavlja centralnu računarsku jedinicu sistema i zadužen je za obradu podataka sa senzora, izvršavanje algoritama autonomne vožnje i upravljanje motorima.
Na uređaj je instaliran Raspberry Pi OS, nakon čega je izvršena osnovna konfiguracija sistema (mreža, SSH pristup i lokalizacija). Sistem je optimizovan radom bez grafičkog interfejsa kako bi se smanjilo opterećenje i povećale performanse.
Omogućeni su ključni hardverski interfejsi:
•	I2C za komunikaciju sa senzorima 
•	GPIO i PWM za upravljanje aktuatorima 
•	kamera interfejs za obradu slike 
Instalirane su potrebne biblioteke, uključujući OpenCV i NumPy, koje se koriste za obradu slike i numeričke operacije.
Raspberry Pi je povezan sa kamerom, senzorima i motor kontrolerima, uz stabilno napajanje kako bi se obezbijedio pouzdan rad sistema.
Nakon podešavanja izvršeno je testiranje svih komponenti (kamera, senzori, motori) kako bi se osigurala ispravna funkcionalnost u realnim uslovima.

Pokretanje programa
Pokretanje programa podrazumijeva inicijalizaciju kompletnog softverskog sistema robota i njegovo izvođenje u realnom vremenu, uključujući obradu podataka sa senzora i upravljanje aktuatorima.
Program se pokreće putem komandne linije na uređaju korišćenjem Python interpreter-a. Postoje dva osnovna režima rada:
•	manuelni režim – koristi se za testiranje i upravljanje robotom od strane korisnika 
•	autonomni režim – robot samostalno izvršava algoritam vožnje 
Primer pokretanja programa:
  -python3 manualdrive.py
  -python3 autodrive.py
Za potrebe takmičenja koristi se autonomni režim bez dodatnih interfejsa:
  -python3 autodrive.py no_server
Tokom pokretanja programa vrši se:
•	inicijalizacija kamera i senzora 
•	učitavanje konfiguracionih parametara 
•	pokretanje glavne petlje algoritma 
Program zatim kontinuirano obrađuje ulazne podatke i generiše komande za upravljanje vozilom.

Demonstracioni video snimci

https://www.youtube.com/shorts/UcaWskHsVGI






Kalibracija

Kalibracija je neophodna za pravilno funkcionisanje sistema za obradu slike na Raspberry Pi uređaju, posebno za korekciju distorzije i precizno prepoznavanje okruženja.
Kalibracija kamera se vrši snimanjem više slika šahovske table, nakon čega se pokreće program (calibrate.py) koji generiše parametre kamere (matrice K i D). Dobijene vrijednosti se ubacuju u glavni program (converter.py). Ispravnost kalibracije se provjerava tako što linije na slici postaju prave nakon korekcije.
Pored kamera, vrši se i kalibracija visine zidova. Sistem se pokreće u manuelnom režimu, snima se slika i podešavaju parametri tako da detekcija odgovara realnim pozicijama zidova. Ove vrijednosti se takođe unose u konfiguracioni fajl.
Pravilna kalibracija omogućava pouzdanu obradu slike i značajno poboljšava tačnost autonomne vožnje.

Dijagram ožičenja
<img width="975" height="475" alt="image" src="https://github.com/user-attachments/assets/453a5568-9986-4ddb-ad67-2c90dee8133d" />

Slike tima

<img width="1600" height="900" alt="image" src="https://github.com/user-attachments/assets/956b38d4-bf0a-4b35-bc41-9e4004886ca0" />
<img width="1600" height="900" alt="image" src="https://github.com/user-attachments/assets/ac36ed18-0dba-4c55-a4f3-533aacb8ae54" />


 


