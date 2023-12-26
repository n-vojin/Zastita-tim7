# Zastita-tim7

## **Osiguranje WiFi mreža i rutera: Pretnje, ranjivosti i protivmere**

**Apstrakt:**

Ovaj istraživački rad istražuje ključne aspekte sigurnosti WiFi mreža i rutera, proučavajući njihove funkcionalnosti, mehanizme povezivanja i ranjivosti na potencijalne sajber pretnje. U eri koju dominiraju povezani uređaji i besprekorna razmena podataka, razumevanje nijansi WiFi mreža i rutera od suštinskog je značaja za održavanje sigurnog digitalnog okruženja.

Studija počinje istraživanjem osnovnih operacija WiFi mreža, obazirući se na tehnologije u omogućavanju bežične komunikacije. Prilikom analize mehanizama povezivanja, naglašava se važnost enkripcionih protokola kako bi se zaštitile veze od neovlašćenog pristupa.

Međutim, čak i uz snažne enkripcije, WiFi mreže i ruteri ostaju podložni raznim ranjivostima. Rad identifikuje uobičajene slabosti koje zlonamerni pojedinci mogu iskoristiti, uključujući zastareli softver, podrazumevane pristupne podatke i netačne konfiguracije rutera itd. Adresiranje ovih ranjivosti ključno je za sprečavanje neovlašćenog pristupa i potencijalnih rizika po bezbednost mreže.

### Opis sistema

**Funkcionalnosti koje ruter pokriva:**

1. Povezivanje uređaja unutar mreže i dijeljenje resurasa, podataka i usluga i time omogućava međusobnu komunikaciju.

2. Informacije koje se dijele, stavljaju se u pakete i kruže mrežom, ruteri analiziraju pakete i pronalaze najefikasniji put.

3. Ruteri mogu da daju prioritet određenim vrstama saobraćaja, obezbjeđujući da kritične aplikacije (kao što su glas ili video) dobiju veći prioritet, što rezultuje poboljšanim performansama za aplikacije osjetljive na vrijeme.

4. Ruteri dodjeljuju i upravljaju IP adresama za uređaje unutar mreže. Ovo je ključno za identifikaciju i usmjeravanje podataka na tačno odredište. Mogu uključiti DHCP servere, koji automatski dodjeljuju IP adrese uređajima na mreži, pojednostavljujući konfiguraciju mreže za korisnike.

5. Ruteri su neophodni za povezivanje lokalnih mreža na internet. Oni deluju kao mrežni prolaz, prosleđujući podatke između uređaja na lokalnoj mreži i šireg interneta.

6. Ruteri omogućavaju stvaranje podmreža, dijele veću mrežu na manje segmente. Ova segmentacija poboljšava performanse mreže, bezbednost i upravljanje.

Samim tim se nadovezuje i sam razlog napada na ruter kao jednog od najvažnijih uređaja na mreži sa širokom pokrivenošću je ruter. Ruteri mogu da čuvaju identitet saobraćaja podataka na osnovu tabela dostupnih preko rutera. Brzi napredak tehnologije rutera dokazuje da su ruteri najpotrebniji uređaji, posebno za internet provajdere u izgradnji mreže i njenoj bezbednosti. Glavni cilj napadača pre ulaska u glavni sistem ili centar podataka je da isključi performanse rutera. \[1\]

**Pri istraživanju mogućnosti napada, mogu se izdvojiti dvije vrste:**

1. Napadi direktno na ruter

2. Napadi na rutiranje

&nbsp;

### Ruter napadi

Prvo je potrebno utvriditi koje su ranjivosti koje bi napadači iskoristili kako bi izvršili napad:

###### 1.Firmware

Svi ruteri zasnovani na hardveru dolaze sa automatski instaliranim softverom poznatim kao firmver koji pomaže ruteru da obavlja svoje funkcije. \[2\]

###### 2.Logička adresa rutera

