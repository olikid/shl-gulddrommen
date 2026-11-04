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

- **2026-10-31 — BETA 1.5.4.23:** Ytterligare komprimering av trofésamlingens progresspanel: padding 8/12/9px, gap 2px, mindre typografi och 12px progressbar. Kodcommit `624bcabf7879d8383f94fd8d9dc5043029b6a5e4`. Officiell root orörd.

- **2026-10-31 — BETA 1.5.4.24:** Alla trofékategoriboxar har fått djupare blå gradient, mjukt innerljus, skuggor i flera lager, nedsänkt medaljyta och tydligare men diskreta rubrik-/räknardetaljer. Kodcommit `2d83e69328f6589ed1ea5fcdd281fa4da3371e2f`. Officiell root orörd.

- **2026-10-31 — BETA 1.5.4.25:** Slutresultatsrutan återgår till klassisk grön färgsättning vid seger och röd vid förlust. Spotlight-/glow-lager och animationer stängs av specifikt på resultatkortet; övriga matchvyer orörda. Kodcommit `5327e7d0398fa18661b59692b6a843e1fdb7e300`. Officiell root orörd.

- **2026-10-31 — BETA 1.5.4.26:** Fixat riktningen på färgtoningen i slutresultatskortet: segergrönt utgår från vinnande lagets faktiska vänster-/högersida, förlustrött från förlorande lagets sida. Kantaccent följer samma sida. Inga spotlights. Kodcommit `f8fabd0ed7b339f706046e37602c6bcb0408831c`. Officiell root orörd.

- **2026-10-31 — BETA 1.5.4.27:** Tomt tillstånd i tränarprofilens utmärkelsedropdown (`Dina första utmärkelser väntar`) fyller nu hela bredden i stället för att pressas in i en av medaljrutnätets fyra kolumner. Centrerad text och kompakt blå panel. Kodcommit `db8da00ed62ec7f40e23bdc61dd4910bff5f54a7`. Officiell root orörd.

- **2026-10-31 — BETA 1.5.4.28:** Tränartiteln i karriärprofilen är klickbar och öppnar en kompakt förklaringspanel som visar varför titeln erhållits och vägen till nästa milstolpe (3/8 säsonger, 2 seriesegrar eller SM-guld). Befintlig titelberäkning och sparformat oförändrade. Kodcommit `df6d86a6521a344ac3a24347193ae20e9a82dd03`. Officiell root orörd.

- **2026-10-31 — BETA 1.5.4.29:** Komprimerat tränarprofilkortet efter tillägget av klickbar tränartitel: mindre vertikala mellanrum kring titel, statistik och utmärkelser samt mindre kortpadding. Förklaringsfunktionen kvar. Kodcommit `381121e68f89a49fc61f9dd9fdc2ec86c5e58ee3`. Officiell root orörd.

- **2026-10-31 — BETA 1.5.4.30:** Riktad komprimering av övre delen av tränarprofilkortet: kortets topppadding, rubrikradens höjd/marginal, porträttets höjd och avståndet till tränartitel/statistik. Kodcommit `c210f2ad43ba255665cefc43c0656eb1ec58baa0`. Officiell root orörd.

- **2026-11-03 — BETA 1.5.5.34:** Säkerhetsfix för intermittenta varningar om redan sparad omgång: matchstart synkas mot nästa ospelade omgång; gamla matchcheckpoints valideras mot aktuell historik, säsongsschema och avslutade säsonger; checkpoint sparas inte på nytt vid registrering av färdigt resultat; redan registrerat resultat öppnas utan störande alert och utan dubbelregistrering. Vid faktisk konflikt skickas spelaren till nästa ospelade omgång utan att historiken skrivs över. Kodcommit `50b44d1a11d85e0e9968a7e7eaccba8569176ac2`. Officiell root orörd. Kontroll: riktade kodgranskningar utförda, inte browser-end-to-end-testad; verifiera i mobil med befintlig sparning och återupptagen match.

- **2026-11-03 — BETA 1.5.5.35:** Rättad pressuppföljning efter tidigare löften: en förlust i aktuell omgång får aldrig presenteras som att tränaren just hållit sitt löfte eller att laget vann. Uppföljningen skiljer nu på seger, förlust efter tidigare vinster och fortsatt förlustsvit; svarsalternativ följer utfallet. Kodcommit `251da2eec421e440072ab8c9d503aafc5d7192d4`. Officiell root orörd. Ej browsertestad.

- **2026-11-03 — BETA 1.5.5.36:** Flytande navigeringsmeny visas först sex sekunder efter övergång från match till slutresultat. Slutresultatet sparas direkt som tidigare, oberoende av pressfrågor. När spelaren lämnar resultatvyn via Hem/Spela/Karriär/Meny uppdateras omgången atomärt till nästa ospelade omgång, så avslutad match inte återanvänds som aktiv. Kodcommits `2fd427c5cb8b9e0ce9126abf04f395ba84e48142`, `4fbb290957834ce5152b38351ca87045ec081402`. Officiell root orörd. Ej browser-E2E-testat.

- **2026-11-03 — BETA 1.5.5.37:** Flytande navigering efter matchresultat visas efter 4 sekunder (tidigare 6), med mjuk 0,75 s fade/uppåtglidning och lätt blur; rörelsereducering respekteras. Kodcommit `be9205abbae958dde31e4368f8a34a3562e95f41`. Officiell root orörd. Ej browsertestat.

- **2026-11-03 — BETA 1.5.5.38:** Pressrummets rubrik, journalistfråga och svarsalternativ A/B/C animeras successivt vid nytt slutresultat (fade, lätt uppåtglidning, kort blur, förskjutna starttider). Menyns fyrasekundersfördröjning kvar. Reducerad rörelse respekteras. Kodcommit `6a38a888231affd99ac6005941fb627a35b05276`. Officiell root orörd. Ej browsertestat.

- **2026-11-03 — BETA 1.5.5.39:** Presskonferens före match får samma formspråk som efter match: djupblått pressrumskort, tränarprofil, live-status, inramade SVAR, kursiverade citat, A/B/C och mjukt förskjutna entréanimationer för rubrik, fråga och svar. Separat inför-match-identitet; befintliga val, effekter och matchlogik behålls. Kodcommit `f8d326e43369c29183b619b6b262978eadbed181`. Officiell root orörd. Ej browsertestat.

