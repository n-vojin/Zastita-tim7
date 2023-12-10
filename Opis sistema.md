## **Glavne stavke sistema**

- **Wifi ruter**
- **Uredjaji povezani putem WiFi tehnologije**
    - Smart telefon
    - Televizor
    - Štampač
- **Uređajiv povezani putem Ethernet kabla**
    - Desktop računar
    - Switch

&nbsp;

### Wifi ruter

WiFi ruter je mrežni uređaj koji obavlja funkcije rutera i uključuje i funkcionalnost bežične tačke pristupa. Njegova osnovna uloga je povezivanje više uređaja unutar lokalne mreže (LAN) i usmeravanje podataka između njih.Postoje različite vrste routera u zavisnosti od proizvođača ili tehnologije i protokola koje koriste za pristup internetu.

**Neke od ključnih komponenata i funkcija WiFi rutera:**

1.  **Usmeravanje:** Funkcija rutera uključuje usmeravanje saobraćaja podataka između uređaja unutar lokalne mreže i između lokalne mreže i šireg interneta. Ruteri koriste protokole poput TCP/IP za upravljanje tokom podataka.
    
2.  **Bežična tačka pristupa (WAP):** Funkcija bežične tačke pristupa omogućava uređajima poput pametnih telefona, laptopova i tableta da se bežično povežu sa lokalnom mrežom putem WiFi standarda (kao što su 802.11ac ili 802.11n).
    
3.  **Ethernet portovi:** Većina WiFi rutera ima ugrađene Ethernet portove koji omogućavaju žičane veze za uređaje poput računara, externih switcheva, IP kamera...
    
4.  **Mrežni prekidač (Switch):** Ruteri često imaju ugrađeni mrežni prekidač koji omogućava višestruke žičane veze uređaja putem Ethernet kablova.
    
5.  **Router Firewall:** Ruteri obično uključuju osnovni firewall koji pomaže u zaštiti lokalne mreže od neovlašćenog pristupa sa interneta.
    
6.  **DHCP server:** Funkcija DHCP servera automatski dodeljuje IP adrese uređajima unutar lokalne mreže, pojednostavljujući proces postavljanja novih uređaja na mreži.
    
7.  **NAT (Network Address Translation):** NAT omogućava više uređaja unutar lokalne mreže da dele jednu javnu IP adresu, što je ključno za štednju IPv4 adresa i omogućavanje komunikacije sa internetom.
    
8.  **Firmware i konfiguracioni interfejs:** Ruteri imaju firmware, što je u osnovi njihov operativni sistem. Korisnici mogu konfigurisati postavke rutera putem veb interfejsa, omogućavajući podešavanje sigurnosnih mera, prilagođavanje mrežnih postavki, postavlanje i menjanje lozinki i još mnogo toga.
    

&nbsp;

### Uredjaji povezani putem WiFi tehnologije

Uređaji povezani putem WiFi tehnologije razmenjuju podatke putem bežičnih signala koristeći određene WiFi protokole. Jedan od osnovnih WiFi protokola je **IEEE 802.11.**

*Najčešći bežični standardi s kojima ćete se susresti su IEEE 802.11 bežična lokalna mreža (Wireless LAN - WLAN) i Mesh. IEEE ažurira 802.11 Wi-Fi standard svakih nekoliko godina. U trenutku pisanja, najčešće korišćeni Wi-Fi standard je 802.11ac, dok je sledeći generacijski Wi-Fi standard 802.11ax (poznat i kao Wi-Fi 6 i Wi-Fi 6E) \[1\]*.

Iako je najnoviji standard 802.11ax ili WiFi6, opšte je poznato da je kod nas i dalje najviše zastupljen WiFi 4 sa 802.11n standardom.

&nbsp;

### Uredjaji povezani putem Ethernet kabla

IEEE Standard 802.3 za Ethernet prvi put je objavljen 1985. godine. Specifikovao je polu-dupleksni protokol za kontrolu pristupa sa otkrivanjem sudara (CSMA/CD), koji radi brzinom od 10 Mb/s, i kontrolu pristupa za srednji nivo (Medium Access Control - **MAC**). Takođe je uključivao jedinicu za priključivanje sredstva (Medium Attachment Unit - MAU) za rad na koaksijalnom kablarnom medijumu, podržavajući topologiju autobusa između povezanih krajnjih stanica \[2\].

