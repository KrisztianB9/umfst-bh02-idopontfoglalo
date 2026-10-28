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
  https://github.com/KrisztianB9/umfst-bh02-idopontfoglalo/commit/be8d183e14138dddb8d949d52d2410a7740dd152
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
  https://github.com/KrisztianB9/umfst-bh02-idopontfoglalo/commit/e2ac8131496818abdb4e7710179701aee3b6d6eb
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
  https://github.com/KrisztianB9/umfst-bh02-idopontfoglalo/commit/9547e3d36d95ec26d5a15be7b3e84c6886669f5c
- **Hogyan tesztelted (kézi tesztlépések, konzolos ellenőrzés vagy egységteszt):**
Kezi teszteles, felvettem egymas utan egy 11:00, 7:00 majd egy 9:00 idopontot, a vegen sikeresen rendezesre kerultek es idorendi sorrendben kerultek kijelzesre.
- **Tanulság / érintett alapelv:**
A JS sort() fuggvenyebe atadott callbacknek szammal kell visszaternie, nem logikai ertekkel.

## 4. hiba
- **Hiba leírása és reprodukálása:**
Ha a beteg nevekent a <img src=x onerror="document.body.style.background='red'"> kodot adjuk meg, az bekerul a html-be, hibara fut a nem letezo kep miatt es az onerror esemenyben levo js lefut, ami pirosra allitja a hatteret.
- **Gyökérok (sor + magyarázat):**
Az app.js 24. soraban a render fuggveny a felhasznalo altal megadott nevet mindenfele tisztitas vagy kodolas nelkul, kozvetlenul fuzi be a DOM-ba. Mivel a bongeszo HTML-kent ertelmezi a szoveget, a kod is lefut. Ezt XSS-nek hivjuk, Cross-Site Scripting.
- **Javítás (commit link):**
  https://github.com/KrisztianB9/umfst-bh02-idopontfoglalo/commit/8e11063b28b722684b4352ae10b81e1014894ac3
- **Hogyan tesztelted (kézi tesztlépések, konzolos ellenőrzés vagy egységteszt):**
Kezi tesztelessel, beirtam a rosszindulatu kodot es a hatter nem valtozott, a szoveg karaktersorkent jelent meg a listaban.
- **Tanulság / érintett alapelv:**
Sose bizz meg a felhasznaloban, a felhasznalotol erkezo adatokat mindig escapelni kell.

## 5. hiba
- **Hiba leírása és reprodukálása:**
A Torles feliratra a tab nyomasaval nem lehet ralepni, ha megis sikerulne, enterrel nem lehet aktivalni.
- **Gyökérok (sor + magyarázat):**
A Torles felirat es span elembe van rakva, egy span nem fokuszalhato, nem interaktiv elem es nem ismeri fel a billentyuzetes esemenyeket.
- **Javítás (commit link):**

- **Hogyan tesztelted (kézi tesztlépések, konzolos ellenőrzés vagy egységteszt):**
Kezi tesztelessel, rogzitettem egy beteget, majd a billentyuzeten a tab lenyomasaval ra tudtam lepni a torles gombra es az enterrel kitoroltem. 
- **Tanulság / érintett alapelv:**
Ha valami gombkent viselkedik, akkor button elem kell legyen.

## 6. hiba
- **Hiba leírása és reprodukálása:**
- **Gyökérok (sor + magyarázat):**
- **Javítás (commit link):**
- **Hogyan tesztelted (kézi tesztlépések, konzolos ellenőrzés vagy egységteszt):**
- **Tanulság / érintett alapelv:**

## Összegzés
- Mit tanultam:
- Melyik alapelv sérült a leggyakrabban: 
