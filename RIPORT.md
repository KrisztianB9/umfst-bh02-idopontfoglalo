# A rakoncátlan időpontfoglaló – hibariport

Repó: https://github.com/KrisztianB9/umfst-bh02-idopontfoglalo
Készítette: Bacso Krisztian, InfoLM3

## 1. hiba
- **Hiba leírása és reprodukálása:**
Ugyanarra az idopontra tobb foglalast is lehet kerni.
Reprodukalas: Irunk egy nevet 9:00 idoponthoz es rakattintunk a Foglalasra. Ezutan beirunk egy masik nevet a 9:00 idoponthoz es engedni fogja rogziteni.
- **Gyökérok (sor + magyarázat):**
Az app.js 12-14 soraiban a foglalt(ido) fuggveny a foglalasok.indexOf(ido) !== -1 koddal ellenoriz. A problema az, hogy a foglalasok tomb nem egyszeru stringeket tartalmaz, hanem objektumokat es igy mindig -1et ad vissza.
- **Javítás (commit link):**

- **Hogyan tesztelted (kézi tesztlépések, konzolos ellenőrzés vagy egységteszt):**
Kezi tesztelessel, megprobaltam ujra ugyanarra az idore ket foglalast tenni, nem engedte.
- **Tanulság / érintett alapelv:**
Objektumokat tartalmazo tombre nem hasznalunk indexOf-ot primitiv ertek keresesere mint a string. Helyette beepitett iteracios fuggvenyt hasznalunk, mint a some.

## 2. hiba
- **Hiba leírása és reprodukálása:**
- **Gyökérok (sor + magyarázat):**
- **Javítás (commit link):**
- **Hogyan tesztelted (kézi tesztlépések, konzolos ellenőrzés vagy egységteszt):**
- **Tanulság / érintett alapelv:**

## 3. hiba
- **Hiba leírása és reprodukálása:**
- **Gyökérok (sor + magyarázat):**
- **Javítás (commit link):**
- **Hogyan tesztelted (kézi tesztlépések, konzolos ellenőrzés vagy egységteszt):**
- **Tanulság / érintett alapelv:**

## 4. hiba
- **Hiba leírása és reprodukálása:**
- **Gyökérok (sor + magyarázat):**
- **Javítás (commit link):**
- **Hogyan tesztelted (kézi tesztlépések, konzolos ellenőrzés vagy egységteszt):**
- **Tanulság / érintett alapelv:**

## 5. hiba
- **Hiba leírása és reprodukálása:**
- **Gyökérok (sor + magyarázat):**
- **Javítás (commit link):**
- **Hogyan tesztelted (kézi tesztlépések, konzolos ellenőrzés vagy egységteszt):**
- **Tanulság / érintett alapelv:**

## 6. hiba
- **Hiba leírása és reprodukálása:**
- **Gyökérok (sor + magyarázat):**
- **Javítás (commit link):**
- **Hogyan tesztelted (kézi tesztlépések, konzolos ellenőrzés vagy egységteszt):**
- **Tanulság / érintett alapelv:**

## Összegzés
- Mit tanultam:
- Melyik alapelv sérült a leggyakrabban: 
