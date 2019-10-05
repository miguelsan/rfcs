# 0000 - Extended subscriptions

## Status
[status]: #status

Proposed

## Summary
[summary]: #summary

Users shall be able to subscribe for changes in selected regions and for selected tags.

> Notification für Änderungen in Regionen und Stichwörtern

> Moderator*innen werden bei Änderungen und neuen
Bewertungen in ihrer Stadt (Regionalpilot*innen) bzw. zu
ihrem Stichwort (Themenpilot*innen) benachrichtigt

## Context
[context]: #context

> This section describes the forces at play, including technological, political, social, and project local. These forces are probably in tension, and should be called out as such. The language in this section is value-neutral. It is simply describing facts.

> MVP:
> - Nicht nur bei Änderungen, sondern auch bei Bewertungen
werden Subscriber informiert
> - Am Ende jeder Notification Mail gibt es einen Link, worüber
das Abonnement beendet werden kann
> - Notification-Mails werden nur alle 30 min. verschickt, jeweils
mit der bis dahin letzten änderung (Das verhindert eine
Mailflut, wenn jemand 20 mal hintereinander den selber
Beitrag editiert)
> - Wird ein Eintrag gelöscht, wird den Piloten der Löschgrund
mitgeteilt.

> NTH:
> - Notifications von gelöschten Beiträgen erhalten nur Piloten
und leute, die den einzelnen Beitrag abonniert haben.
Normale "Flächenabonnementen" werden nicht über
löschungen informiert.

> MVP: Wird derzeit in Weißrussland entwickelt. Siehe
http://mapa.falanster.by/
> - Über Sharing-Button rechts mittig kann der Nutzer folgende
Optionen wählen
#Kartenansicht abonnieren (Pop-up zum mailadresse
eingeben.)
#URL-Teilen (Pop-up mit aktueller URL der Karte)
#Karte einbetten (Pop-up mit Iframe-Code)
#Download (Popup mit Feld für Mailadresse, an die der
Downloadlink geschickt werden soll. Eingeloggte Nutzer sehen
Download-Link direkt. Evtl. Downloadbutton nur für eingeloggte
Nutzer zeigen.
> - Beim Abonnieren wird nicht nur der Bereich berücksichtigt,
sondern auch die gewählten Hashtags. Hat der Nutzer dagegen
nur einen einzelnen Eintrag geöffnet, wird nur dieser abonniert.
(also ganz logisch wird immer das abonniert bzw. geteilt, was
gerade in der URL steht.)
> - Über einen Kurztext unter der Mail-Eingabe-Zeile wird dann

> NTH:
> - Beim Abonnieren werden nicht nur Hashtags berücksichtigt
sondern auch suchbegriffe
> - Umfassende Suchfunktion, die mehrere Suchbegriffe
gleichzeitig filtern kann als und-Suche bzw. mit Komma als
Oder-Suche

## Decision
[decision]: #decision

> This section describes our response to these forces. It is stated in full sentences, with active voice. "We will ..."

## Consequences
[consequences]: #consequences

> This section describes the resulting context, after applying the decision. All consequences should be listed here, not just the "positive" ones. A particular decision may have positive, negative, and neutral consequences, but all of them affect the team and project in the future.

## References
[references]: #references

- http://thinkrelevance.com/blog/2011/11/15/documenting-architecture-decisions
