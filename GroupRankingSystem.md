# Group Ranking System
## Dokumentace k systému
**Je důležité, aby jste si dokumentaci přečetli celou a dělali přesně to co vám bude řečeno, jinak systém nebude fungovat.**

**Dokumentace je celá napsána v českém jazyce. ‼️For non-czech speakers, ask for translation via my Discord omamelo‼️**

---
### Začátečné rozpoložení

Na začátku se vám ve Workspaci objeví Folder s názvem "GroupRanker"

![image](https://github.com/omamelo/OSS-Documentation/assets/113608366/137ffc8d-1d59-4861-aa06-6856d20da158)

Všechny části systému jsou ve folderi rozložené podle toho, jaký Parent mají mít ve hře. 
1. Jako první přesuňte obě dvě položky z folderu "ReplicatedStorage" do "ReplicatedStorage"
2. Přesuňte script "API" z folderu "ServerScriptService" do "ServerScriptService"
3. Přesuňte ScreenGui z folderu "StarterGui" do "StarterGui"
4. V Game Settings vaší hry v "Security" povolte "Allow HTTP requests"
   
![image](https://github.com/omamelo/OSS-Documentation/assets/113608366/b8730a09-869e-43a5-8b79-83606e88e00d)

Po skončení přesouvání můžete tento folder zničit

---
### Spárování s groupkou

1.

Najděte objekt s názvem "GroupID"

![image](https://github.com/omamelo/OSS-Documentation/assets/113608366/58dfd482-7f63-4593-b6ef-96aa9a684caf)

V Properties nastavte "Value" na ID groupky, pro kterou tento systém pracuje

![image](https://github.com/omamelo/OSS-Documentation/assets/113608366/20cd8987-2698-4d04-a56c-61940ebb83e3)

2.

Najděte objekt s názvem "MinRank"

![image](https://github.com/omamelo/OSS-Documentation/assets/113608366/58dfd482-7f63-4593-b6ef-96aa9a684caf)

V Properties nastavte "Value" na minimální rank, který může mít k systému přístup

![image](https://github.com/omamelo/OSS-Documentation/assets/113608366/795f8c3b-2440-404a-a136-11cadab1db5e)

---
### Spárování se systémem OSS

Otevřete script s názvem "API", uloženým v ServerScriptService

Najděte řádku 4:
```lua
local apikey = ""
```

Do uvozovek vložte hodnotu vašeho ApiKey, který jste si vytvořil v Admin Panelu OSS webu

Klíč musí obsahovat povolení na group, které jste přidávaly při vytváření klíče

Kód bude vypadat následovně třeba takhle:
```lua
local apikey = "abSID59kpodk58PDjkuOSASPijjiw464dsaj1SAD" --tahle hodnota je vymyšlená a k žádnému účtu nevede
```

Máte hotovo, systém by teď měl být plně funkční

---

### Problémy
Kdyby se objevila jakákoli chyba, nebo se chcet na něco zeptat, kontaktujte mě na discordu **omamelo**

---

### Licence
Tento systém je plně přístupný všem uživatelům, kteří si zakoupili alespoň Basic plán na OSS webu.

K používání (ne ke šíření) je přístupný také adminům (uživatelů s dostatečným rankem) groupek, jejichž majitelé využívají tento systém

Jakékoliv šíření systému osobám, které nemají zakoupeny alespoň basic plán, může vést až k zrušení účtu v OSS systému
