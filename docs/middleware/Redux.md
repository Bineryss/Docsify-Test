# Redux

Redux ist toll, da es den gesammten Datenfluss handelt.
Zudem muss man sich auch nicht drum kümmern, die Daten zu speichern, 
da dass von [Saga](/middleware/SagaMiddleware.md) übernommen wird.

Zur installation folgender befehl
>npm install redux

### Modell von Redux
Redux handelt intern die Verbindung zum Server und updatet enstprechend die View.
````mermaid
graph LR
Reducer --> ControllerView
ControllerView --> ActionCreator
ActionCreator --> Store
ActionCreator --- Server
Store --> Reducer
````

## Reducer
Der Reducer macht reducer Sachen. 

## Controller View
Die Controller View handelt das Verhalten des View Elements.
Das wird hier von der [Logik](/react/AufbauKomponente.md) gehändelt.
>Man sieht die **Controller View** als Wrapper für das HTML-Element

## Action Creator
Der Action Creator händelt die Verbindung zum Server sowie das Speichern und Updaten von Daten.

### Server
Der [Server](/server/README.md) (Backend) behandelt die Datenverarbeitung und liefert neue Preis Daten.

## Store
Der Store ist der Datenspüeicher für das Frontend, da hier alles gespeicher wird, 
dass nur für die aktuelle Sitzung wichtig ist.
>Beim schließen der Seite wird der Store gelöscht

Man sollte aber beachten, da die entsprechenden Ports nicht blockiert sind, 
keine sensiblen Informationen im Stor zu speichern. Da Browser den gesammten Store auslesen können.