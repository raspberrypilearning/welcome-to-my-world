## Bouw en test

Nu is het tijd om je simulatie te maken. Begin met nadenken over de achtergrond van je simulatie. Zal het bewegen of zal het statisch zijn?

![Voorbeelden van wereldprojecten.](images/step.png)

**Tip**: Vergeet niet om je project elke keer te testen wanneer je iets toevoegt. Het is veel gemakkelijker om bugs te vinden en op te lossen voordat je meer wijzigingen aanbrengt.

--- task ---

Kies een achtergrond die je wilt gebruiken voor je simulatie. De achtergrond kan statisch blijven, of je zou hem kunnen laten bewegen.

--- collapse ---
---
title: Laat een achtergrond bewegen
---

In plaats van de achtergrond te laten bwegen, ga je in feite een sprite laten bewegen, die je hebt gemaakt door een achtergrond te kopiëren.

Maak een nieuwe sprite door de afbeeldingen vanaf een achtergrond te kopiëren en toe te voegen aan je sprite.

![Teken een nieuw sprite-gereedschap geselecteerd.](images/paint-new-sprite.png) ![Het kopieer gereedschap dat is gemarkeerd in de werkbalk.](images/copy-backdrop.png) ![Het plak gereedschap dat is gemarkeerd in de werkbalk.](images/paste-backdrop.png)

Maak een nieuwe `variabele`{:class='block3variables'} met de naam `beweeg_x`{:class='block3variables'}.

De volgende blokken zullen een beweeg-effect op de sprite maken wanneer de muis naar links en rechts wordt bewogen.

```blocks3
when flag clicked
go to x: (0) y: (0)
create clone of (myself v)
set [beweeg_x v] to (0)
forever
if <(mouse x) > (200)> then
change [beweeg_x v] by (5)
end
if <(mouse x) < (-200)> then
change [beweeg_x v] by (-5)
end
go to x: ((beweeg_x v) mod (480)) y: (0)

when I start as a clone
forever
go to x: ((beweeg_x v) mod (-480)) y: (0)
```

**Tip:** In plaats van de muispositie te gebruiken, kun je op een knop klikken of op een toets drukken om de `beweeg_x`{:class='block3variables'} variabele te wijzigen.

--- /collapse ---

--- /task ---

--- task ---

Denk aan de sprites die je gaat gebruiken voor je simulatie. Zullen sommigen van hen niet bewegen in de scène, zal hun uiterlijk, effect of beweging veranderen wanneer ze worden gebruikt? Schuiven ze over het scherm? Hoe worden ze bestuurd als ze bewegen?

--- collapse ---
---
title: Beweeg een sprite met een druk op een toets
---

```blocks3
when flag clicked
forever
if <key (left arrow v) pressed?> then
change x by (-10)
end
if <key (right arrow v) pressed?> then
change x by (10)
end
```

--- /collapse ---


--- collapse ---
---
title: Verplaats een sprite met besturingselementen op het scherm
---

Maak sprites voor je richtingen en plaats ze op het scherm.

![Scratch kat op het speelveld met de rechter- en linkerknop in de rechterbenedenhoek van het scherm.](images/scratch-controls.png)

De knoppen zouden besturing moeten hebben om hun richting uit te zenden wanneer ze worden aangeklikt.

![Linker sprite knop.](images/left-sprite.png)
```blocks3
when this sprite clicked
broadcast [links v]
```

De sprite die wordt bestuurd moet in de aangegeven richting bewegen. ![De Scratch kat-sprite.](images/scratch-cat.png)
```blocks3
when I receive [links v]
change x by (-10)
```

--- /collapse ---

--- collapse ---
---
title: Wijzig een sprite wanneer erop wordt geklikt
---

Je kunt het uiterlijk en de oriëntatie van een sprite veranderen wanneer er op wordt geklikt. Hier zijn enkele codevoorbeelden.

```blocks3
when this sprite clicked
switch costume to [uiterlijk2 v]

when this sprite clicked
change [color v] effect by (25)

when this sprite clicked
turn cw (30) degrees
```

--- /collapse ---

--- collapse ---
---
title: Animeer een sprite met uiterlijken
---

Er zijn verschillende manieren om een sprite te animeren met behulp van uiterlijken. Hier zijn een paar voorbeelden.

```blocks3
when flag clicked
forever
next costume
wait (0.2) seconds

When I receive [rechts v]
switch costume to [rechts v]
repeat (3)
next costume
wait (0.2) seconds

When this sprite clicked
repeat (3)
next costume
```

--- /collapse ---

--- collapse ---
---
title: Verander de laag van een sprite
---

