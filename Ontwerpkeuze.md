# Ontwerpkeuzes

Alles hier is html en css die ik zelf heb geschreven. geen framework en geen template.
opgezocht op youtube en in de docs van mdn.

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

## Keuze 3, game fonts voor de koppen en een rustig font voor de tekst

De h1 is press start 2p en de h2 is MonsterFriend, allebei pixel fonts die passen bij de
undertale achtergrond. maar in zo'n font een hele alinea lezen is niet fijn, dus alle p
tekst staat in het sans font. de eigen fonts laad ik in met font-face zodat ze op elke
computer hetzelfde zijn.

Waarom: het moet er wel uitzien als mij, het is een portfolio en geen bedrijfssite. maar de
recruiter uit scenario 1 moet mijn tekst ook echt kunnen lezen.

Bron: https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face

## Keuze 4, donker met lichte tekst en rode koppen

De video achtergrond is donker dus de tekst is aliceblue of wit. de h2 is rood, dat valt op
tegen zwart en hakt de pagina in stukjes zodat je snel kan scannen waar iets over gaat. dat
is precies wat je wil als je snel door de blog scrollt.

## Keuze 5, externe css en een assets map

De css staat in 1 apart bestand en niet in de html. ik pas het op 1 plek aan en het
verandert op alle 4 de paginas. in assets staan css, fonts, img en video apart, zodat ik er
zo een nieuwe pagina of blogpost bij kan zetten zonder dat ik iets moet verplaatsen.

## Eerlijk over mobile first

Ik heb de site op mijn laptop gebouwd en dus niet mobile first. mdn raadt mobile first aan
en dat had ik beter kunnen doen, want dan begin je klein en bouw je omhoog in plaats van
andersom.

Getest heb ik hem daarna wel, met f12 in de browser op 320, 375, 768 en 1280 breed.
nergens horizontaal scrollen en de tekst blijft leesbaar. dat komt vooral door keuze 2,
alles staat al onder elkaar en ik gebruik bijna nergens vaste breedtes in px.

Wat nog niet af is: het portret is 190px breed en staat op float right. op 320px duwt hij de
tekst ernaast in een smal kolommetje. de mail link in de footer is nu zwart op een donkere
achtergrond en dat is te weinig contrast. dat zijn de 2 dingen die ik hierna ga fixen.
