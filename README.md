# Vorlage Belegabgabe

Vorlagen für die Abgabe der Belegarbeiten in SE I

## SE I - Belegabgabe

1. Vorlage-Datei *se1_belegabgabe_t00.adoc* laden.
2. Themennummer **t00** in der Vorlage-Datei mit Ihrer Themennummer (t01, t02, ...) ersetzen.
3. Vorlage-Datei in Ihr Projektrepository aufnehmen.
4. Inhalt der Vorlage-Datei anpassen:
    - Im Dokumententitel nach dem `:` das `<Projektthema>` mit Ihrem Projektthema ersetzen:
    
        ```
        // --- 1. Projektthema -------------------------
        = SE I - Belegabgabe: <Projektthema>
        ```
    
    - **alle** Teammitglieder als Autoren eintragen
    
        ```
        // --- 2. Teammitglieder -----------------------
        Vorname Nachname <s00000@htw-dresden.de>; Vorname Nachname <s00000@htw-dresden.de>; ...
        ```
    
    - Versionsdatum als **Abgabedatum** eintragen
    
        ```
        // --- 3. Abgabedatum --------------------------
        00. Januar 2020
        ```
        
    - **include-Pfade** und **Dateinamen** zu den einzelnen Dateien (*path/to/file.adoc*) anpassen bzw. für zusätzliche Dokumente erweitern:
    
        ```
        include::path/to/file.adoc[lines=1..1;4..-1,leveloffset=+1]
        ```
    
5. PDF erzeugen ([Hinweise aus dem Praktikum](https://www.informatik.htw-dresden.de/~zirkelba/praktika/se/arbeiten-mit-git-und-asciidoc/praktikumsaufgaben-teil-2.html#_aufgabe_2_1_htmlpdf)):

    ```sh
    $ asciidoctor -r asciidoctor-pdf -b pdf se1_belegabgabe_t00.adoc
    ```
6. Prüfen Sie, dass das korrekte Thema und alle Teammitglieder auf dem Deckblatt stehen und dass alle erforderlichen Dokumente mit ihren Inhalten enthalten sind.
