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
