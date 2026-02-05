

# MÉRÉSI JEGYZŐKÖNYV

**Intézmény:** Miskolc SC Kandó Kálmán Technikum   
**Helyszín:** V3 terem    
**Dátum:** 2026. 02. 05.   

---

**Mérést végezte:** Spisák Roland Konstantin   
**Mérés tárgya:** Műveleti erősítős sávszűrő áramkör vizsgálata (Bode-analízis)   

---

## 1. A mérés célja
Egy aktív sávszűrő áramkör frekvenciamenetének felvétele, a rezonanciafrekvencia ($f_0$), az erősítés ($A$) és a fáziseltolódás vizsgálata NI ELVISmx műszerrel.

## 2. Kapcsolási elrendezés
A méréshez összeállított áramkör egy invertáló bemenetű aktív szűrő, amely az alábbi alkatrészekből épül fel:

* **Aktív elem:** Műveleti erősítő (Op-Amp)
* **Passzív elemek:**
    * $R_{bemeneti} = 220\,\Omega$
    * $R_{visszacsatoló} = 10\,\text{k}\Omega$
    * $R_{kompenzáló} = 220\,\Omega$ (a nem invertáló bemeneten)
    * $C_{csatoló} = 100\,\text{nF}$ ($2\text{ db}$)

**Az összeállított áramkör kapcsolási rajza:**

<img width="915" height="588" alt="image" src="https://github.com/user-attachments/assets/2b4ca620-f9ea-40bb-88b2-1d294a861034" />   

## 3. Alkalmazott mérőeszközök és beállítások
* **Hardver:** NI myDAQ
* **Szoftver:** NI ELVISmx - Bode Analyzer
* **Frekvenciatartomány:** $200\,\text{Hz}$ – $20\,\text{kHz}$
* **Jelszint:** $0,10\,\text{V}$ (Peak)
* **Lépésköz:** 50 lépés/dekád

## 4. Mérési eredmények
A Bode-analizátorral felvettük az áramkör átviteli karakterisztikáját. A felső grafikon az erősítést (Gain), az alsó a fázist (Phase) mutatja.

**A kapott jelleggörbék:**

<img width="925" height="740" alt="image" src="https://github.com/user-attachments/assets/ad813c1b-3e6d-4c94-bfb7-b7588568ee65" />   

### Eredmények kiértékelése (Kurzor adatok alapján)

A grafikonon a kurzort a rezonanciacsúcsra (a legnagyobb erősítés helyére) állítva az alábbi értékeket kaptuk:

| Fizikai mennyiség | Mért érték |
| :--- | :--- |
| **Rezonanciafrekvencia ($f_0$)** | **$1741,93\,\text{Hz}$** |
| **Erősítés ($A_{dB}$)** | **$24,02\,\text{dB}$** |
| **Erősítés (szorzóként)** | **$15,89\times$** |
| **Fáziseltolódás** | **$-176,21^\circ$** |

## 5. Összegzés
A mérés során sikeresen vizsgáltuk az aktív sávszűrőt.
1.  A kapcsolás **sávszűrőként** viselkedik: alacsony és magas frekvencián vág, $1,74\,\text{kHz}$ környékén pedig kiemel.
2.  A mért **$24\,\text{dB}$**-es erősítés jelentős jelkiemelést mutat a rezonanciaponton.
3.  A fázisgörbe a rezonanciafrekvencián közel **$-180^\circ$**, ami igazolja, hogy az áramkör invertáló alapkapcsolású.

---
**Aláírás:** **Spisák Roland Konstantin**
___________________________
