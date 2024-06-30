- [Mennyit lát belőlünk az internet?](#mennyit-lát-belőlünk-az-internet)
  - [Mit lát a szolgáltató - az internetes protokoll sebezhetőségei](#mit-lát-a-szolgáltató---az-internetes-protokoll-sebezhetőségei)
    - [Az IP címről](#az-ip-címről)
    - [A névfeloldás problémái (DNS)](#a-névfeloldás-problémái-dns)
    - [Megoldások a névfeloldás titkosítására: DNS-over-HTTP, DNS-over-TLS](#megoldások-a-névfeloldás-titkosítására-dns-over-http-dns-over-tls)
    - [A titkosított TLS Client Hello üzenet sebezhetősége](#a-titkosított-tls-client-hello-üzenet-sebezhetősége)
    - [Megoldás a Client Hello üzenet javítására (ECH)](#megoldás-a-client-hello-üzenet-javítására-ech)
    - [Konklúzió](#konklúzió)
  - [Mit lát a másik oldal (a weblap, amit lekérek)?](#mit-lát-a-másik-oldal-a-weblap-amit-lekérek)
    - [Egy weblap, amely felfedi, hogy milyen információt lát tőlünk](#egy-weblap-amely-felfedi-hogy-milyen-információt-lát-tőlünk)
    - [Helymeghatározás IP címmel](#helymeghatározás-ip-címmel)
    - [Digitális ujjlenyomatok](#digitális-ujjlenyomatok)
      - [A HTTPS kérés értékes mezői](#a-https-kérés-értékes-mezői)
      - [Javascript (futtatható kód) felhasználása a gép képességeinek felderítésére](#javascript-futtatható-kód-felhasználása-a-gép-képességeinek-felderítésére)
  - [Információcsere weblapok között](#információcsere-weblapok-között)
    - [A reklámok, nyomkövetők működése](#a-reklámok-nyomkövetők-működése)
    - [Süti harmadik félnek](#süti-harmadik-félnek)
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
  - [Konklúzió](#konklúzió-1)

# Mennyit lát belőlünk az internet?

Érdekelt, hogy internetezés közben ha valaki belehallgat a titkosított adatfolyamokba hozzájuthat-e értékes információkhoz. A dokumentum azt elemzi ki, hogy lehetséges-e belehallgatni és abból használható információkat levonni. Az elemzés elvi szintű, hogy a valóságban mi történik, azt nem tudom.

Az elemzéshez a wireshark hálózati analizátort használtam.

TBD: kép


## Mit lát a szolgáltató - az internetes protokoll sebezhetőségei

### Az IP címről

TBD

### A névfeloldás problémái (DNS)

TBD

### Megoldások a névfeloldás titkosítására: DNS-over-HTTP, DNS-over-TLS

TBD

### A titkosított TLS Client Hello üzenet sebezhetősége

TBD

### Megoldás a Client Hello üzenet javítására (ECH)

TBD

### Konklúzió

TBD

## Mit lát a másik oldal (a weblap, amit lekérek)?

### Egy weblap, amely felfedi, hogy milyen információt lát tőlünk

TBD

### Helymeghatározás IP címmel

TBD

### Digitális ujjlenyomatok

TBD

#### A HTTPS kérés értékes mezői

TBD

#### Javascript (futtatható kód) felhasználása a gép képességeinek felderítésére

TBD

## Információcsere weblapok között

TBD

### A reklámok, nyomkövetők működése

TBD

### Süti harmadik félnek

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