- **2026-11-03 — BETA 1.5.5.40:** Grundseriens avslutning får exklusiv guldkantad vinnarvy med djupare mörkblå/guldtoner, större vinnarbudskap, säsongskicker, mjuk guldbelysning och 68 animerade konfettipartiklar i bakgrunden. Konfetti ligger bakom text och påverkar inte knapparna. Icke-vinnare behåller befintlig nedtonad sammanfattning. Reducerad rörelse respekteras. Kodcommit `defbffd886cbd5aa30c23fabc6d7f10ebb2474d6`. Officiell root orörd; ej browsertestat.

- **2026-11-03 — BETA 1.5.5.41:** Korrigering efter feedback: grundserievinnarens banner återgår till kompakt höjd, extra slogans tas bort, 100 små skarpa konfettibitar läggs över hela bakgrunden med mild rörelse. CSS-regler placeras i faktisk befintlig style-tagg (tidigare CSS-injektion matchade inte HTML-strukturen). Kodcommit `95d79e60372ad0e317b4767da939b14a0b01054f`. Officiell root orörd. Ej mobiltestat.

- **2026-11-03 — BETA 1.5.5.42:** Behåller exakt kompakt storlek och 100 konfettibitar från 1.5.5.41 men ger djup genom separata skärpe-/opacitetslager, diskret perspektivrörelse, varierad drift och mjuk radial guldbelysning. Ingen extra text eller höjd. Kodcommit `0758b451482951920e9668ff6a707eb49c82d113`. Officiell root orörd; ej browsertestat.

- **2026-11-03 — BETA 1.5.5.43:** Konfettin i den kompakta grundserievinnar-rutan får kraftigare lageroskärpa och sänkt kontrast, med mörk tonad gradient över partiklarna bakom vänsterställd text. Texten har högsta lagerprioritet och starkare kontrast/skugga. Antal konfettibitar, textrader och rutans storlek oförändrade. Kodcommit `c8fa8a886efa4ffb4fdd64ee5cbb12904d6341ee`. Officiell root orörd. Ej mobiltestat.

- **2026-11-03 — BETA 1.5.5.44:** På användarens begäran återställdes ENBART grundseriens avslutningsruta/vinnarbanderoll till utförandet före firandeexperimenten 1.5.5.40–43, med exakt `seasonSummary`-markup från commit `6a38a888` (BETA 1.5.5.38). Experimentell konfetti-/djup-CSS borttagen. Övriga ändringar inklusive presskonferens före match från 1.5.5.39 behålls. Kodcommit `39ec03ccfeb7a62847c3f6762c6662d1021830a1`. Officiell root orörd. Ej browsertestat.

- **2026-11-03 — BETA 1.5.5.45:** Presskonferensen inför match var felrenderad eftersom tidigare special-CSS inte hade nått fram. Den använder nu samma faktiska `press20`-struktur och stilar som efter match: enradig rubrik/LIVE, korrekt separerade A/B/C, inramade SVAR och kursiva citat, successiv animation. Befintliga `worldAnswer`-effekter bevaras. Kodcommit `3b783b5e80f11f059fe76f4f447bd518eb92cbc7`. Officiell root orörd; ej mobiltestat.

- **2026-11-03 — BETA 1.5.5.46:** Rättar flytande Hem/Spela/Karriär/Meny-rad efter match: CSS-animationen saknades faktiskt trots tidigare klass. Nu får raden en engångsanimation efter befintlig 4-sekundersfördröjning, med .85 s mjuk fade/uppåtglidning/lätt blur; flagga nollställs så vanliga omrenderingar inte återstartar animationen. Reducerad rörelse respekteras. Kodcommit `b9f9c40204e4a24ad86f5455fdac3e731fc7a1d6`. Officiell root orörd; ej browsertestat.

- **2026-11-03 — BETA 1.5.5.47:** Presskonferenser före och efter match får kompaktare svarskort: minskad vertikal padding, mindre mellanrum mellan SVAR och citat, kortare radavstånd, ingen påtvingad minhöjd och fortsatt naturlig höjd för långa svar. A/B/C, färger och animationer bevarade. Kodcommit `15cfe1649e576f6bc75f1036cedfdf5f1be5144c`. Officiell root orörd; ej mobiltestat.

- **2026-11-03 — BETA 1.5.5.48:** Efter besvarad presskonferens efter match visas citat, sammanfattning och effekter i 3 sekunder; sedan tonas pressrummet bort mjukt på 0,65 sekunder med liten uppåtglidning/blur och tas bort ur vyn. Dold status per press-ID i aktuell session skyddar mot återkomst vid omrendering; svar/effekter/nyhetsarkiv ligger kvar i sparad karriär. Före-match-pressen opåverkad. Kodcommits `3023323141996e46c9e0af7926ebb6314ad93941`, `fb9eceafef136d6aa4418a5f54c5230cd1d688a1`. Officiell root orörd; ej mobiltestat.

- **2026-11-03 — BETA 1.5.5.49:** Fixar flytande navmenyn som hamnade till höger efter avslutad match. Rotorsak: animationsnyckelbilderna överskrev menypositioneringens `translateX(-50%)`. Alla animationssteg bevarar nu horisontell centrering samtidigt som menyn tonas in och glider upp efter 4 sekunder. Kodcommit `2cf71f5cfec208d6b0c35c2dfc7e296e8c30b070`. Officiell root orörd. Ej mobiltestat.

- **2026-11-03 — BETA 1.5.5.50:** På resultatsidan visas `OMGÅNGENS MATCHER` med sju successivt animerade rader (0,24 s förskjutning), lätt sidoglidning och fade. Varje rad växer från 0 till full höjd, så omgivande box expanderar naturligt. Engångsanimation vid övergång från match till resultat, ej vid vanlig omrendering; reducerad rörelse respekteras. Kodcommit `25a6dd946d7d27926a7aace845526d1612a5e5a6`. Officiell root orörd. Ej mobiltestat.

