# SHL Gulddrömmen – projektbibel (2026-10-27)

## Källor och versioner
- Repository: olikid/shl-gulddrommen, standardgren main.
- Publicerad huvudsida: index.html (hämtad blob 19fd1c3fc78d95a9364046bf489d9a1581cb3d19).
- Utvecklingssida: development/index.html (hämtad blob be47aa79e81c5a001d55f8e0fd8c9305bfbbbc02).
- Användarens versionsstatus: BETA 1.2.2 är senaste stabila baslinjen; BETA 1.3 utvecklas. Tidigare BETA 1.2.1 är äldre stabil version. Versionsetiketten i development/index.html visar fortfarande "BETA 1.0.2" trots BETA 1.3-kommentarer och funktioner i koden. Versionsnummer ska verifieras mot kod och Git-historik, inte enbart sidrubriken.
- Spel: https://olikid.github.io/shl-gulddrommen/ ; utveckling: https://olikid.github.io/shl-gulddrommen/development/

## Bekräftad kodstruktur
- Fristående HTML-filer med inbäddad CSS och JavaScript.
- Laglista T, matchschema F, 52 omgångar, matchsimulering, taktiska val och animerad rink.
- Tabell beräknas av standings(history); 3 poäng för ordinarie seger, 2/1 vid övertid.
- Renderfunktion styr sidor som home, match, preview, result, table, career, archive, news och end.
- Speltillståndet g sparas via update() i localStorage-nyckeln shl_gulddrommen_development. Separat karriärarkiv: shl_gulddrommen_career_archive_v1.
- nextSeason() sparar säsongshistorik och skapar klubberbjudanden.
- BETA 1.3-kod omfattar worldState(), worldStreak(), worldEvent(), worldReplySet(), worldAnswer(), worldPressCard(), nyhetsflöde samt personalNewsCards() och leagueNewsCards().
- Presskonferenssvar påverkar moral, fans och styrelse; händelser bygger bland annat på seger-/förlustsviter, bottenläge och tabellplacering.
- Nyhetscentralen visar personliga nyheter och liganyheter; befintlig återgångsknapp finns sist i nyhetssektionen. returnToManagerHub() finns redan.

## Beslut och kommande arbete
1. Nästa önskade ändring: en tydlig tillbaka-till-Managerhubben-knapp högst upp i Nyhetscentralen, helst sticky under scrollning, utan att återställa speltillstånd.
2. Bevara stabila versioner; ändra bara development/index.html tills testad.
3. Tränarscore: över 75 grönt, 50–75 befintligt blått, under 50 gult och under 40 kraftigare rött (önskad skala; kontrollera exakta kodtrösklar före ändring).
4. Tränarscore följer tränaren över säsonger och klubbyten; supporter- och styrelsepress ska reagera på aktuell klubbform.
5. Personliga nyheter och en levande hockeyvärld är prioriterat; användaren tycker nuvarande nyhetsinnehåll ser bra ut.

## Säkerhetsregler
- Läs senaste fil och blob-SHA före varje ändring.
- Ändra aldrig huvudfilen index.html av misstag.
- Skapa helst separat commit för varje funktion och testa mobilnavigation samt sparade säsonger.
- Denna projektbibel är en översikt, inte en kopia av fullständig källkod.


## Milstolpe: BETA 1.3 stabil återställningspunkt (2026-10-27)
- Användaren har speltestat BETA 1.3 och bekräftat att spelet fungerar bra och börjar bli roligt.
- **Fryst GitHub-branch:** `stable/beta-1.3-2026-10-27`.
- **Exakt snapshot-commit:** `72da3610fa0be1c3b49716b9278e3050e747aa28`.
- **Snapshot-fil:** `development/index.html` (blob `4a3633fa94de14b4295c24aa1771224923466a8f`).
- Den frysta branchen ska inte ändras. Framtida utveckling sker i `development/index.html` på `main`, utan att ändra `index.html` eller snapshot-branchen.
- Bekräftade funktioner: sticky tillbaka-knapp i Nyhetscentralen, taktisk scouting och förutsägbarhet efter upprepade taktikval, fasta matchbeslut och sticky scoreboard, kompakt TV/assistent och power-ups, aktiva power-up-effekter visas även när menyn stängs, kompakta resultatlistor, separata kort för slutresultat och omgångens matcher, samt nästa-match-genvägar på resultatsidan (utom omgång 52).
- Detta är en användarverifierad stabil baslinje, inte ett fullständigt automatiserat regressionstest.

## Officiell release 2026-10-27
- BETA 1.3 publicerad som officiell version i rotfilen `index.html` på `main`.
- Release-commit: `b9b7f1d06ef5c2efacd6f4eb9e7d96699bb23681`.
- Källkod från frysta `stable/beta-1.3-2026-10-27` (endast synlig versionsetikett uppdaterad till BETA 1.3 OFFICIELL VERSION).
- Publik spellänk: https://olikid.github.io/shl-gulddrommen/
- Utvecklingslänk: https://olikid.github.io/shl-gulddrommen/development/
- Notera: releasefilen använder fortfarande localStorage-nyckeln `shl_gulddrommen_development` för att bevara befintliga sparade karriärer på samma origin. Ändra inte utan planerad migration.

