R Markdown
================

# Warum R Markdown?

## Was kann das?

In aller Kürze: Folgender Code genügt, ein html-Dokument mit
eingebettetem R-Code zu generieren:

    ---
    title: Ein Beispiel
    output: html_document
    ---
    
    Dies ist ein vollständiges -- wenn auch simples -- R Markdown Dokument.
    
    Es enthält R Code:
    
     ```{r}
     hundert_zufallszahlen <- rnorm(100)
     hundert_zufallszahlen
     ```
    
    Man kann auch Plots einbetten:
    
     ```{r, echo=FALSE}
     plot(hundert_zufallszahlen)
     ```

Das Ergebnis ist [eine html-Seite](simple.html), wie sie jeder
Web-Browser öffnen kann, ob sie nun auf deiner Festplatte oder auf einem
Webserver liegt. HTML ist ein wahnsinnig vielseitiges Format und kann
beinahe jeden erdenklichen Inhalt haben.

Eine winzige Änderung in der Zeile

    output: html_document

ganz oben zu

    output: pdf_document

oder zu

    output: word_document

bewirkt, dass die Ausgabe stattdessen als statisches [pdf-](simple.pdf)
oder [Word-Dokument](simple.docx) erfolgt.

Es gibt noch eine ganze Reihe weiterer interessanter Ausgabe-Formate
(z.B. interaktive Tutorials wie
[dieses](http://195.201.24.35:3838/RasGIStutorial_german/)), aber auch
weniger interessante (wie PowerPoint).

… und was die Inhalte angeht, sind der Fantasie beinahe keine Grenzen
gesetzt.

Neugierig geworden?

## Markdown — Was ist das überhaupt?

**Markdown** ist eine vereinfachte *Auszeichnungssprache*, also eine
maschinenlesbare Sprache für die Gliederung und Formatierung von Texten
(und anderen Daten). Mit *Auszeichnungssprachen* werden Eigenschaften
und Darstellungsformen von Textabschnitten (Zeichen, Wörtern, Absätzen)
beschrieben. Die Beschreibung erfolgt dabei in Textform, wobei ein
erklärtes Ziel von **Markdown** ist, dass bereits der Quellcode leicht
lesbar
    ist.

### Ein Beispiel sagt mehr als 51 Worte

#### Normaler Text, Absätze und Zeilenumbrüche:

    Normaler Text wird so dargestellt wie eingegeben und automatisch umgebrochen, falls nötig.
    Eine neue Zeile im Quelltext erzeugt keinen(!) manuellen Zeilenumbruch.
    Zeilenumbrüche erzwingt man stattdessen durch zwei oder mehr
    Leerzeichen, wie hier -->      
    am Ende einer Zeile.
    
    Eine Leerzeile erzeugt immer einen neuen Absatz.

Normaler Text wird so dargestellt wie eingegeben und automatisch
umgebrochen, falls nötig. Eine neue Zeile im Quelltext erzeugt
keinen(\!) manuellen Zeilenumbruch. Zeilenumbrüche erzwingt man
stattdessen durch zwei oder mehr Leerzeichen, wie hier –\>  
am Ende einer Zeile.

Eine Leerzeile erzeugt immer einen neuen Absatz.

#### Hervorhebungen

    *Kursiv*, **Fett** und ***Fett kursiv***

*Kursiv*, **Fett** und ***Fett kursiv***

#### Aufzählungen

    * Ein Punkt in einer ungeordneten Liste
    * Ein weiterer Punkt in einer ungeordneten Liste
        * Ein Unterpunkt, um vier Leerzeichen eingerückt
     * Statt * funktionieren auch + oder -
        + das vorangestellte Zeichen spielt dabei keine Rolle
        - lediglich die Einrückung zählt

  - Ein Punkt in einer ungeordneten Liste
  - Ein weiterer Punkt in einer ungeordneten Liste
      - Ein Unterpunkt, um vier Leerzeichen eingerückt
  - Statt \* funktionieren auch + oder -
      - das vorangestellte Zeichen spielt dabei keine Rolle
      - lediglich die Einrückung zählt

#### Überschriften

Überschriften und Unterüberschriften werden durch ein oder mehrere
vorangestellte “\#” ausgezeichnet. Je mehr “\#”, desto tiefer die
Unterüberschriften-Ebene. Dieser Text z.B, steht unter der
Unterüberschrift “Überschriften”, die wiefolgt erstellt
    wurde:

    #### Überschriften

#### Hyperlinks

##### Webseiten

    [Beschriftung des Hyperlinks](https://de.wikipedia.org/wiki/Markdown "Titel, der beim Überfahren mit der Maus angezeigt wird")

[Beschriftung des
Hyperlinks](https://de.wikipedia.org/wiki/Markdown "Titel, der beim Überfahren mit der Maus angezeigt wird")

##### Dateien

    [Ein pdf](Example.pdf)

[Ein pdf](Example.pdf)

    [Dasselbe als docx](Example.docx)

[Dasselbe als docx](Example.docx)

    [Und nochmal als html](Example.html)

[Und nochmal als
    html](Example.html)

##### Bilder einbetten

###### aus dem Netz

    ![ein Beispielbild](https://upload.wikimedia.org/wikipedia/commons/d/d9/Example_de.jpg "Titel, der beim Überfahren mit der Maus angezeigt wird")

![ein
Beispielbild](https://upload.wikimedia.org/wikipedia/commons/d/d9/Example_de.jpg
"Titel, der beim Überfahren mit der Maus angezeigt wird")

###### vom lokalen Datenträger

    ![Windenergieanlagen](wind-power.png "Eine Handvoll WEA.")

![Windenergieanlagen](wind-power.png "Eine Handvoll WEA.")

-----

Soweit, so gut. Damit lassen sich Dokumente relativ einfach
strukturieren und formatieren.

> “Aber all das kann ich auch mit Word oder PowerPoint”

wirst du jetzt erwidern.  
Ja, stimmt, aber wir sind ja auch erst am Anfang.

## R Markdown

Was ist nun **R Markdown**?

R Markdown ist ein Dateiformat zur Erstellung dynamischer Dokumente mit
R. Ein R Markdown-Dokument wird in **Markdown** geschrieben (ein einfach
zu schreibendes Klartextformat, siehe [oben](#markdown)) und kann Teile
von eingebettetem R-Code enthalten.

#### Ein Beispiel mit einigen wichtigen Inhalten:

    ---
    output: html_document
    ---
    
    # Überschrift (oberste Ebene)
    
    ## Unterüberschrift
    
    Dies ist ein **R Markdown** Dokument.
    
    ## weitere Unter-Überschrift
    
    Markdown ist eine einfache *Auszeichnungssprache*
    um 
    
    - HTML, 
    - PDF, und 
    - MS Word Dokumente 
    
    zu erstellen.
    
    ### Uner-unter-Überschrift
    
    Ein Klick auf die **Knit** Schaltfläche generiert
    ein Dokument, das die Markdown-Inhalte sowie die
    Ergebnisse des eingebetteten R-Codes enthält.
    
    R-Code wird folgendermaßen eingebettet:
    
     ```{r}
     summary(cars)
     ```
    
    Man kann auch Plots einbetten:
    
     ```{r, echo=FALSE}
     plot(cars)
     ```
    
    Der `cars` Datensatz ist ein in R integrierter
    Test-Datensatz.
    Darin sind beispielhaft Meta-Daten verschiedener
    [Autos (das ist ein Link)](https://de.wikipedia.org/wiki/Automobil) gelistet.
    
    ![So sehen Autos aus](https://de.wikipedia.org/wiki/Datei:Auto_scrapyard_1.jpg)

#### In einem daraus generierten HTML-Dokument sieht das Ergebnis dann so aus:

# Überschrift (oberste Ebene)

## Unterüberschrift

Dies ist ein **R Markdown** Dokument.

## weitere Unter-Überschrift

Markdown ist eine einfache *Auszeichnungssprache* um

  - HTML,
  - PDF, und
  - MS Word Dokumente

zu erstellen.

### Uner-unter-Überschrift

Ein Klick auf die **Knit** Schaltfläche generiert ein Dokument, das die
Markdown-Inhalte sowie die Ergebnisse des eingebetteten R-Codes enthält.

R-Code wird folgendermaßen eingebettet:

    ##      speed           dist       
    ##  Min.   : 4.0   Min.   :  2.00  
    ##  1st Qu.:12.0   1st Qu.: 26.00  
    ##  Median :15.0   Median : 36.00  
    ##  Mean   :15.4   Mean   : 42.98  
    ##  3rd Qu.:19.0   3rd Qu.: 56.00  
    ##  Max.   :25.0   Max.   :120.00

Man kann auch Plots einbetten:

![](Tutorial_files/figure-gfm/unnamed-chunk-2-1.png)<!-- -->

Der `cars` Datensatz ist ein in R integrierter Test-Datensatz. Darin
sind beispielhaft Meta-Daten verschiedener [Autos (das ist ein
Link)](https://de.wikipedia.org/wiki/Automobil) gelistet.

![So sehen Autos
aus](https://upload.wikimedia.org/wikipedia/commons/thumb/c/cd/Auto_scrapyard_1.jpg/800px-Auto_scrapyard_1.jpg)

-----

# Lust auf mehr?

Hier gehts zum interaktiven Tutorial: [“Einführung in R und R als
GIS”](http://195.201.24.35:3838/RasGIStutorial_german/)

Feedback gern an [mich](mailto:marko.lipka@posteo.de)