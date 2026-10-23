# Kapitola 5 — Přílohy: věkové skupiny pojištěnců a podrobná úprava přerozdělování

**Téma kapitoly:** Kapitola komentuje dvě přílohy zákona č. 592/1992 Sb., které tvoří technické jádro přerozdělování pojistného podle části třetí zákona (§ 20–21f). Příloha č. 1 vymezuje 38 věkových skupin pojištěnců (19 pro muže, 19 pro ženy) a pravidla jejich přeřazování; příloha č. 2 obsahuje úplný algoritmus přerozdělování — nastavitelné parametry (seznam farmaceuticko-nákladových skupin, kombinace skupin, koeficient zajišťovací konstanty, hranice spotřeby léčiv), pravidla jejich zařazení do systému, vstupní data a klasifikaci pojištěnců, iterační regresní výpočet nákladových indexů a zajišťovací konstanty, měsíční klasifikaci pojištěnců zdravotními pojišťovnami a výpočet nákladového indexu pojištěnce a příjmu z přerozdělování podle indexů.

Přílohy nejsou samostatnými zdroji práv a povinností plátců pojistného; jejich adresáty jsou zdravotní pojišťovny, správce zvláštního účtu (VZP), Ministerstvo zdravotnictví a Dozorčí orgán. Mají však přímý dopad na rozdělení prostředků veřejného zdravotního pojištění mezi pojišťovny, a tím i na jejich hospodaření. Právně jde o normativní obsah na úrovni zákona — změnu algoritmu nelze provést vyhláškou, prováděcí předpis podle § 21f písm. a) stanoví jen hodnoty nastavitelných parametrů v rozmezích, která příloha č. 2 vymezuje.

### Příloha č. 1 k zákonu č. 592/1992 Sb.

> **Příloha č. 1 k zákonu č. 592/1992 Sb.**
>
> Věkové skupiny pojištěnců pro přerozdělování pojistného podle indexů
> Číslo skupiny (muži):Číslo skupiny (ženy):Dosažený věk od:Dosažený věk do:120méně než 1 rokméně než 1 rok2211 rok4 roky3225 let9 let42310 let14 let52415 let19 let62520 let24 let72625 let29 let82730 let34 let92835 let39 let102940 let44 let113045 let49 let123150 let54 let133255 let59 let143360 let64 let153465 let69 let163570 let74 let173675 let79 let183780 let84 let193885 letbez limitu
>
> Rozhodujícím datem pro zařazení pojištěnce do věkové skupiny je den dosažení celého roku života, tedy den narozenin pojištěnce. Pojištěnec se přeřazuje do vyšší věkové skupiny vždy k tomu dni, kdy dosáhl požadovaný věk.
>
> Do skupin č. 1 a 20 bude pojištěnec zařazen ode dne narození až do dne předcházejícího dni jeho prvních narozenin. Do skupin č. 2 a 21 bude pojištěnec zařazen ode dne svých prvních narozenin včetně až do dne, který předchází dni jeho pátých narozenin.
>
> Do dalších skupin bude pojištěnec zařazen obdobně.

**Výklad:**

#### Funkce přílohy

Příloha č. 1 naplňuje § 20 odst. 5 větu druhou, podle níž je věkovou skupinou „každá z nákladových věkových skupin pojištěnců uvedených v příloze č. 1“. Věková skupina je jednou ze tří kategorií nákladových skupin (vedle farmaceuticko-nákladových skupin a kombinací skupin, příloha č. 2 oddíl J) a každý pojištěnec patří v daném okamžiku právě do jedné věkové skupiny. Nákladový index věkové skupiny se pak podílí na nákladovém indexu pojištěnce (příloha č. 2 oddíl Q).

#### Rozpis tabulky

Tabulka je ve zdroji slitá do jednoho řádku; přehledně rozepsána:

| Skupina — muži | Skupina — ženy | Dosažený věk od | Dosažený věk do |
|---|---|---|---|
| 1 | 20 | méně než 1 rok | méně než 1 rok |
| 2 | 21 | 1 rok | 4 roky |
| 3 | 22 | 5 let | 9 let |
| 4 | 23 | 10 let | 14 let |
| 5 | 24 | 15 let | 19 let |
| 6 | 25 | 20 let | 24 let |
| 7 | 26 | 25 let | 29 let |
| 8 | 27 | 30 let | 34 let |
| 9 | 28 | 35 let | 39 let |
| 10 | 29 | 40 let | 44 let |
| 11 | 30 | 45 let | 49 let |
| 12 | 31 | 50 let | 54 let |
| 13 | 32 | 55 let | 59 let |
| 14 | 33 | 60 let | 64 let |
| 15 | 34 | 65 let | 69 let |
| 16 | 35 | 70 let | 74 let |
| 17 | 36 | 75 let | 79 let |
| 18 | 37 | 80 let | 84 let |
| 19 | 38 | 85 let | bez limitu |

Kromě kojenecké skupiny (do prvních narozenin) a skupiny 1–4 let jde o pětileté intervaly; nejvyšší skupina 85+ je otevřená. Rozlišení podle pohlaví odráží odlišný nákladový profil mužů a žen v jednotlivých věkových kohortách (typicky v reprodukčním věku).

#### Pravidla zařazení a přeřazení

Rozhodným dnem je den narozenin — pojištěnec se přeřazuje do vyšší skupiny ke dni, kdy dosáhl požadovaného věku. Příloha výslovně demonstruje pravidlo na skupinách 1/20 (od narození do dne předcházejícího prvním narozeninám) a 2/21 (od prvních narozenin včetně do dne předcházejícího pátým narozeninám); u dalších skupin se postupuje obdobně.

Příloha č. 1 sama nestanoví, ke kterému dni se zařazení zjišťuje pro jednotlivé účely přerozdělování. To doplňuje příloha č. 2: pro **měsíční přerozdělování** zařazují pojišťovny pojištěnce podle věku dosaženého **k prvnímu dni měsíce**, v němž přerozdělování probíhá (oddíl N; srov. § 21 odst. 1 písm. a)), kdežto pro **výpočet vypočítaných parametrů** Ministerstvo zdravotnictví zařazuje pojištěnce podle převládající měsíční příslušnosti v posledním účetně uzavřeném roce, kde měsíční příslušnost se určuje podle věku **k poslednímu dni měsíce** (oddíl G). Den narozenin z přílohy č. 1 je tedy hmotným kritériem dosažení věku, procesní „řez“ určuje příloha č. 2.

#### F. Kazuistika

**1. Modelová situace.** Dívka se narodila 15. 3. 2025, chlapec 1. 4. 2021. Zdravotní pojišťovna sestavuje sdělení správci zvláštního účtu pro dubnové přerozdělování 2026.

**2. Právní otázka.** Do které věkové skupiny pojišťovna k 1. 4. 2026 oba pojištěnce zařadí?

**3. Použitelné právo.** Příloha č. 1; příloha č. 2 oddíl N; § 20 odst. 5; § 21 odst. 1 písm. a).

