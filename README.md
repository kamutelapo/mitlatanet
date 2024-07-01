![Mit árul el rólunk az internet](kepek/mit_arul_el_az_internet.png)

- [Mit árul el rólunk az internet?](#mit-árul-el-rólunk-az-internet)
  - [Mit lát a szolgáltató / az internetes protokoll sebezhetőségei](#mit-lát-a-szolgáltató--az-internetes-protokoll-sebezhetőségei)
    - [Az IP címről](#az-ip-címről)
    - [A titkosítatlan névfeloldás problémái (DNS)](#a-titkosítatlan-névfeloldás-problémái-dns)
    - [Megoldások a névfeloldás eltakarására: DNS-over-HTTPS, DNS-over-TLS](#megoldások-a-névfeloldás-eltakarására-dns-over-https-dns-over-tls)
    - [A titkosított TLS Client Hello üzenetek sebezhetősége](#a-titkosított-tls-client-hello-üzenetek-sebezhetősége)
    - [Megoldás a Client Hello üzenet eltakarására (ECH)](#megoldás-a-client-hello-üzenet-eltakarására-ech)
    - [Konklúzió](#konklúzió)
  - [Mit lát a weboldal, amihez kapcsolódunk?](#mit-lát-a-weboldal-amihez-kapcsolódunk)
    - [Létezik egy oldal, amely megmutatja, hogy mit lát belőlünk](#létezik-egy-oldal-amely-megmutatja-hogy-mit-lát-belőlünk)
    - [Helymeghatározás IP címmel](#helymeghatározás-ip-címmel)
    - [Digitális ujjlenyomatok](#digitális-ujjlenyomatok)
      - [A HTTPS kérés értékes mezői](#a-https-kérés-értékes-mezői)
      - [Javascript (futtatható kód) felhasználása a számítógépünk, telefonunk képességeinek felderítésére](#javascript-futtatható-kód-felhasználása-a-számítógépünk-telefonunk-képességeinek-felderítésére)
  - [Információcsere internetes weblapok között](#információcsere-internetes-weblapok-között)
    - [A reklámok, nyomkövetők működése](#a-reklámok-nyomkövetők-működése)
    - [Süti harmadik félnek](#süti-harmadik-félnek)
    - [Konklúzió](#konklúzió-1)
- [Megoldások az információ áramlás korlátozására](#megoldások-az-információ-áramlás-korlátozására)
  - [Reklámok blokkolása](#reklámok-blokkolása)
  - [A digitális ujjlenyomat meghamisítása](#a-digitális-ujjlenyomat-meghamisítása)
  - [Megakadályozni sütik harmadik félnek történő átadását](#megakadályozni-sütik-harmadik-félnek-történő-átadását)
- [Amikor teljes sötétség és senki sem ismer senkit](#amikor-teljes-sötétség-és-senki-sem-ismer-senkit)
  - [A TOR hálózat (dark web)](#a-tor-hálózat-dark-web)
    - [A hálózat működése](#a-hálózat-működése)
    - [Legális-e a használata?](#legális-e-a-használata)
    - [A TOR böngésző telepítésének menete](#a-tor-böngésző-telepítésének-menete)
    - [A nyelv átállítása](#a-nyelv-átállítása)
    - [Szkriptek (futtatható kód) tiltása](#szkriptek-futtatható-kód-tiltása)
    - [Ennyit lát a túloldal](#ennyit-lát-a-túloldal)
    - [Mi történik a TLS Client Hello-val?](#mi-történik-a-tls-client-hello-val)
    - [Az onion címek](#az-onion-címek)
- [Hogyan viszonyulnak az egyes szolgáltatók a névtelenséghez?](#hogyan-viszonyulnak-az-egyes-szolgáltatók-a-névtelenséghez)
  - [www.google.com](#wwwgooglecom)
  - [www.duckduckgo.com](#wwwduckduckgocom)
  - [www.brave.com](#wwwbravecom)
  - [www.facebook.com](#wwwfacebookcom)
  - [www.cloudflare.com](#wwwcloudflarecom)
  - [Hogyan használhatunk névtelenül szkripteket is?](#hogyan-használhatunk-névtelenül-szkripteket-is)
  - [Konklúzió](#konklúzió-2)


# Mit árul el rólunk az internet?

Felvetődhet a kérdés, hogy internetezés közben valaki belehallgat-e a titkosított adatfolyamokba, hozzájuthat-e értékes információkhoz rólunk. A dokumentum azt elemzi ki, hogy ez elvi szinten lehetséges-e. Hogy a valóságban mi történik, azt nem tudom.

Az elemzéshez a wireshark hálózati analizátort használtam.


## Mit lát a szolgáltató / az internetes protokoll sebezhetőségei

### Az IP címről

Amikor az internetre csatlakozunk, a szolgáltató ad nekünk egy címet, ami egyértelműen azonosít minket. Az előfizetésünk alapján követhetőek vagyunk, tehát ha támadást indítunk, név és cím szerint azonosíthatóak leszünk. Mindez nem probléma, a kérdés, hogy mennyire lát a szolgáltató bele az internetes tevékenységünkbe?

A szolgáltatótól kapott IP cím kinézete:
* IPv4 cím: 104.26.15.72 (négy számból áll)
* IPv6 cím: 2606:4700:20::681a:f48 (hexadecimális számjegyekből áll)

Az IP címünk közelítő információt is elmond a lakhelyünkről bárkinek.

[https://browserleaks.com/ip](https://browserleaks.com/ip)

![IP cím](kepek/ip_cim.png)


### A titkosítatlan névfeloldás problémái (DNS)

![DNS probléma](kepek/dns_problema.png)

A névfeloldás azt jelenti, hogy amikor egy weboldalt megkeresünk (pl. www.github.org), akkor a névből IP címet állít elő egy távoli szolgáltatás (140.82.121.3) és az internetes csomagjaink erre a címre fognak elmenni. A kommunikáció titkosítatlan formában történik. Aki belehallgat a hálózati beszélgetésünkbe (lásd kép), tudni fogja, hogy milyen weblapokat látogatunk meg.

Mivel az adatfolyam titkosítatlan, ezért szolgáltató képes hamis választ is visszaadni, vagy másik kiszolgálóhoz átirányítani.

Amikor az állam letiltja a tiltotttartalom.com weboldalt, akkor ezzel az eszközzel él. A csomagjaink nem fognak eljutni az eredeti weblaphoz, hanem egy másik oldal jelenik meg helyette, amelyik értesít, hogy a tartalom tiltásra került.


### Megoldások a névfeloldás eltakarására: DNS-over-HTTPS, DNS-over-TLS

A szakemberek észlelték, hogy a DNS csomagokkal komoly bajok lehetnek, bárki belematathat, átirányíthat, letilthat lekéréseket, ezért biztonságosabb, ha azok is titkosított csatornán haladnak.
Megjelentek megoldások a DNS forgalom eltakarására publikus DNS névfeloldó rendszerekkel. Ezek a szolgáltatók úgy termelnek pénzt, hogy elemzik a lekéréseket, összképet kapva az internetes szokásainkról.
Elég nekik azt tudni, hogy X millió embert mi érdekel, nincs szükségük a személyes adatainkra. Némelyik szolgáltató pornószűrést, anonimitást és egyéb extra szolgáltatást is biztosít, hogy nekik szolgáltassunk az adatainkat.

A nagyobb publikus DNS szolgáltatók közül a következőket említeném:
* Cloudflare (1.1.1.1, a leggyorsabb, teljes névtelenséget ígér)
* Google (8.8.8.8)

Firefox alatt így lehet a DNS-over-HTTPS-t bekapcsolni Cloudflare alá (Adatvédelem és biztonság almenü).

![DNS-over-HTTPS](kepek/dns-over-https.png)

### A titkosított TLS Client Hello üzenetek sebezhetősége

A DNS-over-TLS vagy a DNS-over-HTTPS bekapcsolásával a szolgáltató többé nem fogja látni a DNS üzeneteinkből, hogy milyen weboldalakat olvasunk. Ezek a megoldások megvédik a DNS forgalmat.

Viszont ugyanez az adat más forrásból is beszerezhető a TLS internetes protokoll egy sebezhetősége miatt (Client Hello üzenet). Amint a weboldalhoz kapcsolódunk, teljesen láthatóvá válik bárki számára, hogy kivel beszélünk. Egyetlen komoly előnye van a titkosított DNS üzenetnek, hogy nem lehet meghamisítani. A lehallgatástól nem véd meg.

Képen a lehallgatott kommunikáció:

TBD

### Megoldás a Client Hello üzenet eltakarására (ECH)

Természetesen a szakemberek észlelték a problémát, hogy nem előnyös, ha bárki megtudhatja, hogy milyen oldalakkal beszélgetünk, ezért megjelent az ESNI, majd később ECH megoldás. Az ECH titkosítja a Client Hello üzenetnek a problémás részét, kitakarva belőle minden értékes adatot. Az ECH opcionális, jelenleg nagyon kevés weboldal támogatja. Firefox alatt a DNS-over-HTTPS ECH-t is használ, ha lehet, de az internetes oldalak 95%-a még nem támogatja. Reméljük ez megváltozik a jövőben.

### Konklúzió

A legtöbb kapcsolat HTTPS alatt fut és titkosítva van, a szolgáltató nem látja, hogy milyen beszélgetést folytatunk rajta. A DNS/TLS protokollok biztonsági rései miatt viszont elvileg megláthatja a weblapok nevét, amit olvasunk. Azt is lemérheti, hogy mennyit időt töltünk ezeken az oldalakon, ebből az információból pedig egészen pontosan meg lehet tippelni valaki politikai hovatartozását, szokásait, érdeklődési körét névreszólóan. Elvileg tehát nem lehetetlen megoldani. Bízunk benne, hogy nem teszik meg. Általános megoldás jelenleg nincs a probléma kivédésére, az ECH bizonyos lapokat eltakarhat, de a többségük titkosítatlanul fog megérkezni.

## Mit lát a weboldal, amihez kapcsolódunk?

### Létezik egy oldal, amely megmutatja, hogy mit lát belőlünk

Ha kíváncsiak vagyunk, hogy mit lát belőlünk a túloldal, érdemes megnyitni a [https://browserleaks.com/](https://browserleaks.com/) honlapot. Ez a weblap megmondja, hogy milyen információk jutnak el tőlünk hozzá.

### Helymeghatározás IP címmel

TBD

### Digitális ujjlenyomatok

TBD

#### A HTTPS kérés értékes mezői

TBD

#### Javascript (futtatható kód) felhasználása a számítógépünk, telefonunk képességeinek felderítésére

TBD

## Információcsere internetes weblapok között

TBD

### A reklámok, nyomkövetők működése

TBD

### Süti harmadik félnek

TBD

### Konklúzió

TBD

# Megoldások az információ áramlás korlátozására

TBD

## Reklámok blokkolása

TBD

## A digitális ujjlenyomat meghamisítása

TBD

## Megakadályozni sütik harmadik félnek történő átadását

TBD

# Amikor teljes sötétség és senki sem ismer senkit

TBD

## A TOR hálózat (dark web)

TBD

### A hálózat működése

TBD

### Legális-e a használata?

TBD

### A TOR böngésző telepítésének menete

TBD

### A nyelv átállítása

TBD

### Szkriptek (futtatható kód) tiltása

TBD

### Ennyit lát a túloldal

TBD

### Mi történik a TLS Client Hello-val?

TBD

### Az onion címek

TBD

# Hogyan viszonyulnak az egyes szolgáltatók a névtelenséghez?

TBD

## www.google.com

TBD

## www.duckduckgo.com

TBD

## www.brave.com

TBD

## www.facebook.com

TBD

## www.cloudflare.com

TBD

## Hogyan használhatunk névtelenül szkripteket is?

TBD

## Konklúzió

TBD
