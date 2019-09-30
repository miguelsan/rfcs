# 0004 - Moderation of entries, comments, and ratings

## Status
[status]: #status

Proposed

## Summary
[summary]: #summary

Admins and scouts shall be able to archive or delete entries (both places and events) as well as the corresponding comments and ratings.

> Admin kann RP ernennen, RP kann Bewertungen und
Einträge löschen

> Login-Funktion für Moderator*innen (Bildungsagent*innen u.
Regionalpilot*innen)

## Context
[context]: #context

> This section describes the forces at play, including technological, political, social, and project local. These forces are probably in tension, and should be called out as such. The language in this section is value-neutral. It is simply describing facts.

### MVP

> Login und Passwortreset funktioniert zuverlässig
> - Nutzername kann weg bei login. Mail und Passwort reicht!
(Login wird nur zum Löschen von Einträgen und Bewertungen
gebraucht, nicht zum Abonnieren, daher kann login-Link von
kvm.org direkt auf ofdb.org verweisen. Nutzername als
optionaler und änderbarer Name)

> Einträge können ~~gelöscht~~archiviert werden
> - Unter ofdb.org wird ähnlich dem Archivieren-Button für
Bewertungen ein Archivieren-Button für Einträge angezeigt.
> - Der Eintrag ist dann auf der Karte nicht mehr sichtbar. Kann
folglich auch nicht mehr bearbeitet werden.
> - Über die ID des Eintrags, kann man den Beitrag im Backend
wiederfinden. Gelöschte Einträge sind im Backend als solche
Markiert. Löschgrund steht dabei, auch der letzte
Bearbeiter/Löscher wird angezegit.
> - Statt dem Archivieren-Button ist bei gelöschten Einträgen ein
"Restore-Button".
>-  Der Archvieren-Button ist ein Dropdown, wo man den
> Löschgrund auswählen muss. Da ist die Auswahl:
>    - #löschen-da-duplette
>    - #löschen-da-geschlossen
>    - #löschen-da-spam
>    - #löschen-da-fehleingabe
>    - #löschen-da-rechtswiedrig (Datenschutz, Illegal...)
> - Der Löschgrund wird als Hashtag zum Eintrag gespeichert

### NTH
> Archivierte Einträge können wiederhergestellt werden:
> - Muss man Restore-Gründe angeben??? (erstmal weglassen)
> - Wählt eine Nutzer #löschen-da-duplette wird ein Feld
angezeigt, wo man die ID des Eintrags eingeben muss, wovon
es eine Duplette ist. Alle Hashtags vom zu löschenden Beitrag
werden dann automatisch dem bleibenden hinzugefügt.
> - Kooperation mit GoodDB: Im Backend wird eine übersicht
angezeigt aller möglichen Dupletten mit dem Grad der
Dupletten übereinstimmung zum ältesten möglichen
Dupletteneintrag. Dies ist besonders wichtig, wenn wir Mass-
Uploads oder Schnittstellen zu anderen Portalen haben.

> - Eingeloggte Nutzer können einen Filter setzten "Zeige nur
veränderte Einträge" und sehen dann nur Änderungen

> - Alle geänderten Einträge die auf Freischaltung warten, sind als
Pinfarbe rot markiert

> Fairlogin als Plattformübergreifender login mit Facebook und
Google single sign on

> Alle Lösch und Archivierungsbutton werden Admins
direkt auf kvm.org angezeigt, sodass es die Oberfläche von
ofdb.org nicht braucht

## Decision
[decision]: #decision

> This section describes our response to these forces. It is stated in full sentences, with active voice. "We will ..."

## Consequences
[consequences]: #consequences

> This section describes the resulting context, after applying the decision. All consequences should be listed here, not just the "positive" ones. A particular decision may have positive, negative, and neutral consequences, but all of them affect the team and project in the future.

## References
[references]: #references

- https://github.com/kartevonmorgen/kartevonmorgen/issues/267
