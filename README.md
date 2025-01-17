# Sortieralgorithmus für Zylinder

Ein Projekt zur Implementierung eines Sortieralgorithmus, der verschiedene Zylinder basierend auf Symbolen erkennt, sortiert und an die korrekten Positionen transportiert.

## Projektübersicht

Dieses Projekt beinhaltet:
- **Sortieralgorithmus:** Realisiert mithilfe von Teach-Pendant-Code für Industrieroboter.
- **Ziel:** Zylinder basierend auf erkannten Symbolen wie Dreieck, Quadrat oder Kreis korrekt sortieren.
- **Positionserkennung:** Steuerung des Greifers zu markierten Positionen zur Identifikation und Ablage.
- **Visualisierung:** Funktionspunkte und ein Aktivitätsdiagramm, das den Ablauf veranschaulicht.

---

## Funktionsweise

1. **Initialisierung:**
   - Der Algorithmus setzt die Anfangsparameter wie `User-Tool` und `User-Frame` fest.
   - Alle Register werden auf 0 initialisiert.

2. **Pick Position:**
   - Basierend auf dem aktuellen Zustand des Registers springt das Programm mithilfe einer `Select`- und `Jump-Label`-Anweisung zu den jeweiligen Positionen.

3. **Symbolerkennung:**
   - Nach der Platzierung des Zylinders wird das Unterprogramm `MESSEN` aufgerufen, das das Symbol identifiziert und das Ergebnis im Register speichert.

4. **Sortierung:**
   - Je nach erkanntem Symbol (Dreieck, Quadrat, Kreis oder fehlerhaft) wird der Zylinder in die entsprechende Zielposition gelegt.

5. **Schleifenabschluss:**
   - Die Schleife endet, wenn alle Zylinder sortiert wurden.

---

## Diagramme und Bilder

### Teach-Pendant Code Beispiel
![TP Code Beispiel](Screenshot/TP_HandsOn.jpg)

### Funktionspunkte
Dieses Diagramm zeigt die Ziel- und Abholpositionen der Zylinder.
![Funktionspunkte](Screenshot/Funktionspunkte.png)

### Aktivitätsdiagramm
Das Aktivitätsdiagramm visualisiert die Logik des Sortierprozesses.
![Aktivitätsdiagramm](Screenshot/Aktivitaetsdiagramm.png)

---

## Code-Beschreibung

### Hauptprogramm: `Sortierung_Main`
```plaintext
1. Initialisierung:
   - UTOOL_NUM = 1
   - UFRAME_NUM = 2
2. Register nullen:
   - R[1] = 0
   - R[2] = 0
3. Pick Position:
   - R[1] = 0 bis 5
   - SELECT-Anweisungen
4. Symbolerkennung:
   - Aufruf des Unterprogramms MESSEN
5. Fehlerbehandlung:
   - Ablage fehlerhafter Teile.
6. Platzierung nach Symbol:
   - Zuweisung für Dreieck, Quadrat und Kreis.

### Unterprogramm: `Messen`
1. Positionierung:
   - Bewegung zur Messposition.
2. Symbolerkennung:
   - Aktivierung des Vision-Systems.
3. Ergebnis:
   - Speicherung des Symbols im Register.

