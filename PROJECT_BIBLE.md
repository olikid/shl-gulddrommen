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
