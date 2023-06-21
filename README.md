# Introduction to cyber-security
Introduction to cyber security - security awareness - Óbuda University 2023

## Kiberfenyegetés
### Biztonság tudatosság
Tudatosság az a képesség, melyben közvetlenüll megismerjük és érzékeljük az eseményeket </br>
**Olyan állapot, amelyben**: </br>
- az alany bír valamilyen információval </br>
- ez az információ a rendelkezésére áll </br>
- és amely befolyásolja viselkedési folyamatait </br>

Azonosítható tudatos hozzáállással. </br>
</br>

### Biztonság tudatosság célja
**A biztonság-tudatosság arra öszpontosít , hogy**: </br>
Tudatosítsa a gyorsan változó információ formák lehetséges kockázatait, </br>
az információ gyorsan növekvő veszélyeit, amelyek az emberi viselkedést célozzák meg. </br>
A biztonságtuudatosság az információbiztonság számos alapelve közül az egyik. </br>

-----------------
### Biztonság tudatosság szükségessége
"Internet is not secure by design"
-----------------

Test: </br>
![Test](test.png) </br>

</br>

### Támadási célpontok
**Támadási módszerek és célpontjaik**: </br>
|Methods|People|Companies|
| --- | :-: | :-: |
|Malware|x|x|
|Web based attacks|   |x|
|Phishing|x|x|
|Web application attacks|   |x|
|Spam|x|x|
|Distributed Denial of Service (DDoS)|   |x|
|Identity theft|x|   |
|Data breaches|   |x|
|Insider threats|   |x|
|Botnets|   |x|
|Physical manipulation, damage, theft and loss|x|x|
|Information leakage|   |x|
|Ransomware|x|x|
|Cyberespionage|   |x|
|Cryptojacking|x|   |

</br>

------------------------------------------------------------------------------------------------------------
## Böngészés az interneten
### Böngésző
![Browser](browser.png) </br>
- Mit jelképez a lakat szimbólum? </br>
- Milyen gyakran gépelünk el webcímeket? </br>
- Mi történik, ha egy hivatkozás fölé visszük az egeret a webböngészőben? </br>
- Mik azok a web sütik (cookie)? </br>
- Érdemes privát böngészési módot használni? Miért? </br>

</br>

