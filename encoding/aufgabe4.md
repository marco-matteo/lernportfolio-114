## UTF-8 vs UTF-16

### Wo wird UTF-8 eingesetzt?
- Webtechnologien (HTML, CSS, JSON, XML)
- Unix/Linux-Dateisysteme
- Programmiersprachen: Python, Go, JavaScript
- Datenübertragung (E-Mail, APIs)
- ASCII-kompatibel (erste 128 Zeichen identisch mit ASCII)

### Wo wird UTF-16 eingesetzt?
- Windows-Betriebssystem und -APIs (Win32)
- Programmiersprachen: Java (intern), C#, .NET, Android (Java)
- Geeignet für Texte mit vielen nicht-lateinischen Zeichen (z. B. asiatische Sprachen)

---

## Was bedeutet die Byteorder bei UTF-16?
- Gibt die Reihenfolge der Bytes an (Endianness):
  - **Big-Endian (BE)**: Höherwertiges Byte zuerst
  - **Little-Endian (LE)**: Niedrigwertiges Byte zuerst
- **Byte Order Mark (BOM)**:
  - Kennzeichnung der Byte-Reihenfolge
  - BE: `FE FF`, LE: `FF FE`

---

## Was bedeutet «abwärtskompatibel» bei UTF-8?
- Die ersten 128 Zeichen (U+0000 bis U+007F) entsprechen exakt dem ASCII-Standard
- UTF-8-Dateien mit nur ASCII-Zeichen sind auch gültige ASCII-Dateien
- **UTF-16 ist NICHT abwärtskompatibel** mit ASCII

---

## Speicherbedarf (Deutsch/Englisch) – Vergleich

| Codierung     | Speicherbedarf (meist)     | Bemerkung                         |
|---------------|-----------------------------|-----------------------------------|
| ISO-8859-1    | 1 Byte pro Zeichen          | Kein Unicode, nur westeuropäisch  |
| UTF-8         | 1–2 Bytes (DE/EN)           | ASCII = 1 Byte, Umlaute = 2 Bytes |
| UTF-16        | 2 Bytes (meist)             | Basis-Multilingual-Plane          |

---

## Wann wird ein UTF-16-Code 4 Byte lang?
- Bei Zeichen außerhalb der **Basic Multilingual Plane (BMP)** (d. h. > U+FFFF)
- Verwendung von **Surrogatpaaren**
- Beispiele: Emojis, seltene Schriftzeichen, Musik-Notationen

---

## Unicode-Zeichen in Word eingeben (z. B. Eurozeichen)
1. Unicode eingeben, z. B. `20AC` für €
2. Direkt danach `Alt` + `C` drücken
3. Zeichen erscheint

---

## Problem bei Zeichen wie dem Violinschlüssel (𝄞 U+1D11E)
- Es funktioniert nur bei bestimmten **Fonts**
- Es kann sein das andere Fonts nicht jeden Unicode hat. heisst wenn nicht ersetzt word den font automatisch