# Demonstratief Nedasco Polis Project


## Het label / regel Object
Het label / regel object wordt naar verwachting opgenomen in databestanden die in JSON zijn genoteerd. JSON staat voor
javascript object notation en is een vrij eenvoudige manier van gestructureerd data op te slaan. Het is tegenwoordig 
de standaard op het web en wordt dus ook door alles en iedereen ondersteund. Voordat er verder gelezen wordt is het
sterk aangeraden om eerst de basis van JSON door te nemen op [deze website](https://developers.squarespace.com/what-is-json).
Gezien het feit dat veel uitleg over JSON niet geschreven is voor lezers zonder technische achtergrond volgt er nu een
hoofdstuk waarin kort uitgelegd wordt wat JSON nu eigenlijk is zonder al te veel technische termen.

#### JSON
Javascript(JS) Object Notation, ofwel JSON is een databestand dat een gestructureerde notatie aanhoudt welke overeen komt
met de notatie zoals die in Javascript code voorkomt. Het heet niet voor niets een 'Object Notation'. In JSON is alles 
namelijk gestructureerd door middel van het groeperen van data in objecten. Zo'n object is te herkennen aan de accolades:
```text
{
 ...
}
```
Deze accolades, en dus objecten, vormen de basis van een JSON bestand. Ieder JSON bestand begint daarom ook altijd met
een open accolade, en eindigt met een gesloten accolade. In zo'n object willen we data op slaan, en het liefst zo 
logisch mogelijk. De logica komt voornamelijk door structuur die de gebruiker zelf in bouwt en hanteert, en zo zullen ook 
onze labels / regels een eigen stramine aanhouden. Verdere uitleg volgt in latere hoofdstukken.

Allereerst is het nodig om te laten zien hoe objecten hun data vast houden. In een excel bestand bijvoorbeeld, staat alles
netjes in kolommen of rijen ingedeeld. Wat hierbij cruciaal is is het aangeven van de locatie van deze waarde. De rijen
en kolommen samen geven een makkelijke manier van het aangeven waar de data zich bevindt, namelijk de letter-cijfer 
combinatie. Zo is linksboven bijvoorbeeld de cell 'A1', en rechts naast deze cell is 'B2'. Hieronder een voorbeeld van
een Excel tabel:

| 1 | A    | B  | C     |
|---|------|----|-------|
| 2 | dit  | is | de    |
| 3 | data | in | excel |

In dit geval is de 'data' van de tabel: 'dit is de data in excel'. De data is verdeeld over verschillende cellen, en de 
locatie is A1 tot en met C2, ofwel A1:C2. In het volgende onderdeel focussen we op een individueel datapunt, een cell.
Daaropvolgende onderdelen zullen laten zien hoe meerdere datapunten een logische vorm van gegevens op slaan kan zijn,
net zoals rijen en kolommen in een Excel bestand.

##### Waarden in een JSON bestand
Net zoals een cell in Excel een locatie aanduiding heeft (bijvoorbeeld A3 of D19), heeft JSON dit ook. Alleen de aanduiding
in JSON moet zelf verzonnen worden door middel van een stukje tekst tussen twee dubbele aanhalingstekens. Achter de 
locatie komt een dubbele punt, en daarna volgt de data die bij deze locatie hoort. Hieronder een voorbeeld:
```json
{
  "A1": "dit"
}
```
In het voorbeeld is te zien dat de locatie 'A1' is, en hierbij de waarde 'dit' hoort. Net zoals in ons Excel bestand.
Nu zouden we alle cel-aanduidingen kunnen overnemen en in JSON opnieuw noteren in een andere vorm, maar dat is natuurlijk
niet de insteek van het gebruiken van JSON. Wat bij Excel in de titelregel gedaan wordt, het aangeven wat een datapunt
weergeeft, kan bij JSON in het object gedaan worden, door de aanduiding een omschrijven de naam te geven. Neem de volgende
tabel:

| 1 | A     | B            |
|---|-------|--------------|
| 2 | Label | Omschrijving |
| 3 | 10142 | branche      |

Als we deze tabel lezen is het de data redelijk duidelijk: Het label 10142 heeft de omschrijving 'branche'. Zo ook in
JSON:
```json
{
  "label": "10142",
  "omschrijving": "branche"
}
```
Ook hier is het voor de hand liggend: het label is '10142' en de omschrijving die daarbij hoort, is 'branche'. De 
aanduidingen van waarden in een JSON object noemen we vanaf nu **properties** (enkelvoud: property). "label" en "omschrijving" zijn dus 
**properties** van het json object. Dit luidt het nieuwe onderdeel in: de soorten data.

##### Soorten waarden
Een property kan verschillende soorten waarden hebben. Zoals in Excel bijvoorbeeld een celeigenschap notatie bestaat, met
 als waarde 'getal', 'datum', 'tekst' etc., bestaan ook in JSON verschillende soorten waardes. In Excel wordt echter
 een celeigenschap meegegeven om aan te duiden welk soort de waarde is. In JSON wordt dit gedaan door een 
 andere manier van noteren. Er bestaan 3 basis soorten (Integer, String en Boolean), en 2 geavanceerde soort (Array, Object).
 
 ###### Integer (getal)
 In JSON wordt een getal een 'integer' genoemd, dit is redelijk voor de hand liggend wat betreft notatie: gewoon een getal.
 Er hoeven geen aanhalingstekens om het getal heen gezet te worden. Dit laat de computer weten dat het gaat om een 
 getal. **Let wel op, decimalen worden aangeduid met een punt '.', en niet een komma ','!**. Dit ziet er als volgt uit:
 ```json
{
  "getal": 24.2
}
```

###### String (tekst)
In JSON wordt een stuk tekst een 'string' genoemd. Dit kan een woord zijn, een letter, maar ook een of meerdere hele 
zinnen. Een string wordt altijd geopend en gesloten met dubbel aanhalingstekens. Dit zit er als volgt uit:
```json
{
  "string": "Dit is een regel tekst!"
}
```

###### Boolean (Ja/Nee)
In JSON (en de hele computer wereld) bestaat ook een Ja/Nee waarde, genoemd naar een 
[Britse wiskundige / logicus](https://nl.wikipedia.org/wiki/George_Boole) George Boole: de boolean. Dit wordt aangegeven
met twee mogelijke waarden: **true** en **false**. Hier hoeven geen dubbele aanhalingstekens om heen. Dit ziet er als 
volgt uit:
```json
{
  "boolean": true
}
```

###### Array (lijst)
Een van de meer geavanceerde soorten waarden zijn Array's of lijsten. Dit verklapt eigenlijk al wat het is: een 
opsomming van waarden. De notatie is ook heel simpel: de opsomming begint met een open nietje '\[' en sluimet een gesloten
nietje '\]'. Alle andere soorten waarden kunnen in deze opsomming voor komen. Dit ziet er bijvoorbeeld zo uit:
```json
{
  "array": ["dit is en string", 10.42, false, "nog een string", true]
}
```

###### Object 
Misschien niet verrassend, maar het 'object' waar we het voortdurend over hebben, zoals ook JSON, is ook een 
soort waarde. En zoals ook eerder beschreven, we noteren een object met accolades, met daarin alle properties die we 
zelf willen. Hier onder een voorbeeld van een leeg object (een object zonder properties):
```json
{

}
```
En een object met 1 property, genaamd 'key' met als waarde een nieuw (leeg) object:
```json
{
  "key": {}
}
```
En bij deze hebben we de kracht van JSON meteen te pakken, nameelijk: de combinatie van lijsten en object, die weer in
andere lijsten en objecten staan.

---

```json
  {
    "omschrijving": "Soort verzekering",
    "inhoud": "${10142o}",
    "vereiste_labels": [],
    "type": "standaard"
  }
```

## Voorbeeld tabel fuctioneel ontwerp bodyblock
De volgende tabel is een voorbeeld van een functioneel ontwerp van een bodyblok van een polis. De 'regel template' is
weg gelaten.

| omschrijving        | inhoud             | weergave                  | uitlijnen | regel verwijderen | regel template                                  | P311 | P368 | P375 |
|---------------------|--------------------|---------------------------|-----------|-------------------|-------------------------------------------------|------|------|------|
| Soort verzekering   | 10142              |                           |           |                   | 02 Soort verzekering         10142              | x    | x    | x    |
|                     | 10142              | Omschrijving              | Links     | niet verwijderen  |                                                 | x    | x    | x    |
| Risico adres        | 10708 10710 10711  |                           |           |                   | 03 Risico adres              10708 10710 10711  | x    | x    |      |
|                     | 10708              |                           | Links     | verwijderen       |                                                 | x    | x    |      |
|                     | 10710              | Getal exclusief decimalen | Links     | niet verwijderen  |                                                 | x    | x    |      |
|                     | 10711              |                           | Links     | niet verwijderen  |                                                 | x    | x    |      |
| Eigen risico        | € 10043 Vrijwillig |                           |           |                   | 10 Eigen risico              € 10043 Vrijwillig |      |      | x    |
|                     | 10043              | Getal inclusief decimalen | Links     | verwijderen       |                                                 |      |      | x    |
| Gezinssamenstelling | 10694              |                           |           |                   | 10 Gezinssamenstelling       10694              | x    |      |      |
|                     | 10694              | Omschrijving              | Links     | verwijderen       |                                                 | x    |      |      |

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
genereren. Het is is voor optie A wel iets meer werk gezien de data bestanden niet in denkwijze en structuur overeen 
komen met het functioneel ontwerp.
