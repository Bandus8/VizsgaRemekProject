# Főiskolai sporterőforrás foglaló
## Bevezetés

A Sport Erőforrás Foglalási Alkalmazás azért készült, hogy lehetővé tegye a hallgatók számára a sporteszközök foglalását. Az adminisztrátor nyomon tudja követni az erőforrások elérhetőségét, és egyszerűsíti a büntetési folyamatot. Ez az alkalmazás megoldja a meglévő manuális rendszerben előforduló problémákat. Emellett rendkívül egyszerűvé teszi a hallgatók számára, hogy erőforrást foglaljanak, ellenőrizzék azok elérhetőségét, megnézzék a hátralékokat, ha vannak, valamint a foglalások történetét, és az adminisztrátor számára, hogy kiadja az erőforrásokat, kiszabja a büntetéseket és megnézze a foglalások történetét. Az alkalmazás számára kifejlesztett API a Heroku-n van telepítve, és készen áll arra, hogy válaszoljon az alkalmazás által tett kérésekre a várt kimenetekkel, hozzáférve az adatbázishoz.

### Problémadefiníció
A projekt 2 modult tartalmaz

#### Felhasználó
- Diák bejelentkezés
- A kezdőlap megjeleníti az összes elérhető erőforrást és azokat az erőforrásokat, amelyeket lefoglalt.
- Foglaljon le egy erőforrást, amely 20 percre lesz fenntartva számára.
- Foglalás törlése.
- Foglalások története.
- Korlátozás csak 1 foglalásra.
- Erőforrásokat 12:00-tól 16:00-ig lehet kiadni, így a foglalások 11:40-től 15:00-ig kezdődhetnek - A letiltott felhasználók nem foglalhatnak erőforrást, amíg nem rendezik a tartozásukat.

#### Admin
- Admin bejelentkezés
- Erőforrások hozzáadása
- Erőforrások törlése
- (A lefoglalások csökkentése az elérhető erőforrásokból a háttérben kell, hogy történjen)
- Erőforrások kiadása és a foglalás frissítése
- (Minden erőforrást 16:20-ig vissza kell hozni, különben bírságot kell fizetni, és automatikusan le kell tiltani őket)
- A foglalás frissítése, amint a felhasználó visszahozza az erőforrásokat.
- Bírságok készpénzes befizetése és a felhasználó feloldása.

### A projekt hatóköre: 
Ez az alkalmazás segíthet csökkenteni a manuális rendszerrel kapcsolatos problémákat. Az adminisztrátor egy kattintással kiadhatja vagy elutasíthatja a foglalást, és ez még segít neki nyomon követni a foglalások történetét és a letiltott felhasználók listáját is. Az adminisztrátor erőforrásokat is hozzáadhat vagy törölhet. Ez megkönnyíti az adminisztrátor számára az összes erőforrás és foglalás nyomon követését. A mobilalkalmazás rendkívül egyszerűvé teszi a felhasználók számára az erőforrások lefoglalását és a korábbi foglalások történetének ellenőrzését.

## Tech Stack
### Front-End Design

#### Web Application: HTML, CSS, BOOTSTRAP

A Hypertext Markup Language (HTML) az alapértelmezett jelölőnyelv, amelyet weboldalak és webalkalmazások létrehozására használnak. A Cascading Style Sheets (CSS) és a JavaScript mellett a World Wide Web három sarokkövének technológiáit alkotja. A webböngészők HTML-dokumentumokat kapnak egy webszerverről vagy helyi tárolóból, és ezeket multimédiás weboldalakká alakítják. Az HTML szemantikailag írja le egy weboldal felépítését, és eredetileg tartalmazta a dokumentum megjelenésének utasításait.

A Cascading Style Sheets (CSS) egy stíluslapnyelv, amelyet a jelölőnyelvben, például HTML-ben írt dokumentum megjelenésének leírására használnak. A CSS a World Wide Web egyik sarokkövének technológiája, az HTML és a JavaScript mellett. A CSS célja a megjelenés és a tartalom szétválasztásának lehetővé tétele, beleértve a layoutot, a színeket és a betűtípusokat. Ez a szétválasztás javíthatja a tartalom hozzáférhetőségét, nagyobb rugalmasságot és ellenőrzést biztosít a megjelenési jellemzők meghatározásában, lehetővé teszi, hogy több weboldal megossza a formázást a megfelelő CSS egy külön .css fájlban történő megadásával, és csökkenti a struktúrált tartalom bonyolultságát és ismétlését.

A Bootstrap egy ingyenes és nyílt forráskódú front-end könyvtár weboldalak és webalkalmazások tervezéséhez. HTML- és CSS-alapú tervezési sablonokat tartalmaz a tipográfiához, űrlapokhoz, gombokhoz, navigációhoz és egyéb felhasználói felület komponensekhez, valamint opcionális JavaScript kiterjesztéseket. Sok webes keretrendszerrel ellentétben csak a front-end fejlesztésre összpontosít.

#### Android Application: JAVA, XML

A Java egy magas szintű programozási nyelv, amelyet a Sun Microsystems fejlesztett ki. Eredetileg set-top boxok és kézi eszközök programjainak fejlesztésére tervezték, de később népszerű választássá vált webalkalmazások létrehozásához. A Java szintaxisa hasonlít a C++-ra, de szigorúan objektum-orientált programozási nyelv. A Windows végrehajtható állományai (.EXE fájlok) vagy Macintosh alkalmazásai (.APP fájlok) ellentétben a Java programokat nem közvetlenül az operációs rendszer futtatja. Ehelyett a Java programokat a Java Virtuális Gépe (JVM) értelmezi, amely több platformon is fut.

