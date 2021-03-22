# Ruegen-Ranger-Pretest Codebuch #
Codebuch Stand 2021-03-10<br>
erstellt von Artur Stolinsky (as383@hdm-stuttgart.de)

## Inhalt
- Finale_Edgelist_Rügen-Ranger.csv
- Finale_Nodelist_Rügen-Ranger.csv 
- Codebuch.md (Codierung der Datensätze)

## Ursprung und Datenerhebung

Im Pretest werden exemplarisch zehn vom Presserat öffentlich gerügte Artikel in einem Gesamtnetzwerk dargestellt. Die Daten wurden auf der Website des Presserats unter folgendem Link erhoben: (https://www.presserat.de/ruegen-presse-uebersicht.html). Die Artikel aus dem Pretest stammen von 1990 und 2020.

In der endgültigen Datenerhebung werden die Daten im Zeitraum von 1990 bis 2019 erhoben. 

Das Netzwerk ist ein *gerichtetes two-mode Akteursnetzwerk*. Das Gesamtnetzwerk wird aus vielen kleinen Teilnetzwerken bestehen, ausgehend von den jeweiligen Ziffern des Pressekodex.

## Weitere Anmerkungen

Dieses Codebuch wird für das restliche Projekt verwendet werden. Das Codebuch wird bei Änderungen schnellstmöglich aktualisiert.

# Nodes und dazugehörige Attribute


0 = Ziffer<br>
1 = Publikationsmedium


### Ziffern Pressekodex

Diese Nodes stehen für einzelne Ziffern des Pressekodex, gegen die verstoßen worden ist. Sie werden im Netzwerk zwischen dem Presserat und den gerügten Artikeln dargestellt. Außerdem gibt es die Nodes ZifferPra und Zifferunbekannt. Ersteres für die Präambel, Zweiteres für Artikel, zu denen keine Ziffer gefunden wurden. Ziffern, gegen die von keinem Artikel verstoßen worden sind, werden nicht in Nodelist und Netzwerk berücksichtigt. Gegen die Ziffern 15 und 16 gab es keinen Verstoß, diese sind in der Nodelist nicht zu finden.
Diese Kategorie besitzt folgende ***Attribute***:

**id**

eindeutige Codierung des Knotens, wird als "Ziffer" + Zahl angegeben (z.B. Ziffer10). Ausnahmen: ZifferPra und Zifferunbekannt

**name**

Vollständiger Name des Knotens (z.B. Pressekodex Ziffer 1)

**type**

Unterscheidung zwischen Ziffer und Publikationsmedium

0 = Ziffer<br>
1 = Publikationsmedium


### Publikationsmedium

Diese Nodes stehen für die Artikel, die eine Rüge vom Presserat erhalten haben. Sie werden außen im Netzwerk dargestellt. Diese Kategorie besitzt folgende ***Attribute***:

**id**

Anzeigename, entweder vollständig oder als Abkürzung (z.B. Bild, WAZ)
Zur Verhinderung von gleichen **id**'s ist eine gemeinsames Dokument erstellt worden. Dort sind alle bereits verwendeten Abkürzungen und Namen vermerkt.

**name**

Vollständiger Name des Publikationsmediums + Online/Offline (z.B. Grazia Magazin Online, Westfälischa Abendzeitung Offline)

**region**

Handelt es sich um ein regionales oder überregionales Publikationsmedium?

0 = überregional<br>
1 = regional<br>
3 = nichts davon, weil Ziffer

**type**

Unterscheidung zwischen Ziffer und Publikationsmedium

0 = Ziffer<br>
1 = Publikationsmedium

**published**

Definiert die Verfügbarkeit des Artikels

0 = online<br>
1 = offline<br>
3 = nichts davon, weil Ziffer


# Edge-Attribute

**from**

Ausgangspunkt der Kante (Name aus **id** verwenden)

**to**

Endpunkt der Kante (Name aus **id** verwenden)

**weight**

Art der Rüge

1 = öffentliche Rüge<br>
2 = nicht-öffentliche Rüge

**year**

Definiert das Jahr, in dem die Rüge erteilt worden ist

**az**

Aktenzeichen (z.B. (0031/20/2))

**code**

Codierung des gerügten Artikels (z.B. Bild/1990/1)
