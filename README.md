# CursusPython 2025 - Avond 3 - micro:Python

## Microcontrollers
  - Raspberry Pi Pico
  - ESP32
  - Micro:bit

## Python vs microPython
| Kenmerk                  | **Python**                          | **MicroPython**                      |
|--------------------------|----------------------------------|------------------------------------|
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
Wat is een MicroPython Interpreter en Waar Bevindt Deze Zich?
Een MicroPython-interpreter is een programma dat MicroPython-code direct uitvoert op een microcontroller, zoals de BBC micro:bit, ESP32 of Raspberry Pi Pico.

MicroPython is speciaal ontworpen voor kleine, embedded systemen met beperkte rekenkracht en geheugen. In tegenstelling tot gewone Python, draait het zonder besturingssysteem en werkt het direct met de hardware.

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