**4. Subsumpce.** Dívka dosáhla 1 roku 15. 3. 2026; k 1. 4. 2026 má dosažený věk 1 rok → skupina 21 (ženy, 1–4 roky). Chlapec dosáhl 5 let právě 1. 4. 2026; podle přílohy č. 1 se přeřazuje ke dni dosažení věku, tedy již k 1. 4. → skupina 3 (muži, 5–9 let).

**5. Řešení.** Pro dubnové přerozdělování: dívka skupina 21, chlapec skupina 3. V březnovém přerozdělování (stav k 1. 3. 2026) byla dívka ve skupině 20 a chlapec ve skupině 2.

**6. Varianty.** Pro výpočet vypočítaných parametrů za rok 2026 by se u dívky vyhodnotila převládající měsíční příslušnost podle věku k poslednímu dni každého měsíce (oddíl G) — od března skupina 21, tedy převažuje skupina 21.

#### G. Protiargumenty a rizika

- *„Přeřazení nastává až od měsíce následujícího po narozeninách.“* Neutralizace: příloha č. 1 stanoví přeřazení ke dni dosažení věku; u narozenin připadajících na první den měsíce se pojištěnec zařadí do vyšší skupiny již v tomto měsíci.
- *Slabé místo:* rozdílné referenční dny v oddílech G (poslední den měsíce) a N (první den měsíce) vedou k tomu, že tentýž pojištěnec může být pro výpočet parametrů a pro měsíční přerozdělování v hraničním měsíci zařazen odlišně; jde o záměr zákona, nikoli o chybu.
- *Riziko dat:* chybné pohlaví nebo datum narození v registru pojištěnců vede k chybnému zařazení a promítá se do přerozdělování.

#### H. Praktický závěr

Příloha č. 1 definuje 38 věkových skupin (19 + 19) a přeřazování ke dni narozenin; referenční den pro jednotlivé účely určuje příloha č. 2.

**Checklist (advokát / soud / správní orgán / adresát normy):**
- [ ] Ověřit pohlaví a datum narození pojištěnce v registru.
- [ ] Určit účel zařazení (měsíční přerozdělování — oddíl N; výpočet parametrů — oddíl G).
- [ ] Zjistit dosažený věk k příslušnému referenčnímu dni (narozeniny se započítávají včetně).
- [ ] Přiřadit číslo skupiny podle tabulky (muži 1–19, ženy 20–38).

**Typicky rozhodné důkazy / podklady:** údaje centrálního registru pojištěnců, sdělení pojišťovny podle § 21 odst. 1, výstupy elektronické aplikace podle § 21 odst. 2.

### Příloha č. 2 k zákonu č. 592/1992 Sb.