Sprites die je gebruikt als achtergrond moeten op de achterlaag staan. Sprites die je op de voorgrond wilt hebben, moeten op de bovenste laag staan. Je kunt de laag van een sprite of de kloon instellen.

```blocks3
when flag clicked
go to [back v] layer

when I start as a clone
go to [front v] layer
```

--- /collapse ---

--- /task ---

--- task ---

Zullen je sprites zichzelf moeten klonen? Zullen ze veel kopieën maken die verschillende acties uitvoeren wanneer ze beginnen?

--- collapse ---
---
title: Maak klonen van een sprite
---
Hier zijn een paar manieren om klonen te maken en ze te verwijderen na verschillende gebeurtenissen.

```blocks3
when flag clicked
repeat (20)
create clone of (myself v)

when flag clicked
forever
if <touching (mouse-pointer v)> then
create clone of (myself v)

when I start as a clone
forever
if <touching (edge v)> then
delete this clone
```

--- /collapse ---

--- collapse ---
---
title: Maak je klonen willekeurig
---

Wanneer een kloon wordt gemaakt, kan hij instructies nodig hebben over hoe te bewegen, en dit zou je zelfs per kloon verschillend kunnen instellen. Je kunt `willekeurig getal`{:class='block3operators'} blokken gebruiken om dit te doen.

```blocks3
when I start as a clone
point in direction (pick random (0) to (359))
forever
move (10) steps
wait (0.1) seconds
if on edge, bounce

when I start as a clone
forever
glide (pick random (1) to (10)) secs to (mouse-pointer v)
```

--- /collapse ---

--- collapse ---
---
title: Gebeurtenissen om een kloon te maken
---

Klonen kunnen worden gemaakt met veel verschillende `gebeurtenissen`{:class='block3events'}. De blokken hieronder zullen een kloon van een sprite maken elke keer dat er op wordt geklikt.

```blocks3
when this sprite clicked
create clone of [myself v]
```

Je kunt ook klonen maken zodra er met de muis wordt geklikt, en de kloon op de plek van de muisaanwijzer tevoorschijn laten komen. Klonen kunnen op elke gewenste locatie worden weergegeven, dus je zou ze naar een specifieke sprite of positie kunnen laten gaan.

```blocks3
when flag clicked
forever
if <mouse down?> then
create clone of [myself v]

when I start as a clone
go to x: (mouse x) y: (mouse y)
```

--- /collapse ---

--- /task ---

--- task ---

Zal er een muziek- of geluidseffect-aspect in je simulatie zijn? Misschien is er achtergrondgeluid, of speelt een sprite een melodie af wanneer er op wordt geklikt?

--- collapse ---
---
title: De Scratch-muziekextensie
---

Zodra je de extensie hebt toegevoegd, zijn er nieuwe blokken beschikbaar.

Er zijn drie belangrijke elementen die binnen deze blokken kunnen worden veranderd.

- `beats`{:class='block3custom'} zijn een tijdseenheid die wordt gebruikt in muziek. Een beat kan een seconde lang of een kwart seconde lang zijn. Het is aan jou.

- `tempo`{:class='block3custom'} stelt in hoeveel slagen er in een minuut zijn: `60` slagen per minuut zou betekenen dat een hartslag `1` seconde lang is.

- `noot`{:class='block3custom'} is de toonhoogte van de toon die wordt afgespeeld: `60` is hetzelfde als **centrale C** op een piano.

--- /collapse ---

[[[generic-scratch3-sound-from-library]]]

[[[scratch3-record-sound]]]

[[[scratch3-sound-effects]]]

[[[scratch3-reverse-sound]]]

[[[scratch3-crop-sound]]]

--- /task ---

--- task ---

Wil je dat je sprites een actie blijven herhalen, totdat aan een voorwaarde is voldaan? Je kunt `herhaal tot`{:class='block3control'} blokken gebruiken om dit te doen.

--- collapse ---
---
title: Gebruik herhaal tot blokken
---

Hier is een reeks blokken die een sprite in beweging houdt, totdat de `y`{:class='block3motion'} positie `-250` bereikt.

```blocks3
when flag clicked
repeat until <(y position) < [-250]>
change y by (-10)
```

--- /collapse ---

--- /task ---


--- task ---

Denk aan de structuur van je blokken, en de input die nodig zou kunnen zijn. Kun je `Mijn blokken`{:class='block3myblocks'} gebruiken om je project **te optimaliseren**?

--- collapse ---
---
title: Gebruik Mijn blokken om code te organiseren
---

De eenvoudigste manier om `Mijn blokken`{:class='block3myblocks'} te gebruiken is om je code te helpen organiseren. Hier is een eenvoudig voorbeeld.

