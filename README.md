# ⚡ DigiSwift
### Coding By DigiFan — Windows Performance Toolkit v2.0

---

## 📋 Leírás

A **WinOptimizer Pro** egy modern, grafikus felületű PowerShell-alapú rendszeroptimalizáló eszköz, amely automatikusan megtisztítja a Windows szemétfájlokat, felszabadítja a tárhelyet és maximalizálja a rendszer teljesítményét.

---

## 🚀 Funkciók

| Modul | Leírás |
|-------|--------|
| ⚡ Gyors Optimalizálás | Temp, cache, DNS flush, RAM felszabadítás — egyetlen kattintásra |
| 🔥 Teljes Optimalizálás | MINDEN modul futtatása egyszerre |
| 🗑️ Temp Mappák törlése | `%TEMP%`, `%TMP%`, `C:\Windows\Temp`, Prefetch |
| 🌐 Böngésző Cache | Chrome, Edge, Firefox, Opera, Brave |
| 📋 Eseménynapló törlés | Windows Event Logs teljes ürítése |
| 🪣 Lomtár ürítés | Recycle Bin automatikus törlése |
| 🔄 Windows Update Cache | SoftwareDistribution mappa tisztítása |
| ⚙️ Energiaséma | Nagy teljesítményű profil aktiválása |
| 🛡️ SFC Ellenőrzés | Rendszerfájlok integritásának vizsgálata |
| 🧠 RAM Felszabadítás | .NET GC futtatása + szabad memória kijelzése |
| 🌐 Hálózat Optimalizálás | TCP/IP tuning (autotuninglevel, RSS, Chimney) |
| 🎨 Vizuális Effektek | Teljesítmény-módra optimalizálva |
| 🚫 Indítóprogramok | Felesleges startup appok tiltása |

---

## 🖥️ Rendszerkövetelmények

- **Windows 10 / 11** (64-bit ajánlott)
- **PowerShell 5.1** vagy újabb
- **Rendszergazdai (Admin) jogosultság** — a szkript automatikusan kéri!

---

## ▶️ Indítás

### Módszer 1 — Jobb klikk
```
Jobb klikk a WinOptimizer-DigiFan.ps1 fájlon
→ "Futtatás PowerShell-lel"
```

### Módszer 2 — PowerShell konzol
```powershell
# Végrehajtási engedély megadása (csak egyszer kell):
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser

# Szkript futtatása:
.\WinOptimizer-DigiFan.ps1
```

### Módszer 3 — Admin konzol
```powershell
Start-Process PowerShell -Verb RunAs -ArgumentList "-File .\WinOptimizer-DigiFan.ps1"
```

> **⚠️ Fontos:** Ha az ExecutionPolicy blokkolja, futtasd ezt Admin PowerShell-ből:
> ```powershell
> Set-ExecutionPolicy Bypass -Scope Process -Force
> ```

---

## 🎨 GUI Felület

```
┌─────────────────────────────────────────────────────────┐
│  ⚡ WinOptimizer Pro          Coding By DigiFan    v2.0  │
├──────────┬──────────┬──────────┬──────────┤
│ MENTETT  │ RAM      │ OS       │ CPU      │ ← Stat kártyák
├──────────┴──────────┴──────────┴──────────┤
│ [Gombok] │  KIMENET / LOG konzol           │
│          │  ─────────────────────────────  │
│  Gyors   │  [HH:MM:SS] ✔  Temp törölve    │
│  Teljes  │  [HH:MM:SS] ✔  42.3 MB ment.  │
│  Temp    │  [HH:MM:SS] ►  Böngésző cache  │
│  Cache   │  ...                           │
│  ...     │                                │
└──────────┴────────────────────────────────┘
│  Készen áll  •  Coding By DigiFan  •  Admin módban fut  │
└─────────────────────────────────────────────────────────┘
```

---

## ⚙️ Konfiguráció

A szkript tetején módosíthatók az alapértékek:

```powershell
# Saját temp mappák hozzáadása az Invoke-CleanTemp függvényben:
@{ P = "D:\SajatTemp"; L = "Saját Temp Mappa" }

# Saját böngésző cache hozzáadása az Invoke-CleanBrowser függvényben:
@{ P = "$env:LOCALAPPDATA\Saját_Böngésző\Cache"; L = "Saját Böngésző" }
```

---

## 🔒 Biztonság

- A szkript **CSAK a saját gépeden** fut, semmit nem tölt fel
- Nincs hálózati kapcsolat, nincs telemetria
- Csak **nyilvánosan dokumentált Windows API-kat** használ
- A rendszerfájlokat (`C:\Windows\System32`) **NEM érinti**
- Az SFC (`sfc /scannow`) beépített Windows eszköz

---

## 📁 Fájlszerkezet

```
WinOptimizer-DigiFan.ps1    ← Fő szkript (minden egyben)
README.md                   ← Ez a dokumentum
```

---

## 🐛 Hibaelhárítás

| Hiba | Megoldás |
|------|----------|
| "nem engedélyezett a futtatás" | `Set-ExecutionPolicy RemoteSigned -Scope CurrentUser` |
| GUI nem jelenik meg | Ellenőrizd, hogy PowerShell 5.1+ fut-e |
| Hozzáférés megtagadva | Futtasd Rendszergazdaként |
| SFC sokáig fut | Ez normális, akár 15-20 percet is vehet |

---

## 📝 Verziónapló

| Verzió | Változások |
|--------|-----------|
| v2.0 | Modern GUI, stat kártyák, böngésző cache, hálózat optimalizálás |
| v1.0 | Alap temp törlés, lomtár, DNS flush |

---

## 👤 Szerző

```
Coding By DigiFan
Windows Performance & Automation Tools
```

---

## ⚠️ Felelősségkizárás

Ez a szkript személyes használatra készült. A szerző nem vállal felelősséget
semmiféle adatvesztésért. Használat előtt ajánlott rendszermentést (restore point)
készíteni:

```powershell
Checkpoint-Computer -Description "WinOptimizer előtt" -RestorePointType MODIFY_SETTINGS
```

---

*⚡ DigiSwift — Coding By DigiFan*