Logičku adresu rutera predstavlja interfejs rutera. Za svaki primljeni mrežni paket, ruter određuje se na koji ga interfejs prosleđuje. To radi preko tabele za rutiranje. (eng. Routing table). Napad koji iskorištavaju interfejs kako bi došli do određenog cilja je [UI redressing](https://github.com/n-vojin/Zastita-tim7/blob/main/UI%20Redressing.md).

UI redressing je tehnika napada za modifikovanje ponašanja i opciono izgled napadnutog interfejsa. Napadačev cilj je dozvoliti žrtvi da izvrši radnje koje su određene od strane napadača. U sklopu ove tehnike imamo dva tipa napada Clickjacking I Tabjacking .

Kod Clickjacking napdač ubacuje svoju stranicu ili element unutar IFrame-a, gdje namamljuju korisnika da klikne na određen element. Tabjacking koristi objekat window.name i time napadač može manipulisati URL-om administrativnog interfejsa, namami žrtvu da klikne na link maliciozne veb stranicu koju kontroliše.

Tipičan scenario: web stranica napadača sadrži “a” element sa kodom target="router_interface" href="//192.168.1.1" tako da kada klikne na “a” element, otvara se stranica administrativnog interfejsa, gdje se potom namami žrtvu da klikne na link maliciozne veb stranice. U tom linku se nalazi href="#" onclick="window.open('//evil.com', 'router_interface'); return false;" Tako povezan ruter interfejs i maliciozna stranica, omogućavaju krađu svih unesenih podataka. \[3\]

&nbsp;

Drugi napadi vrijedni istraživanja koji koriste logičke adrese rutera kako bi pristupili svim informacijama su Cross Site Scripting ([XSS](https://github.com/n-vojin/Zastita-tim7/blob/main/XSS.md), Cross-Site Request Forgery (CSRF) \[3\]

&nbsp;

###### 3.Fizička adresa

Fizička adresa, poznata i kao IP adresa  je jedinstveni niz brojeva koji koriste mašine u međusobnom saobraćaju putem interneta. Drugim riječima, IP adresa je medij komunikacije koja pomaže uređajima i računarima da upute korisnika na pravu stranicu. \[4\]

&nbsp;

IP adresa na portu rutera takođe može značiti mrežni prolaz na mrežnom segmentu. IP Gateway se obično koristi kao meta za aktivnosti napada na mreži. kada dođe do DOS napada na mrežu rutera, povećava se opterećenje CPU-a i memorije. Na osnovu rezultata sistema za praćenje saobraćaja, nakon što je došlo do [DOS](https://github.com/n-vojin/Zastita-tim7/blob/main/DoS%20Napad.md) napada, utvrđeno je da je opterećenje CPU paketa podataka sistema za praćenje saobraćaja poraslo na 100% i da je memorija od 7,6 MiB značajno porasla. Ovo dovodi do smanjenja mrežnog saobraćaja zbog DOS napada na rutere. \[5\] Denial of Service ([DOS](https://github.com/n-vojin/Zastita-tim7/blob/main/DoS%20Napad.md)) je jedan od najčešćih napada na veb sajt, mreže, rutere i servere. Ima za cilj da mrežni ruter učini nesposobnim da servisira zahteve ovlašćenih korisnika. \[5\]

&nbsp;

###### 4.[Podrazumjevani kredencijali](https://github.com/n-vojin/Zastita-tim7/blob/main/Napad%20preko%20direktne%20povezanosti.md)

Konkretno se baziramo na podrazumjevanu (default) lozinku. Razlog tome jeste što postoji mali broj podrazumjevanih lozinki i često se desi da ruteri mogu imati istu lozinku. Napad koji se može tu izvršiti jeste CSRF (Cross-Site Request Forgery).

Kako funkcioniše CSRF: žrtva mora da posjeti web stranicu napadača, samim tim se šalje HTTP zahtjev u kojem stoji podrazumjevano korisničko ime i lozinku. Skripta napadača dozvoljava žrtvi da sačeka nekoliko sekundi da bi bili sigurni da je korisnik prijavljen na ruter sa podrazumevanim korisničkim imenom i lozinkom. Kod napadača omogućava žrtvi da pošalje drugi zahtev, koji manipuliše interfejsom administracije napadnutog rutera, pa napadač ima pristupa nekom web odredištu u ime žrtve. Od ovakvog napada ruter se može zaštiti korišćenjem osnovne HTTP autentifikacije. \[5\]

Otisak prsta ([Fingerprinting](https://github.com/n-vojin/Zastita-tim7/blob/main/Fingerprinting.md)) je još jedan napad koji se koristi kao tehnika prodora u mrežu kako bi se prikupilo što više informacija o konfiguraciji sistema. Često se koristi kao priprema za ozbiljnije napade, tipa [DOS](https://github.com/n-vojin/Zastita-tim7/blob/main/DoS%20Napad.md) napade. \[6\] U ovom slučaju Fingerprinting se radi kako bi se otkrila defaultna lozinka rutera time bismo više ili manje mogli ugroziti mrežu. Koliko ruter igra ulogu kao vitalni organ mreže zavisi i od same hardverske distribucije. \[6\]

&nbsp;

###### 5.Tabela za rutiranje (eng. Routing table)

Tabela rutiranja predstavlja podatke pohranjene u RAM memoriji koji govore ruteru kako proslijediti primljeni paket susjednoj ili udaljenoj mreži. Trovanje tabela rutiranja se dešava kada dođe do drastične zlonamjerne promjene u rutini tabela rutiranja. Ovi agresivni napadi se postižu uređivanjem paketa informacija koji kruže kroz tabelu rutiranja. Trovanje rutiranjem može prouzrokovati izuzetnu štetu mrežama i serverima kao rezultat dodavanja netačnih podataka u tabelu rutiranja. Primjer napada koji uključuje tabelu rutiranja i samo rutiranje jeste [LSA Falsifikovanje](https://github.com/n-vojin/Zastita-tim7/blob/main/LSA%20Falsifikovanje.md).

Načini odbrane:

Ažuriranje Firmware-a

Mijenjanje podrazumjevanih kredencijala

Korišćenje osnovne HTTP autentifikacije

Koristiti dobru enkripciju

Filter zaštitnog zida i ruteri zaštitnog zida su efikasni u terinada terranga DoSpada rutermikrotik. Funkcije filtera zaštitnog zida menjaju paketne podatke kao na ruteru, dok funkcije rutera zaštitnog zida za IP blokove blokiraju paketne podatke koji se nalaze na ruteru. Da biste sprečili napade, morate usmeriti ruter pomoću resetovanja rutera sa hardverskim zaštitnim zidom. \[5\]

### Reference

[1] [Yudhana,A.,Riadi,I.,& Ridho, F. (2018). DDoS Classification Using Neural Network and Naïve Bayes Methods for Network Forensics. International Journal of Advanced Computer Science and Applications(IJACSA),9(11), 177-183.DOI:](https://thesai.org/Publications/ViewPaper?Volume=9&Issue=11&Code=ijacsa&SerialNo=25)

\[2\] Richard Deal (2004) Cisco Router Firewall Security

\[3\] Marcus Niemietz, Jorg Schwenk (2015) Owning Your Home Network: Router Security Revisited

\[4\] Ivana Mihajlović (2021) Sve što treba da znate o IP adresama

\[5\] Budi Jaya, Yuhandri Yunus, Sumijan (2020) Peningkatan Keamanan Router MikrotikTerhadap Serangan Denial ofService(DoS)

\[6\] Emeline Marechal, Benoit Donnet (2020) Network Fingerprinting: Routers under Attack
