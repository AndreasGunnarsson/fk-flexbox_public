https://forsakringskassan.se/

---

## Avgränsingar
Har gjort flera avgränsingar som finns på orginal-sidan. Det mesta på grund av tidsbrist.
- Största är att jag i slutändan tog bort innehållet i "footer". Existerar fortfarande en "#social_footer" med några länkar till diverse sociala medier men ovanför den är bara en grön ruta som ska innehålla lite information. Hade gjort stora delar på det men valde att försöka lägga den tid jag hade på att finslipa "main" mer.
- När man markerar en länk på orginal-sidan så är det en speciell border runt dem som jag skippat.
- När man klickar på hamburger-menyn så får man en snygg meny till höger på sidan med diverse länkar.
- När bredden på hemsidan går under 890 pixlar och man får den kompaktare headern så kan man klicka på "Sök"-knappen och får då fram en sökruta med input-fält.

---

## Hur orginal-hemsidan förändras
Sidan har tre ställen där den faktiskt förändras avsevärt.\
Om man utgår från hemsidans bredaste läge (1200 pixlar) så sker nästa förändring när man går under 1024 pixlar, förädrningen efter det under 890 pixlar och sista under 640 pixlar.\
1200 pixlar är max-bredden. Denna max-bredd påverkar allt förutom bakgrunden till headern och footern.\
Under 1024 pixlar påverkar "main" där man går från tre till två kolumner (beroende på hur man räknar). Räknar då två kolumner i det jag i css kallat "#inside_main" plus "<aside>". Det som var i <aside> kommer att istället för att vara till höger på hemsidan att hamna längst ner i "main".\
Även footern påverkas men är inte med av skäl i "Avgränsingar" (se ovan).\
Under 890 pixlar så ändras headern till kompaktare design.\
Under 640 pixlar så är endast en kolumn tillåten i "main".\
Påverkar också det jag kallat "#social_footer" och den footer som är ovanför.

---

## Problem
Har generellt varit mycket som man behövt kompromissa mest pga. tid men har i stora hela försökt att göra sidan responsiv på det sätt den ska vara. I storlekskordning skulle jag säga att de största problemen är:
- Alla element matchar inte precis orginal-hemsidan i storlek. Tyckte det var svårt att göra så att flexbox exakt beter som som man vill när man ska kopiera något rakt av (som inte använder flexbox). Delvis är det också mycket som måste finjusteras när det kommer till margin, padding, height osv..
- Bättre strukturerad kod. Skulle vilja kollat lite mer på OOCSS, coola/användbara CSS selektorer (nu är allt id och klasser) och strukturerat css-filerna i egna kataloger (kunde inte ladda bilderna som laddas via "background-image" då jag testade, försökte med ../images/MINBILD.svg utan resultat).
- Det som jag i index.html har kallat för "TWO COLUMN - LOWER" är för höga och ska egentligen anpassas bättre. Hade kanske gått att fixa med annat flex-direction men inget jag hunnit med att fixa. Fokuserade tidigt i processen mest på bredden som olika element har och höjden blev för låg prioritet.
- De rutor i main som har rubrikerna "Arbetssöka" och "Funktionsne" ska egentligen skriva ut "Arbetssökande" och "Funktionsnedsättning". Problemet jag stötte på var att om man skriver ut hela ordet så kommer flexbox inte bete sig önskevärt mellan 640 och 1024 pixlar bred sida då orden inte wrappas (som de gör på orginal-sidan). Testat med word-wrap men antar de skulle behöva haft . Också för sent i prcossen för att undersöka vidare.
- Diverse småsaker när det kommer till stylingen..

---

## Upplägget (filer och kod)
- styles.css kan ses som en grund för hela sidan.
- Alla css-filer med prefixet "below" är filer som körs då sidan går under en viss bredd. T.ex. "below_1024.css" exekveras då sidan är under 1024 pixlar bred.
- inside_main.css är allt i "main". aside.css innehåller den "sidebar" som är till höger då sidan är över 1023 pixlar bred.
- Kommenterat en del i css-filerna som förhoppningsvis förklarar det mesta av vart man är.
- Id:n som har prefixet "special" är oftast för att göra en "override" på något en tillhörande klass till samma element använder.
- inside- och inside_inside-prefixen till ett id eller en klass beskriver oftast en div i en annan div.
