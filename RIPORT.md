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
A napi limit 8-ra van allitva, de megis be enged 9 foglalast es csak a 10. lesz elutasitva. 
- **Gyökérok (sor + magyarázat):**
Az app.js 40. soraban az if-ben talalhato feltetel hibas, ">" helyett ">=" kell hasznalni, mivel igy amikor mar 8 foglalasunk van, elutasitja hogy meg egyet foglaljunk.
- **Javítás (commit link):**

- **Hogyan tesztelted (kézi tesztlépések, konzolos ellenőrzés vagy egységteszt):**
Kezi tesztelessel, ahhoz hogy gyorsabban menjen ideiglenesen atirtam a napi limitet 3-ra es nem , mikor megprobaltam berogziteni a 4. foglalast, elutasitotta.
- **Tanulság / érintett alapelv:**
Off-by-one hiba. Mindig oda kell figyelni a relacios jelek mefelelo hasznalatara.

## 3. hiba
- **Hiba leírása és reprodukálása:**
A foglalasok nem rendezodnek sorrendbe ido alapjan. Ha lefoglalunk egy idopontot 10:00 orara, majd egyet 8:30 orara, a 8:30 a 10:00 alatt lesz.
- **Gyökérok (sor + magyarázat):**
Az app.js 17. soraban a rendezes() fuggveny hibas. a .sort() metodus nem logikai ertekeket var vissza, az a.ido > b.ido booleant ad vissza, ezert a rendezes elmarad.
- **Javítás (commit link):**

- **Hogyan tesztelted (kézi tesztlépések, konzolos ellenőrzés vagy egységteszt):**
Kezi teszteles, felvettem egymas utan egy 11:00, 7:00 majd egy 9:00 idopontot, a vegen sikeresen rendezesre kerultek es idorendi sorrendben kerultek kijelzesre.
- **Tanulság / érintett alapelv:**
A JS sort() fuggvenyebe atadott callbacknek szammal kell visszaternie, nem logikai ertekkel.

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
