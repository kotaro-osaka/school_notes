**24.08.2023** 
## 1. Erklären Sie JVM, Compiler, Interpreter

> [!info] JDK
> - "Java Development Kit" - Entwicklungsumgebung
> - Programme werden erfasst, getestet & übersetzt

> [!info] JRE
> - "Java Runtime Environment" - Laufzeitumgebung
> - Realisiert die Java Platform
> - Muss auf dem Computer installiert sein
> - Beinhaltet:
> 	- Virtuelle Maschine - VM
> 		- Interpretation & Ausführung des übersetzten Programms
> 	- Java-API
> 		- "Application Programming Interface"
> 		- Bibliothek

> [!info] Compiler
> - Übersetzt Programme - Programmier-/ Quellsprache(source code) --> Maschinencode
> - Zu übersetzendes Programm - Quellprogramm
> - Übersetztes Programm - (Ziel)Programm
> - Kompiliertes Programm ist maschinenabhängig und kann nicht auf jeder Computerplatform ausgeführt werden
> - Java:
> 	1.  Ziel: ~~Ausführbares Programm~~ - Java- Byte- code - "Zwischencode"
> 	2. Mit Java Interpreter auf jeder Platform ausführbar (VM)
> 		- Auf jeweiliges Betriebssystem optimiert
> - Übersetzung
> 	- Befehle werden auf korrekte Syntax geprüft
> 	- Manche Compiler brechen bei Fehlern den Vorgang ab
> 		- Art & Position des Fehlers werden angegeben
> 		- Kann nach Korrektur wird der Prozess wiederholt
> 	- Manche Compiler übersetzen gesamten Quellcode
> 		- Ohne Abbruch bei Fehlererkennung
> 		- Übergeben Liste der auftretenden Fehler nach Übersetzung

> [!info] Interpreter
> - Übersetzt während der Laufzeit eines Programms vorhandenen Quelltext
> - Syntaxprüfung erfolgt zeilenweise
> - Syntaxprüfung erfolgt zeilenweise
> - Programme, die von einem Interpreter bearbeitet werden, laufen im Vergleich zu kompilierten
> - Programmen relativ langsam ab
> 	- Daher für komplexe Lösungen ungeeignet
> 	- Nicht Computerabhängig
>```mermaid
>flowchart LR
>1(Zeile übersetzen) --> 2(Ausführen) --> 3(Wiederholen)
>```
- `static`
	- Method is associated with the class, not a specific instance (object) of that class
	- You can call a static method without creating an object of the class
- `abstract`
	- Subclasses need to implement method
- vererbung -Subclass extends Superclass KLASSEN
- polymorphie -wiederverwenden von methoden einer existierenden klasse bei creation einer neuen klasse METHODEN