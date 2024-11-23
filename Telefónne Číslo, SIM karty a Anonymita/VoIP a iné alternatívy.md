Ak chceme používať "naše číslo", pričom sa nechceme spoliehať na milióny rôznych SIMiek, mali by sme sa zamyslieť nad tým, čo vieme v tejto situácii spraviť pre naše súkromie.

Previazaniu SIM karty s našou identitou sa žiaľ nevyhneme, minimálne nie vtedy, ak SIM kartu používame napr. ako 2FA pre našu banku, Revolut aplikáciu a pod. A niečomu takému sa nevyhneme.

Vieme však navýšiť naše súkromie tak, že táto "KYC" SIMka nepreviazaná s našou identitou môže ostať odložená mimo nášho telefónu, pričom ju môžeme tu a tam používať na prijímanie SMSiek, prípadne prijímanie telefonátov. 

Čo tým vyriešime? No jednoducho to, že mobilný operátor nebude mať našu polohu, keďže v našom zariadení SIM karta nebude. Ideálnym riešením preto môže byť SMS forwarding. 

SMS forwarding je proces automatického odosielania prichádzajúcich SMS správ na iné telefónne číslo, e-mailovú adresu alebo iné zariadenie.

Existuje niekoľko možností preposielania SMS v závislosti od typu používaného zariadenia a služby. Používatelia iPhonu si napr. môžu preposielať SMS/MMS správy z iPhonu na iné zariadenia pomocou Text Message Forwarding feature. Aj keď tento konkrétny prípad vašu digitálnu stopu veľmi nemaže, viete si zhruba predstaviť, ako to funguje.

Na to, aby mobilný operátor nemal vašu polohu, veľakrát stačí “forwardovať” si správy na iné telefónne číslo, prípadne na email, alebo dokonca do Matrixu pomocou bota. Existuje na to mnoho mobilných aplikácii – stačí iba googlovať a zistiť si, ktorá vyhovuje práve vám. Mnohé z nich mimo iné podporujú aj presmerovanie samotných hovorov, čo sa nám určite bude hodiť. Na to, aby to fungovalo stačí mať iba zariadenie na nabíjačke so strčenou SIMkou, ktorej príchodzie správy budeme forwardovať a zariadenie, na ktoré správy prichádzajú. Tak jednoduché to je.

Ak máte tú možnosť, na tento účel sa dá mimo iné využiť aj GSM brána.

Takýmto spôsobom sa môžeme pohrať napr. aj s telefónnym číslom, ktoré je previazané s našou identitou (napr. číslo na klasický paušál od mobilného operátora) – ak číslo chceme stále používať, no nechceme prezrádzať svoju polohu GSM sieti tým, že so sebou budeme neustále nosiť SIMku, tak práve toto je ideálna voľba.

Tento postup však má aj niektoré nevýhody. V prvom rade je možné, že klasickí operátori sa rozhodnú registráciu vášho čísla u VoIP klienta/GSM brány blokovať. Niečo také je výsadou takzvaných „banánových operátoroch“, ktorých mimo iné môžeme nájsť aj na Slovensku alebo v ČR. Patrí medzi nich mimo iné aj Vodafone. Tento problém sa však dá vyriešiť vďaka používaniu VPN.

Čo však VPN nevyrieši, je to, ak niekomu chcete zavolať z vášho VoIP čísla. Veľkarát sa napr. môže stať nešťastie, kedy VPN neumožní port forwarding (v praxi to vyzerá tak, že vytočíte číslo a po pár sekundách sa vám to položí). Ak sa vám to stane, môžete použiť VPN ktorá port forwarding umožňuje, prípadne si zvoliť Skype.

O niečo viac konšpiračnou teóriou ktorá by vysvetľovala príčinu tohto „položeného telefonátu“ je aj to, že ho zablokuje „banánový operátor“. Teória zohľadňuje situáciu, pri ktorej napr. máte vo vašom mobile s VoIP klientom aj funkčnú eSIM (napr. od KeepGo), ktorá má s podobnými „banánovými operátormi“ zmluvu. Ak sa rozhodnete z vášho VoIP čísla niekomu zavolať, mobilný operátor s ktorým má vaša eSIM zmluvu môže tento telefonát zrušiť (a teda vám telefonát položí).

Či už je vo veci konšpirácia s eSIM bypassujúcou VPN alebo VPN neschopná forwardingu, podobná situácia vie nejedného z nás skutočne potrápiť a treba si preto dobre rozmyslieť výber eSIM, výber VPN (ak teda vôbec existuje nejaká, ktorá by to vedela vyriešiť), ako aj to, či možnosť volania z vášho VoIP klienta skutočne potrebujete.

Pre predstavu, nejak takto môže vyzerať registrácia a nastavenie účtov na iOS u VoIP klienta Zoiper (Zoiper podporuje IAX a aj SIP protokoly, avšak iba pri protokole SIP je možné si predplatiť tzv. „push notifikáciu“, skrz ktorú vám prídu prichádzajúce hovory aj v prípade, že apliácia Zoiperu momentálne aktívne nebeží):

XXX SCREENSHOT ZO ZOIPERU

# Presmerovanie čísla na Skype

Ak sa nám nepáči presmerovanie hovorov na VoIP klienta a zdá sa nám príliš komplikované, môžeme ho nechať tak. Čo však urobíme keď sme teda ostali iba s forwardovaním SMS?

Riešením tohto problému môže byť napr. číslo presmerované na Skype. Cez Skype si viete kúpiť VoIP číslo, na ktoré si môžete presmerovať vaše aktuálne číslo. Bude vás to stáť približne 7 eur mesačne/20 eur na tri mesiace/50 eur na rok. Anonymný spôsob nákupu určite existuje, no nemusíte ho riešiť, ak vám v tomto prípade ide iba o skrytie polohy – môžete si ho prepojiť s Microsoft účtom.

Microsoft nebude vedieť vašu polohu ale bude vidieť vašu IP – ak používate VPN, tak bude vidieť akurát VPN endpoint, ktorý používate.

Skype však nepodporuje slovenské čísla – podporuje iba české. Navyše pozor – ak si budete kupovať VoIP číslo na Skype, máte na výber širokú paletu krajín – avšak mnoho mobilných operátorov nedovolí slovenské či české čísla presmerovať na iné ako slovenské či české číslo (potrebujete si teda kúpiť české, keďže slovenské nie je podporované). Navyše, za presmerovanie platíte rovnako ako za volanie; dokonca u niektorých operátorov sa takéto presmerovanie neráta ani do “voľných minút”.

Ďalšou nevýhodou je nemožnosť presmerovať SMS – práve preto je nevyhnutné využiť SMS forwarding.

XXX ČESKÉ VOIP ČÍSLO