- **2026-11-03 — BETA 1.5.5.51:** Efter match med aktiv presskonferens visas slutresultat och pressrum först; övriga resultatsidans boxar (omgångens matcher, nästa match och managerhubben) hålls dolda. När användaren svarat visas citat/effekter i befintliga 3 sekunder, pressrummet tonas bort och övriga boxar glider/tonas fram successivt med 0,28 s förskjutning; matchradernas egna stegvisa animation triggas då. Utan presskonferens visas boxarna direkt. Sparade svar och effekter oförändrade. Kodcommit `a497490d687ba9eb5d623ee9bee882fcb7677df8`. Officiell root orörd; ej mobiltestat.

- **2026-11-03 — BETA 1.5.5.52:** Fixar besvarat pressrum som återkom och fastnade efter siduppdatering/omstart. Redan sparad `press20.answered` är nu auktoritativ för att hålla rutan dold vid ny sidladdning; endast en tillfällig minnesflagga `press20ReadingKey` visar den under 3-sekunders svarskvittot i samma session. Efter fade nollställs flaggan och resultatsidans boxar visas successivt. Fallback efter 850 ms frigör också boxarna om transitionend uteblir. Tidigare sparade karriärer omfattas utan migrering. Kodcommit `69c5b971d1a0b497660a3a68b8b4bcc807b3a948`. Officiell root orörd; ej mobiltestat.

- **2026-11-03 — BETA 1.5.5.53:** Nyheten om möte med tränarens tidigare klubb ändras från direkt tilltal (`Du möter ...`) till supporterorienterad journalistik i tredje person. Rubrik och ingress använder aktuellt lag och motståndare dynamiskt; inga påhittade citat eller reaktioner. Rivalitetslogik och övriga nyheter orörda. Kodcommit `9145c9301eef94a475207891bc78b9a5c66182c5`. Officiell root orörd; ej mobiltestat.

- **2026-11-03 — BETA 1.5.5.54:** Presskonferenser glesas ut efter spelarfeedback. Efter match krävs minst fyra omgångar sedan senaste pressmöte (tidigare två); betydelsefulla händelser prioriteras, vardagsfrågor normalt först efter fem–sju omgångar. Inför match ökar minsta mellanrum mellan vanliga presshändelser från två till fyra omgångar, medan verkligt akuta händelser (prioritet >=95) fortfarande kan bryta spärren. Befintliga presshistorik-/svarssystem och animationer oförändrade. Kodcommit `cc3001e856e28eaa5469d7b3b6142b729374959a`. Officiell root orörd; ej mobiltestat.

- **2026-11-03 — BETA 1.5.5.55:** Tar bort fasta 4-omgångars spärrar för presskonferenser. Efter match viktas nyhetsvärde från kris, segersvit, rivalitet, slutspurt, målskillnad och tidigare löften, med deterministisk situationsvariation som gör frekvensen mindre förutsägbar men stabil vid omladdning. Press kan komma i två omgångar i rad när nyhetsvärdet är stort; vardagsmatcher får lägre sannolikhet. Inför match viktas händelsens prioritet och situationsvariation i stället för fast cooldown. Inga ändringar av pressens utseende, svar, effekter eller animationer. Kodcommit `55673d447fad22889482b8948146b8151c06b73f`. Officiell root orörd; ej mobiltestat.

- **2026-11-03 — BETA 1.5.5.56:** På resultatsidan får `OMGÅNGENS MATCHER` en kompakt växlare MATCHER/TABELL i samma box. Tabellvyn visar aktuell SHL-ställning efter avslutad omgång (placering, lag, matcher, målskillnad, poäng), med egna laget markerat. Växling byter panelinnehåll med mjuk fade/slide; både tabellrader och matchrader kommer fram successivt, och boxens höjd följer innehållet. Befintlig press-staging och resultatsidans övriga boxar bevaras. Kodcommit `56dd65f5b149b9321eb1bf01bbd1151708f11c72`. Officiell root orörd; ej mobiltestat.

## 2026-11-03 — Officiell release 1.5.5 och start 1.5.6

- Officiell 1.5.5 släppt: root index.html ersattes med development/index.html från BETA 1.5.5.56, med versionsraden ändrad till VERSION 1.5.5 · OFFICIELL UTGÅVA · INOFFICIELLT FANSPEL. Release-commit 758a77f09970962f8422bbeea330bcc6297233d4. URL: https://olikid.github.io/shl-gulddrommen/
- Säkerhetsgren: releases/beta-1.5.5.56-2026-11-03 skapad från main före publiceringen. Innehåller BETA 1.5.5.56 och projektbibeln vid releasetillfället.
- Ny utvecklingsbas: development/index.html märkt BETA 1.5.6.0 · THE FIGHTING UPDATE · UTVECKLINGSVERSION i commit e93354c54e6938ccbba7992b79fc984ca1dc207c. Inga slagsmåls- eller skadesystem har implementerats ännu.
- Vision 1.5.6 — THE FIGHTING UPDATE: slagsmål, gruff, utvisningar, skador, matchdynamik, disciplinära följder och sportjournalistiska reaktioner. Exakt design och balans ska utformas med användaren före kodning.
- Skydd: ändra endast development/index.html tills användaren uttryckligen begär ny officiell release. Bevara localStorage, saves och kompatibilitet. Kontrollera SHA och versionsrad före ändringar.
- Teststatus: ingen automatiserad JS-, mobil- eller webbläsarregression och ingen live Pages-verifiering utfördes i release-steget. Tidigare mobilfeedback var positiv.

- **2026-11-03 — Officiell 1.5.5 hotfix:** Tränarporträtten i root index.html använde relativa sökvägar `../assets/Coaches/coach_*.webp` från development-mappen. I officiell root ändrades de två referenserna till `assets/Coaches/coach_*.webp`. Filerna finns i GitHub assets/Coaches. Kodcommit `ee4ef53a10f66570b44fb651236c88336588cc9a`. Development/index.html orörd; sparfiler och logik orörda. Ej live-webbläsartestat.

