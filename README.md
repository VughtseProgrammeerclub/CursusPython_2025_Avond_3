# CursusPython 2025 - Avond 3 - microPython

## Microcontrollers

Een microcontroller is een compacte schakeling met een processor, geheugen en I/O (Input/Output), gebruikt voor het aansturen van sensoren en motoren.

Relevante microcontrollers:

- RPi Pico: Gebruikt de RP2040, een dual-core ARM Cortex-M0+.
- ESP32: Van Espressif, met WiFi en Bluetooth, ideaal voor IoT (Internet of Things).
- micro:bit: Met Nordic nRF52833 of nRF51822, inclusief Bluetooth en sensoren.

Microcontrollers worden veel gebruikt in elektronica, IoT en educatie.

|**Raspberry Pi Pico**|**ESP32**|**Micro:bit**|
|----------|----------|----------|
| ![RPi Pico](Raspberry_Pi_Pico_top_and_bottom-1200.jpg) | ![ESP32](SparkFun-Thing-Plus-ESP32-C6-Top-Bottom.jpg) | ![micro:bit](microbit-overview-1-5-1200.png)           |
|Dit is de eenvoudigste uitvoering. Er zijn ook nieuwere uitvoeringen met o.a. WiFi.|Dit is maar één voorbeeld, er bestaan vele uitvoeren van ESP32's.|Dit is V1-uitvoering (de originele), inmiddels is er ook een V2-uitvoering met een luidspreker, microfoon en meer geheugen.|

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
De *MicroPython interpreter* is een programma dat MicroPython-code direct uitvoert op een microcontroller, zoals de BBC micro:bit, ESP32 of Raspberry Pi Pico.

MicroPython is speciaal ontworpen voor kleine, embedded systemen met beperkte rekenkracht en geheugen. In tegenstelling tot het gewone Python, draait het zonder besturingssysteem en werkt het direct met de hardware.

**Waar bevindt de MicroPython interpreter zich?**
De MicroPython Interpreter bevindt zich op de microcontroller zelf. Dit betekent:
  - Opgeslagen in het flashgeheugen van de microcontroller.
  - Start automatisch op wanneer de microcontroller wordt ingeschakeld.
  - Geen apart besturingssysteem nodig, het draait direct op de hardware.

Wanneer je een script naar de microcontroller uploadt (via Thonny, Mu Editor of een seriële verbinding), wordt het door de interne MicroPython-interpreter uitgevoerd.

**Hoe werkt de MicroPython interpreter?**
- Je schrijft code in een editor zoals Thonny of Mu Editor.
- De code wordt als tekstbestand (met de extensie *'.py.'* geüpload naar de microcontroller.
- De MicroPython interpreter op de microcontroller voert de code direct uit.
- Bij een herstart blijft het programma draaien, zolang het in het bestand als main.py is opgeslagen op de microcontroller.
- Wil je live testen? Je kunt de REPL (Read-Eval-Print Loop) gebruiken, waarmee je direct opdrachten aan de MicroPython interpreter geeft via een seriële verbinding.

**Hoe komt de MicroPython interpreter op de microcontroller?**

Dat hangt af van de programmeeromgeving die je gebruikt. Dit zijn de meest bekende omgevingen:

- Mu-editor (https://codewith.mu/)
- Python.microbit.org (https://python.microbit.org/v/3)
- MakeCode (https://makecode.microbit.org/)
- Thonny (https://thonny.org/)

In deze cursus hebben we tot nu toe gewerkt met Thonny en hier gaan we nu ook mee door.

- **Thonny** zal de interpreter bij de eerste keer dat je een programma op de microcontroller wilt uitvoeren direct proberen te uploaden. Als dit niet lukt dan kan je de interpreter zelf vanuit Thonny in het flashgeheugen van de microcontroller zetten. We komen hier nog op terug.
- Bij **andere programmeeromgevingen** moet je de interpreter handmatig installeren.
  
**Kan ik de MicroPython interpreter ook weer verwijderen?**

De MicroPython interpreter wordt opgeslagen in het flash-geheugen van de microcontroller. Dit betekent dat het 'bestand' van buitenaf niet zichtbaar/toegangelijk is (zie verderop de beschrijving van het Thonny-venster *Files*). Op de micro:bit kan je de interpreter verwijderen door in de programeeromgeving https://makecode.microbit.org/ een programma te schrijven en dit vanuit die omgeving te uploaden naar de micro:bit. Je kan ook een hex-bestand dat gemaakt is in MakeCode via de Windows verkenner kopiëren naar de micri:bit. Dit overschrijft alles wat eerder met Thonny op de micro:bit is gezet.

## Thonny en de micro:bit

We hebben het hiervoor al even gehad over Thonny en de micro:bit. We kijken eerst nog even naar de belangrijkste vensters in Thonny, we gaan een micro:bit aansluiten en ons eerste MicroPython-programma op de micro:bit zetten.

**Welke Thonny-vensters waren ook al weer belangrijk?**
|Venster|Waarvoor?|
|:-----|:-----|
|**Editor** |Hierin schrijven we onze programma's. Zolang het programma in de editor staat is het een gewoon tekstbestand dat we ook hadden schrijven in bijvoorbeeld het kladblok van Windows of in Word. Om aan te geven dat het een Pythonprogramma is krijgt het bestand de extensie *'.py'*.|
|**Shell**  |Het deel van Thonny dat de uitvoer van je code laat zien en waar je ook direct opdrachten kan invoeren. De Shell in Thonny fungeert als een REPL, wat betekent dat je hier direct Python-commando’s kunt invoeren en meteen de uitvoer kunt zien. <br>**REPL (Read-Evaluate-Print-Loop):** Een interactieve omgeving waarin je Python-commando’s in real-time kunt uitvoeren. Thonny bevat een ingebouwde REPL, toegankelijk via de Shell, waarmee je direct commando’s naar de micro:bit kunt sturen en de uitvoer meteen kunt zien. De REPL maakt gebruik van de interpreter om elk commando direct te evalueren en het resultaat ervan in de Shell te tonen. Dit maakt het mogelijk om snel te experimenteren met kleine stukjes code, in tegenstelling tot de editor, waar je complete programma’s schrijft die pas na uitvoering worden getest.|
|**Files**  |Bij de eerdere Pythonlessen was de eigen 'verkenner' van Thonny nog niet zo belangrijk, maar bij microcontrollers als de Raspberry Pi Pico en de micro:bit kan je de programmacode ook op de controller zelf opslaan. Met de Verkenner van Windows zijn deze echter niet zichtbaar.|


{Bestanden op de micro:bit}
