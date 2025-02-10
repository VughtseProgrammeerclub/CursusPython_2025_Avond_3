# CursusPython 2025 - Avond 3 - microPython

## Microcontrollers

|**Raspberry Pi Pico**|**ESP32**|**Micro:bit**|
|----------|----------|----------|
|afbeelding 1|Afbeeling 2|Afbeelding 3|

## Python vs microPython
|**Kenmerk**               |**Python**                      |**MicroPython**                   |
|:-------------------------|:-------------------------------|:------------------------------------|
| **Doelgroep**            | Algemeen gebruik op computers  | Microcontrollers (zoals micro:bit, ESP32) |
| **Taalversie**           | Gebaseerd op Python 3          | Afgeslankte versie van Python 3  |
| **Interpreter**          | CPython (standaard)            | MicroPython-interpreter          |
| **Modules**              | Grote standaardbibliotheek     | Kleinere, geoptimaliseerde bibliotheek |
| **Besturingssysteem nodig?** | Ja (Windows, macOS, Linux)   | Nee, draait direct op de microcontroller |
| **Geheugengebruik**      | Vereist veel RAM en opslag     | Geoptimaliseerd voor weinig geheugen |
| **Prestaties**           | Sneller dankzij JIT-compilatie | Langzamer vanwege beperkte hardware |
| **I/O-mogelijkheden**    | Bestanden, netwerken, databases | Directe controle over hardware (GPIO, I2C, SPI, etc.) |
| **Stroomverbruik**       | Geen beperkingen              | Laag energieverbruik voor embedded systemen |

## Interpreter
De microPython-*interpreter* is een programma dat MicroPython-code direct uitvoert op een microcontroller, zoals de BBC micro:bit, ESP32 of Raspberry Pi Pico.

MicroPython is speciaal ontworpen voor kleine, embedded systemen met beperkte rekenkracht en geheugen. In tegenstelling tot het gewone Python, draait het zonder besturingssysteem en werkt het direct met de hardware.

Waar bevindt de MicroPython Interpreter zich?
De MicroPython-interpreter bevindt zich op de microcontroller zelf. Dit betekent:

  - Opgeslagen in het flashgeheugen van de microcontroller.
  - Start automatisch op wanneer de microcontroller wordt ingeschakeld.
  - Geen apart besturingssysteem nodig, het draait direct op de hardware.

Wanneer je een script naar de microcontroller uploadt (via Thonny, Mu Editor of een seriële verbinding), wordt het door de interne MicroPython-interpreter uitgevoerd.

Hoe werkt de MicroPython Interpreter?
- Je schrijft code in een editor zoals Thonny of Mu Editor.
- De code wordt geüpload naar de microcontroller.
- De MicroPython-interpreter op de microcontroller voert de code direct uit.
- Bij een herstart blijft het programma draaien, zolang het in het bestand main.py is opgeslagen.
- Wil je live testen? Je kunt de REPL (Read-Eval-Print Loop) gebruiken, waarmee je direct opdrachten aan de MicroPython-interpreter geeft via een seriële verbinding.

## Enkele programmeeromgevingen om micro:bit met Python te programmeren:
- Mu-editor (https://codewith.mu/)
- Python.microbit.org (https://python.microbit.org/v/3)
- MakeCode (https://makecode.microbit.org/)
- Thonny (https://thonny.org/)

In deze cursus hebben we tot nu toe gewerkt met Thonny en hier gaan we nu ook mee door.

Welke Thonny-vensters waren ook al weer belangrijk?
|Venster|Waarvoor?|
|-----|-----|
|**Editor** |Hierin schrijven we onze programma's. Zolang het programma in de editor staat is het een gewoon tekstbestand dat we ook hadden schrijven in bijvoorbeeld het kladblok van Windows of in Word. Om aan te geven dat het een Pythonprogramma is krijgt het bestand de extensie *'.py'*.|
|**Shell**  |Het deel van Thonny dat de uitvoer van je code laat zien en waar je ook direct opdrachten kan invoeren. De Shell in Thonny fungeert als een REPL, wat betekent dat je hier direct Python-commando’s kunt invoeren en meteen de uitvoer kunt zien. <br>**REPL (Read-Evaluate-Print-Loop):** Een interactieve omgeving waarin je Python-commando’s in real-time kunt uitvoeren. Thonny bevat een ingebouwde REPL, toegankelijk via de Shell, waarmee je direct commando’s naar de micro:bit kunt sturen en de uitvoer meteen kunt zien. De REPL maakt gebruik van de interpreter om elk commando direct te evalueren en het resultaat ervan in de Shell te tonen. Dit maakt het mogelijk om snel te experimenteren met kleine stukjes code, in tegenstelling tot de editor, waar je complete programma’s schrijft die pas na uitvoering worden getest.|
|**Files**  |Bij de eerdere Pythonlessen was de eigen 'verkenner' van Thonny nog niet zo belangrijk, maar bij microcontrollers als de Raspberry Pi Pico en de micro:bit kan je de programmacode ook op de controller zelf opslaan. Met de Verkenner van Windows zijn deze echter niet zichtbaar.|
- Shell