- **2026-11-03 — BETA 1.5.6.1:** Första isolerade visuella fightprototypen på matchskärmen: knapp `🥊 TESTA FIGHT` öppnar helskärmsmodal med illustrerad sidovy över is, två hockeyfigurer, läktare/sarg, klubbnamn, stora röda `SLÅSS!` och blå `DUCKA!` arkadknappar. Valen visar enkel slag-/duckanimation och återkoppling; stäng/återgå till matchen. Mobilanpassning och reduced motion. Ingen påverkan på sparfiler, resultat, utvisningar, skador eller matchmotor; detta är avsiktligt en designprototyp för användarfeedback, inte automatisk fighttrigger. Kodcommit `0e369557474c96811cb4371702c5558516f9df7a`. Officiell root orörd. Ej webbläsar-/mobiltestat.

- **2026-11-03 — BETA 1.5.6.2 KRITISK HOTFIX:** BETA 1.5.6.1 råkade infoga bokstavlig `\\n` direkt före `let roundResultsEntrancePending=false;` utanför sträng i JavaScript, vilket orsakar SyntaxError och gör att hela utvecklingsspelet inte startar. Ersatt med faktisk radbrytning, versionsrad uppdaterad till 1.5.6.2. Kodcommit `c790c2c9ed6b78772ac2a69eab030f39c2a32c29`. Officiell root orörd. Kräver användarverifiering efter Pages-uppdatering.

- **2026-11-03 — BETA 1.5.6.3 EMERGENCY ROLLBACK:** Användaren rapporterade fortsatt blank utvecklingssida efter 1.5.6.2. Samtliga tillägg från 1.5.6.1 fightprototypen har därför avlägsnats ur development/index.html (CSS, JS och testknapp), så att baslinjens funktion återställs. Endast versionsetikett skiljer från pre-prototypbasen. Kodcommit `42773404730f5aa2df087271cac1f499fc167f93`. Officiell root orörd. Väntar på användarens bekräftelse att sidan laddar.

- **2026-11-03 — BETA 1.5.6.4:** Ny isolerad fight-arcade-prototyp på development/index.html efter rollback. Matchknappen `🥊 TESTA FIGHT` öppnar sidovy med CSS-hockeyspelare och röda `SLÅSS!`/blå `DUCKA!`-knappar samt enkla animationer. Endast visuell demo utan match-/sparfilskonsekvenser. Undviker föregående fel med bokstavlig `\\n` i JS. Kodcommit `50fefb7e4ba145ac552675e45bb758a439c2945a`. Officiell root orörd; användarens browsertest inväntas.

- **2026-11-03 — BETA 1.5.6.5 EMERGENCY ROLLBACK:** Användaren rapporterade åter blank sida efter 1.5.6.4. All fightprototyp-CSS, JS och knapp åter borttagen från development/index.html; baslinje återställd, endast versionsetikett ändrad. Kodcommit `d6c689e8fe1562e32b015dfa073bd716a217a711`. Viktigt: bygg INTE in fightprototypen igen förrän exakt JavaScript-parse/runtime-fel har verifierats med faktisk JS-parser/browser-console; validera nästa patch innan commit. Officiell root orörd.

- **2026-11-03 — BETA 1.5.6.6:** Efter två blank-screen-incidenter skapades en separat, helt JavaScript-fri fightprototyp `development/fight/index.html` (commit `82bdf112d19d98fab181af1757dacb76458a18f0`). CSS-only sidovy, två hockeyspelare, röd `SLÅSS!` och blå `DUCKA!`, CSS-radio-val och feedback. En enkel HTML-länk `🥊 TESTA FIGHT-ARCADE` visas i matchvyn i `development/index.html` (commit `31b27d46c838f9720a195eb7ea8a27433300b28d`), versionsetikett 1.5.6.6. Inga nya JS-funktioner eller ändringar i karriärlogik/sparfiler. Officiell root orörd. Invänter webbläsarbekräftelse.

- **2026-11-03 — FIGHT ARCADE 1.5.6.7:** Den separata `development/fight/index.html` är nu spelbar med HP- och stamina-mätare för båda spelarna, upprepade SLÅSS-/DUCKA-val, automatisk motståndarreplik, slumpad träff/skada, återhämtning, animationer och fightavslut vid 0 HP eller efter 18 rundor. Endast den separata sidan ändrades, `development/index.html` och officiell root orörda. Inga karriärkonsekvenser eller sparfilsmutationer. Kodcommit `5bcc6de30678cd5316915b7b395bc92f57df1f3e`. Invänter användarens speltest.


- **2026-11-03 — Fight Arcade 1.5.6.27:** `development/fight/index.html` uppdaterad: DUCKA till vänster och SLÅSS till höger. Runda tidigt-2000-talsinspirerade arkadknappar med glans, djup, tryckeffekt, tangentbordsfokus och mobilstorlekar. Versionsetikett uppdaterad. Kodcommit `47ba9f745d63aecfe49fe7fd526124d1959cc39d`. Officiell version orörd. Visuellt mobiltest återstår.

- **2026-11-03 — Fight Arcade 1.5.6.28:** `development/fight/index.html`: låser SVG-armarnas ledpositioner under träffreaktioner för att förhindra att de flyger iväg; behåller dramatisk handskkastning men lägger till iskontakt, en studs, kort glidning och uttoning. Commit `d1a0a9235a45802c345df1dbde80d062efdda1c7`. Ingen ändring i fightens spelmekanik eller officiella version. Mobiltest återstår.

- **2026-11-03 — Fight Arcade 1.5.6.29:** `development/fight/index.html`: mer aggressiv motståndare, kortare attackintervall, högre press och skada vid passivitet efter ca 1,7 s, snabbare staminaåterhämtning för AI och förbättrad belöning för aktiv duckning. Handskkastning med landningspositioner relativa till isytan, studs, glid och uttoning för att minska risken att de försvinner utanför mobilvyn. Commit `2690fa9a9495225eb20b7a120e3b27edbae87a2c`. Officiell version orörd; spelbalans och mobilanimation återstår att testas.

- **2026-11-03 — Fight Arcade 1.5.6.30:** `development/fight/index.html`: handskarnas kast och studs bibehålls, men slutläget har nu 100 % opacitet så handskarna ligger kvar på isen under fighten. Motståndarens aggressivitet och kontroller oförändrade. Commit `8bd536d2923e17ffaf8cb2e2a55bfbee20ad8bc9`. Officiell version orörd; mobiltest återstår.