## Versionspolicy för utvecklingsversionen (beslut 2026-10-29)
- Användarens uttryckliga önskemål: varje sparad kodändring i `development/index.html` ska höja det synliga versionsnumret med ett steg, så att varje testversion kan identifieras.
- Aktuell startpunkt: **BETA 1.4.1** (införd 2026-10-29; endast versionsetiketten ändrades).
- Nästa koduppdatering ska märkas **BETA 1.4.2**, sedan **BETA 1.4.3**, osv. Större funktionella milstolpar kan få en ny minor-version efter uttryckligt beslut.
- Versionsetiketten ska alltid vara synlig i spelets header, och varje commit ska ha en tydlig beskrivning av vad som ändrats.
- Behåll den separata cache-busting-parametern i testlänken; den är inte samma sak som det synliga versionsnumret.
- Endast `development/index.html` får ändras för utvecklingsuppdateringar. Officiella `index.html` (BETA 1.3.4) ska förbli orörd utan uttryckligt godkännande.
- Nuvarande godkänd logotyp: **Swedish Hockey Arcade**, kompakt textlogga i vit/blå stil, blå accent `#17ADF5`; minimalistisk SHA-symbol är separat variant. Orange är inte längre huvudaccent för loggan.

## Officiell release: BETA 1.4.1 (2026-10-29)
- Användaren godkände uttryckligen BETA 1.4.1 som ny officiell sparad/släppt version.
- Officiell fil `index.html` på `main` uppdaterad med innehållet från `development/index.html` (BETA 1.4.1); synlig etikett bytt till `BETA 1.4.1 · OFFICIELL VERSION`.
- Release-commit: `bc4d043503623bcdd04967843a22739a59ef51bb`.
- Fryst återställningsbranch: `stable/beta-1.4.1-2026-10-29` (pekar på release-commit).
- Föregående BETA 1.3.4 har separat fryst backup `stable/beta-1.3.4-2026-10-27`.
- Fortsatt utveckling enbart i `development/index.html`, nästa synliga version **BETA 1.4.2**. Ändra inte officiella `index.html` förrän användaren godkänner nästa release.

## Versionspolicy – stora och små ändringar (beslut 2026-10-29)
- Användaren vill skilja mellan större funktionella uppdateringar och små ändringar.
- Nuvarande utvecklingsversion: **BETA 1.4.3**. Nästa mindre ändring blir **BETA 1.4.3.1**, därefter **BETA 1.4.3.2**, osv. Nästa större förbättring blir **BETA 1.4.4**.
- Alla koduppdateringar ska ändra synlig versionsetikett i spelet. Varje commit får en beskrivande ändringsrad.
- Detta ersätter tidigare regel om att varje ändring måste öka tredje versionssegmentet; små patchar ökar fjärde segmentet.
- Officiell version förblir **BETA 1.4.1** tills användaren uttryckligen godkänner en ny release.


---

# AKTUELL PROJEKTSTATUS — 2026-10-31 (ersätter äldre statusuppgifter ovan)

> **Läs detta avsnitt först.** Äldre avsnitt ovan bevaras som historik. Deras påståenden om "aktuell version", "nästa ändring" och "officiell version" är historiska och gäller inte längre.

## Verifierad versionsstatus och källor
- **Projekt-/spelvarumärke:** Swedish Hockey Arcade (tidigare SHL Gulddrömmen).
- **Repository:** `olikid/shl-gulddrommen`, branch `main`.
- **Aktuell utvecklingsversion:** **BETA 1.5.0.5**, verifierad både genom synlig versionssträng i `development/index.html` och senaste spelkod-commit `37a7ac0295f6910e90544848a5c85ad248de1d7a` (2026-10-31 01:16 UTC).
- **Senast officiellt publicerade version:** **BETA 1.4.5.100**, release-commit `d1e73c11d` (2026-10-31 00:46 UTC), bekräftad i commit-historik för `index.html`. Ändra aldrig officiella `index.html` utan uttrycklig instruktion från användaren.
- **Aktuell utvecklingsfil:** `development/index.html`. Den synliga versionssträngen innehåller `BETA 1.5.0.5 · UTVECKLINGSVERSION`.
- **Officiell URL:** https://olikid.github.io/shl-gulddrommen/
- **Utvecklings-URL:** https://olikid.github.io/shl-gulddrommen/development/
- **Projektbibel:** `PROJECT_BIBLE.md`. Uppdateras som en del av varje framtida spelversionsändring.
- Det finns äldre frysta återställningsbrancher för BETA 1.3, 1.3.3, 1.3.4 och 1.4.1. För BETA 1.4.5.100 finns en verifierad release-commit; en särskild fryst branch för denna release är **inte** verifierad.

