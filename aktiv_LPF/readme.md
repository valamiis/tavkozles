# KIEGÉSZÍTÉS A MÉRÉSI JEGYZŐKÖNYVHÖZ

**Dátum:** 2026. január 29.
**Tárgy:** Frekvenciamenet vizsgálata (Bode-analízis) – Aktív aluláteresztő szűrő

---

## 8. Áramköri módosítás
Az eredeti invertáló alapkapcsolás visszacsatoló ágába ($R_2$ ellenállással párhuzamosan) beépítésre került egy kondenzátor.

**Új alkatrész:**
* **C (Visszacsatoló kondenzátor):** $10\,nF$ ($10 \cdot 10^{-9}\,F$)
* **R2 (Visszacsatoló ellenállás):** $99.9\,k\Omega$

Ez a módosítás frekvenciafüggővé teszi a visszacsatolást: ahogy a frekvencia nő, a kondenzátor reaktanciája csökken, így "rövidre zárja" a visszacsatoló ellenállást, ami csökkenti az erősítést a magasabb frekvenciatartományban.

## 9. Elméleti számítások (Határfrekvencia)
A kapcsolás egy elsőrendű aluláteresztő szűrőként viselkedik. A törésponti frekvenciát (más néven határfrekvenciát, $f_c$, ahol az erősítés 3 dB-t esik) a visszacsatoló ág időállandója határozza meg:

$$f_c = \frac{1}{2\pi \cdot R_2 \cdot C}$$

Behelyettesítve az értékeket:

$$f_c = \frac{1}{2\pi \cdot 99900\,\Omega \cdot 10 \cdot 10^{-9}\,F} \approx 159,3\,Hz$$

**Várt viselkedés:**
* **$f < f_c$:** Az erősítés állandó (a korábban számított $\approx 18,5\,dB$).
* **$f = f_c$:** Az erősítés $3\,dB$-t csökken ($\approx 15,5\,dB$).
* **$f > f_c$:** Az erősítés $-20\,dB/dekád$ meredekséggel csökken.

## 10. Bode-diagram elemzése (NI ELVISmx Bode Analyzer)  
<img width="923" height="734" alt="image" src="https://github.com/user-attachments/assets/45e58855-1f92-471b-b202-22a6ba243fc8" />

A csatolt ábra (Bode Analyzer) alapján az alábbi megállapítások tehetők:

### 10.1 Amplitúdó-menet (Felső grafikon - Gain)
* **Alacsony frekvencián (10 Hz - 50 Hz):** A görbe vízszintes, az erősítés állandó. Az értéke kb. $18-19\,dB$. Ez megegyezik az eredeti (kondenzátor nélküli) invertáló erősítő erősítésével ($20 \cdot \log(8.466) \approx 18.55\,dB$).
* **Töréspont:** A görbe kb. $100\,Hz$ és $200\,Hz$ között kezd el görbülni lefelé. A $159\,Hz$-es elméleti érték vizuálisan reálisnak tűnik a 3 dB-es esés helyénél.
* **Magas frekvencián:** A görbe lineárisan csökken a logaritmikus skálán. A meredeksége jellegzetes $-20\,dB/dekád$, ami az elsőrendű szűrőkre jellemző.

### 10.2 Fázismenet (Alsó grafikon - Phase)
* **Kezdő fázis:** Alacsony frekvencián a fázis $180^\circ$-hoz közelít. Ez igazolja, hogy az áramkör továbbra is **invertáló** jellegű a passzív tartományban.
* **Fázistolás:** A határfrekvencia környékén a fázis csökkenni kezd.
* **Végfázis:** Magas frekvencián ($>10\,kHz$) a fázis $90^\circ$ felé tart. Ez azért történik, mert a kondenzátor dominánssá válik a visszacsatolásban, és az integráló jelleg $90^\circ$-os fáziskésést visz be az alap $180^\circ$-os fordításhoz képest.

## 11. Következtetés
A $10\,nF$-os kondenzátor beépítése sikeresen átalakította az áramkört egy sávszélesség-korlátozott invertáló erősítővé (aluláteresztő szűrő). A mérési eredmények (Bode-diagram) jól mutatják a frekvenciafüggő erősítést, amely megvédi az áramkört a magas frekvenciás zajoktól, illetve alacsony frekvencián biztosítja a kívánt jelerősítést.

A mért karakterisztika összhangban van az elméleti $159\,Hz$-es törésponti frekvenciával.

---
**Aláírás:**
Spisák Roland Konstantin