Az XML kód, amely a World Wide Web Consortium (W3C) hivatalos ajánlása, hasonlít a Hypertext Markup Language (HTML)-ra. Mind az XML, mind az HTML tartalmaz jelölő szimbólumokat az oldalak vagy fájlok tartalmának leírására. Az XML dokumentum alapvető építőeleme egy elem, amelyet címkék határoznak meg. Az elemnek van egy kezdő és egy záró címkéje. Minden elem egy XML dokumentumban egy külső elemben található, amelyet gyökerelemnek neveznek. Az XML támogatja a beágyazott elemeket is, vagyis az elemeket más elemekben. Ez a képesség lehetővé teszi az XML számára a hierarchikus struktúrák támogatását. Az elemnevek leírják az elem tartalmát, a struktúra pedig az elemek közötti kapcsolatot.

### Back-End

#### Web Application: Django

A Django egy ingyenes és nyílt forráskódú webalkalmazás keretrendszer, amely Python nyelven íródott. A Django saját névadási rendszert alkalmaz minden funkcióra és komponensre (pl. az HTTP válaszokat "nézeteknek" hívják). A Django keretrendszer a gyors fejlesztés elveit alkalmazza, ami azt jelenti, hogy a fejlesztők egyszerre több iterációt is végezhetnek anélkül, hogy az egész ütemtervet nulláról kellene kezdeniük. A Django segítségével bármilyen méretű és kapacitású projektekbe belevághatunk, legyen szó egy egyszerű weboldalról vagy egy nagy terhelésű webalkalmazásról.

#### Database: MySQL

A MySQL egy Oracle által támogatott, nyílt forráskódú relációs adatbázis-kezelő rendszer (RDBMS), amely a Strukturált Lekérdező Nyelven (SQL) alapul. Az SQL alapvető parancsait, mint például az ADD, DROP, INSERT és UPDATE, a MySQL-lal együtt lehet használni, amelyek segítségével információkat adhatunk hozzá, távolíthatunk el és módosíthatunk az adatbázisban.

#### RESTful API: Flask

A Flask egy webalkalmazás keretrendszer, amely Python nyelven íródott. A Flask a WSGI (Web Server Gateway Interface) eszközkészletén és a Jinja2 sablonmotoron alapul. A WSGI lényegében egy protokoll, amelyet arra határoztak meg, hogy a Python alkalmazások kommunikálhassanak egy webszerverrel, és így webalkalmazásként használhatóak CGI-n kívül.



## Irodalomkutatás

### Bevezetés

A Sport Erőforrás Menedzsment Rendszer egy web- és android alkalmazás. Az adminisztrátor hozzáadhatja és törölheti az erőforrásokat a weben, és kezelheti a felhasználókat az erőforrások elfogadása és visszautasítása során. A felhasználók az android alkalmazásból foglalhatják az erőforrásokat, és 20 percen belül átvehetik azokat az irodában, sőt, akár törölhetik is a kérelmet.

### Meglévő Rendszer

A meglévő rendszerben a felhasználóknak manuálisan kell ellátogatniuk a sportirodába, és ott kell átvenniük az erőforrásokat. A felhasználók nem tudják rezerválni az erőforrást bárhol is legyenek. Még ha a felhasználó blokkolva is van, elmehet az irodába, és kérheti az erőforrást. Az adminisztrátornak manuálisan kell ellenőriznie a felhasználót, hogy szerepel-e a blokkolt listán, és ki kell adnia az erőforrást.

### Javasolt Rendszer

A javasolt rendszerben a felhasználók bárhonnan rezerválhatják és foglalhatják az erőforrást, és 20 percen belül átvehetik azt. Ebben a rendszerben, ha egy felhasználó blokkolva van, nem tud új erőforrást foglalni, amíg nem rendezi a büntetést. A felhasználó az android alkalmazásban ellenőrizheti a fizetendő büntetés összegét.

### Szoftverkövetelmény Megfogalmazás

#### Felhasználói Követelmények

Két felhasználói szerep létezik: adminisztrátor és felhasználó, azaz diák. A felhasználó minimális követelménye, hogy értsen az alapvető angol nyelvhez, tudja, hogyan kell foglalni egy erőforrást, ellenőrizni a büntetést, és átvenni az erőforrást a sportirodából. Az adminisztrátornak tudnia kell, hogyan fogadja el a felhasználók kérelmeit, blokkolja a felhasználót, kézi erőforrást adjon ki, gyűjtse be a büntetéseket a felhasználóktól és oldja fel a blokkolt felhasználókat.

#### Szoftverkövetelmények

- Bármely webböngésző
- Python 3 Django modullal
- 64 bites operációs rendszer
- Emulator
- Android Studio
- pip
- virtualenv
- Virtualenvwrapper
- Flask modul

### Hardverkövetelmények

#### Modern Operációs Rendszer:

- Windows 7 vagy 10
- Mac OS X 10.11 vagy újabb, 64-bites
- Linux: RHEL 6/7, 64-bites (szinte minden könyvtár működik Ubuntu alatt is)
- x86 64-bites CPU (Intel / AMD architektúra)
- Minimum 4 GB RAM
- Minimum 5 GB szabad lemezterület
- A 64 bites környezet szükséges az Android 2.3x Gingerbread és újabb verziókhoz.
- Legalább 250 GB szabad lemezterület a kód letöltéséhez és egy extra 150 GB a fordításához.
- Legalább 8 GB RAM/swap