## Säker utvecklingsprocess — användarens uttryckliga beslut 2026-10-31
1. **Endast `development/index.html` får ändras som spelkod**, såvida användaren inte uttryckligen godkänner annan fil. Dokumentationsfilen `PROJECT_BIBLE.md` får uppdateras löpande enligt detta uppdrag. Tillhörande framtida bildresurser kräver separat överenskommelse om sökväg/uppladdning.
2. **Rör aldrig `index.html`**, den officiella versionen, utan ett tydligt, uttryckligt godkännande för just den releasen.
3. Före varje kodändring: läs aktuell utvecklingsfil och dess blob-SHA, kontrollera aktuell synlig version och jämför mot senaste GitHub-commit.
4. Varje spelkodändring får en **ny synlig BETA-version**, med beskrivande Git-commit. Mindre korrigeringar höjer fjärde sifferledet; större milstolpar kan höja tredje eller annat led enligt överenskommelse. Börja från verklig aktuell version, inte från gamla projektbibelnoteringar.
5. **Samma uppdatering ska dokumenteras i projektbibeln**: version, datum, vad som ändrats, berörda funktioner, risker/teststatus och gärna commit-SHA. GitHub-commits för kod och projektbibel kan vara separata; dokumentera båda och rapportera om dokumentationen av någon anledning inte kunde uppdateras.
6. Undvik att ändra `localStorage`-nycklar, nollställa karriärer, skriva över frysta återställningspunkter eller ändra matchflödet oavsiktligt. Kontrollera mobil-UI, sparad karriär och JavaScript-syntax när möjligt; skilj på kodgranskning och faktiskt webbläsartest.
7. **Projektbibeln är den kontinuerliga överlämningen mellan chattar.** Kontrollera den och aktuell kod vid ny chatt; äldre minnesuppgifter och äldre versionstexter får inte övertrumfa GitHub.

## BETA 1.4.5.100 — verifierad stabil release
- BETA 1.4.5-serien innehöll omfattande justeringar av Managerhubben, karriärvyn, visuella effekter, matchstatistik och förtroendeindikatorer.
- I sena patchar: fyra kompakta matchstatistikrutor, vinst/förlust-differens, förfinad karriärhistorik och guldmarkering för förstaplats.
- Karriärens förtroendefärger justerades i BETA 1.4.5.91: **85+ grönt, 55+ blått, 40+ gult, under 40 rött**. Denna senare skala ersätter äldre önskemål om 75/50/40 i historiken ovan.
- BETA 1.4.5.100 publicerades officiellt innan BETA 1.5-utvecklingen började.

## BETA 1.5 — verifierad utvecklingshistorik
- Första försöket med BETA 1.5 introducerade tränaridentitet, porträttval och minne för karriärhändelser, men gav ett JavaScript-startfel. Efter hotfix-försök gjordes **nödåterställning till verifierad BETA 1.4.5.100** (commit `7824fea5a`).
- BETA 1.5 byggdes därefter upp försiktigare med tränaridentitet och befintlig sparningsmekanism (commit `d1ef78d2a`).
- BETA 1.5.0.1: tillfällig redigering av tränaridentitet under pågående karriär.
- BETA 1.5.0.2–1.5.0.3: återställd kompakt klubbruta och dess tidigare position/stil.
- BETA 1.5.0.4: synlig versionsetikett synkroniserad.
- BETA 1.5.0.5: fyra illustrerade porträttval för tränare, med reservvisning när bildresurser saknas.
- Verifierat i aktuell kod: `g.coach15` innehåller namn, ålder, nationalitet, porträttindex och `events`; profilens CSS och porträttval finns i `development/index.html`.
- **Begränsning:** inga separata porträttbildfiler finns i GitHub-trädet vid kontroll 2026-10-31. Kontrollera verklig visning i webbläsare innan funktionen kallas visuellt färdig. Kodgranskning är inte ett fullständigt funktionstest.

## Beslutade tränarkaraktärer och NÄSTA STEG
- Användaren har valt en uttrycksfull, illustrerad karaktärsstil framför enkla emojis eller alltför själlösa illustrationer.
- Fyra tränarkaraktärer/porträtt ska finnas i tränarvalet.
- Karaktärerna ska **börja utan kavaj**, med vit skjorta eller piké enligt godkänd visuell riktning; inga oönskade externa företagslogotyper på kläderna.
- **Karriärprogression genom kläder:** spelaren ska senare kunna **köpa/låsa upp en kavaj i spelet** och visuellt avancera från enklare tränarklädsel till mer uppklädd. Detta är ett **planerat system**, inte implementerat i BETA 1.5.0.5.
- **Nästa konkreta arbetssteg:** färdigställ/integrera de fyra valda tränarporträtten som fungerande resurser och planera/implementera klädprogressionen (börja i skjorta, köp kavaj), med versionshöjning och projektbibeluppdatering. För bildfiler krävs godkänd resursstrategi eftersom nuvarande repo saknar sådana.
- Fortsätt bevara redan fungerande matchskärm, karriär, nyhetsflöden, supporter-/styrelsepress, coachscore och sparningar.

## Ändringslogg för projektbibeln
- **2026-10-31 — dokumentationssynk till BETA 1.5.0.5:** verifierat senaste utvecklingscommit, senaste officiella release, kodens tränarprofil och avsaknad av separata bildresurser. Infört obligatorisk dokumentationssynk vid varje framtida versionsändring. Ingen spelkod eller officiell version ändrad.