> **Příloha č. 2 k zákonu č. 592/1992 Sb.**
>
> Podrobná úprava systému přerozdělování
>
> #### Část první
>
> ##### Nastavitelné parametry přerozdělování
>
> ##### Oddíl A
>
> ###### Seznam farmaceuticko-nákladových skupin
>
> - 1. Seznam farmaceuticko-nákladových skupin se sestavuje ve formátu tabulky, v níž každý řádek představuje jednu farmaceuticko-nákladovou skupinu. Sloupce této tabulky jsou v tomto pořadí:
>
> - a) číslo farmaceuticko-nákladové skupiny,
>
> - b) kód farmaceuticko-nákladové skupiny,
>
> - c) název farmaceuticko-nákladové skupiny,
>
> - d) definiční seznam anatomicko-terapeuticko-chemických skupin léčiv (dále jen „definiční skupiny léčiv“) pro farmaceuticko-nákladovou skupinu na příslušném řádku nebo několik těchto seznamů oddělených slovy „a zároveň“,
>
> - e) vyřazovací pravidla s ostatními farmaceuticko-nákladovými skupinami uvozená slovy „ne, pokud zároveň“.
>
> - 2. Farmaceuticko-nákladové skupiny může Ministerstvo zdravotnictví zařadit do seznamu farmaceuticko-nákladových skupin, pokud splňují podmínku stability a podmínku zvýšení předpovědní síly přerozdělování podle oddílu E.
>
> ##### Oddíl B
>
> ###### Seznam kombinací věkové skupiny s farmaceuticko-nákladovou skupinou a dvou farmaceuticko-nákladových skupin navzájem
>
> Kombinace skupin může Ministerstvo zdravotnictví zařadit do přerozdělování, pokud splňují podmínku stability a podmínku zvýšení předpovědní síly přerozdělování podle oddílu E.
>
> ##### Oddíl C
>
> ###### Koeficient pro výpočet zajišťovací konstanty
>
> Ministerstvo zdravotnictví stanoví hodnotu koeficientu pro výpočet zajišťovací konstanty pro každé období přerozdělování v rozmezí 70 až 250, a to tak, aby celková předpokládaná částka na přerozdělování podle nákladných hrazených služeb v příslušném období přerozdělování činila nejméně 5 a nejvýše 15 procent celkové předpokládané přerozdělované částky v tomto období přerozdělování.
>
> ##### Oddíl D
>
> ###### Hranice spotřeby léčiv pro zařazení pojištěnce do farmaceuticko-nákladové skupiny
>
> Ministerstvo zdravotnictví stanoví hodnotu hranice spotřeby léčiv pro každé období přerozdělování v rozmezí 121 až 365, a to s přihlédnutím k předpokládanému počtu pojištěnců zařazených ve farmaceuticko-nákladových skupinách a ke stabilitě systému přerozdělování.
>
> ##### Oddíl E
>
> ###### Pravidla pro zařazení farmaceuticko-nákladových skupin a kombinací skupin do systému přerozdělování
>
> Ověření podmínek pro zařazení nákladových skupin do systému přerozdělování provádí Ministerstvo zdravotnictví v ověřovacím modelu systému přerozdělování, který se shoduje se systémem přerozdělování podle tohoto zákona, přičemž pracuje s posledními dostupnými údaji obdrženými Ministerstvem zdravotnictví od zdravotních pojišťoven podle § 20c (dále jen „ověřovací model“).
>
> ###### Pododdíl A
>
> ###### Podmínka stability
>
> - 1. Podmínka stability je pro farmaceuticko-nákladovou skupinu naplněna, pokud
>
>   - a) je do příslušné skupiny zařazeno alespoň 200 osob a
>
>   - b) úhrn ročních nákladů osob zařazených do příslušné skupiny převyšuje 24000násobek průměrných měsíčních nákladů podle oddílu K.
>
> - 2. Podmínka stability je pro kombinaci dvou farmaceuticko-nákladových skupin naplněna, pokud je do příslušné kombinace skupin zařazeno alespoň 200 osob.
>
> - 3. Podmínka stability je pro kombinaci farmaceuticko-nákladové skupiny s věkovou skupinou naplněna, pokud je do příslušné kombinace skupin zařazeno alespoň 2500 osob.
>
> ###### Pododdíl B
>
> ###### Podmínka zvýšení předpovědní síly přerozdělování
>
> - 1. Pro farmaceuticko-nákladovou skupinu je podmínka zvýšení předpovědní síly přerozdělování naplněna, pokud jsou pro příslušnou farmaceuticko-nákladovou skupinu současně splněny tyto podmínky:
>
>   - a) Předpovědní síla ověřovacího modelu, sestaveného bez zahrnutí této skupiny a kombinací skupin, měřená koeficientem determinace R2 podle oddílu M, klesne alespoň o 0,0001 ve srovnání s ověřovacím modelem sestaveným bez kombinací skupin, avšak se všemi farmaceuticko-nákladovými skupinami.
>
>   - b) Přírůstek nebo úbytek nákladů příslušný k této farmaceuticko-nákladové skupině, odhadnutý v ověřovacím modelu sestaveném bez zahrnutí kombinací skupin postupem podle oddílu M, je statisticky významný na hladině 1 procento.
>
> - 2. Pro kombinaci skupin je podmínka zvýšení předpovědní síly přerozdělování naplněna, pokud jsou pro příslušnou kombinaci skupin současně splněny tyto podmínky:
>
>   - a) Předpovědní síla ověřovacího modelu sestaveného bez zahrnutí této kombinace skupin, měřená koeficientem determinace R2 podle oddílu M, klesne alespoň o 0,0002 ve srovnání s ověřovacím modelem, do kterého jsou zahrnuty všechny nákladové skupiny a všechny kombinace skupin.
>
>   - b) Přírůstek nebo úbytek nákladů příslušný k této kombinaci skupin, odhadnutý postupem podle oddílu M, je statisticky významný na hladině 1 procento.
>
> #### Část druhá
>
> ##### Vstupní údaje a klasifikace pojištěnců za účelem výpočtu vypočítaných parametrů přerozdělování
>
> ##### Oddíl F
>
> ###### Přehled údajů
>
> - 1. Do výpočtu vypočítaných parametrů přerozdělování vstupují údaje vztahující se k poslednímu účetně uzavřenému kalendářnímu roku, která Ministerstvo zdravotnictví obdrželo od zdravotních pojišťoven podle § 20c.
>
> - 2. Jednotliví pojištěnci jsou pro účely přerozdělování charakterizováni unikátním anonymním číselným identifikátorem (dále jen „anonymní identifikátor“), který jim přiděluje správce centrálního registru pojištěnců. Anonymní identifikátory jsou vytvářeny jako náhodně přidělovaná číselná řada a jsou pojištěncům přidělovány za účelem ochrany osobních údajů pojištěnců podle zákona o ochraně osobních údajů a jako bezpečnostní opatření podle zákona o kybernetické bezpečnosti. Jednotliví pojištěnci mají přiřazeny tyto údaje:
>
> - a) Náklady oceněné podle § 20 odst. 7 (dále jen „náklady“).
>
> - b) Počet měsíců pojištění (dále jen „počet měsíců“); měsíc se považuje za měsíc pojištění, pokud byl k prvnímu dni tohoto měsíce pojištěnec evidován některou zdravotní pojišťovnou jako účastník veřejného zdravotního pojištění (dále jen „měsíc pojištění“). Ve vstupních údajích jsou uvedeni pouze pojištěnci s alespoň 1 měsícem pojištění. Počet těchto osob je dále označován jako „počet pojištěnců“.
>
> - c) Příslušnost do věkové skupiny; příslušnosti pojištěnce do věkových skupin se určí postupem podle oddílu G.
>
> - d) Příslušnosti do farmaceuticko-nákladových skupin; příslušnosti pojištěnce do farmaceuticko-nákladových skupin se určí postupem podle oddílu H.
>
> - e) Příslušnosti do kombinací skupin; příslušnosti pojištěnce do kombinací skupin se určí podle oddílu I.
>
> - 3. Seznamem pojištěnců se označuje výčet anonymních identifikátorů ve vzestupném pořadí od nejnižší hodnoty po nejvyšší hodnotu.
>
> ##### Oddíl G
>
> ###### Příslušnosti do věkových skupin
>
> Ministerstvo zdravotnictví zařadí pojištěnce na základě pohlaví a roku a měsíce narození do věkové skupiny podle převládající měsíční příslušnosti do věkových skupin v posledním účetně uzavřeném kalendářním roce; v případě, že jsou u pojištěnce dány 2 věkové skupiny se stejným počtem měsíčních příslušností, zařadí Ministerstvo zdravotnictví pojištěnce do věkové skupiny s vyšším definičním věkem. Měsíční příslušnosti do věkových skupin jsou za tímto účelem určeny podle dosaženého věku k poslednímu dni měsíce. Započítávají se pouze měsíce, k jejichž prvnímu dni byl pojištěnec účastníkem veřejného zdravotního pojištění.
>
> ##### Oddíl H
>
> ###### Příslušnosti do farmaceuticko-nákladových skupin
>
> - 1. Zařazení pojištěnců do farmaceuticko-nákladových skupin provádí Ministerstvo zdravotnictví na základě údajů sdělených jednotlivými zdravotními pojišťovnami podle § 20c a seznamu léčivých přípravků, u nichž Ústav rozhodl o výši a podmínkách úhrady, a který je vydáván Ústavem podle zákona o veřejném zdravotním pojištění (dále jen „seznam léčiv“).
>
> - 2. Ministerstvo zdravotnictví zařadí pojištěnce do farmaceuticko-nákladové skupiny, pokud naplnil podmínku spotřeby léčiv pro tuto skupinu a zároveň se na tuto skupinu nevztahují vyřazovací pravidla s jinými farmaceuticko-nákladovými skupinami, pro které pojištěnec naplnil podmínku spotřeby léčiv. Za pojištěnce, který naplnil podmínku spotřeby léčiv, se považuje takový pojištěnec, u něhož úhrn obvyklých denních terapeutických dávek léčiv příslušných definičních skupin léčiv překročil v každém z definičních seznamů definičních skupin léčiv této farmaceuticko-nákladové skupiny hranici spotřeby léčiv stanovenou jako nastavitelný parametr přerozdělování pro období přerozdělování, pro které jsou vypočítané parametry přerozdělování počítány. Do tohoto úhrnu se započítávají léčivé přípravky vyzvednuté nebo podané pojištěnci v posledních 12 měsících jeho pojištění, avšak za dobu nejvýše posledních dvou účetně uzavřených let.
>
> ##### Oddíl I
>
> ###### Příslušnosti do kombinací skupin
>
> - 1. Ministerstvo zdravotnictví zařadí pojištěnce do kombinace dvou farmaceuticko-nákladových skupin, jestliže patří do obou těchto skupin a příslušná kombinace je pro období přerozdělování, pro které jsou vypočítané parametry modelu přerozdělování počítány, stanovena jako nastavitelný parametr modelu přerozdělování.
>
> - 2. Ministerstvo zdravotnictví zařadí pojištěnce do kombinace farmaceuticko-nákladové skupiny s věkovou skupinou, jestliže patří do obou těchto skupin a příslušná kombinace je pro období přerozdělování, pro které jsou vypočítané parametry modelu přerozdělování počítány, stanovena jako nastavitelný parametr modelu přerozdělování.
>
> ##### Oddíl J
>
> ###### Nákladové skupiny
>
> - 1. Nákladovými skupinami jsou pro účely výpočtu vypočítaných parametrů označeny věkové skupiny, farmaceuticko-nákladové skupiny a kombinace skupin.
>
> - 2. Nákladové skupiny se pro jednotlivého pojištěnce uvádějí v tomto pořadí:
>
> - a) Věkové skupiny seřazené vzestupně podle svého číselného označení uvedeného v příloze č. 1 k tomuto zákonu.
>
> - b) Farmaceuticko-nákladové skupiny seřazené podle pořadí uvedeného v seznamu farmaceuticko-nákladových skupin podle oddílu A; použije se seznam farmaceuticko-nákladových skupin, který byl stanoven jako nastavitelný parametr pro období přerozdělování, pro které jsou vypočítané parametry modelu přerozdělování počítány.
>
> - c) Kombinace skupin seřazené v pořadí podle seznamu kombinací skupin podle oddílu B; použije se seznam kombinací skupin, který byl stanoven jako nastavitelný parametr pro období přerozdělování, pro které jsou vypočítané parametry modelu přerozdělování počítány.
>
> #### Část třetí
>
> ##### Výpočet vypočítaných parametrů přerozdělování
>
> ##### Oddíl K
>
> ###### Matematické objekty nutné pro výpočet vypočítaných parametrů přerozdělování
>
> Do výpočtu vypočítaných parametrů přerozdělování se započítávají pojištěnci s alespoň 1 měsícem pojištění, a to vzestupně podle svého anonymního identifikátoru. Řazení podle předchozí věty se použije i pro složky vektorů veličin týkajících se jednotlivých pojištěnců.
> Pro výpočet vypočítaných parametrů se označí:
> n počet pojištěnců vstupujících do výpočtu vypočítaných parametrů přerozdělení,
> m počet nákladových skupin podle oddílu J,
> y = (y1, y2, ..., yn)' vektor nákladů pojištěnců a
> w = (w1, w2, ..., wn)' vektor počtu měsíců pojištění pojištěnců.
> Sestaví se matice příslušností pojištěnců do nákladových skupin R typu n × m takto:
>
> Ri,j=1⇔pojištěnec i je zařazen v nákl. skupině j0 jinak, i=1,…,n;j=1,…,m.
> Sestaví se matice počtů měsíců W typu n × n takto:
>
> Wi,j=wi⇔i=j0 jinak, i=1,…,n;j=1,…,n.
> Dále se pro účely výpočtu vypočítaných parametrů přerozdělování označí:
> W celkový počet měsíců pojištění, který se vypočte podle vzorce
>
> W=∑i=1nwi,
> ȳ průměrné měsíční náklady, které se vypočtou podle vzorce
>
> y¯=∑i=1nyiW.
>
> ##### Oddíl L
>
> ###### Výpočet zajišťovací konstanty
>
> Zajišťovací konstanta se označí C a vypočte se takto:
>
> C=CK·y¯
> kde CK je koeficient pro výpočet zajišťovací konstanty podle oddílu C.
>
> Zajišťovací konstanta se zaokrouhluje na celé tisíce.
>
> ##### Oddíl M
>
> ###### Výpočet nákladových indexů
>
> Nákladové indexy se určí postupem popsaným v bodech 1 až 6. Jeho součástí je iterační výpočet, zahrnující opakování bodů 2 až 5, až do splnění konvergenční podmínky v bodu 5. Indexem v pravém horním rohu jednotlivých veličin, uzavřeným v závorkách, označujeme číslo iterace k, ke které se tato veličina vztahuje.
>
> - 1. Definuje se k = 0 a ϒ(1) = y.
>
> - 2. Hodnota k se zvýší o 1.
>
> - 3. Sestaví se regresní model, jehož prostřednictvím se metodou vážených nejmenších čtverců odhadne vektor ϒ(k) takto:
>
> - 3.1. Složky vektoru vysvětlovaných nákladů ϒ(k) se označí ϒ1(k), ϒ2(k), ..., ϒn(k).
>
> - 3.2. Vážený průměr vektoru vysvětlovaných nákladů se označuje ϒ¯(k) a vypočte se podle vzorce ϒ¯(k)=∑i=1nϒi(k)W.
>
> - 3.3. Vektor centrovaných měsíčních vysvětlovaných nákladů se označuje u(k) a vypočte se podle vzorce:
>
> u(k)=W-1·ϒ(k)-ϒ¯(k).
>
> - 3.4. Metodou vážených nejmenších čtverců s vahami w a s regresní maticí R se vypočte vektor odhadnutých přírůstků nebo úbytků nákladů příslušných nákladovým skupinám a(k) podle vzorce:
>
> a(k)=R'·W·R-1R'·W·u(k).
>
> - 3.5. Odhadnuté centrované měsíční vysvětlované náklady u(k)^ se vypočtou podle vzorce:
>
> u(k)^=R·a(k).
>
> - 3.6. Odhadnuté vysvětlované náklady ϒ(k)^ se vypočtou podle vzorce:
>
> ϒ(k)^=W·u(k)^+ϒ¯(k).
>
> - 4. Z reálných nákladů, odhadnutých vysvětlovaných nákladů a zajišťovací konstanty se vypočte simulované zajištění z(k) podle vzorce:
>
> z(k)=max0;0,8·y-ϒ(k)^+C+max0;0,15·y-ϒ(k)^+6·C,
> kde 0 označuje nulový vektor o délce n a funkce „max“ se uplatňuje na každou složku svých argumentů zvlášť, takže jejím výsledkem je vektor o délce n.
> Vektor vysvětlovaných nákladů pro další iteraci se označí ϒ(k+1) a vypočte se podle vzorce:
>
> ϒ(k+1)=y-z(k).
>
> - 5.
>
> - 5.1. Je-li k = 1, postupuje se opět podle bodu 2.
>
> - 5.2. Je-li k > 1, označí se kvalita přiblížení vysvětlovaných nákladů Q a vypočte se podle vzorce:
>
> Q=∑i=1nϒi(k-1)-ϒi(k)∑i=1nyi.
> Platí-li
> Q ≥ 0,0005,
> postupuje se opět podle bodu 2.
> Platí-li
> Q < 0,0005,
> je splněna konvergenční podmínka a iterační algoritmus je ukončen. Definuje se I = k, kde písmeno I označuje celkový počet iterací, a postupuje se podle bodu 6.
>
> - 6. Nákladové indexy se označí ȧ1; ȧ2, ..., ȧm a vypočtou se podle vzorce:
>
> ȧi=αi(I)ϒ¯(I),i=1,…,m,
> kde αi(I), i = 1, ..., m, jsou složky vektoru α(I) odhadnutých přírůstků nebo úbytků nákladů, příslušných nákladovým skupinám, a jsou zaokrouhleny na čtyři platná desetinná místa. Nákladové indexy přísluší nákladovým skupinám v pořadí podle oddílu J. Nákladový index příslušný kombinaci skupin se označí jako korekce pro souběh skupin.
> Koeficient determinace R2 se vypočte podle vzorce:
>
> R2=1-u(I)^-u(I)'·W·u(I)^-u(I)u(I)'·W·u(I).
>
> #### Část čtvrtá
>
> ##### Klasifikace pojištěnců pro účely měsíčního přerozdělování podle indexů
>
> ##### Oddíl N
>
> ###### Klasifikace pojištěnců do věkových skupin
>
> Pro účely měsíčního přerozdělování zdravotní pojišťovny své pojištěnce zařadí do věkové skupiny podle pohlaví a podle dosaženého věku k prvnímu dni měsíce, v němž přerozdělování probíhá. Seznam věkových skupin a definice dosaženého věku jsou uvedeny v příloze č. 1 k tomuto zákonu.
>
> ##### Oddíl O
>
> ###### Klasifikace do farmaceuticko-nákladových skupin
>
> - 1. Pro účely měsíčního přerozdělování podle indexů zařazují pojištěnce do farmaceuticko-nákladových skupin zdravotní pojišťovny, a to na základě spotřeby léčiv těchto pojištěnců a podle seznamu farmaceuticko-nákladových skupin a seznamu léčiv.
>
> - 2. Za pojištěnce, který naplnil podmínku spotřeby léčiv, potřebnou pro zařazení do farmaceuticko-nákladové skupiny, se považuje takový pojištěnec, u něhož úhrn obvyklých denních terapeutických dávek léčiv příslušných definičních skupin léčiv překročil v každém z definičních seznamů definičních skupin léčiv této farmaceuticko-nákladové skupiny stanovenou hranici spotřeby léčiv. Do tohoto úhrnu se započítávají léčiva vydaná nebo podaná pojištěnci, s datem vyúčtování v posledních 12 měsících předcházejících měsíci, pro který měsíční přerozdělování probíhá. Zdravotní pojišťovna zařadí pojištěnce do farmaceuticko-nákladové skupiny, jestliže je u něj naplněna podmínka spotřeby léčiv pro zařazení do této skupiny a pokud se na tuto farmaceuticko-nákladovou skupinu nevztahují vyřazovací pravidla s jinými farmaceuticko-nákladovými skupinami, pro které pojištěnec naplnil podmínku spotřeby léčiv.
>
> - 3. Za datum vyúčtování se považuje den, k němuž je příslušná pohledávka poskytovatele pojišťovnou uznána a uzavřena.
>
> ##### Oddíl P
>
> ###### Klasifikace do kombinací skupin
>
> - 1. Pojištěnec je zařazen do kombinace dvou farmaceuticko-nákladových skupin, jestliže je zařazen do obou těchto skupin a příslušná kombinace je pro příslušné období přerozdělování stanovena jako nastavitelný parametr přerozdělování.
>
> - 2. Pojištěnec je zařazen do kombinace farmaceuticko-nákladové skupiny s věkovou skupinou, jestliže je zařazen do obou těchto skupin a příslušná kombinace je pro příslušné období přerozdělování stanovena jako nastavitelný parametr přerozdělování.
>
> #### Část pátá
>
> ##### Nákladový index pojištěnce a příjem na pojištěnce z přerozdělování podle indexů
>
> ##### Oddíl Q
>
> ###### Nákladový index pojištěnce
>
> Nákladový index pojištěnce se vypočítá jako součet čísla 1, nákladového indexu věkové skupiny, do níž je pojištěnec zařazen, nákladových indexů všech farmaceuticko-nákladových skupin, do nichž je pojištěnec zařazen podle své spotřeby léčiv, a korekcí pro souběh skupin stanovených pro příslušné období přerozdělování.
>
> ##### Oddíl R
>
> ###### Příjem na pojištěnce z přerozdělování podle indexů
>
> - 1. Příjem zdravotní pojišťovny na pojištěnce z přerozdělování podle indexů se počítá pro konkrétní období přerozdělování a pro konkrétního pojištěnce.
>
> - 2. Příjem zdravotní pojišťovny na pojištěnce z přerozdělování podle indexů se spočte jako součet měsíčních příjmů zdravotní pojišťovny na tohoto pojištěnce z přerozdělování podle indexů v měsících spadajících do příslušného období přerozdělování, v nichž byl pojištěnec příslušný k této zdravotní pojišťovně.
>
> - 3. Měsíční příjem zdravotní pojišťovny na pojištěnce z přerozdělování podle indexů se spočte jako součin nákladového indexu pojištěnce pro příslušný kalendářní měsíc podle oddílu Q a podílu na standardizovaného pojištěnce použitého v příslušném kalendářním měsíci podle § 21 odst. 7.

