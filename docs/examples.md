# Voorbeelden van wijzigingen

### Tekstueel
Origineel object:
```json
  {
    "omschrijving": "Soort verzekering",
    "inhoud": "${10142o}",
    "vereiste_labels": [],
    "type": "standaard",
    "maatschappij": ["P311"]
  }
```

Er komt een wijziging binnen: De omschrijving van polis 05000/05501 moet worden gewijzigd. Er staat nu de omschrijving die
uit ANVA komt, maar dit moet een statische tekst worden, nl. 'Inboedel'. Verander de inhoud van het regel object naar:
'Inboedel'. Omdat er geen accolades omheen en dollar teken bij staat, is de inhoud nu veranderd naar statische tekst.
Dit ziet er als volgt uit:
```json
  {
    "omschrijving": "Soort verzekering",
    "inhoud": "Inboedel",
    "vereiste_labels": [],
    "type": "standaard",
    "maatschappij": ["P311"]
  }
```

### Nieuwe maatschappij
```json
  {
    "omschrijving": "Soort verzekering",
    "inhoud": "${10142o}",
    "vereiste_labels": [],
    "type": "standaard",
    "maatschappij": ["P311"]
  }
```
Branche 05000/05501 heeft een nieuwe maatschappij, P330. De labels moeten ook voor de nieuwe maatschappij gaan gelden. Neem het
regel object, en specifiek de 'maatschappij' eigenschap, en voeg waar nodig de nieuwe maatschappij toe aan de lijst. De
regel zal nu ook voor die maatschappij op het polisblad komen.
Voor het voorbeeld ziet dit er als volgt uit:
```json
  {
    "omschrijving": "Soort verzekering",
    "inhoud": "${10142o}",
    "vereiste_labels": [],
    "type": "standaard",
    "maatschappij": ["P311", "P330"]
  }
```