- **2026-10-31 — BETA 1.5.0.6:** Användaren laddade upp fyra porträtt i `assets/Coaches/coach_0.webp`–`coach_3.webp` (observera stort C). Utvecklingsfilen kopplades till dessa exakta sökvägar både i porträttvalet och tränarprofilens huvudbild; synlig version höjdes till 1.5.0.6. Spelkod-commit `b659b5b95f5ff7230ebf756d4801029a254b7e13`. Endast `development/index.html` ändrad som spelkod, officiell `index.html` orörd. GitHub-kodkontroll genomförd; visuell webbläsartest återstår. Nästa steg: verifiera porträtten i mobilvyn och utveckla köpbar kavaj/klädprogression.

- **2026-10-31 — BETA 1.5.0.7:** Användarens mobilskärmbilder visade att de fyra tränarporträtten var för hårt beskurna. Ändrat CSS från `object-fit:cover` till `object-fit:contain`, placerat hela figuren mot nederkant och ökat porträttvalens höjd från 110 till 132 px med matchande mörkblå bakgrund. Ändringen gäller även huvudprofilbildens bildpassning. Kodcommit `4d0d0a0aecc7718c050b734ed1ca9d570acb524b`. Officiella versionen orörd. Mobilvisuell återtest av användaren återstår.

- **2026-10-31 — BETA 1.5.0.8:** Användaren godkände stora porträttväljaren i 1.5.0.7 men påpekade att lilla profilbilden fick för mycket tomma sidmarginaler. Endast lilla profilbildens CSS fick `object-fit:cover;object-position:center 22%`; stora porträttväljaren behåller `contain`. Kodcommit `38af701f49babf2ac3f70031019462ef121e527f`. Officiell version orörd. Mobiltest av användaren återstår.

- **2026-10-31 — BETA 1.5.0.9:** Managerhubbens förhandsvisning av 'Tidigare säsonger' har fått samma karriärsäsongskortstruktur och färgindelning som karriärsidans säsongslista. Länken 'Alla säsonger' går direkt till `page:'career'` och scrollar till säsongskorten; den gamla separata `archive`-sidans rendering är borttagen, och gamla sparningar med `page:'archive'` omdirigeras till karriärsidan. Ingen ändring i sparade säsongsdata eller officiell version. Kodcommit `aa7b18fbef79684d13a560e725a2e3dfe9cce5bd`. Visuellt mobiltest återstår.

- **2026-10-31 — BETA 1.5.0.10:** Finjusterat endast lilla tränarprofilbildens vertikala position från `object-position:center 22%` till `center 10%` så att motivet flyttas lite nedåt och får mer luft upptill. Stora porträttväljaren och övriga karriärvyn oförändrade. Kodcommit `7b2baac774913b4155dc0b8166d13ad07b1917d8`. Officiell version orörd. Mobiltest av användaren återstår.

- **2026-10-31 — BETA 1.5.0.11:** Användarbeslut: tränarens identitet är permanent efter att karriären startats. Tagit bort knappen 'Ändra tränare (tillfälligt)' på aktiv karriär, begränsat profilredigering till första karriärstartens setup, låst `coach15Set` under aktiv karriär och sparat `coach15`/`coach15Locked` vid säsongsstart, nästa säsong och uppsägning/klubbbyte. Gamla sparningar med aktiv karriär får ingen redigeringsknapp; befintliga profiluppgifter bevaras. Kodcommit `98ff22a13b2bc6c482584fbdea1f8351740f132a`. Officiell version orörd. Användartest återstår. **Nästa designsteg:** garderob/kavaj som låsbart karriärframsteg, utan att ändra tränarens grundidentitet.

- **2026-10-31 — BETA 1.5.1.0:** Infört första versionen av personlig plånbok (Mynt) i Managerhubben: startsaldo 0 för nya och befintliga karriärer utan plånbok, beständig wallet i development-localStorage, lön 100 Mynt var 5:e omgång (omgång 5–50), +5 Mynt per vinst, +15 vid 3 raka, +25 vid 5 raka och +50 vid 10 raka. Bonus vid exakt uppnådd svit; förlust bryter. De tre senaste transaktionerna visas i plånboken. Vid nästa säsong omförhandlas lönen efter slutplacering (+150/+100/+60/+20/0/−50), golv 75 och tak 800 Mynt, och plånboken följer med vid ny säsong/klubbbyte. För gamla sparningar startar plånboken från aktuell omgång utan retroaktiv lön. Inga köp eller garderob ännu; klubbtrohetsbonus ännu inte implementerad. Kodcommit `a93a42a6f2780c7c0db0f68e8376e8f4812e782f`. Officiell root orörd; användartest krävs.

- **2026-10-31 — BETA 1.5.1.1:** Utökat befintlig plånbok med knappen 'ÖPPNA MIN EKONOMI' och separat `wallet`-sida från Managerhubben. Visar Mynt-saldo, fast lön var femte omgång, omgångar till nästa utbetalning, segersvit, ackumulerade inkomster/utgifter baserat på sparad transaktionslista (upp till 60 senaste poster), transaktionshistorik med säsong/omgång och framtida tillgångar: gratis standardboende, ingen bil, standardkläder. Ingen debitering eller köp ännu. Befintlig wallet och sparad karriär bevaras. Kodcommit `f5cb6be9ee2a02e00f3406089249fe7994496a92`. Officiell version orörd; användartest kvarstår.

