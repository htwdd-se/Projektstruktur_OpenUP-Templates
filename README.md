# Vorlage Projektstruktur & OpenUP-Templates

Das Repository enthält die Vorlage einer Projektstruktur und Template-Dokumente im AsciiDoc-Format. Dies wird für die Bearbeitung der Belegarbeit in Software Engineering I und II benötigt. Im Detail wären dies:

- Projektstruktur anhand der Work Products im OpenUP
- Templates der benötigten OpenUP-Dokumente (AsciiDoc-Format)
- Vorlage für die Belegabgabe in SE I (AsciiDoc-Format)

_Hinweis: Dieses Repository enthält keinen Code._



**Inhaltsverzeichnis**
- [Projektstruktur](#projektstruktur)
- [Unified Process - Templates](#unified-process---templates)
- [Hinweise zu AsciiDoc](#hinweise-zu-asciidoc)
- [Belegabgabe in SE I](#belegabgabe-in-se-i)
- [Lizenz](#lizenz)


## Projektstruktur
Die Projektstruktur im Verzeichnis **docs** orientiert sich an den <ins>Work Products</ins> im OpenUP und den für die <ins>Abgabe im SE 1 Beleg</ins> geforderten Dokumenten.

```
docs
├── architecture
│   └── architecture_notebook.adoc
├── deployment
├── development
│   └── design.adoc
├── environment
├── project_management
│   ├── iteration_plan_01.adoc
│   ├── project_plan.adoc
│   ├── risk_list.adoc
│   └── risks.csv
├── requirements
│   ├── domain_model.adoc
│   ├── glossary.adoc
│   ├── system-wide_requirements.adoc
│   ├── use-case_model.adoc
│   ├── use_case_01.inc.adoc
│   └── vision.adoc
└── test
    └── test_cases.adoc
```


## Unified Process - Templates
Dieses Repositority enthält Vorlagen im AsciiDoc-Format für die Arbeit mit dem Open Unified Process. Die Vorlagen basieren auf den Templates der offiziellen OpenUP Dokumentation in der Version 1.5x aus dem Eclipse Process Framework (EPF) und wurden bis auf geringe inhaltliche / strukturelle Anpassungen lediglich auf deutsch übersetzt.

### Hinweise
* Im Unified Process gibt es eine "Supplementary Specification", die Anforderungen enthält, die nicht als Use Case Model spezifiziert werden können. Das sind z.B. nicht-funktionale und systemweite Anforderungen. Im OpenUP (und in diesem Repository) heißt dieses Dokument "System-wide Requirements".
* Falls Sie Fehler korrigieren oder Verbesserungen machen möchten, können Sie dies gern über einen _Pull Request_ tun.

### Referenzen
* [Eclipse Process Framework](https://www.eclipse.org/epf/downloads/configurations/pubconfig_downloads.php)
* [Open Unified Process 1.5 Dokumentation](https://www2.htw-dresden.de/~anke/openup/index.htm)

## Hinweise zu AsciiDoc
Die Datei _default-attributes.inc.adoc_ im **docs/\_includes** Verzeichnis enthält die gemeinsamen Dokumentenattribute für alle AsciiDoc-Dokumente. In jedem Dokument selbst können, nach dem include der Datei, entsprechend noch extra benötigte Attribute mit aufgenommen werden.

### Projektnamen definieren

In der _default-attributes.inc.adoc_ Datei ist am Anfang der **Projektname** definiert, welcher in jedem Dokument im Title verwendet wird. Ersetzen Sie hier bitte `<Projektname (T00)>` mit Ihrem Belegthema:

```
// Meta
:project-name: <Projektname (T00)>
```

### Bilder einbinden

In dem Dokumentenattribut `:imagesdir: images` ist das Standardverzeichnis für die Bilder festgelegt. Somit reicht es, in den jeweiligen Dokumenten, die Bilder ohne Angabe des **images** Verzeichnis einzubinden:

```
requirements
├── images
│   └── example.jpg
└── vision.adoc
```
```
// vision.adoc
image::example.jpg[Beispielbild]
```


## Belegabgabe in SE I

Im Verzeichnis **belegabgabe_se1** finden Sie die Vorlagedatei *se1_belegabgabe_t00.adoc*, welche alle Ihre erzeugten Dokumente für die Abgabe als PDF in <ins>ein</ins> Dokument bündelt.

(Nutzen Sie nicht die Projektvorlage **Projektstruktur_OpenUP-Templates**, kopieren sie sich die Vorlagedatei *se1_belegabgabe_t00.adoc* in Ihr Projektrepository)

Folgende Schritte sind für eine Belegabgabe durchzuführen:

1. Ändern Sie die Themennummer **t00** in der Vorlagedatei *se1_belegabgabe_t00.adoc* in Ihre Themennummer (t01, t02, ...).
3. Inhalt der Vorlagedatei anpassen:
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

4. Erzeugen Sie das Abgabe-PDF _*se1_belegabgabe_t00.pdf*_ ([Hinweise aus dem Praktikum](https://www.informatik.htw-dresden.de/~zirkelba/praktika/se/arbeiten-mit-git-und-asciidoc/praktikumsaufgaben-teil-2.html#_2_generieren_des_ausgabeformates)):

    ```sh
    $ asciidoctor-pdf se1_belegabgabe_t00.adoc
    ```
    oder:
    ```sh
    $ asciidoctor -r asciidoctor-pdf -b pdf se1_belegabgabe_t00.adoc
    ```
5. Prüfen Sie, dass das korrekte **Projektthema**, alle **Teammitglieder** und das **Abgabedatum** auf dem Deckblatt stehen und dass ebefalls alle erforderlichen **Dokumente** mit ihren Inhalten enthalten sind.

6. Geben Sie das finale Abgabe-PDF _*se1_belegabgabe_t00.pdf*_ über den mitgeteilten Weg ab.


## Lizenz
Sämtliche Inhalte dieses Repositories unterliegen der [CC-BY-4.0](https://choosealicense.com/licenses/cc-by-4.0/) Lizenz.