**Výklad:**

#### Systematika a funkce přílohy

Příloha č. 2 je zákonným „algoritmem“ přerozdělování, na který odkazují § 20 odst. 5 věta poslední (výpočet nákladového indexu pojištěnce), § 20a odst. 1 (postup stanovení proměnlivých parametrů) a § 21a odst. 1 (příjem z přerozdělování podle indexů a zajišťovací konstanta). Člení se do pěti částí a oddílů A–R:

- **Část první (A–E)** — nastavitelné parametry a podmínky jejich zařazení do systému;
- **Část druhá (F–J)** — vstupní údaje a klasifikace pojištěnců pro výpočet parametrů (provádí Ministerstvo zdravotnictví);
- **Část třetí (K–M)** — matematický výpočet zajišťovací konstanty a nákladových indexů;
- **Část čtvrtá (N–P)** — měsíční klasifikace pojištěnců (provádějí zdravotní pojišťovny);
- **Část pátá (Q–R)** — nákladový index pojištěnce a příjem pojišťovny na pojištěnce.

Logika je dvoufázová: jednou ročně Ministerstvo zdravotnictví z anonymizovaných dat za poslední účetně uzavřený rok (§ 20c) vypočte vypočítané parametry (nákladové indexy, korekce pro souběh, zajišťovací konstantu) pro následující období přerozdělování, jímž je kalendářní rok (§ 20a odst. 4); každý měsíc pak pojišťovny klasifikují své pojištěnce a správce zvláštního účtu podle těchto parametrů rozdělí částku určenou k přerozdělování (§ 21).

