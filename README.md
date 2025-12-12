# 🌍 Földrajz Kvíz - AI-alapú, tanulást segítő alkalmazás 
Az alábbi leírást MI generálta, fejlesztő ellenőrizte és javította.

## 📖 Áttekintés

Ez egy interaktív földrajz kvíz alkalmazás, amely **mesterséges intelligenciát** használ a diákok szöveges válaszainak automatikus értékelésére. A program célja, hogy támogassa a földrajztanulást azáltal, hogy azonnali, részletes visszajelzést ad a tanulóknak.

## ✨ Főbb funkciók

### 🎓 Tanulás mód
- **Témakör szerinti szűrés**: Légkör, Vízburok vagy minden téma
- **Nehézségi szint választás**: Könnyű, Közepes, Nehéz (terv)
- **Részletes AI visszajelzés**: Konstruktív értékelés, konkrét fejlesztési javaslatok
- **Segítség funkció**: Kulcsszavak felfedése (pontlevonással)
- **Korlátlan gyakorlás**: Ismételhető kérdések, nincs időkorlát

### 🎯 Teszt mód
- **5 véletlenszerű kérdés** a választott témakörből
- **Tanúsítvány generálás**: 90%+ eredmény esetén letölthető PNG tanúsítvány
- **Szigorúbb értékelés**: Csak összpontszám látható (részletes visszajelzés nélkül)
- **Témakör megjelenik a tanúsítványon**: "A légkör tesztet", "A vízburok tesztet", stb.

## 🤖 AI-alapú értékelés

A program a **Google Gemini API**-t használja a válaszok értékelésére. Az AI:
- ✅ **Tartalmi pontosságot** értékel (nem nyelvtant!)
- ✅ **Kulcsszavakat** ellenőriz
- ✅ **Példákat** vár, ha a programnak megadott mintaválasz is tartalmaz
- ✅ **Részletességet** számon kér (teljes mondatok vs. felsorolás)
- ✅ **Tipikus hibákat** felismeri és korrigálja

### Pontozási rendszer
- **10 pont**: Helyes, részletes, tartalmazza az összes kulcsszót és példát
- **7-9 pont**: Jó válasz, de van kisebb hiányosság
- **4-6 pont**: Részben helyes, de fontos elemek hiányoznak
- **0-3 pont**: Helytelen vagy hiányos válasz
- **-2 pont**: Minden felhasznált segítség után

## 🛠️ Technikai részletek

### Architektúra
- **Frontend**: HTML, JavaScript, Tailwind CSS
- **AI motor**: Google Gemini 2.5 Flash (10 rotáló API kulcs)
- **Adatforrás**: CSV fájl (kérdések, mintaválaszok, kulcsszavak)
- **Hosting**: GitHub Pages kompatibilis

### CSV fájl formátum
```
Kérdés;Mintaválasz;Kulcsszavak;Tipikus hibák;Témakör;Nehézség
```

**Fontos:** A mintaválaszokban (CSV fájl) **NE használj pontosvesszőt** (`;`)! Helyette használj vesszőt (`,`) vagy pontot (`.`), mert a pontosvessző az elválasztó karakter.

### Telepítés
1. Töltsd le a repository-t
2. Cseréld ki az API kulcsokat a sajátjaidra (`API_KEYS` tömb)
3. Töltsd fel a `ai3.csv` fájlt a kérdésekkel
4. Nyisd meg az `index.html`-t vagy használj webszervert

## 📊 Jelenlegi tartalom
- **🌤️ Légkör**: Atmoszféra, időjárás, éghajlat
- **💧 Vízburok**: Tengerek, folyók, vízforgalom
- **19 kérdés** összesen (bővíthető)

## 🔐 API kulcsok kezelése

A programban **10 API kulcs rotál**, hogy kezelje az osztálytermi használatot (30+ tanuló). 

**Biztonsági beállítások (Google Cloud Console):**
- Domain korlátozás
- HTTP referrer korlátozás engedélyezve
- Kvóta: Alapértelmezett ingyenes tier

## 📝 Pedagógiai megjegyzések

### Amit a program JÓL csinál:
✅ Azonnali visszajelzés minden válaszra  
✅ Konstruktív, nem bántó értékelés  
✅ Megkülönbözteti a tartalmi hibát a nyelvtani hibától  
✅ Tanúsítvány motiválja a tanulókat  

### Amire érdemes figyelni:
⚠️ Az AI néha túl elnéző vagy túl szigorú lehet  
⚠️ Komplex földrajzi fogalmak esetén ellenőrizd az értékelést  
⚠️ A tanulók megtanulhatják "kijátszani" a rendszert  

**Javaslat**: Használd kiegészítő eszközként, ne helyettesítse a tanári értékelést!

## 🎨 Testreszabás

### Új témakör hozzáadása
1. A CSV-ben add hozzá az új témakört (E oszlop)
2. Emoji hozzáadása opcionális (pl. `🌋 Földfelszín`)
3. Automatikusan megjelenik a dropdown-ban!

### Új kérdés hozzáadása
Egyszerűen adj új sort a CSV-hez a megfelelő formátumban.

## 📄 Licenc

Ez egy oktatási célú projekt. Szabadon használható és módosítható iskolai környezetben.

## 🤝 Közreműködés

Ha hibát találsz vagy új funkciót javasolnál, írj e-mailt: havassy@budai-rfg.hu.

---

**Készítette**: Havassy András (földrajz tanár)  
**Verzió**: 1.0  
**Utolsó frissítés**: 2025. december