&nbsp;

## Termini

**MAC -** Media Access Control (MAC) adresa je 48-bitna adresa koja je trajno dodeljena mrežnom interfejsu (NIC) ili bežičnoj kartici. Ova adresa se dodeljuje od strane proizvođača. Svaki uređaj na mreži ima MAC adresu koja pomaže tim uređajima da komuniciraju sa drugim uređajima na sloju 2 (Datalink Layer) **OSI** modela. S druge strane, IP adresa je mrežna adresa koja omogućava uređaju da komunicira s drugima na sloju 3 (Network Layer) OSI modela u mreži. MAC adresa se takođe naziva fizičkom adresom interfejsa. "Mac Address Spoofing" je aktivnost koja se izvodi kako bi se promenila MAC adresa uređaja. To može raditi ovlašćeno ili neovlašćeno lice kako bi pristupilo mreži ili resursima. Ove vrste aktivnosti izvode i hakeri koji menjaju MAC adresu svog računara/laptopa kako bi njihov uređaj bio prepoznat kao ovlašćen u toj mreži \[3\].

**OSI Model -** Koji se često pominje u radu : Otvoreni sistem interkonekcije (OSI) model opisuje sedam slojeva koje računarski sistemi koriste za komunikaciju putem mreže. To je bio prvi standardni model za mrežne komunikacije, usvojen od svih glavnih računarskih i telekomunikacionih kompanija početkom 1980-ih. Moderni internet nije zasnovan na OSI, već na jednostavnijem TCP/IP modelu. Međutim, OSI 7-slojni model se i dalje široko koristi jer pomaže vizualizaciji i komunikaciji o tome kako mreže funkcionišu, kao i pomaže u izolaciji i rešavanju problema u mrežama \[4\].

 <img src="../_resources/Screenshot_1-2.png" alt="Screenshot_1.png" width="540" height="393"> *Slika 1. OSI vs TCP/IP Model \[4\].*

**TCP -** Transmisioni kontrolni protokol (TCP) je internet standard koji osigurava uspešnu razmenu podataka između uređaja putem mreže. TCP je osnovni protokol za komunikaciju za različite aplikacije, uključujući veb servere i sajtove, aplikacije za e-poštu, FTP i peer-to-peer aplikacije. TCP funkcioniše zajedno sa Internet protokolom (IP) kako bi odredio kako se podaci razmenjuju onlajn. IP je odgovoran za slanje svakog paketa do njegove destinacije, dok TCP garantuje da se bajtovi prenose u redosledu u kojem su poslati, bez grešaka ili propusta. Zajedno, ova dva protokola se nazivaju TCP/IP. \[5\]

*TODO : Još detaljnije opisati sistem, sa konkretnijim i kompleksnijim komponentama i protokolima koje koriste, okrenuti narativ datoteke da sagleda zasto bi neka od komponenata sistema bila zanimljiva malicioznim korisnicima.*

&nbsp;

&nbsp;

### Literatura

\[1\] https://www.makeuseof.com/tag/understanding-common-wifi-standards-technology-explained/

\[2\] https://cpham.perso.univ-pau.fr/ENSEIGNEMENT/PAU-UPPA/RHD/PAPER/EvolutionEthernet.pdf

\[3\] https://www.airitilibrary.com/Article/Detail/P20160719004-201604-201607280029-201607280029-41-60

\[4\] [https://www.imperva.com/learn/application-security/osi-model/#:~:text=The%20Open%20Systems%20Interconnection%20(OSI,companies%20in%20the%20early%201980s](https://www.imperva.com/learn/application-security/osi-model/#:~:text=The%20Open%20Systems%20Interconnection%20%28OSI,companies%20in%20the%20early%201980s)

\[5\] https://www.imperva.com/learn/ddos/tcp-transmission-control-protocol/

\[6\]

\[7\]

\[8\]

\[9\]

\[10\]

\[11\]

\[12\]

\[13\]

\[14\]

\[15\]

\[16\]

\[17\]

\[18\]

\[19\]

\[20\]

\[21\]

\[22\]

\[23\]

\[24\]

\[25\]

\[26\]

\[27\]

\[28\]

\[29\]

\[30\]

&nbsp;

&nbsp;

&nbsp;