#### Část první — nastavitelné parametry (oddíly A–D)

Nastavitelné parametry (§ 20a odst. 2) stanoví prováděcí předpis podle § 21f písm. a); příloha vymezuje jejich strukturu a meze:

- **Oddíl A — seznam farmaceuticko-nákladových skupin (FNS).** Tabulka s pěti sloupci: číslo, kód, název, definiční seznam(y) ATC skupin léčiv (více seznamů spojených „a zároveň“ znamená kumulativní podmínku spotřeby ve všech) a vyřazovací pravidla („ne, pokud zároveň“), která brání dvojímu započtení příbuzných diagnóz (např. hierarchie mezi lehčí a těžší formou téhož onemocnění). Zařadit FNS lze jen při splnění podmínky stability a zvýšení předpovědní síly (oddíl E).
- **Oddíl B — kombinace skupin** (věková skupina × FNS; FNS × FNS); slouží k výpočtu korekcí pro souběh skupin, které zachycují, že náklady pacienta s více chronickými onemocněními nejsou prostým součtem. Platí tytéž podmínky z oddílu E.
- **Oddíl C — koeficient pro výpočet zajišťovací konstanty (CK)** v rozmezí 70–250. Ministerstvo jej volí tak, aby přerozdělování podle nákladných hrazených služeb činilo 5–15 % celkové předpokládané přerozdělované částky. Jde o zákonné „pásmo“ mezi plošným (indexovým) a zajišťovacím (nákladovým) přerozdělováním.
- **Oddíl D — hranice spotřeby léčiv** v rozmezí 121–365 obvyklých denních terapeutických dávek (ODTD; pojem a náhradní použití definovaných denních dávek viz § 20a odst. 2 písm. d)). Hodnota fakticky odpovídá počtu „dní léčby“ za 12 měsíců; dolní mez zajišťuje, že do FNS se dostane jen pacient s chronickou, nikoli epizodickou léčbou.

