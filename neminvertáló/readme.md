



# MÉRÉSI JEGYZŐKÖNYV

**Név:** Spisák Roland Konstantin   
**Helyszín:** Miskolci SZC Kandó Kálmán Informatikai Technikum, V3 labor   
**Dátum:** 2026. január 29.   
**Tárgy:** Műveleti erősítő vizsgálata – Invertáló alapkapcsolás   

---

## 1. A mérés célja
Műveleti erősítővel felépített invertáló (fázisfordító) erősítő alapkapcsolás vizsgálata, a feszültségerősítés elméleti számítása, valamint a szimulációs/mért eredmények összehasonlítása NI ELVIS II+ környezetben.

## 2. Felhasznált eszközök és szoftverek
* NI ELVIS II+ mérőállomás (vagy annak szimulációs környezete)
* NI ELVISmx Instrument Launcher (Függvénygenerátor, Oszcilloszkóp)
* Számítógép, áramkörszimulációs szoftver (pl. Multisim)

## 3. Kapcsolási elrendezés és paraméterek
A méréshez használt kapcsolás egy invertáló erősítő.   
<img width="1181" height="684" alt="image" src="https://github.com/user-attachments/assets/12e60b71-be09-4c7f-a0ba-c69827f3e69a" />  

**Felhasznált alkatrészek:**
* **R1 (Bemeneti ellenállás):** $11.8\,k\Omega$
* **R2 (Visszacsatoló ellenállás):** $99.9\,k\Omega$
* **R3 (Kompenzáló ellenállás a nem invertáló lábon):** $11.9\,k\Omega$

**Bemeneti jel (Függvénygenerátor beállításai):**
* Jelalak: Szinusz
* Frekvencia: $100\,Hz$
* Amplitúdó: $1.00\,V_{pp}$ (csúcstól-csúcsig)
* DC eltolás (Offset): $0.00\,V$
   
<img width="522" height="591" alt="image" src="https://github.com/user-attachments/assets/0ce7b51d-86fc-4405-bc73-e543752f830d" />   

## 4. Elméleti számítások
Az invertáló erősítő feszültségerősítését ($A_u$) az ellenállások aránya határozza meg:

$$A_u = -\frac{R_2}{R_1}$$

Behelyettesítve a kapcsolási rajz értékeit:

$$A_u = -\frac{99.9\,k\Omega}{11.8\,k\Omega} \approx -8.466$$

Ez azt jelenti, hogy a kimeneti jel elméletileg 8,466-szorosa lesz a bemenetinek, és a fázisa 180°-kal elfordul (invertálódik).

## 5. Mérési eredmények

### 5.1 Oszcilloszkóp mérések
A mérés során az NI ELVISmx Oszcilloszkóp moduljával vizsgáltuk a jeleket.

* **CH0 (Zöld - Bemenet):**
    * $V_{p-p}$ (Csúcstól-csúcsig feszültség): $999.56\,mV \approx 1.00\,V$
    * Frekvencia: $100.001\,Hz$
    * RMS feszültség: $352.71\,mV$

* **CH1 (Kék - Kimenet):**
    * $V_{p-p}$ (Csúcstól-csúcsig feszültség): $8.488\,V$
    * Frekvencia: $100.000\,Hz$
    * RMS feszültség: $2.996\,V$

### 5.2 Erősítés meghatározása a mért adatokból
A mért erősítés ($A_{mért}$) a kimeneti és bemeneti csúcsfeszültségek hányadosa:

$$A_{mért} = \frac{V_{out(pp)}}{V_{in(pp)}} = \frac{8.488\,V}{0.99956\,V} \approx 8.49$$   

<img width="1078" height="747" alt="image" src="https://github.com/user-attachments/assets/61236906-b3be-4dc4-ac87-0f4253030d66" />    

(A fázisfordítás az oszcilloszkóp ábráján látható: amikor a zöld jel pozitív, a kék jel negatív tartományban van).

## 6. Összehasonlító táblázat

| Paraméter | Elméleti / Számított érték | Mért érték (Szimuláció) | Eltérés |
| :--- | :---: | :---: | :---: |
| Erősítés ($A_u$) | -8.466 | -8.49 (magnitúdó) | < 0.3% |
| Kimeneti feszültség (DC teszt alapján) | -8.472 V | -8.472 V | 0% |
| Kimeneti feszültség (AC csúcs) | 8.466 Vpp | 8.488 Vpp | ~0.26% |

## 7. Következtetés
A mérés során sikeresen összeállítottuk és vizsgáltuk az invertáló erősítő kapcsolást. A kapcsolási rajzon végzett DC analízis ($-8.472\,V$) és az oszcilloszkóppal mért AC jelek ($8.488\,V_{pp}$) is alátámasztják az elméleti számításokat.

Az oszcilloszkóp ábráján tisztán látható a műveleti erősítő alapvető tulajdonsága ebben a kapcsolásban: a bemeneti (zöld) és a kimeneti (kék) jel között 180°-os fáziseltolódás van, az amplitúdó pedig az ellenállások arányának megfelelően növekedett. A mért értékek a tűréshatáron belül megegyeznek a számított értékekkel.

---
**Aláírás:**
Spisák Roland Konstantin