```blocks3
define ga naar rechts
if <not <touching (edge v) ?>> then
switch costume to [rechts_1 v]
change x by (2)
switch costume to [rechts_2 v]
change x by (2)
switch costume to [rechts_3 v]
change x by (2)
end

define ga naar links
if <not <touching (edge v) ?>> then
switch costume to [links_1 v]
change x by (-2)
switch costume to [links_2 v]
change x by (-2)
switch costume to [links_3 v]
change x by (-2)
end

when flag clicked
forever
if <key (right arrow v) pressed> then
ga naar rechts
end
if <key (left arrow v) pressed> then
ga naar links
```

--- /collapse ---

--- collapse ---
---
title: Invoer gebruiken met Mijn blokken
---

In `Mijn blokken`{:class='block3myblocks'} kun je tekst en cijfers invoeren.

```blocks3
define beweeg (richting) (snelheid)
if <(richting) = [links]> then
change x by ((-1) * (snelheid))
end
if <(richting) = [rechts]> then
change x by ((1) * (snelheid))

when flag clicked
if <(mouse x) < (-200)> then
beweeg [links] (snelheid)
end
if <(mouse x) > (200)> then
beweeg [rechts] (snelheid)
```

--- /collapse ---

--- /task ---

--- task ---

Het belangrijkste van de meeste 2.5D scènes is het veranderen van de grootte van een sprite om de indruk te geven dat het verder weg is.

--- collapse ---
---
title: De grootte van de sprite wijzigen ten opzichte van de positie
---

De volgende blokken maken een sprite kleiner als deze omhoog beweegt, en lijken daarom verder weg.

```blocks3
when flag clicked
forever
change y by (10)
change size by (-3)
wait (0.2) secs
```

--- /collapse ---

--- /task ---


--- task ---

**Test:** Laat iemand anders je project zien en ontvang hun feedback. Wil je wijzigingen aanbrengen in je scène?

--- /task ---

--- task ---

**Fouten oplossen:** Mogelijk vind je enkele fouten in jouw project die je moet oplossen. Hier zijn enkele veelvoorkomende fouten.

--- collapse ---
---
title: Mijn klonen verschijnen niet
---

Zijn je klonen verborgen? Zorg ervoor dat wanneer de klonen worden gemaakt, de `verschijn`{:class='block3looks'} optie wordt gebruikt. Zorg er ook voor dat je ze op de `voorgrond`{:class='block3looks'} hebt.


--- /collapse ---

--- collapse ---
---
title: Mijn sprite beweegt niet goed van het scherm af
---

Als je wilt dat een sprite van de ene kant van het scherm naar de andere gaat, of verdwijnt wanneer het naar de ene kant van het scherm gaat, dan kun je de positie ervan controleren en wat actie uitvoeren. Controleer waar het centrum van je sprite is, op het uiterlijk, om ervoor te zorgen dat dit goed werkt. Het is het makkelijkst om de sprite naar de zijkant van het scherm te slepen en vervolgens de `x`{:class='block3motion'} en `y`{:class='block3motion'} posities te controleren.


--- /collapse ---

--- collapse ---
---
title: Mijn blokken werken niet
---

Heb je gecontroleerd of je je nieuwe blok ergens in je code gebruikt. Je kunt een nieuw blok `definiëren`{:class='block3myblocks'}, maar dan moet je het gebruiken om de code eronder daadwerkelijk uit te voeren.

--- /collapse ---

--- collapse ---
---
title: Mijn klonen doen niets
---

Gebruik je het `wanneer ik als kloon start`{:class='block3control'} blok, om de kloon te vertellen wat hij moet doen?

Heb je voorwaarden die de klonen zouden kunnen tegenhouden? Moeten ze bijvoorbeeld bewegen totdat ze de rand van het scherm raken? Als er een kloon wordt gemaakt aan de rand van het scherm, dan doen ze niets.


--- /collapse ---

--- collapse ---
---
title: Mijn sprites bewegen in de verkeerde richting
---

Controleer of je het `verander x met`{:class='block3motion'} blok gebruikt om de sprites naar links en rechts te verplaatsen, en het `verander y met`{:class='block3motion'} blok om ze omhoog en omlaag te bewegen.

Controleer of je positieve en negatieve getallen correct gebruikt om `x`{:class='block3motion'} en `y`{:class='block3motion'} te verhogen of te verlagen.

--- /collapse ---

Mogelijk vind je een fout die hier niet wordt vermeld. Kun je erachter komen hoe je het kunt oplossen?

We horen graag over je fouten en hoe je ze hebt opgelost. Gebruik de feedback knop onderaan deze pagina als je een andere fout in je project hebt gevonden.

--- /task ---

--- save ---
