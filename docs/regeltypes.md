# Regel Types
In de onderstaande voorbeelden zijn volledige labels gebruikt om een correct en compleet voorbeeld te hanteren. De layout 
van een regel wordt uitsluitend bepaald a.d.h.v. de waarde van 'type'.

<details>
<summary>Standaard regel</summary>
Een normale omschrijving. Achter de dubbele punt komt meteen de inhoud, links uitgelijnd.
```json
  {
    "omschrijving": "Soort verzekering",
    "inhoud": "${10142o}",
    "vereiste_labels": [],
    "type": "standaard",
    "maatschappij": ["P311"]
  }
```
```text
Soort verzekering         : Personenauto
```
</details>

<details>
<summary>Bedrag regel</summary>
Een normale omschrijving. Achter de dubbele punt komt een euro teken, en het bedrag (de inhoud) is rechts uitgelijnd zodat 
alle bedragen op dezelfde plaats uitlijnen.

```json
  {
    "omschrijving": "Eigen risico",
    "inhoud": "${10043}",
    "vereiste_labels": [],
    "type": "bedrag",
    "maatschappij": ["P311"]
  }
```
```text
Eigen risico              : €   500,00
```
</details>