### Webcímek
- Uniform Resource Locator (URLs) </br>
- Az RFC 1738 definiálja </br>
- Általános formátum: scheme:[//[user[:password]@]host[:port]][/path][?query] [#fragment] </br>

</br>

### A domain
- TLD – Top Level Domain: “.hu”, “.com” </br>
- Restricted / korlátozott domainek: “.mil”, “.gov” </br>
- Domain: “uni-obuda.hu” </br>
- Aldomain: neptun.uni-obuda.hu </br>

</br>

### Webcímek formátuma
Séma szerinti web url: http://user:pass@example.tld:8080 </br>

</br>

### Protokollok
http, https, ftp, gopher, ... </br>

</br>

### Weboldalak felépítése
A weboldalak tartalmát hierarchiába lehet rendezni: </br>
https://neptun.uni-obuda.hu/hallgato/login.aspx </br>

Speciális karakterek dinamikus oldalak esetén pl.: “?”, “&“, “#” </br>
“%20” - szóköz </br>

</br>

### Hol van a HTTP?
![OSI](osi.png) </br>

</br>


### HTTPS
- Felek azonosítása külső tanúsító szervezetek (Certifcate Authorities, CA) segítségével </br>
- Lehetőséget biztosít hibásan azonosított weboldalak automatikus tiltására </br>
- Adatok védelme erős titkosítás segítségével. </br>

</br>

### Tanúsítványok
![Credentials](credentials.png) </br>

</br>

### Támadások
- Adatgyűjtés tudatos hozzájárulás nélkül </br>
- Bizalmasság megsértése: </br>
  - Lehallgatás (snifng, wiretapping) </br>
  - Közbeékelődés (MitM) </br>
- Kérések eltérítése: </br>
  - Címhamisítás (DNS, DHCP, IP, ARP </br>
  - Trükkös kódolás (URL kódolás, homoglyph támadás) </br>
- Social engineering: </br>
  - Phishing </br>
  - Kattintásvadászat </br>
  - Rémisztgetés </br>
- Rendszer (böngésző) elleni támadások: </br>
  - Szkriptelés (CSRF, XSS) </br>
  - Puffer túlcsordulások </br>
  - ... </br>
- Felhasználó megtévesztése kibővített unicode karakterek segítségével
  - ![Unicode](unicode.png)
    ```
    http://gοοɢӏе.com
    ```
  - valójában: </br>
    ```
    http://g%u03BF%u043E%u0261%u217C%u0435.com
    http://xn--gl-jgb31l6qtb.com
    http://xn--g-s1a36hsnmb7023a.com
    ```

</br>


------------------------------------------------------------------------------------------------------------

## Levelezés biztonsága
### E-mail szolgáltatások
- Milyen gyakran kapunk ismeretlen feladóktól származó leveleket? </br>
- Mit tehetünk velük? </br>
- Miért tekinthetők károsnak a SPAM (kéretlen) levelek? </br>
- Mennyire tekinthetők privátnak a magánleveleink? </br>
- Ki és mikor olvashatja el őket? </br>

</br>

### Levelezőrendszerek - kliens
Levelező kliens (Mail User Agent, MUA) </br>
- Elsődleges felhasználói felület </br>
- Feladata az üzenetek megjelenítése és elkészítése </br>
- Az RFC524 és MIME (Multipurpose Internet Mail Extensions) szabványokat használja </br>
- Egyéb protokollok: SMTP, MAPI, IMAP, POP3 </br>

</br>

### Levelező szerver
Levelező kiszolgáló (Message Transport Agent, MTA) </br>
- Feladata az üzenetek küldése és fogadása </br>
- Az SMTP (Simple Mail Transfer Protocol) szabványt használja </br>

</br>

### E-mail: fejléc
Fejléc mezők (kulcs- értékek) </br>
- From (üzenet feladó) </br>
- To (üzenet címzett) </br>
- CC (másolat) </br>
- Dátum (a feladó rendszerben) </br>
- Subject (tárgy) </br>
- A tartalom típusa és sok minden más… </br>

</br>

### E-mail: fejléc
Üzenettörzs (fő tartalom) </br>
Tartalom típusok: </br>
- multipart/mixed – több rész </br>
- text/plain – szöveges rész </br>
- text/html – formázott szöveges rész </br>
- application/octet-stream – mellékletek </br>
Számos kódolási típus </br>

</br>

### SMTP protokoll alapok
Szöveg alapú ősprotokoll: </br>
- SMTP bővítmények </br>

Küldő oldali üzenetek: </br>
- HELO – kezdő üzenet </br>
- MAIL FROM – boríték feladó </br>
- RCPT TO – boríték címzett DATA – e-mail adatok </br>

Protokoll kiegészítések (eg. 8 bit a 7 bit helyett): </br>
- SASL (felhasználó/jelszó) </br>
- PKI (tanúsítványok) Titkosítás </br>
- SSL/TLS </br>

</br>

### E-mail biztonsági lehetőségek
Üzenet hitelesítés: </br>
- S/MIME – megbízható külső felek (CAk) </br>
- PGP – bizalmi háló („kulcsaláíró bulik”) </br>
- Nem terjedtek el – elég – széles körben </br>

Titkosítás: </br>
- Üzenetek: S/MIME és PGP </br>
- Kommunikáció: SMTPS (SSL/TLS) </br>
- Nem oldanak meg mindent! </br>

Küldő fél azonosítása: </br>
- Sender Policy Framework (SPF) </br>
- Domain Keys Identifed Mail (DKIM) </br>

</br>

### Spam, malware
Kéretlen levél (spam): </br>
- Hirdetés </br>
- Phishing levél </br>
- Malware-t terjesztő levelek </br>

Rosszindulatú kód (Malware): </br>
- Vírus, féreg, kémprogram </br>
- Reklámprogram </br>
- Zsarolóprogram </br>

</br>

### Védekezés
SPAM és Malware elleni küzdelem: </br>
- DNS alapú szűrőlisták </br>
- Azonosítás (SPF/DKIM </br>

Szabályrendszer alapú szűrések: </br>
- Antivirus rendszerek (általános célú) Antispam rendszerek (specifikus) </br>
- Adatelemzés (pl. bayes alapú szűrés, képfelismerés) </br>
- Protokoll alapú trükkök (pl. graylisting) </br>

</br>

### További támadások
- Scam-ek, csaló üzenetek (pl.: nigériai levelek) </br>
- Feladó hamisítás </br>
- Rendszerek (MUA, MTA) elleni támadások </br>


</br>


------------------------------------------------------------------------------------------------------------

## EU Általános Adatvédelmi Rendelet (GDPR)
### GDPR jellemzői
- Az EU általános adatvédelmi rendelete </br>
- 2016-ban fogadták el, ekkor is lépett hatályba, de 2018-tól kell alkalmazni </br>
- A személyes adatok védelméhez kapcsolódó jogokat rögzíti </br>
- Adatkezelők, adatfeldolgozók számára jelentős változásokat jelent </br>
- Jogharmonizációt a 2018. évi XIII. és XXXVIII. tv. biztosítja </br>

</br>

### GDPR előzményei
- az 1992. évi LXIII tv (Avtv.) a személyes adatok védelméről és a közérdekű adatok nyilvánosságáról
- a 2011. évi CXII. tv (Infotv) az információs önrendelkezési jogról és az információszabadságról

</br>

### Kapcsolódó fogalmak
- Érintett </br>
- Személyes adat </br>
- Különleges személyes adat </br>
- Adatkezelés </br>
- Adatkezelő </br>
- Adatfeldolgozó </br>

</br>

### Adatkezelés elvei
- jogszerűség, tisztességes eljárás és átláthatóság </br>
- célhoz kötöttség </br>
- adattakarékosság </br>
- pontosság </br>
- korlátozott tárolhatóság </br>
- integritás és bizalmas jelleg </br>

</br>

### Érintettek jogai
- tájékoztatáshoz való jog </br>
- hozzáféréshez való jog </br>
- helyesbítéshez való jog </br>
- törléshez való jog („az elfeledtetéshez való jog”) </br>
- adatkezelés korlátozásához való jog </br>
- adathordozhatósághoz való jog </br>
- tiltakozáshoz való jog </br>
- jogorvoslathoz való jog </br>


</br>

### Adatkezelési tájékoztató
- minden adatkezelő számára kötelező az elkészítése </br>
- megelőzi az adatkezelést </br>
- tartalma: </br>
  - adatkezelő megnevezése </br>
  - adatkezelés célja, kezelt adatok köre </br>
  - adatkezelés jogalapja, kezelésük időtartama </br>
  - érintett kapcsolódó jogai </br>

</br>

### Az adatkezelések biztonsága
Az adatkezelő feladatai: </br>
- szükség esetén anonimizál, titkosít </br>
- folyamatosan biztosítja az adatok bizalmasságát, integritását és rendelkezésre állását </br>
- incidens esetén tájékoztat, helyreállít </br>
- rendszeresen teszteli a fentiek teljesülését </br>

</br>

### Adatvédelmi incidensek kezelése
Az adatkezelő feladatai: </br>
- incidensek nyilvántartása </br>
- illetékes hatóság tájékoztatása (72 órán belül) </br>
- érintettek tájékoztatása, ha szükséges </br>
- incidens kezelése (helyreállítás, megelőzés) </br>

</br>

### Adatkezelések nyilvántartása
- az adatkezelők és adatfeldolgozók számára is kötelező az adatkezelési tevékenységekről </br>
  nyilvántartást vezetni (eltérő tartalommal) </br>
- 250 főnél kevesebb személyt foglalkoztató vállalatoknál nem kell ilyen nyilvántartás, ha az </br>
  adatkezelés az érintettek jogaira nézve valószínűsíthetően nem jár kockázattal, illetve az </br>
  adatkezelés alkalomszerű

</br>

### Adatvédelmi hatásvizsgálat
- magas kockázatú adatkezelések esetén kötelező
- különösen személyes jellemzők automatizált gyűjtése, valamint nyilvános helyek </br>
  nagymértékű, módszeres megfigyelése esetén </br>
- elemei: </br>
  - adatkezelési műveletek, célok bemutatása </br>
  - szükségesség és arányosság vizsgálata </br>
  - kapcsolódó kockázatok vizsgálata </br>
  - kockázatok kezelésének bemutatása </br>

</br>

### Adatvédelmi tisztviselő
kötelező kijelölni: </br>
- közfeladatot ellátó szervek esetében </br>
- szisztematikus, nagymértékű megfigyelés esetén </br>
- különleges adat kezelése esetén </br>

feladatai: </br>
- a GDPR előírásainak és az érintettek jogainak érvényesülésének biztosítása </br>
- az adatkezelést végzők szakmai támogatása </br>
- adatvédelmi incidensek kivizsgálása, jelentése </br>
- a hatósággal való együttműködés </br>

</br>


------------------------------------------------------------------------------------------------------------

## Jelszavak kezelése
### Jelszavakkal kapcsolatos megállapítások
- A különböző vizsgálatok eredményei alapján rossz minőségű jelszavak használatosak </br>
- Oktatás szerepe -> jelszóképzési technikák ismertetése </br>
- Jelszavakra vonatkozó szabályok körültekintő kialakítása </br>
- Üzemeltető állomány felelőssége: </br>
  - Jelszavakkal kapcsolatos operációs rendszer szintű beállításol </br>
  - Kiemelt jogosultságok körültekintő használata </br>
  - Jelszó blacklistek létrehozása </br>
  - A technikai fejlődés figyelembe vétele </br>

</br>

### Jelszótárolás elvi lehetőségei
- <s> Clear text </s> </br>
- <s> Titkosított jelszótárolás </s> </br>
- Jelszóhash </br>

</br>

### Hash algoritmusok fajtái
- Jelszavak hashelésére nem alkalmas függvények: </br>
  - MD5 </br>
  - SHA-1 </br>
  - SHA-256 </br>
  - SHA-512 </br>
  - ... </br>
- Jelszavak hashelésére alkalmas függvények: </br>
  - Bcrypt </br>
  - Scrypt </br>
  - Argon2 </br>
  - PBKDF2 </br>

</br>

### Hash algoritmusok jellemzői
- Egyirányú kódolási rutin
- Adott bemenetből mindig ugyanaz a kimenet képződik </br>
- A kimeneti adat egyértelműen utal a bemeneti adatra… </br>
- …de a kimeneti adatból nem állítható elő a bemeneti adat </br>
- A bemeneti adat legkisebb változása teljesen más kimenetet eredményez </br>

</br>

### Hash értékkészlet jellemzői
![Hash](hash.png) </br>

</br>

### Jelszó hash algoritmusok
- LM (Windows NT 1.0) </br>
- NTLM v1 (Windows NT 3.1) </br>
- NTLM v2 (Windows NT 4.0) </br>
- KRB5TGS (Kerberos) </br>

</br>

### Jelszóképzés szempontjai
- Ideális jelszóhossz
- Hosszú vs. összetett jelszó: melyik preferáljuk? </br>
- Jelszavakra vonatkozó szabályok körültekintő kialakítása </br>
- Jelszócsere: az új jelszó ne hasonlítson az előző jelszóra! </br>
- Divatos jelszóképzési technikák: valóban biztonságos? </br>
  (Budapest12 -> Bud@p$st12) </br>
- Feketelisták jelentősége </br>
- Kódmondaton alapuló jelszavak </br>
  (Afm100%iv) </br>

</br>

### Hosszú vs. összetett jelszó
![Password](password.png) </br>

</br>

### Eltúlzott biztonsági beállítások következményei
![Settings consequences](consequences.png) </br>

</br>

### Biztonsági problémák a gyakorlatban
- Legacy rendszereknél alapértelmezett lehet az NTLM v1 </br>
- A jelszóhash-ek sok esetben megszerezhetők (hálózati forgalom, lokál gép) </br>
- 8 karakteres jelszó egy közepes vga-val akár 350 milliárd (!) hash legenerálható </br>
- … azaz egy 8 karakter hosszúságú, bármilyen bonyolultságú jelszó 5-6 óra alatt törhető, ha megvan a hash </br>

</br>

### Jelszóházirend beállítások
- Enforce password history: >24 </br>
- Maximum password age: >360 </br>
- Minimum password age: 1 day </br>
- Minimum password lenght: >12 </br>
- Password must meet complexity: Enabled (?) </br>
- Store password using reversible encryption: Disabled </br>

</br>

### Password manager programok jellemzői
- Automatikus (biztonságos) jelszóképzés </br>
- Jelszavak titkosított adatbázisban történő tárolása </br>
- Mesterjelszóval történő (akár automatizált) hozzáférés a jelszavakhoz </br>
- Lehet felhős vagy lokális tárolású megvalósítás is </br>

</br>

### Követelmények
- Jelszó adatbázis és mesterjelszó erős algoritmussal történő titkosítása (AES-256, stb.) </br>
- Gyártói támogatás (sérülékenység menedzsment) </br>
- Biztonsági mentés lehetősége </br>
- Kétfaktoros hitelesítés </br>
- Felhős változat esetén: </br>
  - Zero-knowledge architektúra </br>
  - Local only encryption/decryption </br>

</br>

### Ajánlott password manager alkalmazások
- 1Password </br>
- KeePass </br>
- Dashlane </br>
- LastPass </br>
- Syspass </br>
- Különböző PAM megoldások (pl. Thycotic, Thalos) </br>

</br>

------------------------------------------------------------------------------------------------------------

## Közösségi média és felhőalapú adatmegosztó platformok
###


</br>


------------------------------------------------------------------------------------------------------------

## Zero Trust Architecture (ZTA)
### Bevezetés
Egy tipikus vállalat infrastruktúrája egyre bonyolultabbá vált. </br>
Egy vállalat több belső hálózatot, saját helyi infrastruktúrával rendelkező távoli irodát, távoli </br>
és/vagy mobil egyéneket, valamint felhőszolgáltatásokat üzemeltethet. </br>
Ez az összetettség felülmúlta a határvédelem (perimeter) alapú hálózatbiztonság korábbi </br>
módszereit, mivel nincs egyetlen, könnyen azonosítható kerület a vállalat számára </br>
A határvédelem alapú hálózati biztonság sem bizonyult elégségesnek, mivel amint a </br>
támadók áttörik a kerületet, a további oldalirányú mozgás akadálytalan. </br>

A ZT nem egyetlen architektúra, hanem a munkafolyamat, a rendszertervezés és a műveletek </br>
vezérelvei, amelyek segítségével javítható bármilyen alkalmazó biztonsági szintje, helyzete </br>
[FIPS199]. </br>

A ZTA-ra való átállás egy utazás, arról szól, hogy egy szervezet miként értékeli a kockázatokat </br>
küldetése során, és ez nem valósítható meg egyszerűen a technológia cseréjével. Ennek </br>
ellenére sok szervezet vállalati infrastruktúrájában már ma is megtalálhatók a ZTA elemei. </br>

A szervezeteknek törekedniük kell a ZTA bizalmi elvek, a folyamatváltozások és a </br>
technológiai megoldások fokozatos bevezetésére, amelyek felhasználási esetenként védik </br>
adatvagyonukat és üzleti funkcióikat. </br>

A legtöbb vállalati infrastruktúra hibrid zéró bizalom/perem alapú üzemmódban fog </br>
működni, miközben továbbra is befektet az IT-korszerűsítési kezdeményezésekbe és javítja a </br>
szervezeti üzleti folyamatokat. </br>

</br>

### Alapvetések
A ZT egy kiberbiztonsági paradigma, amely az erőforrások védelmére összpontosít, és arra az </br>
előfeltevésre, hogy a bizalmat soha nem adják meg implicit módon, hanem folyamatosan értékelni kell. </br>

A ZT architektúra a vállalati erőforrás- és adatbiztonság teljes körű megközelítése, amely magában </br>
foglalja az identitást (személyes és nem személyi entitások), a hitelesítő adatokat, a hozzáférés- </br>
kezelést, a műveleteket, a végpontokat, a tárhely-környezeteket és az összekapcsoló infrastruktúrát.</br>

Arra kell összpontosítani, hogy az erőforrásokat azokra korlátozzák, akiknek csak a küldetés </br>
végrehajtásához szükséges minimális jogosultságokat (például olvasási, írási, törlési) kell hozzáférniük </br>
és megadniuk. </br>

</br>

### ZTA tételek
1. Minden adatforrás és számítástechnikai szolgáltatás erőforrásnak minősül.</br>
2. A hálózat helyétől függetlenül minden kommunikáció biztonságos. A hálózati hely önmagában nem jelent bizalmat. </br>
3. Az egyes vállalati erőforrásokhoz való hozzáférés munkamenetenkénti alapon történik. </br>
4. Az erőforrásokhoz való hozzáférést dinamikus házirend határozza meg – beleértve az ügyfélazonosság, az alkalmazás/szolgáltatás és a kérelmező eszköz
   megfigyelhető állapotát –, és más viselkedési és környezeti jellemzőket is tartalmazhat. </br>
5. A vállalat felügyeli és méri az összes tulajdonában lévő és kapcsolódó eszköz integritását és biztonsági helyzetét. </br>
6. Minden erőforrás-hitelesítés és engedélyezés dinamikus, és a hozzáférés engedélyezése előtt szigorúan betartandó. </br>
7. A vállalkozás a lehető legtöbb információt összegyűjti az eszközök aktuális állapotáról, a
hálózati infrastruktúráról és a kommunikációról, és ezt felhasználja biztonsági helyzetének javítására. </br>

</br>

### ZTA Hálózati nézete
1. A teljes vállalati magánhálózat nem tekinthető implicit bizalmi zónának. </br>
2. Előfordulhat, hogy a hálózaton lévő eszközök nem lehetnek a vállalat tulajdonában és nem konfigurálhatók. </br>
3. Egyetlen erőforrás sem eleve megbízható. </br>
4. Nem minden vállalati erőforrás található a vállalati infrastruktúrán. </br>
5.  A távoli vállalati alanyok és eszközök nem bízhatnak teljes mértékben a helyi hálózati kapcsolatukban. </br>
6.  A vállalati és nem vállalati infrastruktúra között mozgó eszközöknek és munkafolyamatoknak következetes biztonsági politikával és helyzettel kell rendelkezniük. </br>

</br>

### Házirend motor (PE)
Ez a komponens felelős a végső döntésért, hogy hozzáférést biztosítanak-e egy adott téma erőforrásához. </br>

A PE vállalati szabályzatot, valamint külső forrásokból (pl. CDM-rendszerekből, alább </br>
ismertetett fenyegetés-felderítő szolgáltatásokból) származó bemenetet használ egy </br>
megbízhatósági algoritmus bemeneteként az erőforráshoz való hozzáférés megadására, </br>
megtagadására vagy visszavonására. </br>

A PE párosítva van a házirend-rendszergazda összetevővel. </br>

A házirend-motor hozza meg és naplózza a döntést (jóváhagyva vagy elutasítva), </br>
a házirendadminisztrátor pedig végrehajtja a döntést. </br>

</br>

### Házirend-adminisztrátor (PA)
Ez az összetevő felelős az alany és az erőforrás közötti kommunikációs útvonal </br>
létrehozásáért és/vagy leállításáért (a megfelelő PEP-ekhez küldött parancsokon keresztül). </br>

Ez létrehozna minden munkamenet-specifikus hitelesítési és hitelesítési tokent vagy </br>
hitelesítő adatot, amelyet az ügyfél a vállalati erőforrás eléréséhez használ. </br>

Szorosan kötődik a PE-hez, és annak döntésére támaszkodik, hogy végül engedélyezi vagy </br>
megtagadja a munkamenetet. </br>

</br>

### Irányelv-végrehajtási pont (PEP)
Ez a rendszer felelős az alany és a vállalati erőforrás közötti kapcsolatok engedélyezéséért, </br>
figyeléséért és esetlegesen megszüntetéséért. </br>

A PEP kommunikál a PA-val a kérelmek továbbítása és/vagy az irányelv-frissítések fogadása érdekében.</br>

Ez egyetlen logikai komponens a ZTA-ban, de két különböző összetevőre bontható: a kliens </br>
(pl. ügynök a laptopon) és az erőforrás oldal (pl. a hozzáférést vezérlő erőforrás előtti átjáró </br>
komponens) vagy egyetlen portálkomponens, amely működik. mint a kommunikációs utak kapuőre. </br>

A PEP-n túl található a vállalati erőforrást kiszolgáló bizalmi zóna. </br>

</br>

### Folyamatos diagnosztikai és kockázatcsökkentő (CDM) rendszer
... </br>
... </br>


</br>

### ...
... </br>
... </br>


</br>

------------------------------------------------------------------------------------------------------------

## Digitális identitás
### Jogosultság kezelési módszerek, megoldások
- Access Control List – ACL </br>
- Discretionary Access Control </br>
- Mandatory Access Control </br>
- Role Based Access Control  </br>
- Attribute Based Access Control </br>
- Bell-LaPadula modell </br>
- Clark-Wilson modell </br>

</br>

### ACL
A számítógépes biztonságban a hozzáférés-vezérlési lista (ACL) a rendszererőforráshoz </br>
(objektumhoz) társított engedélyek listája. </br>

Az ACL meghatározza, hogy mely felhasználók vagy rendszerfolyamatok kapnak hozzáférést </br>
az objektumokhoz, valamint hogy milyen műveletek engedélyezettek az adott objektumokon. </br>

A tipikus ACL minden bejegyzése meghatároz egy tárgyat és egy műveletet. Például, ha egy </br>
fájlobjektum rendelkezik ACL-lel, amely tartalmazza </br>

</br>

### DAC
A számítógépes biztonságban a diszkrecionális hozzáférés-szabályozás (DAC) egyfajta </br>
hozzáférés-szabályozás, amelyet a Trusted Computer System Evaluation Criteria (TCSEC) </br>
határoz meg, amely eszközként korlátozza az objektumokhoz való hozzáférést az alanyok </br>
és/vagy csoportok identitása alapján tartoznak. </br>

Az ellenőrzések diszkrecionálisak abban az értelemben, hogy egy bizonyos hozzáférési </br>
engedéllyel rendelkező alany képes ezt az engedélyt (talán közvetetten) átadni bármely más </br>
alanynak (hacsak nem korlátozza a kötelező hozzáférés-szabályozás). </br>

</br>

### MAC
A számítógépes biztonságban a kötelező hozzáférés-szabályozás (MAC) a hozzáférésszabályozás egy olyan típusát jelenti, </br>
amellyel az operációs rendszer vagy az adatbázis korlátozza az alany vagy a kezdeményező azon képességét, hogy hozzáférjen </br>
egy objektumhoz vagy célhoz, vagy általában valamilyen műveletet hajtson végre azokon. </br>

Az operációs rendszerek esetében az alany általában egy folyamat vagy szál; Az objektumok olyan konstrukciók, mint a fájlok, </br>
könyvtárak, TCP/UDP portok, megosztott memória szegmensek, IO-eszközök stb. </br>

Az alanyok és objektumok mindegyike rendelkezik biztonsági attribútumokkal. </br>

</br>

### RBAC
A számítógépes rendszerek biztonsága, a szerepkör-alapú hozzáférés-vezérlés (RBAC) vagy a </br>
szerepalapú biztonság egy olyan megközelítés, amely a rendszerhez való hozzáférést az </br>
engedélyezett felhasználókra korlátozza. </br>

Ez egy megközelítés a kötelező hozzáférés-vezérlés (MAC) vagy a diszkrecionális hozzáférésvezérlés (DAC) megvalósítására. </br>

A szerepkör alapú hozzáférés-vezérlés egy házirend-semleges hozzáférés-vezérlési </br>
mechanizmus, amely szerepkörök és jogosultságok köré épül. </br>

</br>

### ABAC
Az attribútum-alapú hozzáférés-vezérlés (ABAC), más néven IAM szabályzatalapú hozzáférésvezérlés, </br>
egy hozzáférés-vezérlési paradigmát határoz meg, amelyben az alany jogosultságát </br>
egy műveletkészlet végrehajtására az alanyhoz, objektumhoz, kért műveletekhez társított </br>
attribútumok kiértékelése határozza meg, és bizonyos esetekben a környezeti jellemzők is. </br>

Az ABAC egy olyan hozzáférés-vezérlési házirendek megvalósítási módja, amely </br>
nagymértékben adaptálható, és az attribútumok széles skálájával testreszabható, így </br>
alkalmas elosztott vagy gyorsan változó környezetben való használatra. </br>

</br>

### Bell-Lapadula modell



</br>

###



</br>

###



</br>

###



</br>

------------------------------------------------------------------------------------------------------------

##




</br>

###



</br>

###



</br>

###



</br>

###



</br>
