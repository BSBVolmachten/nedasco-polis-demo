# Demonstratief Nedasco Polis Project

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
| Eigen risico        | € 10043 Vrijwillig      |                           |           |                   |      |      |      |
|                     | 10043                   | Getal inclusief decimalen | Links     | verwijderen       |      |      |      |
| Gezinssamenstelling | 10694                   |                           |           |                   | x    |      |      |
|                     | 10694                   | Omschrijving              | Links     | verwijderen       | x    |      |      |


## Optie A

Optie A splits bestanden op per hoofdbranche/branche/maatschappij. Een voorbeeld is 
[hier](https://github.com/BSBVolmachten/nedasco-polis-demo/blob/main/src/b/05000/05011.json) te vinden.

Enkele voordelen hiervan zijn:
- meer overzicht over welke labels voor welk polisblad bestemd zijn vanuit de data bestanden
- minder condities nodig in het opbouwen van de polis
  - minder vast te leggen in het bestand zelf
  - minder code nodig voor het verwerken
  - versimpeld automatisch testen

Enkele nadelen hiervan zijn:
- meer bestanden dus meer onderhoud aan de data zelf
- meer dubbel werk m.b.t. labels die veel voor komen voor meerdere maatschappijen (grote impact)
- denkwijze losgekoppeld van functioneel ontwerp
  - 1 wijziging in het functioneel ontwerp zorgt voor meerdere wijzigingen in meerdere data bestanden