## Framtida funktion – Ekonomisk stress (idé från användaren, 2026-10-31)
Tränarens privatekonomi ska i en framtida version påverka matchbeslut och i förlängningen sannolikheten för matchresultat. Hög ekonomisk stress kan ge fler dåliga taktiska beslut och sämre fokus/stresshantering. Stress bör bedömas utifrån saldo, lön och löpande levnadskostnader, inte enbart saldo. Trygg ekonomi ska innebära normal förmåga, inte garanterad seger; även ekonomisk kris ska bara påverka sannolikheter och aldrig avgöra match automatiskt. **Endast framtida designidé – inte implementerad.** Förankra exakta effekter och balans med användaren innan kodändring.

- **2026-10-31 — BETA 1.5.1.2:** Ersatt stora plånbokskortet på Managerhubben med en liten högerjusterad klickbar Mynt-indikator (🪙 och aktuellt saldo) som öppnar befintlig ekonomisida. Plånboksdata, löner och bonusar oförändrade. Ingen övrig omdesign av Din klubb/tränarprofil ännu. Kodcommit `59cd2121c296a885141b142712af74995397ec7f`. Officiell version orörd; visuell användarverifiering återstår.

- **2026-10-31 — BETA 1.5.1.3:** Fixat regression från 1.5.1.2: plånboksikonen lades först in som första barn i `#app` och bröt `main.managerhome #app > .card:first-child`-reglerna för kompakt DIN KLUBB. Myntikonen placeras nu i `.gamebranding`, och gammal ikon tas bort vid render för att undvika dubbletter. Klubbkortet är åter första elementet i `#app` och behåller sina befintliga kompaktregler. Kodcommit `9e9a4faa55032069cdd137c30c2e8bd46b3f5504`. Officiell version orörd, behöver användartestas.

- **2026-10-31 — BETA 1.5.1.4:** Managerhubben: kombinerat tidigare DIN KLUBB-kortet och separata tränarprofilen till ett kort med tränarporträtt, fullständigt namn, liten nationalitetsflagga (Sverige/Finland/Norge/Danmark/Kanada/USA eller jordglob), ålder, litet klubbmärke, klubbnamn, placering, poäng, målskillnad, tränarscore och form. Tränarens header är klickbar till karriärsidan; placeringens befintliga tabellknapp behålls. Tagit bort separat 'MIN MANAGERKARRIÄR'-knapp och separat tränarprofilkort på startsidan. Myntikonen ligger kvar i branding. Kodcommit `6dbbe702b08fe3fefc083300b96a3c876cd2092e`. Officiell root orörd. Användartest och mobil-layoutkontroll behövs.

- **2026-10-31 — BETA 1.5.1.5:** Finjusterat det sammanslagna tränarkarriärkortet på Managerhubben: mindre inre padding, något mindre porträtt (76×85 px), kortare avstånd mellan rubrik, identitet, klubb, statistik och form. Ingen ändring i logik eller övrig layout. Kodcommit `3c81573cfd72e75c60c3d44328d63cf4ec603381`. Officiell version orörd, visuell användarverifiering återstår.

- **2026-10-31 — BETA 1.5.1.6:** Flyttat lilla klickbara Mynt-indikatorn från `.gamebranding` till övre högra hörnet i första tränarkarriärkortets `.cap`, med flexlayout. Justerat tränarporträttets storlek till 73×83 px och `object-fit:contain` för att ge mer luft över huvudet; tajtat kortets marginaler/padding och avstånd ungefär ytterligare 5 %. Ingen ändring av ekonomi- eller matchlogik. Kodcommit `12b210c6172c1c94bfe32c112fb8f184023ed55c`. Officiell root orörd; användartest återstår.

- **2026-10-31 — BETA 1.5.1.7:** Återställt tränarporträttets beskurna fyrkantiga stil efter att `object-fit:contain` i 1.5.1.6 visade hela överkroppen för litet. Nu 78×85 px, `object-fit:cover`, `object-position:center 10%`, 12 px hörnradie. Behåller myntindikator i tränarkortets övre högra hörn och kompakt layout. Kodcommit `08dc6d8eabf92ade1b1ffb9a15756255c34fcee3`. Officiell root orörd; visuell användarverifiering återstår.

- **2026-10-31 — BETA 1.5.1.8:** Minskat vertikalt mellanrum mellan tränarkortets rubrikrad (med Mynt) och porträtt/namn genom min-height 24 px, margin-bottom 0 och profilhuvud margin-top -3 px. Övrig layout och porträttbeskärning oförändrade. Kodcommit `3296136d1ef42da06987b36e83f16e7f0c9fb57a`. Officiell root orörd.

- **2026-10-31 — BETA 1.5.1.9:** Efter användarens annoterade skärmbild kapat yttre luft i första tränarkarriärkortet: top-padding 5 px, bottom-padding 4 px, rubrikradens min-height 22 px och formradens slutmarginal/linjehöjd minskad. Porträtt, typografi, statistik och myntposition behållna. Kodcommit `5b3b8b3e791c591bddc5c19d0c7132c05fc7bbf9`. Officiell root orörd.

