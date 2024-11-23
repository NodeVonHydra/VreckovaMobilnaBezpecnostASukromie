Mudi V2 (GL-E750V2) , vyrábaný spoločnosťou GL.iNet, je prenosný bezdrôtový router kompatibilný s globálnymi operátormi 4G LTE, ktorý je optimalizovaný pre cestovateľov so záujmom o ochranu súkromia podobne ako NitroWall.

Mudi beží na OpenWRT, podporuje WiFi rýchlosti  až do 733 Mb/s (300 Mb/s na 2,4 GHz plus 433 Mb/s na 5 GHz) a je vybavený slotom pre microSD kartu s kapacitou až 1 TB, čo umožňuje užívateľom ľahko ukladať, zdieľať a zálohovať dáta. Podobne ako Nitro Wall podporuje aj protokoly WireGuard a OpenVPN, narozdiel od neho však nepodporuje Tor.

Mudi má na boku manuálny “switch”, ktorým si použitie VPN viete zapnúť a vypnúť. 

V srdci Mudi V2 poháňa procesor Qualcomm QCA9531 s taktfrekvenciou 650 MHz, doplnený o 128 MB DDR2 RAM a 144 MB pamäte (16 MB NOR Flash + 128 MB NAND Flash). Je vybavený lítium-polymérovou batériou s kapacitou 7000 mAh, ktorá slúži aj ako powerbanka, umožňujúca nabíjanie externých zariadení. Tento router je tak nielen zdrojom Wi-Fi na vašich cestách, ale mimo to je aj praktickým záložným zdrojom energie.

V čase písania tohto textu si zariadenie môžete objednať na webovej stránke shop.nitrokey.com za cenu 152 amerických dolárov.

A to ma konečne privádza k otázke – výhoda zariadenia Mudi oproti zariadeniu NitroWall spočíva v pomere jeho ceny a výkonu. 

Ako ste si už mohli správne všimnúť, v špecifikách ohľadom Mudi sme si nespomenuli nič ohľadom zmeny IMEI. A malo to svoj dôvod – Mudi zmenu IMEI defaultne skutočne neumožňuje. Potrebujete si na to stiahnuť modul “blue-merle” z GitHubu, ktorého inštalácia a implementácia je extrémne jednoduchá a aj keď sú preferencie každého z nás odlišné, osobne by som povedal že cenový rozdiel približne 140 eur je stále dosť veľký na to, aby sa mi oplatilo sa na chvíľku pohrať s terminálom a gitklonovať 🙂

# Ako zmeniť IMEI cez blue-merle

V prvom rade si treba zapnúť náš Mudi hotspot (SIMka – a ani internet – v ňom byť nemusí). Na desktope ostaneme pripojení na našu domácu wifi, ktorá však internetové pripojenie mať musí :)

