# Ontwerpkeuzes

Alles hier is html en css die ik zelf heb geschreven. geen framework en geen template.
opgezocht op youtube en in de docs van mdn.

In de opdracht staat dat je minimaal 2 gebruikersscenario's en minimaal 3 ontwerpkeuzes moet
onderbouwen, met minimaal 1 bron. ik ga niet voor die minimale eis. ik heb 6 keuzes
uitgewerkt met 4 bronnen erbij, want ik wil hier boven voldoende op staan en niet precies op
de streep.

## Voor wie ik het maak

**Scenario 1, de recruiter met weinig tijd**
Iemand van een stagebedrijf krijgt mijn link en opent hem op een laptop. die heeft geen zin
om te zoeken. hij wil binnen 10 seconden zien wie ik ben, wat ik gemaakt heb en hoe hij mij
kan mailen.

**Scenario 2, een klasgenoot of docent die mijn blog leest op de telefoon**
Die zit in de trein en wil zien hoe ik iets heb opgelost. hij wil gewoon scrollen, niet
steeds in en uit klikken en niet inzoomen om de tekst te kunnen lezen.

## Keuze 1, overal hetzelfde menu op dezelfde plek

Elke pagina heeft precies dezelfde header met dezelfde 4 knoppen in dezelfde volgorde.
projecten staat als 2e zodat de recruiter er meteen bij is. de pagina waar je nu staat
krijgt aria-current="page", zodat je het ziet en een screenreader het ook voorleest.

Waarom: allebei de scenarios hebben dit nodig. de recruiter wil in 1 klik naar projecten en
degene die de blog leest wil daarna makkelijk terug.

Bron: https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-current

## Keuze 2, alles in 1 kolom onder elkaar

Geen kolommen naast elkaar. header, dan main, dan footer, gewoon onder elkaar. daardoor
hoeft de layout op een smal scherm niet om te klappen, hij staat al goed. de knoppen zijn
30px tekst met padding eromheen dus je raakt ze met je duim.

Waarom: scenario 2. blog lezen op de telefoon zonder horizontaal scrollen.

Bron: https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design

## Keuze 3, mobile first met media queries

De gewone css die buiten alle media queries staat is mijn mobiele versie. daar zit geen
vaste breedte in en alles staat onder elkaar. daarna gebruik ik min-width om er dingen bij
te zetten voor grotere schermen: vanaf 768 en vanaf 1024 krijgt main een max width zodat de
regels tekst niet superlang worden op een breed scherm. dat is de mobile first volgorde,
klein beginnen en omhoog bouwen in plaats van andersom, en dat is ook wat mdn aanraadt.

Voor mobiel zelf heb ik 1 max-width query. tot en met 480px zet ik het portret op float none
zodat mijn tekst er niet meer in een smal kolommetje naast geduwd wordt, en worden de
knoppen wat kleiner.

Getest met f12 op 320, 375, 768 en 1280 breed. nergens horizontaal scrollen en de tekst
blijft overal leesbaar.

Waarom: scenario 2 leest mijn blog op een telefoon, die mag niet hoeven zoomen of
horizontaal scrollen.

Bron: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_media_queries/Using_media_queries

## Keuze 4, custom fonts

De h1 is press start 2p en de h2 is MonsterFriend, allebei pixel fonts. undertale was
vroeger als kind mijn favoriete game, daarom heb ik de achtergrond en juist dit stel fonts
gekozen. het zijn custom fonts, dus geen standaard font van de browser maar bestanden die ik
zelf heb gedownload en in mijn assets map heb gezet. met font-face geef ik ze in de css een
naam en het pad naar dat bestand, en daarna gebruik ik die naam gewoon in font-family. zo
ziet het er op elke computer hetzelfde uit, ook als iemand dat font niet geinstalleerd heeft.

Maar in zo'n pixel font een hele alinea lezen is niet fijn, dus alle p tekst staat in het
sans font.

Waarom: het moet er wel uitzien als mij, het is een portfolio en geen bedrijfssite. maar de
recruiter uit scenario 1 moet mijn tekst ook echt kunnen lezen.

Bron: https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face

## Keuze 5, donker met lichte tekst en rode koppen

De video achtergrond is donker dus de tekst is aliceblue of wit. de h2 is rood, dat valt op
tegen zwart en hakt de pagina in stukjes zodat je snel kan scannen waar iets over gaat. dat
is precies wat je wil als je snel door de blog scrollt.

## Keuze 6, externe css en een professionele mappenstructuur

De css staat in 1 apart bestand en niet in de html. ik pas het op 1 plek aan en het
verandert meteen op alle 4 de paginas.

Verder heb ik bewust voor een professionele mappenstructuur gekozen en niet alles los in 1
map. in assets staan css, fonts, img en video netjes apart. dat had ik ooit gelezen en het
wordt ook zo aangeraden. het is veel overzichtelijker, ik weet meteen waar ik moet zijn, en
ik kan er zo een nieuwe pagina of blogpost bij zetten zonder dat ik iets hoef te verplaatsen.

## Wat ik hierna nog ga doen

Een echte foto in het portret zetten in plaats van tekst, met een alt tekst erbij. en mijn
footer is nu leeg op alle paginas, daar wil ik nog iets in zetten.
