# Infosystém Unicontrols DIS-218
## Dokumentace k systému
**Je důležité, aby jste si dokumentaci přečetli celou a dělali přesně to co vám bude řečeno, jinak infopanely nebudou fungovat.**

**Dokumentace je celá napsána v českém jazyce. ‼️For non-czech speakers, ask for translation via my Discord omamelo‼️**

---
### Začátečné rozpoložení

Na začátku se ve workspaci objeví folder s názvem "Unicontrols - Infopanely"

![Snímka obrazovky 2023-05-25 175705](https://github.com/omamelo/Infosystem/assets/113608366/37fcd54e-7bd4-4798-a28b-c5b3a7da6821)

Všechny části systému jsou ve folderi rozložené podle toho, jaký Parent mají mít ve hře. 
1. Jako první přesunete model "Tabule" uložený ve folderi "Workspace" do "Workspace"
2. Přesunete obě dvě položky z folderu "VehicleSeat" do sedadla vašeho vlaku
3. Přesunete oba dva ModuleScripty z folderu "ServerScriptService" do "ServerScriptService"

Po tomhle kroku by měl být systém plně funkční. Folder "Unicontrols - Infopanely" i s vnořenýma folderama můžete smazat.

---
### Resize

V modelu "Tabule" se nacházejí dva party o velikosti 21.1 na 11 studs. Jde je zmenšit, v případě problému se zmenšováním nastavte požadovanou velikost partu a vevnitř partu najděte SurfaceGUI pod názvem "ZSSK" u obou typů a v okénku Properties najděte property PixelsPerStud a pohrajte si s tím číslem. 

![Snímka obrazovky 2023-05-25 174525](https://github.com/omamelo/Infosystem/assets/113608366/64fd1e86-0d26-4c66-8556-5536be72b8d4)
![Snímka obrazovky 2023-05-25 174553](https://github.com/omamelo/Infosystem/assets/113608366/aec2fb35-997d-4548-8905-543ac015e2a7)

---
### Vytváření nových panelů

Jestli potřebujete víc než jeden panel, je to možné.
1. Zajděte do modelu "Tabule" a najděte panel který chcete zduplikovat, zduplikujte ho a přesuňte na požadované místo
2. Ve vehicleseatu kam jste přesunuli věci z folderu "VehicleSeat" najděte ModuleScript s názvem "ModuleScript" který je uložený na pozici "Vehicleseat;Route;Frame;Frame;ModuleScript

![image](https://github.com/omamelo/Infosystem/assets/113608366/1a10e2ee-ff80-4811-bccf-2e28e25df7fa)

3. ModuleScript otevřete
4. Defaultně je tam napsána lokace dvou panelů. Za poslední čárku vpište lokaci nového framu. **Je nezbytné aby pod jedním parentem byl jenom jeden child se stejným názvem aby se předešlo chybám v kódu. Proto si každý panel pojmenujte jinak anebo ať k němu vede jiná cesta.**

Před:
```lua
local module = {{game.Workspace.Tabule.ZSSK, game.Workspace.Tabule.CD}}

return module
```
Po:
```lua
local module = {{game.Workspace.Tabule.ZSSK, game.Workspace.Tabule.CD1, game.Workspace.Tabule.CD2}}

return module
```
Tento ModuleScript používejte i tehdy když měníte název nebo pozici tabule

---
### Vytváření nové linky

Na začátku jsou k dispozici dvě základní linky. Košice-Bratislava a Košice-Humenné. Tyto linky jde změnit. Následujte tyto pokyny

Řekněme si, že chceme založit linku Praha Hl. N.- Praha Braník.
1. Jako první zduplikujeme jeden z dvou ModuleScriptů uložených ve ServerScriptService.
2. Jestli chceme jen jednu linku, ostatní ModuleScripty můžeme smazat
3. Po zduplikování ModuleScriptu Kosice_Bratislava si ho přejmenujeme na "Hlavak_Branik". Na názvu teď nezáleží ale je důležítý pro další účely. Nepíšeme tedy s diakritikou a na rozdělení nepoužíváme - ale _
4. Po otevření by měl vypadat takhle
```lua
local route = {
	"EX 610",
	"Košice - Bratislava",
	"StartingTime",
	{	["Nazev"] = "Košice",
		["Plustime"] = 0,
		["waiting_time"] = 0,
		["arrival"] = 0,
		["departure"] = 0
	},
	{	["Nazev"] = "Kysak",
		["Plustime"] = 13,
		["waiting_time"] = 2,
		["arrival"] = 0,
		["departure"] = 0
	},
	{	["Nazev"] = "Margecany",
		["Plustime"] = 14,
		["waiting_time"] = 1,
		["arrival"] = 0,
		["departure"] = 0
	},
	{	["Nazev"] = "Spišská Nová Ves",
		["Plustime"] = 26,
		["waiting_time"] = 2,
		["arrival"] = 0,
		["departure"] = 0
	},
	{	["Nazev"] = "Poprad - Tatry",
		["Plustime"] = 17,
		["waiting_time"] = 3,
		["arrival"] = 0,
		["departure"] = 0
	},
	{	["Nazev"] = "Liptovský Mikuláš",
		["Plustime"] = 46,
		["waiting_time"] = 1,
		["arrival"] = 0,
		["departure"] = 0
	},
	{	["Nazev"] = "Ružomberok",
		["Plustime"] = 17,
		["waiting_time"] = 1,
		["arrival"] = 0,
		["departure"] = 0
	},
	{	["Nazev"] = "Kráľovany",
		["Plustime"] = 15,
		["waiting_time"] = 1,
		["arrival"] = 0,
		["departure"] = 0
	},
	{	["Nazev"] = "Vrútky",
		["Plustime"] = 13,
		["waiting_time"] = 2,
		["arrival"] = 0,
		["departure"] = 0
	},
	{	["Nazev"] = "Žilina",
		["Plustime"] = 24,
		["waiting_time"] = 5,
		["arrival"] = 0,
		["departure"] = 0
	},
	{	["Nazev"] = "Považská Bystrica",
		["Plustime"] = 22,
		["waiting_time"] = 2,
		["arrival"] = 0,
		["departure"] = 0
	},
	{	["Nazev"] = "Púchov",
		["Plustime"] = 9,
		["waiting_time"] = 2,
		["arrival"] = 0,
		["departure"] = 0
	},
	{	["Nazev"] = "Trenčín",
		["Plustime"] = 16,
		["waiting_time"] = 3,
		["arrival"] = 0,
		["departure"] = 0
	},	
	{	["Nazev"] = "Trnava",
		["Plustime"] = 35,
		["waiting_time"] = 0,
		["arrival"] = 0,
		["departure"] = 0
	},
	{	["Nazev"] = "Bratislava Hlavná Stanica",
		["Plustime"] = 34,
		["waiting_time"] = 0,
		["arrival"] = 0,
		["departure"] = 0
	},
}
```
Cokoliv za touhle složenou závorkou zůstává stejné takže nás to nezajímá 

Tenhle Module script si můžete vytvořit přes nástroj speciálně určený na tohle na [adrese]([url](https://omameloscriptservices.000webhostapp.com/Infopanely/))

Když pak kliknete "Vytvořit linku", to co se vám ukázalo, můžete zkopírovat a vyměnit za to, co tam je doteď.

Výsledek může mít i takovouhle podobu:
```lua
local route = {
	"Os 6688",
	"Praha Hl. N. - Praha Braník",
	"StartingTime",
	{	["Nazev"] = "Praha Hl. N.",
		["Plustime"] = 0,
		["waiting_time"] = 0,
		["arrival"] = 0,
		["departure"] = 0
	},
	{	["Nazev"] = "Praha Vršovice",
		["Plustime"] = 4,
		["waiting_time"] = 2,
		["arrival"] = 0,
		["departure"] = 0
	},
	{	["Nazev"] = "Praha Kačerov",
		["Plustime"] = 4,
		["waiting_time"] = 0,
		["arrival"] = 0,
		["departure"] = 0
	},
	{	["Nazev"] = "Praha Krč",
		["Plustime"] = 3,
		["waiting_time"] = 0,
		["arrival"] = 0,
		["departure"] = 0
	},
	{	["Nazev"] = "Praha Braník",
		["Plustime"] = 4,
		["waiting_time"] = 0,
		["arrival"] = 0,
		["departure"] = 0
	},
}
```
5. Tento script po této úpravě můžeme zavřít
6. Otevřeme si scrolling frame ve VehicleSeatu na pozici "VehicleSeat;Route;Frame;Frame"
7. Vevnitř jsou dva buttony. Na první z nich klikneme a změníme property Text na tu linku kterou potřebujeme. U nás tedy "Praha Hl. N. - Praha Braník"
8. Druhý Textbutton smažeme
9. Popřípadě se ten button duplikuje a posouvá, název se měnit nemusí
10. Vevnitř se nachází Script, otevřete ho
11. Nás bude zajímat řádek 7
```lua
local new_module = game.ServerScriptService.Kosice_Bratislava:Clone(script.Parent)
```
12. Změníme ho na náš název našeho Modulu. Po změně by to mělo vypadat takhle
```lua
local new_module = game.ServerScriptService.Hlavak_Branik:Clone(script.Parent)
```
**Takhle se dá vytvořit nová linka**

---
### Problémy

Kdyby se objevila jakákoli chyba, nebo se chcet na něco zeptat, kontaktujte mě na discordu **omamelo#1891**

---
### Licence

Tento model a systém je plně přístupný všem lidem, který si ho koupili. Jakékoliv zdílení lidem kteří si tento model nezakoupili je zakázáno

Logo ZSSK je majetkem společnosti Železničná spoločnosť Slovensko a logo ČD je majetkem společnosti České dráhy