- **2026-10-31 — BETA 1.5.1.10:** Justerat första tränarkarriärkortets rubrikrad med explicit flex-centrering, line-height 1 och lätt uppflyttning så `OMGÅNG 52/52` linjerar med Mynt-knappen; flyttat upp profilhuvudet ytterligare marginellt. Ingen spelmekanik ändrad. Kodcommit `307f392d139bc1ed0c7558f449188cbfc59331d4`. Officiell root orörd.

- **2026-10-31 — BETA 1.5.1.11:** Efter annoterad skärmbild justerat första tränarkortets rubrikrad upp 4 px och Mynt-knappen ned 7 px relativt rubriken, för att möta deras överkanter. CSS-only; officiell root orörd. Kodcommit `46caf53c0ade5df24930fddcc7989ac9d2b244a1`.

- **2026-10-31 — BETA 1.5.2.0:** Ny design för sidan Tränarkarriär med porträtt, tränaridentitet, nationalitet, klubb och aktuell säsong i samma visuella språk som den godkända managerhub-profilen, men med luftigare egen karriärlayout. Behåller statistik, utfällbara sektioner för matchstatistik/förtroende/historik, tidigare säsonger och karriärval. Ny sticky navigationsrad `← TILL MANAGERHUBBEN` som följer med scrollningen. Kodcommit `c41c91417b517e994adbdd52f0627df0e6cf069e`. Officiell root orörd; användartest återstår.

- **2026-10-31 — BETA 1.5.2.1:** Tränarkarriärens sticky navigationsrad minskad till en innehållsanpassad vänsterställd tillbaka-knapp. Högertexten `MIN TRÄNARKARRIÄR` borttagen och navigationsbehållarens bredd/padding reducerad; sticky scrollfunktion behållen. Kodcommit `0ec10918a09e82b94301c04d217d86077e06d71f`. Officiell root orörd.

- **2026-10-31 — BETA 1.5.2.2:** Flyttat tränarkarriärens kompakta tillbaka-till-managerhubben-knapp från sticky topp till flytande fast position i nedre högra hörnet. Behåller knappens utseende, säkerhetsmarginal för iPhone safe area och extra sidbottenutrymme. Kodcommit `b64e16f44f4b0aa22c5ff434b9afc1004346eb81`. Officiell root orörd.

- **2026-10-31 — BETA 1.5.2.3:** Lagt till samma klickbara lilla Mynt-saldoindikator som på managerhubben i tränarkarriärsidans första profilkorts övre högra hörn. Använder befintliga `walletTiny()` och `walletGet()` och öppnar befintliga ekonomisidan; ingen ny ekonomi eller förändring av karriärdata. Responsiv rubrikrad. Kodcommit `59baf408d98382aee0dffe17760726f0af175457`. Officiell root orörd.

- **2026-10-31 — BETA 1.5.2.4:** Ersatt silverfärgad Mynt-emoji i gemensamma `walletTiny()` med inline-SVG föreställande en gyllene myntstapel och kronpräglat mynt. Påverkar både managerhubben och tränarkarriären. Saldo, klickfunktion och ekonomi oförändrade. Kodcommit `2128faad448d33ded015493f1042d7abca6a4ea8`. Officiell root orörd.

- **2026-10-31 — BETA 1.5.2.5:** Tagit bort kronpräglingen från det främre guldmyntet i gemensamma Mynt-ikonen, ersatt med diskret guldfärgad mitt. Gjort saldoknappen smalare med 24×22 px ikon, mindre horisontell padding och mellanrum mellan ikon/saldo. Gäller både managerhubben och tränarkarriären. Kodcommit `89129db8cabffbd4138e6a383afba493ff87475d`. Officiell root orörd.

- **2026-10-31 — BETA 1.5.2.6:** Lagt till diskret loopande CSS-animation med två förskjutna skarpa stjärnglimtar på den gemensamma guldmyntsikonen (`walletTiny`), med reducerad rörelse för `prefers-reduced-motion`. Ingen ändring av saldo eller ekonomi. Kodcommit `d3eba9183d8cd0793cf9c335abb05f3b139dc7a7`. Officiell root orörd.

- **2026-10-31 — BETA 1.5.3.0:** Ombyggd tränarkarriärsida med kortare personligt profilkort (porträtt, identitet, klubb, Mynt, karriärtitel och tre meritmått); aktuell säsong separerad i eget kort med synliga match-/vinst-/förlustsiffror och utfällbart lagförtroende; karriärstatistik i fristående kort med matcher, segrar och poäng synliga utan dropdown. Tidigare säsonger, karriärval, flytande tillbaka-knapp och ekonomi bevarade. Karriärtitlar bygger på sparade säsonger och seriesegrar, utan påverkan på spelmekaniken. Kodcommit `629a29f4cf84286e4557d838791ecb986fbbcb2e` (efter korrigering av tränarscore). Officiell root orörd; användartest återstår.

- **2026-10-31 — BETA 1.5.3.1:** Visuell highlight av det fristående kortet `AKTUELL SÄSONG` på tränarkarriärsidan: tunn isblå border, subtil blå glow, lätt ljusgradient och ljusare rubrik. Befintliga guld-/grönfärgade statistikindikatorer och spelmekanik oförändrade. Kodcommit `3a9464c3e92710f5b3911d3c08c6e5d1d2e4bdfb`. Officiell root orörd.