#### Oddíl E — podmínky zařazení skupin do systému

Ministerstvo ověřuje podmínky v **ověřovacím modelu**, který je s přerozdělovacím systémem shodný a pracuje s posledními daty podle § 20c.

**Podmínka stability (pododdíl A)** brání statisticky nespolehlivým skupinám: FNS musí mít alespoň 200 osob a úhrn ročních nákladů jejích členů musí převyšovat 24 000násobek průměrných měsíčních nákladů (ȳ podle oddílu K), tj. zhruba 2 000 průměrných ročních nákladů na pojištěnce; kombinace dvou FNS vyžaduje alespoň 200 osob, kombinace FNS s věkovou skupinou alespoň 2 500 osob.

**Podmínka zvýšení předpovědní síly (pododdíl B)** testuje přínos skupiny metodou „vynechání“: vyřazení FNS z modelu (bez kombinací) musí snížit koeficient determinace R² alespoň o 0,0001, u kombinace (v plném modelu) alespoň o 0,0002, a odhadnutý přírůstek či úbytek nákladů musí být statisticky významný na hladině 1 %. Zákon nespecifikuje použitý statistický test; volba testu je metodickou otázkou, kterou je vhodné transparentně dokumentovat (Dozorčí orgán obdrží podkladová data podle § 20c věty třetí).

#### Část druhá — vstupní údaje a klasifikace pro výpočet parametrů (oddíly F–J)

**Oddíl F — přehled údajů.** Vstupem jsou údaje za poslední účetně uzavřený kalendářní rok předané pojišťovnami podle § 20c. Pojištěnec je reprezentován **anonymním identifikátorem** přiděleným správcem centrálního registru pojištěnců jako náhodná číselná řada; zákon tím spojuje ochranu osobních údajů s bezpečnostním opatřením v oblasti kybernetické bezpečnosti. Odkazy na „zákon o ochraně osobních údajů“ a „zákon o kybernetické bezpečnosti“ je třeba číst dynamicky: zákon č. 101/2000 Sb., o ochraně osobních údajů, byl zrušen § 67 bodem 1 zákona č. 110/2019 Sb., o zpracování osobních údajů (vedle něhož se přímo použije obecné nařízení o ochraně osobních údajů), a zákon č. 181/2014 Sb. byl zrušen § 72 bodem 1 nového zákona č. 264/2025 Sb., o kybernetické bezpečnosti (účinného od 1. 11. 2025). Ke každému identifikátoru se přiřazují: náklady oceněné Ústavem zdravotnických informací a statistiky podle § 20 odst. 7, počet měsíců pojištění (měsíc se počítá, byl-li pojištěnec k jeho prvnímu dni účastníkem veřejného zdravotního pojištění; do dat vstupují jen osoby s alespoň jedním měsícem), věková skupina, FNS a kombinace skupin. Řazení podle identifikátoru (bod 3) zajišťuje reprodukovatelnost výpočtu.

**Oddíl G — věkové skupiny pro výpočet.** Rozhoduje převládající měsíční příslušnost v roce; měsíční příslušnost se určuje podle věku k poslednímu dni měsíce a počítají se jen měsíce pojištění. Při shodném počtu měsíců ve dvou skupinách rozhoduje skupina s vyšším definičním věkem. Kritériem je též pohlaví.

**Oddíl H — FNS pro výpočet.** Zařazení provádí ministerstvo podle dat pojišťoven a seznamu léčiv vydávaného Státním ústavem pro kontrolu léčiv (zákon o veřejném zdravotním pojištění jej označuje jako „Ústav“). Pojištěnec je zařazen do FNS, pokud úhrn ODTD léčiv z definičních skupin překročil hranici spotřeby (oddíl D) v **každém** definičním seznamu dané FNS a nebrání tomu vyřazovací pravidlo. Započítávají se léčiva vyzvednutá nebo podaná v posledních 12 měsících pojištění, nejdéle však za poslední dva účetně uzavřené roky — tím se vyrovnávají přerušení pojištění.

**Oddíl I — kombinace skupin.** Pojištěnec spadá do kombinace, patří-li do obou skupin a kombinace je pro dané období stanovena jako nastavitelný parametr (oddíl B).

**Oddíl J — nákladové skupiny** jsou souhrnným pojmem pro věkové skupiny, FNS a kombinace; jejich pořadí (věkové skupiny 1–38, FNS podle oddílu A, kombinace podle oddílu B) určuje pořadí sloupců regresní matice R a tím i přiřazení výsledných indexů.

#### Část třetí — výpočet vypočítaných parametrů (oddíly K–M)

*Poznámka k textu:* ve zdroji (e-Sbírka) jsou matematické vzorce převedeny do prostého textu a ztratily závorky, horní indexy, inverzi matice a absolutní hodnoty. Níže uvedené zápisy jsou výkladovou rekonstrukcí z textu a z věcné souvislosti s § 21a odst. 2; závazné je znění publikované ve Sbírce.

**Oddíl K — objekty.** n = počet pojištěnců, m = počet nákladových skupin, y = vektor ročních nákladů, w = vektor měsíců pojištění, R = matice příslušností (n × m; 1, pokud pojištěnec patří do skupiny, jinak 0), W = diagonální matice měsíců (diagonála w), W (skalár) = celkový počet měsíců pojištění Σ wᵢ a **ȳ = Σ yᵢ / W** = průměrné měsíční náklady na pojištěnce.

**Oddíl L — zajišťovací konstanta** C = CK · ȳ, zaokrouhlená na celé tisíce. Modelově: při CK = 100 a ȳ = 3 000 Kč by C = 300 000 Kč (hodnoty jsou ilustrativní, skutečné stanoví prováděcí předpis a data).

**Oddíl M — nákladové indexy** se počítají iteračně, aby odhad indexů nebyl zkreslen extrémně nákladnými pojištěnci, jejichž náklady jsou z části kryty přerozdělováním podle nákladných hrazených služeb:

