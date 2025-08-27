# Egy-kattintásos környezet

Az "egy kattintásos" környezet célja, hogy amíg csak egy forrásfájlal kell dolgoznotok (kifejezetten például a félév legelején) is lehetőségetek legyen minél kevesebb vacakolással ezt futtatnotok. Nagyon régóta tapasztalat, hogy mivel már a fejlesztői környezet összerakása is jópár munkaórát igénybe vehet, mire mindent sikerül kikalapálni benne, utána nagyon kevesen veszik a fáradtságot, hogy azt még debuggolásra is alkalmassá tegyék. Bár a tárgyakon látható hozzáállás és kiajánlott környezet egyre fejlődik, biztos ami biztos alapon szerettem volna egy olyan lehetőséget biztosítani, ami pár kattintással is alkalmas erre. Így remélhetőleg ez a későbbi tárgyakra és szakmai életre is hasznosulni fog, és kevesebb "`prinf("itt meg jo");`" kódsorokat látunk.

## A környezet használata

Ha [az előkészületekkel megvagy](https://github.com/itsthatMatthew/progalapkornyezetek/blob/main/README.md#el%C5%91k%C3%A9sz%C3%BCletek), másold le ezt a példaprojektet egy általad kiválasztott helyre. Ezt többféleképpen is megteheted, szerintem a legegyszerűbb módja most az, ha először fájlkezelőben keresel neki egy alkalmas helyet. Windowson itt meg tudod azt csinálni, hogy `Jobb kattintás > Megnyitás parancssorban` (`Open in Terminal`), alternatívaként pedig előre nyithatsz egy parancssort, és a `cd` paranccsal elnavigálhatsz az általad választott helyre, például fájlkezelőből kimásolva azt. Itt a következő utasítást add ki:

```sh
git clone --single-branch -b oneclick-example https://github.com/itsthatMatthew/progalapkornyezetek egykattintasos-pelda
```

Ezzel lemásolod magát a példaprojektet, így ki tudod azt próbálni.

A következő lépés VS Code megnyitása, amennyiben még konzolban vagy, add ki a következő két parancsot:

```sh
cd egykattintasos-peldaprojekt
code .
```

Ezzel először belelépsz a frissen letöltött mappába, majd ezt megnyitod a VS Code alkalmazásban. Persze ezt megnyithatod külön is, majd benne a lemásolt mappát a grafikus felület segítségével.

Ha ezzel is megvagy, már csak a konténer felpörgetése van hátra az éles használathoz. Ha a szükséges bővítményeket előre letöltötted, a VS Code egyből fel fog dobni a jobb alsó sarokban egy `Reopen in Container` lehetőséget, neked csak erre kell rákattintani. Ha a bővítmények még hiányoznak, így is fel fogja ismerni a lehetőséget, ekkor azt fogja felajánlani, hogy letöltsd őket (illetve sorrendben mindig amire szüksége van, előszöt a `Dev Containers` bővítményt, majd ez a `WSL` bővítményt, majd ez magát a `WSL2` rendszert, ha még nincs meg). Ezeket csak kattintgasd végig. Ha bármi hiba felmerülne, olvasd el és nyugodtan keress rá az interneten, de igyekszem én is mindent előre átnézni, hogy ilyen ne legyen. Néha beakadhat egyik-másik bővítmény, ilyenkor szükséges lehet a VS Code újraindítása (friss WSL telepítése esetén akár a gépé is).

Viszont ha ezen túljutottál, akkor a `Dev Containers` bővítmény el fogja kezdi felépíteni a környezetet. Ez első alkalommal kissé lassú lehet, de amint készen van vele, egy Ubuntu környezet fog fogadni, amiben a C/C++ fejlesztéshez és debuggoláshoz szükséges alapkövetelmények mind jelen vannak.

## Kód fordítása és futtatása

A projekt úgy van felkészítve, hogy csak egyetlen fájlt fordítson és futtasson, azt, ami éppen aktívan ki van választva neked. Ennek megfelelően más kiterjesztésű fájlok esetén hibát fog dobni, ettől ne ijedj meg, bizonyosodj meg, hogy egy ilyen forrásfájl van kiválasztva.

Ha egy C/C++ forrásfájl aktív, mondjuk a példaprojektben található `main.c`, akkor futtatása több lehetőséged is van:

- A felső sávon, a megnyitott fájl nevével azonos magasságban található indítás gomb megnyomásával;
- VS Code menüsoráról a `Run > Run Without Debugging` lehetőség kiválasztásával;
- Vagy az emellett is írt `Ctrl + F5` gombok együttes lenyomásával.

Bárhogyan is teszel, az aktív forrásfájl azonnal le fog fordulni és futni. Ha bármi hiba lenne a fordításban, egy felugró ablak fog erre figyelmeztetni. A `Show Errors` lehetőséggel meg tudod nézni, hogy ezt pontosan mi okozza, majd ezt ki tudod javítani.

## Debuggolás

Az előzőekhez nagyon hasonló lépésekkel, de kicsit máshogyan tudod magát a debuggolást elindítani.

Először is fontos, hogy a kódodban valahol elhelyezz egy *breakpoint*-ot. Ez jelzi a debuggernek, hogy amint eléri ezt a pontot, ideiglenesen függessze fel a program végrehajtását, és így tudod megnézni például a lokális változókat.

Breakpointot egy kiválasztott kódsor bal szélére (a számozás mellé), piros pöttyel jelölve tudsz elhelyezni. Tetszőlegesen sok lehet belőlük.

Ha ezzel megvagy, a futtatáshoz hasonlóan több lehetőséged van debuggolásra:

- A felső sávon most nyisd le az indítás gombot, és válaszd a `Debug C/C++ file` lehetőséget, így egy kis bogárka veszi át a helyét, és innentől ezt fogja kattintásra végrehajtani;
- VS Code menüsoráról választhatod a `Run > Start Debugging` lehetőséget;
- Vagy egyszerűen az `F5` gomb lenyomásával.

Az elsőnek elért breakpointnál meg fog állni a programod, és a környezet is meg fog változni egy kicsit. Ha nincs egy sem, vagy nem éri el, akkor a sima futtatással megegyező hatást fogsz csak érzékelni.

Egy breakpoint elérése esetén az adott sor sárga színnel fog megjelenítésre kerülni, felül megjelenik egy kis navigációs panel, illetve bal szélül különböző információkat tartalmazó panelek. A navigációs panelen szereplő gombokra víve az egeret megmutatják, hogy pontosan mit is csinálnak, illetve ezek a billentyűkombinációk használhatóak kiváltásukra:

<<<<<<< HEAD
|Gyorsbillentyű|Hatás/magyarázat|
=======
|||
>>>>>>> e778afa00bf6488e930ac4f1f877eb5f5fcd4ff5
|-|-|
|`F5`|Továbbengedés: a program csak a soron következő breakpointnál fog újra megállni.|
|`F10`|Léptetés: a program sorról-sorra végigléptethető, mindegyiknél állva marad.|
|`F11`|Belépés: egy függvényhívás esetén a függvénybe lép be annak átugrása helyett.|
|`Shift + F11`|Kilépés: kilép az aktuális függvényből (kivéve `main()`).|
|`Ctrl + Shift + F5`|Újraindítás: újraindítja a debuggolást.|
|`Shift + F5`|Leállítás: leállítja a debuggolást.|

A bal oldalon a következő négy fontos szekció szerepel:

|Megnevezés|Tartalom|
|-|-|
|Variables|Az adott ponton lokális változók és értékeik|
|Watch|Hasonló, mint az előző, de ide tetszőlegesen vehetsz fel olyan kifejezéseket, amiket "nézni" szeretnél.|
|Call stack|Azt mutatja, hogy az adott pontba milyen függvényhívásokon keresztül jutott el a program.|
|Breakpoints|A debuggoláshoz beállított breakpointok listája. Ki-be tudod kapcsolni őket, illetve függvény-breakpointot felvenni, ami akkor fogja megakasztani a végrahajtást, ha az adott függvény meghívódik.|

## Kiindulási sablon

Ha csak magát a környezetet szeretnéd elérni (példakód nélkül), az éppen kiválasztott mappába a konficurációs fájlokat a következő paranccsal tudod lemásolni:

```sh
git clone --single-branch -b oneclick https://github.com/itsthatMatthew/progalapkornyezetek .
```
