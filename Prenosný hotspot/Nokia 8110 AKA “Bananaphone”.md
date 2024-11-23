Nokia 8110, známa aj ako "Bananaphone" kvôli svojmu jedinečnému zakrivenému dizajnu, ktorý pripomína banán, je mobilný telefón so skládacím krytom, ktorý bol pôvodne uvedený na trh v roku 1996. V roku 2018 bola Nokia znovu uvedená na trh s prakticky rovnakým dizajnom, pričom bola obohatená o nový operačný systém KaiOS.

KaiOS je mobilný operačný systém založený na Linuxe, ktorý bol navrhnutý pre feature phone (tlačidlové telefóny), poskytujúci prístup k aplikáciám ako WhatsApp, YouTube aviac, čo nadobúda funkcie smartfónov aj na základnejších zariadeniach.

Čo sa týka zmeny IMEI, tak je potrebné vedieť, že Nokia 8110 ako taká neumžňuje zmenu IMEI v originálnom firmvéri – je preto potrebné telefón dočasne [vyrootovať](https://sites.google.com/view/bananahackers/root/temporary-root) a následne do telefónu nahrať modul Wallace Toolbox, ktorý tam pridá nové menu. 

Nižšie nájdeme celý postup ako na to:

Jednou z pozoruhodných vlastností telefónu Nokia 8110 so systémom KaiOS je jeho prispôsobivosť pri spravovaní system permissions a funkcií prostredníctvom rôznych aplikácií. Kľúčové nástroje, ktoré uľahčujú prispôsobenie vrátane zmeny IMEI, sú:

- Wallace ToolBox: Program je primárne určený pre zariadenia so systémom KaiOS a ponúka súbor nástrojov na úpravu vrátane možnosti manipulácie s IMEI. Táto aplikácia je obzvlášť výhodná, pretože sa bezproblémovo integruje so systémom KaiOS a poskytuje stabilné prostredie pre modifikácie systému.
- OmniSD: Táto aplikácia je ďalším dôležitým nástrojom, ktorý umožňuje sideloading aplikácií tretích strán, ako je napríklad Wallace ToolBox, do zariadení KaiOS. Pomáha prekonať predvolené obmedzenia umiestnené v zariadení, čím používateľom poskytuje možnosť upravovať nastavenia a dáta na systémovej úrovni.
- BusyBox: Inštalácia BusyBoxu je nevyhnutná na vykonávanie pokročilých systémových príkazov a operácií. OmniBB, dočasný inštalátor BusyBoxu od spoločnosti Luxferre, zjednodušuje tento proces tým, že umožňuje inštaláciu BusyBoxu na zariadeniach KaiOS, ktoré ho pôvodne nemajú.

# Postup krok za krokom na zmenu IMEI

Zmena IMEI v zariadení Nokia 8110 pomocou platformy KaiOS zahŕňa niekoľko technických krokov, ktoré si vyžadujú starostlivé vykonanie:

Začnite tým, že pomocou OmniSD nainštalujete do zariadenia Wallace ToolBox a OmniBB. Uistite sa, že je aktívny BusyBox, pretože je potrebný pre terminálové príkazy.

Otvorte Wallace ToolBox a prejdite do root access functionalities. Povoľte root access, aby ste mohli bezpečne upravovať systémové súbory.

(OBRÁZOK – Wallace Toolbox)

Následne sa môžeme pustiť do nastavovania zmeny IMEI –  je možné zmeniť IMEI1 a IMEI2 (ide o dual SIM telefón, takže je to možné zmeniť pre oba sloty). V aplikácii Wallace ToolBox vyhľadajte sekciu nastavení alebo nástrojov týkajúcu sa konfigurácie IMEI. Zvyčajne zahŕňa zadanie požadovaného čísla IMEI a potvrdenie zmien.
Používať úplne náhodné IMEI nie je dobrý nápad, lebo je ho možné následne identifikovať ako náhodne vygenerovaný. Preto je lepší nápad použiť náhodné IMEI z definovaného rozsahu samotných výrobcov telefónov – je možné na to použiť napr. aplikáciu [imeichanger.py](https://github.com/narodnik/immi/) od Amira Taakiho.

Po zadaní nového IMEI aplikujte zmeny. Môže byť potrebné rebootovať zariadenie, aby sa zmeny úplne prejavili. Po opätovnom zapnutí zariadenia môžete overiť zmenené IMEI vytočením čísla *#06# v aplikácii telefónu, kde by sa malo zobraziť nové IMEI.
Aby celá anonymizácia mala zmysel, tak po zmene IMEI, treba telefón vypnúť, vložiť novú anonymnú SIM kartu, zmeniť vašu fyzickú polohu a naštartovať telefón s novým IMEI a novou anonymnou SIM kartou (v tomto okamihu sa telefón bude pre GSM sieť javiť ako úplne nový telefón s novou SIM kartou). Polohu je odporúčané zmeniť, aby operátor nevidel, že na mieste kde zmizol starý IMEI/IMSI sa zrazu objavil nový IMEI/IMSI a nedokázal to teda prepojiť.