Na Githube si nájdeme modul blue-merle (https://github.com/srlabs/blue-merle) a stiahneme si release package v možnosti “Offline Install” a unzipneme ho. 

Následne sa z nášho zariadenia pripojíme na WiFi z routera Mudi. Release package skopírujeme do routera offline pomocou commandu v termináli:

`scp -O -r blue_merle_install root@192.168.8.1:/tmp`

Následne otvoríme terminál a pripojíme sa k roteru cez SSH:

`ssh root@192.168.8.1`

Router nás vyzve k vloženiu root hesla (ktoré je totožné s naším Admin Panel heslom v Mudi). Akonáhle sa do routera dostaneme cez SSH, môžeme zmeniť directory do blue-merle, ktorý sme si tam skopírovali:

`cd /tmp/blue_merle_install`

Následne spustíme `./install.sh` a blue-merle sa nám spustí. Blue-merle nám ukáže naše aktuálne IMEI. Vyzve nás k stlačeniu klávesy Enter a po pár sekundách nás vyzve ešte raz s otázkou, či chceme zmeniť IMEI a swapnúť SIM kartu. Ak s tým súhlasíme, ďalej máme na výber z možnosti deterministického (d) a random ® IMEI.

Aký je medzi tým rozdiel?

Random IMEI je vždy random, bez ohľadu na to, či si vymieňame SIM kartu alebo nie. Deterministické IMEI sa mení práve vtedy, keď sa zmení IMSI – a teda – keď sa zmení SIM karta. Využitie random a deterministického IMEI závisí od našich subjektívnych preferencií – môžeme si zvoliť výhradne to, čo vyhovuje práve nám. 
Akonáhle si zvolíme ľubovoľnú zmenu IMEI, terminál nás informuje o tom, že práca bude vyjonaná, akurát musíme zariadenie buď vypnúť (S), alebo resetovať (m).


(OBRÁZOK – admin panel)

Výhoda terminálového okna nepochybne spočíva v zaujímavej geekovskej skúsenosti ako aj v tom, že v termináli si máme šancu overiť samotnú zmenu IMEI, keďže nám ho terminál pri každom novom spustení ./install.sh na blue-merle vypíše. Avšak – modul blue-merle môžete používať aj analógovo. V okamihu, kedy sa blue-merle dostane na vaše zariadenie, sa z bočného switchu na Mudi (ktorý pôvodne slúžil na zapnutie/vypnutie VPN) stane tlačidlo na zmenu IMEI. Tlačidlo jednoducho potiahnete dole, na displeji sa vám ukáže 

Zariadenie nás vyzve k zmene fyzickej SIM karty a následnému potiahnutiu tlačidla smerom nahor. Mudi následne vyberie random IMEI a automaticky sa vypne, no ešte predtým nás upozorní k tomu, aby sme zmenili svoju polohu predtým, než Mudi znovu nabootujeme.

(OBRÁZOK – blue-merle a zmena IMEI na displeji Mudi)

Ak by vám náhodou nestačili dva možné spôsoby zmeny IMEI na Mudi, existuje aj tretí 🙂

Modul blue-merle na zmenu IMEI aktivujete štandardne cez lokálnu linku https://192.168.8.1/cgi-bin/luci/admin/network/blue-merle po tom, ako sa do rozhrania prihlásite ako root. V tomto webovom rozhraní je tak isto možné overiť si IMEI podobne, ako je tomu v termináli pri bežaní ./install.sh.

Aká je však uživateľská skúsenosť? Nuž, pokiaľ experimentujete s Mudi alebo s inými prenosnými hotspotmi, po čase zistíte, že nie je tak úplne jednoduché, ak chcete do vášho routera strčiť SIMku z miestnej trafiky (či už používate Cosmote v Grécku, Vodafone v Česku alebo Bharti Airtel v Indii) a zároveň skrz ňu chcete mať internetové pripojenie.

A to už prečo? Nuž, dôvodom sú všemožné nastavenia. Rôzne SIMky od rôznych operátorov môžu skrátka požadovať rôzne nastavenia Protokolu, Portu, APN, Service, prípadne iných preferencií. Aj takto nejako môže vyzerať nastavenie Cellular Settings pri O2 SIMke na Mudi:

(OBRÁZOK – rôzne nastavenia cellular setting na Mudi)

Samozrejme, nie je to neriešiteľné, dá sa s tým pohrať ale koniec koncov – tento proces je veľakrát oveľa viac nepríjemný a zdĺhavý, než by sme chceli. Ak si SIM kartu dáme do mobilného telefónu a zadáme jej PIN, internet obvykle funguje na prvý šup. A niečo také nám dokáže pokaziť zážitok z Mudi hotspotu

# GLiNet eSIMky

Tento (a mnohé iné problémy) vyriešil eSIM adaptér od firmy GLiNet, ktorý je kompatibilný s routerom Mudi V2 (GL-E750V2).

GLiNet pritom ponúka dva typy eSIM – čipové karty eSIM a fyzické karty eSIM.

Nastavenie a aktivácia eSIM s GL.iNet je navrhnutá tak, aby bola čo najužívateľsky prívetivejšia:
- Vloženie eSIM: Užívatelia vložia fyzickú eSIM kartu do zariadenia, alebo ak používajú čip eSIM, jednoducho aktivujú zariadenie.
- Správa eSIM: Prístup k “eSIM Manage” sa realizuje cez Admin Panel routera GL.iNet (192.168.8.1) v sekcii “Applications”.
- Nákup a aktivácia profilu: Profily eSIM si možno zakúpiť online, a následne sa aktivujú stiahnutím a inštaláciou cez QR kód.
- Pripojenie: Po aktivácii a povolení eSIM môžu používatelia začať ihneď využívať mobilné dátové služby.