- **2026-11-03 — Fight Arcade 1.5.6.31:** `development/fight/index.html`: linjedomare i randig tröja glider in 2,5 sekunder efter avslutad fight och stoppar vinnarens firande; mer aggressiv bakåtsving och rotationsbana för handskarna med bibehållen studs och permanent slutposition på isen. Commit `40911c107a2db2892f967d8fbcc779e844643894`. Officiell version orörd; visuell mobiltest återstår.

- **2026-11-03 — Fight Arcade 1.5.6.32:** `development/fight/index.html`: korrigerar oproportionerligt stor linjedomare (40×83 px), lägger honom vid sidan av vinnaren i stället för framför och minskar firandetiden före ingripandet från 2,5 till 1,5 sekunder. Commit `302d6699891e9a6ade445f6d5a28b1b620ba3449`. Officiell version orörd; visuell verifiering på mobil återstår.

- **2026-11-03 — Fight Arcade 1.5.6.33:** `development/fight/index.html`: ersätter linjedomarens SVG med proportionerligare, kroppsnära armar och sätter storlek till 57×113 px; anpassar placering bredvid vinnaren. Synkroniserar intro: handskkast startar efter 980 ms (tidigare 470 ms), fighten startar efter 1900 ms (tidigare 1750 ms), nedräkning tas bort efter 2550 ms. Domaren kommer fortsatt efter 1,5 sekunder. Commit `de041d3e90208dbdd4f02fca7a0493260a9c837d`. Officiell version orörd, mobiltest återstår.

- **2026-11-03 — Fight Arcade 1.5.6.34:** `development/fight/index.html`: linjedomaren något större (64×126 px från 57×113 px), utan ändringar i animationer, timing, handskkast eller fightbalans. Commit `a8de2f2fc9e294585253af598ee11f7d09067321`. Officiell version orörd.

- **2026-11-03 — Fight Arcade 1.5.6.35:** `development/fight/index.html`: behåller linjedomarens godkända storlek 64×126 px men flyttar hans slutposition åt vänster vid spelarvinst och åt höger vid motståndarvinst för att inte täcka vinnaren. Commit `30f006181ede40f67212c123745656bd82944a2f`. Officiell version orörd; visuell kontroll på mobil återstår.

- **2026-11-03 — Fight Arcade 1.5.6.36:** `development/fight/index.html`: visuella trötthetseffekter för spelaren vid stamina under 38 (hängande huvud, tung andning, långsammare armguard, text TRÖTT) och under 17 (kraftigare utmattning, text HELT SLUT). Ingen ändring i combatlogik, timing, handskar eller domare. Commit `554db7a135ed674dec69040b2574f434009ea35e`. Officiell version orörd; mobiltest återstår.

- **2026-11-03 — Fight Arcade 1.5.6.37:** `development/fight/index.html`: vid stamina under 17 förstärks HELT SLUT med lätt kroppsdarrning, huvudet som faller framåt och tre animerade svettdroppar. Trötthetsnivåer, spelbalans, domare och handskkast oförändrade. Commit `af56dce62d1e0d53370513dbbf3d431fd607475f`. Officiell version orörd; visuell mobilverifiering återstår.

- **2026-11-03 — Fight Arcade matchintegration (första version):** `development/index.html` kan slumpmässigt (9 % per beslut, 18 % vid het rivalitet, från beslut 2–12, högst en gång per pågående match i sessionen) visa inbjudan att ta fight eller avstå. Vid ja visas `development/fight/?embedded=1` i mobilanpassad modal ovanpå pågående match; fighten rapporterar vinnare till managern via origin-kontrollerad `postMessage`, och man återgår till matchen utan att förlora den. Vid nej fortsätter matchen. `development/fight/index.html` har embedded-meddelanden för avslut och exit. Manager commits `e52ca40caec2e8960864757d682c8fa5ec1438bc`, `be2140dcf52566b320f9032a9d98f6a7372e2c92`; fight commit `8d371826933ef3f3c27e8475fc40048e93dfdd3a`. Officiell version orörd. Integration inte visuellt/slut-till-slut-testad; ingen påverkan på matchpoäng eller sparad fightstatistik ännu.

- **2026-11-03 — Matchfight 1.5.6.39:** `development/index.html`: fightinbjudningar triggas inte längre av ren slump vid beslut utan kräver ett faktiskt mål och kontext: tydlig ledning och motståndarfrustration, underläge med upptrissad stämning eller hett rivalmöte. Tidigast efter beslut 3, högst en inbjudan per match. Vinst ger +7 klubbmoral och +3 fans, förlust −7 moral och −2 fans. Från tredje accepterade fighten per säsong minskar styrelsens förtroende (−4 vid tredje, därefter −2 per fight), och antal/vinster/förluster sparas i `g.fightDiscipline`. Avstå ger ingen effekt. Commit `3a294751147aeff906d04003ea5de2a9bc4bda05`. Matchenergi representeras initialt av klubbmoral som redan påverkar matchens offensiva/defensiva faktor; ingen separat stamina för laget. Officiell version orörd; end-to-end-test återstår.

- **2026-11-03 — Fightreaktioner i kommentator och pressrum:** `development/index.html` ger en fightvinst/förlust särskild kommentatorreplik direkt vid återgång till matchen. `g.fightLast` sparar fightresultat, säsong, omgång och motståndare. Efter en match med fight prioriterar `press20Build` en fight-specifik presskonferensfråga oavsett normal frekvenslogik, med tre relevanta svar som påverkar moral, fans och styrelse olika. Commit `23ffe5103ba5521dd8badfaf830901f5926f0865`. Ingen ändring i officiell version. Visuellt end-to-end-test återstår.

- **2026-11-03 — Fightövergång efter mål, dev v41:** När en målutlöst fight väl har valts visas målfirandet kort (~900 ms), sedan avbryts måltoast/glow och blinkande resultatremsa städas, följt av mjuk fade/slide in till fightinbjudan. Vanliga mål utan fight har oförändrad animation. `development/index.html` commit `df7722ca96a9f84581465f5c13a6ff8c44bde4e2`. Produktion orörd, mobiltest återstår.

- **2026-11-03 — Kritisk hotfix:** `development/index.html` visade endast logga/tom sida p.g.a. extra `)` i `press20Build` (`const should`), införd vid fightpressintegration. Extra parentes borttagen; fulla inline-JavaScript-blocket har syntaxtestats med `new Function` och godkänts. Commit `82f918b8d5e21b3c5087e948fa736ed2b760bc5d`. Funktionellt browser-test återstår. Produktion orörd.

