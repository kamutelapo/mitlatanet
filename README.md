![Mit árul el rólunk az internet](kepek/mit_arul_el_az_internet.png)

- [Mit árul el rólunk az internet?](#mit-árul-el-rólunk-az-internet)
  - [Mit lát a szolgáltató / az internetes protokoll sebezhetőségei](#mit-lát-a-szolgáltató--az-internetes-protokoll-sebezhetőségei)
    - [Az IP címről](#az-ip-címről)
    - [A titkosítás nélküli névfeloldás problémái (DNS)](#a-titkosítás-nélküli-névfeloldás-problémái-dns)
    - [Megoldások a névfeloldás eltakarására: DNS-over-HTTPS, DNS-over-TLS](#megoldások-a-névfeloldás-eltakarására-dns-over-https-dns-over-tls)
    - [A titkosított TLS Client Hello üzenetének sebezhetősége](#a-titkosított-tls-client-hello-üzenetének-sebezhetősége)
    - [Megoldás a Client Hello üzenet eltakarására (ECH)](#megoldás-a-client-hello-üzenet-eltakarására-ech)
    - [Konklúzió](#konklúzió)
  - [Mit lát a weboldal, amihez kapcsolódunk?](#mit-lát-a-weboldal-amihez-kapcsolódunk)
    - [Létezik egy oldal, amely megmutatja, hogy mit lát belőlünk](#létezik-egy-oldal-amely-megmutatja-hogy-mit-lát-belőlünk)
    - [Helymeghatározás IP címmel](#helymeghatározás-ip-címmel)
    - [Digitális ujjlenyomatok](#digitális-ujjlenyomatok)
      - [A HTTPS kérés értékes mezői](#a-https-kérés-értékes-mezői)
      - [Javascript (futtatható kód) felhasználása a gép képességeinek felderítésére](#javascript-futtatható-kód-felhasználása-a-gép-képességeinek-felderítésére)
    - [Információcsere weblapok között](#információcsere-weblapok-között)
    - [A reklámok, nyomkövetők működése](#a-reklámok-nyomkövetők-működése)
    - [Süti harmadik félnek](#süti-harmadik-félnek)
    - [Konklúzió](#konklúzió-1)
- [Megoldások az információ áramlás korlátozására](#megoldások-az-információ-áramlás-korlátozására)
  - [Reklámok blokkolása](#reklámok-blokkolása)
  - [Ujjlenyomat meghamisítása](#ujjlenyomat-meghamisítása)
  - [Megakadályozni sütik harmadik félnek történő átadását](#megakadályozni-sütik-harmadik-félnek-történő-átadását)
- [Amikor teljes sötétség és senki sem ismer senkit](#amikor-teljes-sötétség-és-senki-sem-ismer-senkit)
  - [A TOR hálózat (dark web)](#a-tor-hálózat-dark-web)
    - [A hálózat működése](#a-hálózat-működése)
    - [Legális-e a használata?](#legális-e-a-használata)
    - [A telepítés menete](#a-telepítés-menete)
    - [A nyelv átállítása](#a-nyelv-átállítása)
    - [Szkriptek (futtatható kód) tiltása](#szkriptek-futtatható-kód-tiltása)
    - [Kipróbálhatjuk, hogy mennyit lát a túloldal](#kipróbálhatjuk-hogy-mennyit-lát-a-túloldal)
    - [Vajon a TLS Client Hello lát-e minket?](#vajon-a-tls-client-hello-lát-e-minket)
    - [Az onion címek](#az-onion-címek)
- [Kik vannak velünk a teljes névtelenségben?](#kik-vannak-velünk-a-teljes-névtelenségben)
  - [www.google.com](#wwwgooglecom)
  - [www.duckduckgo.com](#wwwduckduckgocom)
  - [www.brave.com](#wwwbravecom)
  - [www.facebook.com](#wwwfacebookcom)
  - [www.cloudflare.com](#wwwcloudflarecom)
  - [Hogyan használhatunk névtelenül szkripteket is?](#hogyan-használhatunk-névtelenül-szkripteket-is)
  - [Konklúzió](#konklúzió-2)


# Mit árul el rólunk az internet?

Érdekelt, hogy internetezés közben ha valaki belehallgat a titkosított adatfolyamokba hozzájuthat-e értékes információkhoz. A dokumentum azt elemzi ki, hogy lehetséges-e belehallgatni és abból használható információkat levonni. Az elemzés elvi szintű, hogy a valóságban mi történik, azt nem tudom.

Az elemzéshez a wireshark hálózati analizátort használtam.


## Mit lát a szolgáltató / az internetes protokoll sebezhetőségei

### Az IP címről

TBD

### A titkosítás nélküli névfeloldás problémái (DNS)

TBD

### Megoldások a névfeloldás eltakarására: DNS-over-HTTPS, DNS-over-TLS

TBD

### A titkosított TLS Client Hello üzenetének sebezhetősége

TBD

### Megoldás a Client Hello üzenet eltakarására (ECH)

TBD

### Konklúzió

A legtöbb kapcsolat HTTPS alatt fut, ez titkosítva van, a szolgáltató nem látja, hogy milyen beszélgetést folytatunk rajta. A DNS/TLS protokollok biztonsági rései miatt viszont megláthatja a weblapok nevét, amit olvasunk. Azt is lemérheti, hogy mennyit időt töltünk ezeken az oldalakon, ebből az információból pedig egészen pontosan meg lehet tippelni valaki politikai hovatartozását, szokásait, érdeklődési körét névreszólóan. Általános megoldás nincs a probléma kivédésére, az ECH bizonyos lapokat eltakarhat, de a többségüket jelenleg nem.

## Mit lát a weboldal, amihez kapcsolódunk?

### Létezik egy oldal, amely megmutatja, hogy mit lát belőlünk

TBD

### Helymeghatározás IP címmel

TBD

### Digitális ujjlenyomatok

TBD

#### A HTTPS kérés értékes mezői

TBD

#### Javascript (futtatható kód) felhasználása a gép képességeinek felderítésére

TBD

### Információcsere weblapok között

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

## Ujjlenyomat meghamisítása

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

### A telepítés menete

TBD

### A nyelv átállítása

TBD

### Szkriptek (futtatható kód) tiltása

TBD

### Kipróbálhatjuk, hogy mennyit lát a túloldal

TBD

### Vajon a TLS Client Hello lát-e minket?

TBD

### Az onion címek

TBD

# Kik vannak velünk a teljes névtelenségben?

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