- **2026-10-31 — BETA 1.5.3.2:** Försiktig komprimering av tränarprofilkortet på karriärsidan för att närma sig managerhubbens tajta profil: porträtt 74×81 px (70×78 på smala skärmar), mindre gap mellan porträtt och identitet, tätare etikett/namn/nationalitet, mindre avstånd till klubb och karriärtitel. Aktuell säsong och övriga kort oförändrade. Kodcommit `950315bef7e80a369ddd763b68a17df556282088`. Officiell root orörd.

- **2026-10-31 — BETA 1.5.4.0:** Första riktiga achievementsystemet: 13 utmärkelser i en egen mobilanpassad `Mina utmärkelser`-sida med kategorifilter, färgade nivåer (brons/silver/guld/diamant), upplåst/låst, framstegsräknare och engångsbelöningar i Mynt. Tränarprofilens titel öppnar galleriet. Sparas i `g.arcadeAwards` med `unlocked` och `bestStreak`, vilket följer karriären över klubbyten. Befintlig säsongshistorik kan ge serie-, topp 3-, klubblojalitets- och matchutmärkelser; segersvit följs via befintlig wallet. SM-guld, krisräddning, hemvändning och klädinköp är definierade men kräver framtida spårning/funktioner innan de kan låsas upp. Guldtränare är nu reserverad för SM-guld; två grundseriesegrar ger titeln Seriespecialist. Ingen retroaktiv sammanblandning av grundseriesegrar med SM-guld. Första implementationscommit `0fbd1a6431dcbba1c1cc7baaf15e4a7775df8316`. Officiell root orörd.

- **2026-10-31 — BETA 1.5.4.1:** Tränarprofilens utmärkelse-UI ombyggt: tränartitel visas åter som separat titel; under profilstatistiken finns en flex-wrap-samling med individuella klickbara, nivåfärgade medaljkort för alla upplåsta achievements. Samtliga medaljer öppnar achievementsidan. En separat kompakt `VISA ALLA →`-knapp sitter i samlingens rubrikrad. Ingen ändring av root. Kodcommit `474416207423439a7d6429525a4a32ba59cb70eb`.

- **2026-10-31 — BETA 1.5.4.2:** `Dina utmärkelser` på tränarprofilen är nu ett semantiskt `<details open>`-block: medaljsamlingen är utfälld som standard, rubriken och pilen fäller ihop/upp den, och `VISA ALLA →` ligger inne i det utfällda innehållet. Individuella medaljer fortsätter länka till galleriet. Kodcommit `3f49fc3bb5ad53d2b6dc28f129e43d379ac21415`; officiell root orörd.

- **2026-10-31 — BETA 1.5.4.3:** Visuell polering av tränarprofilens utmärkelse-dropdown efter skärmbild: `VISA ALLA` flyttad upp i samma rad som rubrik och dropdownpil, onödigt vertikalt tomrum borttaget, medaljer i jämnt fyrkolumners grid, mindre och mer läsbara medaljtexter utan aggressiv ordbrytning. Dropdown fortsatt öppen som standard och medaljer fortsatt klickbara. Kodcommit `c484c2a9b4a84ebee8f5c486d2a754635d76a419`. Officiell root orörd.

- **2026-10-31 — BETA 1.5.4.4:** Buggfix för achievements-dropdown: föregående version placerade `<summary>` inuti en `<div>`, vilket fick Safari att skapa en oönskad standardrad `Detaljer`. `<summary>` är nu direkt barn till `<details>`, `VISA ALLA` är separat positionerad i samma visuella rubrikrad. Öppen som standard, medaljer och klick bevarade. Kodcommit `39b7dcf9bd8b6eab904f4c753c4f4bdcacad7195`. Officiell root orörd.

- **2026-10-31 — BETA 1.5.4.5:** Tränarprofilens medaljdropdown polerad igen: separat `VISA ALLA`-knapp placerad i en gemensam wrapper ovanpå rubrikradens högra sida, så den ligger i samma rad och förblir synlig även när `<details>` är stängt. Rubrik/pil styr öppna/stäng; medaljer visas direkt under när utfälld. Kodcommit `b9819a5ae133337783914bbb55c5e214153fab6b`. Root orörd.

- **2026-10-31 — BETA 1.5.4.6:** Minskad onödig luft överst i tränarprofilens första kort med riktad CSS för topp-padding, rubrikrad och avstånd till porträtt. Myntknappen hålls i samma rubrikrad. Kodcommit `e2ce3691c16274443a20cc0faa113b9786bcda2d`. Officiell root orörd.

- **2026-10-31 — BETA 1.5.4.7:** `Dina utmärkelser` på tränarprofilen har fått en tydligare blå gradientpanel med kant, djup och kraftigare typografi, inspirerad av `Lagets förtroende`. Dropdownen är fortsatt öppen som standard, `VISA ALLA` och pilen ligger i högra delen och medaljerna i panelens innehåll. Kodcommit `d678613b0e4108d63276358c8ef4f6fa1306ffda`. Officiell root orörd.

- **2026-10-31 — BETA 1.5.4.8:** Utmärkelsedropdownen gjordes tunnare (50 px rubrikrad mot tidigare 64 px) och fick mer djup med blå gradient, innerljus och skugga samt kompaktare knappar. Kodcommit `056520a66d00db972ff8ba1ba8acfe2f19faf51c`. Officiell version orörd.