- **2026-11-03 — Lagidentitet i matchfight:** Manager `development/index.html` skickar klubbnamn och kontrasthanterade färger från `rinkColors()` via URLSearchParams till embedded fight. `development/fight/index.html` visar riktiga lagnamn i topp, HUD och under isen samt färgsätter SVG-tröjor och armar med respektive lagfärg. Fristående fight behåller standardfärger. Manager commit `f14c984eec19ba1001da6e9d6edf3e596bff46b3`, fight commit `a85875dd1e4e85d10d6fe12dbb59cd82b9745190`. Syntaxtestat, visuellt mobiltest återstår. Produktion orörd.

- **2026-11-03 — Presskonferens dubbelvisning fix:** Resultatsidan renderade både `worldUpsetCard()` (gammal skrällpress) och `press20Card()` (nya dynamiska pressrummet), vilket gav två samtidiga frågerutor. Renderingen prioriterar nu `press20Card()` och visar endast `worldUpsetCard()` som fallback om nytt pressrum saknas. Commit `77a427c439869c8b86bd09fc97858dc384280507`. Inline-JS syntaxtestat. Produktion orörd.

- **2026-11-03 — Pressfix efter animation:** Tidigare fallback för `worldUpsetCard()` gjorde att den gamla skrällpressen dök upp igen efter att `press20Card()` mjukt animerats bort. `development/index.html`: resultatsidan renderar nu enbart det nya pressrummet; `worldUpsetCard()` returnerar tom sträng på resultatsidan. Inline-JS syntaxtestat. Commit `c1df9c07baed919ee506659fd0518694c9eef784`. Produktion orörd.

- **2026-11-03 — Fightutvisningar i match:** Accepterad/avgjord fight registrerar `g.fightPenalty` för aktuell säsong/omgång, med fem minuters utvisning för en spelare i vartdera laget. Matchsituationen visar båda klubbarna och kvarvarande tid utifrån matchklockan; panelen försvinner när fem spelminuter passerat. Ingen powerplay-effekt då utvisningarna är kvittade; moral/presskonferens påverkas som tidigare. `development/index.html` commits `6a3d2e8008e9afaf6aa994c08219d01ac576fe46`, `e6017a51b31f2c77200287c143306c46b5b5b212`. JS syntaxtestat, inte browser-testat. Produktion orörd.

- **2026-11-03 — Fight exit/finish fix:** Embedded fight visade två konkurrerande 'till matchen'-knappar. Den inre skickade `shl-fight-exit` och tolkades som avstå, vilket tappade fightresultatet. `development/index.html`: ingen exit under fight; efter `shl-fight-finished` visas enda knappen `FORTSÄTT MATCHEN →` som skickar faktiskt win/lose till `matchFightEnd`. `shl-fight-exit` ignoreras. `development/fight/index.html`: inre exit döljs i embedded-läge. Commits `2e75b487b86b721510b8531c75b11d6c57d024ec`, `ed78ea2a8c0e7a965bab50ad530e570d4a1bb975`. JS syntaxtestat; browser-test återstår. Produktion orörd.

- **2026-11-03 — Kompakt fightutvisning (v48):** `fightPenaltyMarkup()` visar en smal statusremsa i stället för stor tvåkolumnsruta: '🥊 SLAGSMÅL', båda lagen markerade 🟨 och kvarvarande matchtid. Minimal padding, responsiv en/tvåradslayout för iPhone, ingen förklarande text. `development/index.html` commit `ae9e4f3e6489668438935b86eb81dbfc6fbba83f`. Syntaxkontrollerad; produktion orörd.

- **2026-11-03 — Utvisningsremsa v49:** Bytt titel från SLAGSMÅL till UTVISNING, tagit bort gula kort-emojis och visat en separat nedräkning bredvid varje lagnamn (t.ex. Brynäs 5:00 | Frölunda 5:00) i en smal horisontell remsa, även på mobil. `development/index.html` commit `1e324c9068dcc8aabc36988d7afaf6b3a8447022`. JS syntaxkontrollerad; produktion orörd.

- **2026-11-03 — Organiska fighter utan testknapp (v50):** Tog bort manuella `🥊 TESTA FIGHT-ARCADE`-länken från matchvyn i `development/index.html`. Mål-/händelsebaserad fightinbjudan och embedded arcade finns kvar, liksom separat `development/fight/` för utveckling. Commit `99b634216c4f84263d0719d7254fc17a77badcf6`. JS syntaxtestat; produktion orörd.

- **2026-11-03 — OFFICIELL RELEASE BETA 1.5.6:** Användaren godkände release. `development/index.html` publicerad till officiella `index.html` med versionsmärkning `BETA 1.5.6 · OFFICIELL UTGÅVA · INOFFICIELLT FANSPEL` (commit `d12b5d9aba70163043c612e33343b673ce9a0017`). `development/fight/index.html` kopierad till `fight/index.html` så relativ iframe `fight/?embedded=1` fungerar i produktion (commit `85e6b9bece09042b5c4fff26ce056e9e9342bc44`). Officiell länk https://olikid.github.io/shl-gulddrommen/?v=156 ; dev och dev/fight kvar. Inline-JS syntaxkontrollerad och filernas existens verifierad i GitHub, men fullständig webbläsar-/mobiltest ej utförd. Tidigare officiella BETA 1.5.5 ersatt.

- **2026-11-03 — OFFICIELL 1.5.6 profilbildshotfix:** Vid flytt av `development/index.html` till `index.html` följde två relativa sökvägar `../assets/Coaches/coach_*.webp` med. Från repo-roten pekade dessa en katalog för högt. Ändrat till `assets/Coaches/coach_*.webp` i officiella `index.html` (commit `9e0ba41a80262e2e74cef311385cd475991720e2`). JS syntaxkontrollerad. Dev oförändrad.

