## XSS Napad

Cross-Site Scripting (XSS) su vrsta injekcije, u kojoj se maliciozne skripte ubrizgavaju u web lokacije. Mane koje omogućavaju uspjehe ovih napada su prilično rasprostranjene i javljaju se svuda gdje web aplikacija koristi unos od korisnika u okviru izlaza koji generiše bez validacije ili kodiranja. Napadač može da koristi XSS da pošalje zlonamjernu skriptu korisniku koji ništa ne sumnja. Pregledač krajnjeg korisnika nema načina da zna da skripti ne treba vjerovati i da će je izvršiti. Pošto misli da je skripta došla iz pouzdanog izvora, zlonamjerna skripta može da pristupi svim kolačićima, tokenima sesije ili drugim osetljivim informacijama koje čuva pregledač [1].
U ovom dokumentu će biti pomenuta dvije varijante XSS napada:

1.  Reflected XSS
    Prvi korak refleksnog XSS napada je slanje vektora napada na serveru putem HTTP zahtjeva GET ili POST. Kada se poruka analizira na serverskoj strani, server šalje odgovor napadaču. Nakon analize serverskog odgovora, napadač provjerava da li je kod za testiranje (djelimično) prikazan i stoga reflektovan. U slučaju HTTP-GET zahtjeva, napadač može da pripremi vezu koja upućuje na ranjivu web aplikaciju, sa zlonamjernim JavaScript kodom ugrađenim u string upita. U slučaju POST zahtjeva, može se koristiti pripremljeni HTML obrazac koji se automatski šalje čim se stranica za napad učita.
2.  Stored XSS
    Ako se vektor napada može trajno čuvati u web aplikaciji (primjer zlonamjerni kod unutar datoteke evidencije), imamo sačuvani XSS. Svaki put kada žrtva posjeti dio web aplikacije gde se vektor čuva, napad će se izvršava [2].

## Stablo napada

## Ranjivosti

XSS ranjivosti se javljaju kada unos koji dolazi u web aplikacije nije validiran ili sadržaj u pretraživaču nije pravilno izbačen pre nego što se prikaže ili taj isti sadržaj nije enkodiran.

## Opisan slučaj napada

U nastavku će se detaljno razmotriti napad na Belkin F7D4301 ruter [3]. Da bi napao korisnika preko XSS-a, napadač može da koristi datoteku koja bi omogućavala dodavanje virtuelnog servera uz pomoć HTTP POST zahteva. Ključna tačka ovog POST zahtjeva je mehanizam validacije unosa. Nije dovoljno striktno konfigurisan da blokira napade ubrizgavanjem koda. Zbog toga je moguće ubaciti sačuvani XSS vektor preko jednog od tekstualnih polja, koje će uvijek biti prikazano kada korisnik posjeti web stranicu.
Dodatno uključivanje eksterne JavaScript datoteke pravi idealne preduslove za korišćenje alata za eksploataciju, time se omogućava povezivanje sa aplikacijom.
Sljedeći mogući koraci jesu:

- Koristiti mehanizme za prikupljanje informacija kako bi napadač dobio informacije vezane za instalirane žrtvine dodatke za izvođenje pojedinačnih eksploatacija pretraživača.
- Napad na korisnika tehnikama društvenog inženjeringa tako što cse instalira Firefox/Chrome ekstenzija koja omogućava trajan ulazak u web pretraživač i na taj način napada sve posećene web lokacije.
- Otkrivanje mreže korišćenjem tehnika skeniranja portova ili implementiranim mrežnim napadima kao što je fingerprinting [2][4].

## Posljedice

U aplikacijama za razgledavanje sadržaja, gdje su svi korisnici anonimni i sve informacije su javne, uticaj XSS napada će često biti minimalan, dok u aplikaciji koja sadrži osjetljive podatke, kao što su bankarske transakcije, imejlovi ili zdravstveni kartoni, uticaj će obično biti ozbiljan.
Ako kompromitovani korisnik ima povišene privilegije unutar aplikacije, onda će uticaj generalno biti kritičan, omogućavajući napadaču da preuzme potpunu kontrolu nad ranjivom aplikacijom i ugrozi sve korisnike i njihove podatke. [5]

## Mitigacije

Ovaj napad oslanja se na činjenicu da postoje prijemnici ulaza, koji nisu pravilno validirani. Stoga, se razmišlja o načinima poboljšanja validacije kako bi se ublažili napadi ubrizgavanjem koda. U slučaju XSS napada, najbolji način da se zaštitite od ovih problema je provera na strani servera sa bijelim listama. Stavljanje na bijelu listu dozvoljava pristup samo određenim IP adresama koji se smatraju pouzdanim za pristup. Alternativa bijelim listama su crne liste. Takva lista može onemogućiti upotrebu specijalnih znakova tako što ih kodira tako da se ne mogu koristiti za izvršavanje zlonamernog koda [2].

## Reference

/[1/] [Kirsten S. Cross Site Scripting (XSS)](https://owasp.org/www-community/attacks/xss/)

/[2/] [Marcus Niemietz, Jorg Schwenk. Owning Your Home Network: Router Security Revisited](https://arxiv.org/pdf/1506.04112.pdf)

/[3/] [Belkin router documentation](https://www.belkin.com/my/support-article?articleNum=7994)

/[4/] [Fingerprinting](fingerprinting)

/[5/] [Portswigger](https://portswigger.net/web-security/cross-site-scripting)