- **2026-10-31 — BETA 1.5.4.9:** Utmärkelseradens höjd minskad från 50 till 38 px (cirka 25 %), rubrik och Visa alla ändrade till normal meningsform, knapparna justerade för tunnare rad. Kodcommit `479d845f4835a70c72c5c8e983d882c05c992add`. Officiell root orörd.

- **2026-10-31 — BETA 1.5.4.10:** Utmärkelsernas dropdown på tränarprofilen är nu stängd som standard. Fördjupad blå gradient, tydligare innerljus och skuggor på panel och knappar. Kodcommit `6b8aeea0efb86294ebba36c993ab3383b7c6ac37`. Officiell root orörd.

- **2026-10-31 — BETA 1.5.4.11:** Mjukare kontrast i utmärkelsernas dropdownpanel: nedtonad blå gradient, mindre framträdande kant och subtilare glans/skuggor på panel och knappar. Stängd som standard kvarstår. Kodcommit `d9c40eebf518e75258aa2d6d6d2ab03503cce2ca`. Officiell root orörd.

- **2026-10-31 — BETA 1.5.4.12:** `Visa alla` på utmärkelsernas dropdown visas endast när menyn är öppen; stängt läge visar bara rubrik och pil för renare UI. Kodcommit `3e0fe037bea309c45d432b5f1f3558e5b6d9fc6a`. Officiell root orörd.

- **2026-10-31 — BETA 1.5.4.13:** `Visa alla` i utmärkelsernas dropdown får mjuk fade/slide/scale vid öppning och stängning (ca 0,3 s), med stöd för reduced-motion. Kodcommit `f2b87f5c3b4b465d026052e68bca14c4f006eca0`. Officiell root orörd.

- **2026-10-31 — BETA 1.5.4.14:** Utmärkelsesidan får visuellt omarbetade medaljkort med metalliska, präglade medalj-emblem och band, olika ytbehandling för brons/silver/guld/diamant, tydligare skillnad mellan upplåsta och låsta utmärkelser, samt mjukare typografi. Ingen ändring i upplåsningslogik eller sparformat. Kodcommit `bceeabcc8a05bdee47775295b9d2a8ba03685ca3`. Officiell root orörd.

- **2026-10-31 — BETA 1.5.4.15:** Trofésamling med individuella emblem, varierade medaljformer, karriärhistorik (säsong/klubb) och expanderbara beskrivningar. Kodcommit `d6d90ff49780892c8a63a334da1d69ac06e9c9d2`.
- **2026-10-31 — BETA 1.5.4.16:** Kompaktare medaljkort och emblem; detaljer (beskrivning, säsong, klubb, belöning) visas först vid tryck på kortet. Kodcommit `19d583ae9486bdabc09b252440291feb2c2ef750`. Officiell root orörd.

- **2026-10-31 — BETA 1.5.4.17:** Trofésamlingen visar tre kompakta medaljkort per rad i stället för två; anpassade emblem, typografi och mobilmarginaler. Expanderbara detaljer kvarstår. Kodcommit `6c912e262494bb37c45278451f98770adb50aae2`. Officiell root orörd.

- **2026-10-31 — BETA 1.5.4.18:** Utmärkelser organiseras i sex separata expanderbara kategoriboxar (Framgång, Form, Lojalitet, Karriär, Ekonomi, Livsstil), vardera med upplåst/total-räknare och tre medaljkort per rad. Tidigare filterknappar ersätts. Kodcommit `31dee02030b89b1159b9c8dae9ca70431ae505e5`. Officiell root orörd.

- **2026-10-31 — BETA 1.5.4.19:** Dynamisk sortering av utmärkelsesamlingen: upplåsta medaljer först inom varje kategoribox och kategoriboxarna sorterade efter antal upplåsta, fallande. Ursprunglig kategoriordning vid lika antal. Kodcommit `1a173e4760eff7f6198f03a48e5fb98bbe213804`. Officiell root orörd.

- **2026-10-31 — BETA 1.5.4.20:** Trofésamlingens progressbar har fått nedsänkt mörkblå skena, mjuk guldgradient och subtil glans. Tillbaka till tränarprofilen är nu en flytande, skrollföljande knapp nere till höger. Kodcommit `d46d0a6645fdfb872183541f830dfc3fb3170211`. Officiell root orörd.

- **2026-10-31 — BETA 1.5.4.21:** Förstärkt och tydligare progressbar på trofésidan efter feedback om att ändringen i .20 inte syntes/fungerade: 20 px nedsänkt skena, tydligare guldindikator, ökad kontrast och robusta CSS-överskrivningar. Flytande tillbaka-knapp oförändrad. Kodcommit `38f5f77cd460e977a4a30f5670cc5b3a9841ec06`. Officiell root orörd.

- **2026-10-31 — BETA 1.5.4.22:** Trofésamlingens progressruta komprimerad med mindre padding, tätare mellanrum, mindre siffertypografi och tunnare progressbar. Kodcommit `9db686301e5b8228d5b4a09975860062477ab121`. Officiell root orörd.