- **2026-11-03 — THE FIGHT CLUB, första spelbara lobby/ranking:** Både officiella `fight/index.html` och `development/fight/index.html` har röd Fight Club-lobby, Quick Fight, låst Turnering, rating (start 1000, +25 vinst/−18 förlust, min 0), Rookie/Challenger/Contender/Elite/Legend, W-L och streak lagrade lokalt i browsern. Quick Fight körs med `?quick=1`, efter match visas FIGHT IGEN och MIN RANKING. Embedded matchfighter går förbi lobbyn och påverkar inte fristående rating. Fight-kortet under FLER SPELLÄGEN på både officiella `index.html` och `development/index.html` är nu klickbart med SPELA → och leder till `fight/`. JS syntaxkontrollerad, full webbläsar-/mobiltest kvarstår. Commits: dev fight `db4e82596dad642e179b818a8b281af3321bcebd`, prod fight `a3a62f6c55dd12f8f407aa495c43815369e6a4f2`, dev manager `6cf781d8f542c692fafa79af5100a1a61550d48c`, prod manager `344e448bd7d3590d1da636a5f1a4d0cae5136a0f`.

- **2026-11-03 — Arbetsflöde & Elo:** Användaren påpekade att Fight Club fortsatt ska utvecklas endast under `/development/` och att officiella länkar/tester inte ska användas för pågående arbete. Framåt: gör inga fler ändringar i officiella `index.html` eller `fight/index.html` utan uttryckligt releasegodkännande. Dev Fight Club kallar nu ratingpoäng **Elo** i UI och matchresultat, med oförändrad localStorage-nyckel så tidigare statistik bevaras. Dev fight commit `21520c2a2eb752e6183c958de29b2292b58886a4`. Dev testlänk: `https://olikid.github.io/shl-gulddrommen/development/fight/?v=elo1` (utan `quick=1`, så lobbyn ska visas). Den tidigare officiella Fight Club-publiceringen var för tidig; ingen rollback gjord ännu.

- **2026-11-03 — Fight Club rankingdesign v2 (endast DEV):** Bytte tre jämnstora statistikboxar mot stor nuvarande divisionssymbol, Elo, W/L, progress mot nästa division och en femstegsrankingstege. Fem egna inline-SVG-emblem med metalliska färger och distinkta symboler: Rookie, Challenger, Contender, Elite, Legend. Responsiv CSS för mobil. Endast `development/fight/index.html` ändrad (commit `b705ed3eb03c55c90f0921920ce46506eca11dd5`). Officiell utgåva orörd. JS syntaxkontrollerad; visuell webbläsartest kvarstår.

- **2026-11-03 — DEV Fight Club motståndare v1:** Sex fiktiva men bestående profiler (Oliver Bergström, Samir Haddad, Elias Nyström, Noah Lind, Leo Falk, Vincent Holm) med egna inline-SVG-porträtt, hemstad, smeknamn, stil, bio, Elo och W/L. Tre motståndare närmast spelarens Elo visas som utmaningskort i lobbyn. Quick Fight-knappen scrollar till valen; klick på profil startar `?quick=1&opponent=<id>`, visar namn/Elo i HUD. Efter fight beräknas Elo-ändring med förväntat resultat och K=32; både spelarens och motståndarens Elo och W/L sparas i localStorage. Simulerade karaktärer, inte riktiga användare; ingen server eller global ranking. Bara `development/fight/index.html` ändrad, commit `81ac760a4014e043b897a413c68165d2f06117c0`. JS syntaxkontrollerad, fullständig browser-test återstår.

- **2026-11-04 — Fight Club fighterpool (DEV only):** Utökat från sex till 198 fiktiva fighters (192 genererade stabilt + 6 original) med profiler, nationalitet (Sweden, Finland, Canada, USA, Czechia, Slovakia, Germany, Switzerland), Elo, statistik, smeknamn och stil. Matchmaking väljer 3 ur närliggande Elo med rotationsvariation och undviker de senaste 14 mötena. Mellan matcher utvecklas 12 andra fighters Elo och statistik, sparat lokalt med `shl-fight-world-v1` och befintlig opponents-nyckel; gamla rivaler kan återkomma senare. Bara `development/fight/index.html` ändrad, commit `1bf9009fada1962be9e2533a89e9878d90f75c94`. JS syntaxkontrollerad; webbläsartest kvarstår. Officiell orörd.

- **2026-11-04 — DEV Fight Club matchmaking och namn:** Valbara motståndarkort borttagna från lobbyn. `HITTA MATCH` söker automatiskt bland Elo-anpassade kandidater, visar laddningsläge och funnen profil och startar fighten automatiskt. Befintlig recent-spärr och Elo-utveckling kvar. De 192 genererade fighterprofilerna har nu landspecifika för- och efternamnslistor (8 länder); befintliga sex profiler kvar. `development/fight/index.html` commit `89af9d140c204104966504fe94ba310b589f0a21`; endast DEV. JS syntaxkontrollerad; interaktiv browser-QA återstår.

- **2026-11-04 — DEV Fight Club Elo-balans:** Ersatt standard Elo K=32 med spelanpassad belöning/risk: ±100 Elo ger +18/−18, större skillnader justerar utfall med 7 per 300 Elo bortom 100-gränsen, avrundat; vinst alltid +10 till +25 och förlust −10 till −25. Högre rankad motståndare ger större vinst/mindre förlust, lägre rankad tvärtom. Båda spelarnas Elo uppdateras som tidigare. Endast `development/fight/index.html`, commit `534757dbbc902ce0731caa0a7ff284f85e54fe96`. JS syntaxkontrollerad, browser-QA kvarstår.

- **2026-11-04 — DEV Fight Club Versus/Result + 20/20 Elo:** Jämna matcher inom 100 Elo ger +20/−20. Skillnader justeras gradvis med hårda gränser +10…+25 och −10…−25, gemensam `fightClubStakes`-funktion. Efter matchmaking visas dramatisk röd VS-overlay med spelare, motståndare, land, Elo och insatser; fighten startar efter ca 2,5 sekunder. Efter avslutad fight visas VICTORY/DEFEAT-overlay med ny Elo och navigationsknappar. Fixar dessutom tidigare runtime-fel i resultatskrivningen. Endast `development/fight/index.html` commit `463c55b074578acda130fa1bf2c77dca49ba813a`. Syntaxkontrollerad, browser-QA återstår.

