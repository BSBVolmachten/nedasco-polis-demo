# Demonstratief Nedasco Polis Project

## Voorbeeld tabel
De volgende tabel is een voorbeeld van een functioneel ontwerp van een bodyblok van een polis. De 'regel template' is
weg gelaten.

| omschrijving        | inhoud                  | weergave                  | uitlijnen | regel verwijderen | P311 | P368 | P375 |
|---------------------|-------------------------|---------------------------|-----------|-------------------|------|------|------|
| Soort verzekering   | 10142                   |                           |           |                   | x    | x    | x    |
|                     | 10142                   | Omschrijving              | Links     | niet verwijderen  | x    | x    | x    |
| Risico adres        | 10708 10710 10711       |                           |           |                   | x    | x    |      |
|                     | 10708                   |                           | Links     | verwijderen       | x    | x    |      |
|                     | 10710                   | Getal exclusief decimalen | Links     | niet verwijderen  | x    | x    |      |
|                     | 10711                   |                           | Links     | niet verwijderen  | x    | x    |      |
| Eigen risico        | € 10043 Vrijwillig      |                           |           |                   |      |      | x    |
|                     | 10043                   | Getal inclusief decimalen | Links     | verwijderen       |      |      | x    |
| Gezinssamenstelling | 10694                   |                           |           |                   | x    |      |      |
|                     | 10694                   | Omschrijving              | Links     | verwijderen       | x    |      |      |


## Opties voor data

#### Optie A
Optie A splits bestanden op per hoofdbranche/branche/maatschappij. Een voorbeeld is 
[hier](https://github.com/BSBVolmachten/nedasco-polis-demo/blob/main/src/b/05000/05011.json) te vinden.

Enkele voordelen hiervan zijn:
- meer overzicht over welke labels voor welk polisblad bestemd zijn vanuit de data bestanden
- minder condities nodig in het opbouwen van de polis
  - minder vast te leggen in het bestand zelf
  - minder code nodig voor het verwerken (kleine impact)
  - versimpeld automatisch testen

Enkele nadelen hiervan zijn:
- meer bestanden dus meer onderhoud aan de data zelf
- meer dubbel werk m.b.t. labels die veel voor komen voor meerdere maatschappijen (grote impact)
- denkwijze losgekoppeld van functioneel ontwerp
  - 1 wijziging in het functioneel ontwerp zorgt voor meerdere wijzigingen in meerdere data bestanden

#### Optie B
Optie B splits bestanden op per hoofdbranche/branche. Een voorbeeld is 
[hier](https://github.com/BSBVolmachten/nedasco-polis-demo/blob/main/src/b/05000/05011.json) te vinden.

Enkele voordelen hiervan zijn:
- significant minder dubbel werk m.b.t. het wijzigen van labels per polisblad
- minder bestanden dus minder onderhoud aan data
- denkwijzige FO nagenoeg 1 op 1 terug te vinden in data bestanden

Enkele nadelen hiervan zijn:
- complexere code nodig om het bestand te verwerken (kleine impact)
- extra complexiteit bij logica wijzigingen (indien direct in het data bestand)
- enkele fouten zijn uitsluitend per branche te herkennen, en niet verder te specificeren naar maatschappij


## Omzetting
Voor beide opties is het nog steeds mogelijk om uit een functioneel ontwerp van de bodyblokken een data bestand te
genereren. Het is is voor optie A wel iets meer werk gezien de data bestanden niet in denkwijze overeen komen met het
functioneel ontwerp.
