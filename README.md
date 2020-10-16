# Vorlage Projektstruktur & OpenUP-Templates

Das Repository enthält die Vorlage einer Projektstruktur und Template-Dokumente im AsciiDoc-Format. Dies wird für die Bearbeitung der Belegarbeit in Software Engineerig I und II benötigt. Im Detrail wären dies:

- Vorlage einer Projektstruktur
- Templates der benötigten OpenUP-Dokumente (AsciiDoc-Format)
- Vorlage für die Belegabgabe in SE I (AsciiDoc-Format)

_Hinweis: Dieses Repository enthält keinen Code._



**Inhaltsverzeichnis**

- [Unified Process - Templates](#unified-process---templates)
- [Belegabgabe in SE I](#belegabgabe-in-se-i)
- [Lizenz](#lizenz)



## Unified Process - Templates
Dieses Repositority enthält Vorlagen im AsciiDoc-Format für die Arbeit mit dem Open Unified Process. Die Vorlagen basieren auf den Templates der offiziellen OpenUP Dokumentation in der Version 1.5x aus dem Eclipse Process Framework (EPF) und wurden bis auf geringe inhaltliche / strukturelle Anpassungen lediglich auf deutsch übersetzt.

### Hinweise
* Im Unified Process gibt es eine "Supplementary Specification", die Anforderungen enthält, die nicht als Use Case Model spezifiziert werden können. Das sind z.B. nicht-funktionale und systemweite Anforderungen. Im OpenUP (und in diesem Repository) heißt dieses Dokument "System-wide Requirements".
* Falls Sie Fehler korrigieren oder Verbesserungen machen möchten, können Sie dies gern über einen _Pull Request_ tun.

### Referenzen
* [Eclipse Process Framework](https://www.eclipse.org/epf/downloads/configurations/pubconfig_downloads.php)
* [Open Unified Process 1.5 Dokumentation](https://www2.htw-dresden.de/~anke/openup/index.htm)


## Belegabgabe in SE I

Im Verzeichnis **belegabgabe_se1** finden Sie die Vorlage-Datei *se1_belegabgabe_t00.adoc*, welche alle Ihre erzeugten Dokumente für die Abgabe als PDF in <ins>ein</ins> Dokument bündelt.

(Nutzen Sie nicht die Projektvorlage **Projektstruktur_OpenUP-Templates**, kopieren sie sich die Vorlage-Datei *se1_belegabgabe_t00.adoc* in Ihr Projektrepository)

Folgende Schritte sind für eine Belegabgabe durchzuführen:

1. Ändern Sie die Themennummer **t00** in der Vorlage-Datei *se1_belegabgabe_t00.adoc* in Ihre Themennummer (t01, t02, ...).
3. Inhalt der Vorlage-Datei anpassen:
    - Ist in Ihrem Projekt in der Datei _docs/\_includes/default-attributes.inc.adoc_ der Projektname im Attribut `:project-name:` nicht gesetzt bzw. nutzen Sie eine andere Struktur, können Sie im Dokumententitel nach dem `:` das `{project-name}` mit Ihrem Projektthema ersetzen:

        ```
        // --- 1. Projektthema -------------------------
        = SE I - Belegabgabe: {project-name}
        ```

    - Tragen Sie **alle** Teammitglieder als Autoren ein:

        ```
        // --- 2. Teammitglieder -----------------------
        Vorname Nachname <s00000@htw-dresden.de>; Vorname Nachname <s00000@htw-dresden.de>; ...
        ```
        > Lange Autorennamen (mehr als 3 Teile) in den Dokumentenattributen müssen mit einem `_` (Unterstrich) zu einer Gruppe von Vor- bzw. Nachnamen zusammengefasst werden. Es treten sonst Formatierungsfehler beim erzeugen der HTML- oder PDF-Dokumente auf. Der `_` (Unterstrich) wird im erzeugten Dokument nicht dargestellt.
        >
        > - `Vorname1_Vorname2 Nachname1_Nachname2 <mail@example.com>`
        > - `Vorname Nachname1_Nachname2_Nachname3 <mail@example.com>`

    - Tragen Sie als Versionsdatum Ihr **Abgabedatum** ein:

        ```
        // --- 3. Abgabedatum --------------------------
        01. Januar 2020
        ```

    - Passen Sie bei abweichender Projektstruktur die **include-Pfade** und **Dateinamen** zu den einzelnen Dateien (*path/to/file.adoc*) an bzw. erweitern Sie es für zusätzliche Dokumente:

        ```
        include::path/to/file.adoc[lines=1..1;4..-1,leveloffset=+1]
        ```
        > Beim `include` wird über die `lines=1..1;4..-1` Angabe jeweils die 1. und alles ab der 4. Zeile übernommen. Jedes Dokument ist eigenständig und somit werden über die Zeilen 2 und 3 die jeweiligen Authoren und das Versionsdatum nicht mit übernommen.

4. Erzeugen Sie das Abgabe-PDF _*se1_belegabgabe_t00.pdf*_ ([Hinweise aus dem Praktikum](https://www.informatik.htw-dresden.de/~zirkelba/praktika/se/arbeiten-mit-git-und-asciidoc/praktikumsaufgaben-teil-2.html#_aufgabe_2_1_htmlpdf)):

    ```sh
    $ asciidoctor -r asciidoctor-pdf -b pdf se1_belegabgabe_t00.adoc
    ```
5. Prüfen Sie, dass das korrekte Projektthema, alle Teammitglieder und Abgabedatum auf dem Deckblatt stehen und dass ebefalls alle erforderlichen Dokumente mit ihren Inhalten enthalten sind.

6. Geben Sie das finale Abgabe-PDF _*se1_belegabgabe_t00.pdf*_ über den mitgeteilten Weg ab.


## Lizenz
Sämtliche Inhalte dieses Repositories unterliegen der [CC-BY-4.0](https://choosealicense.com/licenses/cc-by-4.0/) Lizenz.