- **2026-11-04 — DEV Fight Club VS/ready och resultatslinga:** Matchmaking visar dramatisk VS-overlay och väntar nu på aktivt `REDO · STARTA FIGHTEN` (eller `AVBRYT`); ingen automatisk start. Resultatoverlay behåller VICTORY/DEFEAT men får progressbar med aktuell division, Elo och kvar till nästa rank. Knappar: `NY MATCH` kör ny Elo-matchmaking direkt i samma overlay, visar SEARCHING och sedan ny VS med redo; `TILL MENYN` återvänder till Fight Club-lobbyn. Tidigare dubbla matchslutsknappar under overlay borttagna. `development/fight/index.html` commit `c724c9841f45d6ed8330544f2a1cc5f8280ff8b4`. Endast DEV; JS syntaxkontrollerad, browser-QA återstår.

- **2026-11-04 — DEV Fight Club bindande matcher och divisionsövergångar:** När matchmaking hittar en fighter sparas en pending-match med beräknad förlustrisk i localStorage. Ingen avbryt-knapp på VS-skärmen; redo markerar tillåten övergång till fight via sessionStorage. Om spelaren lämnar matchen eller laddar om och återkommer avräknas förlust och Elo, W/L, streak och motståndarstatistik uppdateras (avräkning vid nästa laddning, inte i bakgrunden när sidan är stängd). Vid normal finish rensas pending. Resultat visar animerad RANK UP/RANK DOWN med gamla och nya divisionsemblem när tröskel passeras. Endast `development/fight/index.html` commit `aa39de0b965472c8d2b2807e30f6fcb9370f9832`. JS syntaxkontrollerad, browser-QA kvarstår.

- **2026-11-04 — Fight Club DEV versionsetikett:** Liten pill-formad knapp under Fight Club-hero visar `DEV 0.4.1 · BUILD 20261104.1`, klick kopierar versionsinfo och URL (Clipboard API med fallback). Endast `development/fight/index.html` commit `80944f584f7d28e1b5aaa903906fde62c708d8fe`. JavaScript syntaxkontrollerad.

- **2026-11-04 — DEV Fight Club Elo-failsafe:** Pending-match skrivs nu först när användaren trycker `REDO · STARTA FIGHTEN`, inte när match hittas eller när `NY MATCH` söker i resultatoverlay. Pending har `phase:'active'`; bara aktiv, oavslutad fight får ge forfeit vid återkomst eller omladdning. Legacy pending utan aktiv fas rensas utan avdrag. Forfeit tar bort pending före Elo-uppdatering (högst en avräkning per fight); normal matchfinish rensar pending. Direktöppnade quick-URL utan giltig ready-token omdirigeras till lobby. Endast `development/fight/index.html` commit `4f1a560d06326aad2215426a64202ff0c20cf36d`. Syntaxkontrollerad; browser-QA återstår.

- **2026-11-04 — DEV Fight Club animerad Elo (0.4.2 / BUILD 20261104.2):** Resultatoverlay räknar Elo från gammalt till nytt under ca 1,45 s, synkar divisionsnamn, kvarvarande Elo och progressbar under hela övergången, med grönt sken för vinst och rött för förlust. RANK UP/DOWN avslöjas efter animationen. Reduced-motion respekteras. Endast `development/fight/index.html` commit `fc48e6ea8cfc0eca4059250b5dea1383291f498b`, versionsbadge commit `f8ebbbb17aca6bf99b37253d0e8e42024b898b46`. JS syntaxkontrollerad; mobiltest kvarstår.

- **2026-11-04 — DEV Fight Club arena redesign 0.4.8:** Standalone ranked quick fights (`?quick=1`, not embedded) get dedicated `.fc-quick-arena` theme: burgundy/rose background and card, compact dark-red HUD, refined HP/stamina meters, arena color accents, polished buttons and typography. Legacy arcade labels hidden and replaced with Fight Club ranked labels; exit returns to Fight Club lobby (existing pending-forfeit logic applies). Embedded SHL fights stay blue/unchanged; underlying combat engine unchanged. Only `development/fight/index.html`, commit `2366fca464cac5f5969b76e37ac772680f30f315`. JS syntaxchecked, browser visual QA outstanding.

- **2026-11-04 — DEV Fight Club 0.4.19:** Sex deterministiska fighterpersonligheter (`AGGRESSIV`, `KONTRARE`, `KRAFT`, `SNABB`, `PRESS`, `TEKNISK`) styr små multiplikatorer för motståndarens attacktempo, skada, blockering och staminaåterhämtning utifrån befintligt `style`-fält. Befintlig Elo-skalning och matchmaking kvarstår; embedded SHL-fights använder neutral STANDARD. Endast `development/fight/index.html` commit `2e52535dc1f6e7b57d6037a0f88bcef0cdd771ea`. JS syntaxkontrollerad; praktisk spelbalans/visuell QA återstår.

- **2026-11-04 — DEV Fight Club 0.4.20:** Sex situationsstyrda signaturbeteenden för ranked-motståndare: AGGRESSIV rusar tidigt/tappar sent; KONTRARE svarar på spelarens kombo; KRAFT varierar med egen stamina; SNABB växlar i tidsfaser; PRESS ökar trycket vid låg spelarstamina; TEKNISK blockerar mer när den ligger under. Små modifikationer av attacktempo/skada/blockering/staminaåterhämtning ovanpå 0.4.18-balansen och 0.4.19-stilarna. Combat-log kan visa aktiv signatur. Embedded SHL-fighter opåverkade. Endast DEV, commit `52df00c11b79d55c45f64d4d581801667ba336c8`. Syntaxkontrollerad; speltest återstår.

- **2026-11-04 — DEV Fight Club 0.4.21:** Liten, expanderbar rivalitetsrad i GET READY vid återkommande motståndare, med inbördes resultat och senaste möte. I Fight Club-lobbyn finns en hopfälld matchhistorik (visar senaste 15, sparar upp till 100 i localStorage), inklusive Elo-förändring och avbrutna aktiva matcher som förluster. Historiken börjar registreras från denna version och retroaktiv data saknas. Endast `development/fight/index.html`, commit `33575a419a2009ebfca80d0546fa3ee7d637f9e5`. JS syntaxkontrollerad; visuell QA återstår.