1. Start: k = 0, vysvětlované náklady Υ⁽¹⁾ = y.
2. k := k + 1.
3. Regrese vážených nejmenších čtverců: vážený průměr Ῡ⁽ᵏ⁾ = Σ Υᵢ⁽ᵏ⁾ / W; centrované měsíční náklady u⁽ᵏ⁾ = W⁻¹·Υ⁽ᵏ⁾ − Ῡ⁽ᵏ⁾ (tj. náklad na měsíc pojištění minus průměr); odhad a⁽ᵏ⁾ = (R'·W·R)⁻¹·R'·W·u⁽ᵏ⁾; odhad û⁽ᵏ⁾ = R·a⁽ᵏ⁾ a odhadnuté roční náklady Ŷ⁽ᵏ⁾ = W·(û⁽ᵏ⁾ + Ῡ⁽ᵏ⁾). Regrese je bez absolutního členu a centrovaná; každý pojištěnec patří do právě jedné věkové skupiny, takže věkové skupiny plní funkci úrovňových konstant.
4. Simulované zajištění: **z⁽ᵏ⁾ = max(0; 0,8·(y − Ŷ⁽ᵏ⁾ − C)) + max(0; 0,15·(y − Ŷ⁽ᵏ⁾ − 6·C))** (po složkách). Součet dává 80 % nákladů nad hranici Ŷ + C a od hranice Ŷ + 6C celkem 95 % — což věcně odpovídá kompenzaci podle § 21a odst. 2 písm. a) a b) (80 % v pásmu do čtyřnásobku C, 95 % nad šestinásobek C; 0,8 · 5C = 4C). Nové vysvětlované náklady Υ⁽ᵏ⁺¹⁾ = y − z⁽ᵏ⁾.
5. Konvergence: od druhé iterace se počítá **Q = Σ |Υᵢ⁽ᵏ⁻¹⁾ − Υᵢ⁽ᵏ⁾| / Σ yᵢ**; při Q ≥ 0,0005 se pokračuje bodem 2, při Q < 0,0005 se iterace ukončí a I = k.
6. Výsledné **nákladové indexy ȧᵢ = aᵢ⁽ᴵ⁾ / Ῡ⁽ᴵ⁾**, zaokrouhlené na čtyři platná desetinná místa (ve zdroji označeno α; jde o tytéž odhadnuté přírůstky či úbytky z bodu 3.4). Index je tedy relativní odchylka měsíčních nákladů skupiny od průměru; index kombinace skupin je „korekcí pro souběh“. Kvalita modelu se měří **R² = 1 − (û − u)'·W·(û − u) / (u'·W·u)** v poslední iteraci; tento koeficient se používá i v testu podle oddílu E.

Výsledek: indexy věkových skupin mohou být záporné (skupiny s podprůměrnými náklady) i kladné; indexy FNS jsou zpravidla kladné, korekce pro souběh mohou být oboustranné. Ministerstvo je zasílá do 15. září Dozorčímu orgánu a pojišťovnám (§ 20c).

#### Část čtvrtá — měsíční klasifikace pojištěnců (oddíly N–P)

Pro **měsíční přerozdělování** klasifikují pojištěnce samy zdravotní pojišťovny a výsledné počty sdělují do osmého dne měsíce správci zvláštního účtu (§ 21 odst. 1 písm. a)):

- **Oddíl N** — věková skupina podle pohlaví a věku dosaženého k prvnímu dni měsíce přerozdělování (příloha č. 1).
- **Oddíl O** — FNS podle spotřeby léčiv: hranice spotřeby v každém definičním seznamu, vyřazovací pravidla; započítávají se léčiva **s datem vyúčtování** v posledních 12 měsících předcházejících měsíci přerozdělování. Datem vyúčtování je den, k němuž pojišťovna pohledávku poskytovatele uznala a uzavřela (bod 3). Rozdíl oproti oddílu H (ten pracuje s léčivy „vyzvednutými nebo podanými“ v posledních 12 měsících pojištění) je záměrný: měsíční klasifikace musí vycházet z dat, která má pojišťovna k dispozici, tedy z uzavřených vyúčtování; v praxi to znamená časový posun mezi výdejem léčiva a jeho promítnutím do klasifikace.
- **Oddíl P** — kombinace skupin, jsou-li pro období stanoveny.

Při změně zdravotní pojišťovny je dosavadní pojišťovna povinna bezplatně předat nové pojišťovně údaje o spotřebě léčiv potřebné pro zařazení do FNS (§ 20 odst. 8); bez nich by nová pojišťovna nemohla pojištěnce správně klasifikovat.

#### Část pátá — nákladový index pojištěnce a příjem (oddíly Q a R)

**Oddíl Q:** nákladový index pojištěnce = **1 + index věkové skupiny + Σ indexů FNS, do nichž je zařazen + Σ korekcí pro souběh skupin**. Konstanta 1 vyjadřuje průměrného pojištěnce; indexy skupin jsou relativní odchylky od průměru (oddíl M bod 6). Součet nákladových indexů všech pojištěnců pojišťovny dává počet jejích standardizovaných pojištěnců (§ 21 odst. 6).

**Oddíl R:** měsíční příjem pojišťovny na pojištěnce = nákladový index pojištěnce pro daný měsíc × **podíl na standardizovaného pojištěnce** (§ 21 odst. 7: částka určená k přerozdělování v měsíci snížená o měsíční zálohy na nákladné hrazené služby podle § 21a odst. 4, dělená celkovým počtem standardizovaných pojištěnců všech pojišťoven). Roční příjem na pojištěnce je součtem měsíčních příjmů za měsíce příslušnosti k pojišťovně v daném období přerozdělování. Tento roční příjem je referenční veličinou pro určení **nákladného pojištěnce** podle § 21a odst. 1: pojištěnec je nákladný, překročí-li úhrada za něj součet příjmu z přerozdělování podle indexů a zajišťovací konstanty.

**Modelový výpočet** (všechny hodnoty ilustrativní): muž ve věkové skupině s indexem −0,15, zařazený do jedné FNS s indexem 1,20, bez stanovené korekce pro souběh, má nákladový index 1 − 0,15 + 1,20 = 2,05. Při podílu na standardizovaného pojištěnce 4 000 Kč činí měsíční příjem pojišťovny na tohoto pojištěnce 2,05 × 4 000 = 8 200 Kč; byl-li u pojišťovny pojištěn všech 12 měsíců při stejném indexu i podílu, je roční příjem 98 400 Kč. Při zajišťovací konstantě 300 000 Kč by se stal nákladným pojištěncem, pokud by úhrada za něj v roce překročila 398 400 Kč; z přesahu do 1 500 000 Kč (5C) by pojišťovně náleželo 80 %, tj. nejvýše 1 200 000 Kč (4C), a z části úhrady převyšující 1 898 400 Kč (příjem + 6C) navíc 95 % (§ 21a odst. 2).

#### F. Kazuistika

**1. Modelová situace.** Pojištěnka s chronickým onemocněním změnila v lednu zdravotní pojišťovnu. Nová pojišťovna ji v únorovém sdělení správci zvláštního účtu nezařadila do příslušné FNS, protože ve svých datech neměla žádná vyúčtování léčiv; dosavadní pojišťovna údaje o spotřebě léčiv předala opožděně. Nová pojišťovna se domáhá dorovnání příjmu z přerozdělování za únor a namítá i to, že ministerstvem stanovená hranice spotřeby léčiv 400 ODTD byla nezákonná.

**2. Právní otázka.** (a) Podle jakých údajů měla nová pojišťovna pojištěnku klasifikovat? (b) Lze dodatečně opravit počty pojištěnců ve FNS? (c) Je hranice 400 ODTD přípustná?

**3. Použitelné právo.**
- *Komentovaná příloha:* oddíly D, O a Q–R přílohy č. 2.
- *Související ustanovení téhož zákona:* § 20 odst. 8 (předání údajů o spotřebě léčiv při změně pojišťovny), § 20a odst. 2 písm. d), § 21 odst. 1 písm. a), d) a e) a odst. 3 (zpětná úprava počtů pojištěnců s odstupem 6 měsíců), § 21f písm. a) (prováděcí předpis k nastavitelným parametrům).
- *Související předpisy:* prováděcí vyhláška podle § 20 odst. 8 o rozsahu, způsobu a lhůtách předávání údajů; zákon č. 48/1997 Sb. (změna zdravotní pojišťovny, seznam léčiv).

**4. Subsumpce.** (a) Podle oddílu O se započítávají léčiva s datem vyúčtování v posledních 12 měsících; u pojištěnky, která přestoupila, tvoří podklad údaje předané dosavadní pojišťovnou podle § 20 odst. 8. Bez nich nemohla nová pojišťovna podmínku spotřeby ověřit. (b) Systém počítá s tím, že počty pojištěnců známé pojišťovně v měsíci přerozdělování se s odstupem 6 měsíců porovnají s pozdějším stavem a správce zvláštního účtu o rozdíly upraví počty (§ 21 odst. 1 písm. d) a odst. 3). (c) Oddíl D připouští hranici jen v rozmezí 121–365; hodnota 400 je mimo zákonné meze.

**5. Řešení.** (a) Nová pojišťovna měla po obdržení údajů pojištěnku do FNS zařadit; za únor se rozdíl promítne mechanismem § 21 odst. 3 při přerozdělování o 6 měsíců později, nikoli samostatným nárokem na dorovnání. Vůči dosavadní pojišťovně lze řešit porušení povinnosti podle § 20 odst. 8 (případně dozorově). (b) Ano, v rámci mechanismu šestiměsíční úpravy. (c) Hranice nad 365 by byla v rozporu se zákonem a prováděcí předpis by v tomto rozsahu nemohl obstát; v reálné situaci je však třeba nejprve ověřit skutečnou hodnotu stanovenou vyhláškou.

**6. Varianty.** (a) Pojištěnka v minulém roce užívala léčivo jen 100 dní — podmínka spotřeby není splněna při jakékoli přípustné hranici (min. 121). (b) Pojištěnka splňuje podmínky dvou FNS, mezi nimiž platí vyřazovací pravidlo — zařadí se jen do skupiny, kterou pravidlo nevylučuje. (c) Pojištěnka je zařazena ve FNS i v kombinaci FNS s věkovou skupinou — do indexu se započte i korekce pro souběh (oddíl Q).

#### G. Protiargumenty a rizika

- *„Algoritmus je jen technická metodika, nikoli právní norma.“* Neutralizace: příloha je součástí zákona; odchylky od ní (jiný vzorec, jiné referenční dny) jsou porušením zákona, nikoli metodickou volbou.
- *„Ministerstvo může parametry stanovit libovolně.“* Neutralizace: oddíly C a D obsahují zákonná rozmezí a oddíl E podmiňuje zařazení FNS a kombinací testy stability a předpovědní síly.
- *Slabá místa:* (1) vzorce v elektronické konsolidaci jsou formátově poškozené (chybějící závorky, inverze, absolutní hodnoty) — pro výpočet je nutné vycházet z publikovaného znění ve Sbírce; (2) zákon neurčuje konkrétní statistický test významnosti v oddílu E; (3) rozdílné referenční dny a datové zdroje v oddílech G/H (výpočet parametrů) a N/O (měsíční klasifikace) mohou vést k odlišnému zařazení téhož pojištěnce; (4) výsledky závisejí na kvalitě dat předaných pojišťovnami a ocenění nákladů Ústavem zdravotnických informací a statistiky (§ 20 odst. 7).
- *Ochrana dat:* anonymní identifikátor chrání identitu pojištěnce, nikoli však ve vztahu ke správci registru; při práci s daty je třeba respektovat pravidla zpracování zvláštních kategorií osobních údajů (údaje o zdraví).

#### H. Praktický závěr

Příloha č. 2 je úplný zákonný algoritmus přerozdělování: ministerstvo jednou ročně vypočte nákladové indexy a zajišťovací konstantu z dat za poslední uzavřený rok, pojišťovny každý měsíc klasifikují pojištěnce a správce zvláštního účtu rozdělí prostředky podle počtu standardizovaných pojištěnců. Spory se typicky týkají klasifikace pojištěnců, kvality dat a zákonnosti nastavitelných parametrů.

**Checklist (advokát / soud / správní orgán / adresát normy):**
- [ ] Rozlišit fázi: výpočet parametrů (oddíly F–M, ministerstvo) × měsíční klasifikace (oddíly N–P, pojišťovny).
- [ ] Ověřit, zda nastavitelné parametry stanovené vyhláškou leží v zákonných rozmezích (CK 70–250; hranice spotřeby 121–365; podíl nákladného přerozdělování 5–15 %).
- [ ] U FNS a kombinací ověřit splnění podmínek stability a předpovědní síly (oddíl E).
- [ ] U konkrétního pojištěnce zkontrolovat věkovou skupinu, FNS (definiční seznamy, hranice, vyřazovací pravidla, datum vyúčtování) a kombinace.
- [ ] Spočítat nákladový index (1 + věk + FNS + korekce) a příjem (index × podíl na standardizovaného pojištěnce).
- [ ] Při změně pojišťovny ověřit předání údajů o spotřebě léčiv (§ 20 odst. 8) a uplatnění šestiměsíční korekce (§ 21 odst. 3).
- [ ] Vzorce ověřovat podle znění publikovaného ve Sbírce, nikoli podle textové konsolidace.

**Typicky rozhodné důkazy / podklady:** prováděcí vyhláška s nastavitelnými parametry pro dané období, vypočítané parametry a podkladová data zaslaná podle § 20c, sdělení pojišťovny podle § 21 odst. 1, výstupy elektronické aplikace podle § 21 odst. 2, údaje o spotřebě léčiv a datech vyúčtování, záznamy o předání údajů mezi pojišťovnami, zápisy Dozorčího orgánu.
