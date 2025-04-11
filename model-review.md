

# 🎬 Evaluation der automatischen Untertitelung, Übersetzung und Vertonung

Im Rahmen dieses Projekts wurde die Leistungsfähigkeit verschiedener KI-Modelle zur automatisierten Verarbeitung von Videos getestet. Dabei wurden drei zentrale Aspekte evaluiert:

1. **Speech-to-Text** (automatische Untertitelung mit Whisper)
2. **Maschinelle Übersetzung** der Untertitel (Deutsch → Englisch)
3. **Text-to-Speech** (automatische Vertonung mit Piper)

Für jedes Modell wurden sowohl **Qualitätskriterien** (wie Genauigkeit, Satzbau, Natürlichkeit) als auch **technische Faktoren** (wie Videolänge und Generierungsdauer) dokumentiert.

📂 **Outputs und Beispielresultate:**  
Alle generierten Untertitel, Übersetzungen und Audiodateien befinden sich in folgendem Verzeichnis:  
👉 [GoogleDrive](https://drive.google.com/drive/folders/1KXznx-bg6Pmnlr_pAbKOwNmhASIdBPAL?usp=sharing)

---
🧪 **Hinweis:**  
Alle im Rahmen dieses Projekts durchgeführten Tests und Messungen wurden auf dem unten aufgeführten System durchgeführt.  
Die Leistungskennzahlen – insbesondere die Generierungszeiten – hängen maßgeblich von den verwendeten Hardwarekomponenten ab und können auf anderen Geräten entsprechend variieren.

### 💻 Systeminformationen

| Komponente             | Spezifikation                             |
|------------------------|--------------------------------------------|
| Prozessor (CPU)        | Intel Core i7-11700 @ 2.50GHz, 8 Kerne / 16 Threads |
| Grafikkarte (GPU)      | NVIDIA GeForce RTX 3070 (8GB VRAM)         |
| RAM                    | 32 GB DDR4                                 |
| Betriebssystem         | Windows 11 Pro                             |


Die Ergebnisse sind in den folgenden Tabellen zusammengefasst:




### 📝 Test der automatischen Untertitelung (Speech-to-Text mit Whisper)

| Modellkombination                        | Spracheingabe → Sprache der Untertitel | Genauigkeit | Synchronisation | Satztrennung | Grammatik | Gesamt (von 20) | 🕒 Videolänge | ⚙️ Generierungszeit | Anmerkungen |
|------------------------------------------|----------------------------------------|-------------|------------------|---------------|------------|------------------|----------------|----------------------|-------------|
| tiny + Purfview's Faster-Whisper-XXL     | Deutsch → Deutsch                      | 3           | 4                | 3             | 3          | **13**           | 02:00 min       | 00:12 min            | Teilweise unklare Sätze, kurze Einheiten, wenig Satzzeichen. |
| base + Purfview's Faster-Whisper-XXL     | Deutsch → Deutsch                      | 4           | 4                | 4             | 3          | **15**           | 02:00 min       | 00:08 min            | Gute Struktur, aber kaum Punktsetzung. Leicht verschachtelte Sätze. |
| small + Purfview's Faster-Whisper-XXL    | Deutsch → Deutsch                      | 4           | 4                | 4             | 4          | **16**           | 02:00 min       | 00:08 min            | Bessere Satzstruktur und Trennung. Höhere Interpunktion. |
| medium + Purfview's Faster-Whisper-XXL   | Deutsch → Deutsch                      | 5           | 4                | 4             | 4          | **17**           | 02:00 min       | 00:17 min            | Sehr gute Lesbarkeit und natürliche Satzgrenzen. |


---
### 🌐 Test der Untertitel-Übersetzung (Deutsch → Englisch)

| Modellkombination                                  | Spracheingabe → Sprache der Untertitel | Übersetzungsqualität | Satzbau | Natürlichkeit | Grammatik | Gesamt (von 20) | 🕒 Videolänge | ⚙️ Generierungszeit | Anmerkungen |
|----------------------------------------------------|----------------------------------------|------------------------|---------|----------------|------------|------------------|----------------|----------------------|-------------|
| Google Translate V1 API (nach Whisper)             | Deutsch → Englisch                     | 3                      | 3       | 2              | 2          | 10               | 02:00 min       | 00:01 min            | Viele maschinelle Formulierungen, zahlreiche Fehler bei Fachbegriffen. „Texture Mapping“ wurde fälschlich als „Redex Champirping“ erkannt. |
| DeepL V2 (nach Whisper)                            | Deutsch → Englisch                     | 4                      | 3       | 3              | 3          | 13               | 02:00 min       | 00:03 min            | Besser als Google, aber teilweise uneinheitliche Terminologie (z. B. „center a texture“) und leichte Sinnverzerrung. |
| ChatGPT mini 3o                                     | Deutsch → Englisch                     | 5                      | 4       | 4              | 4          | 17               | 02:00 min       | 00:04 min            | Sehr klar und korrekt formuliert. Natürlich klingend, nur wenige kleinere Schwächen im Satzfluss. |
|    ↳ GPT-4o mini                                    | Deutsch → Englisch                     | 5                      | 4       | 5              | 4          | 18               | 02:00 min       | 00:08 min            | Sehr natürlich klingend, gute stilistische Variationen. |
|    ↳ GPT-4o                                         | Deutsch → Englisch                     | 5                      | 4       | 4              | 5          | 18               | 02:00 min       | 00:06 min            | Extrem präzise, idiomatisch und stilistisch auf hohem Niveau. |
|    ↳ GPT-4o turbo                                   | Deutsch → Englisch                     | 5                      | 4       | 4              | 5          | 18               | 02:00 min       | 00:08 min            | Schnell und sehr akkurat, besonders gut bei Fachbegriffen. |
|    ↳ GPT-3.5 turbo                                  | Deutsch → Englisch                     | 4                      | 3       | 3              | 4          | 14               | 02:00 min       | 00:05 min            | Übersetzung teilweise wörtlich, leichte Steifheit im Satzbau. Sinn korrekt, aber etwas weniger idiomatisch als GPT-4. |
|    ↳ GPT-4                                          | Deutsch → Englisch                     | 5                      | 4       | 4              | 5          | 18               | 02:00 min       | 00:11 min            | Sehr hohes Sprachniveau, praktisch fehlerfrei und stilistisch geschliffen. |
| MyMemory Translate                                  | Deutsch → Englisch                     | 5                      | 4       | 5              | 4          | 18               | 02:00 min       | 00:03 min            | Beste Balance aus Stil, Natürlichkeit und Korrektheit. „Texture Mapping“ korrekt erkannt, idiomatisch sauber. |

---

### 🎧 Test der automatischen Vertonung (Text-to-Speech mit Piper)

| Modellkombination                                  | Spracheingabe → Sprache der Untertitel | Aussprache | Intonation | Tempo | Audioqualität | Gesamt (von 20) | 🕒 Videolänge | ⚙️ Generierungszeit | Anmerkungen |
|----------------------------------------------------|----------------------------------------|------------|------------|--------|----------------|------------------|----------------|----------------------|----------------------------------------------|
| Piper (alain low, Encoding: aac)                   | Englisch → Englisch                    | 3          | 3          | 4      | 3              | **14**           | 02:00 min       | 00:29 min            | Gute technische Qualität, aber die Stimme wirkt leicht robotisch, mit schwacher Intonation und dumpfem Klang. |
| Piper (alain medium, Encoding: aac)                | Englisch → Englisch                    | 4          | 4          | 4      | 4              | **16**           | 02:00 min       | 00:47 min            | Natürlichere Intonation und klarere Aussprache. Die Stimme wirkt lebendiger, jedoch könnten einige Betonungen noch verbessert werden. |
| Piper (Alba medium, aac)                           | Englisch → Englisch                    | 4          | 4          | 4      | 4              | **16**           | 02:00 min       | 00:55 min            | Klare Aussprache mit natürlicher Intonation. Die Stimme wirkt lebendig und angenehm. |
|    ↳ Text von GPT-4o mini                          | Englisch → Englisch                    | 4          | 4          | 4      | 4              | **16**           | 02:00 min       | 00:57 min            | Gute Natürlichkeit, teilweise dynamisch, aber noch zurückhaltend in der Intonation. |
|    ↳ Text von GPT-4o                                | Englisch → Englisch                    | 4          | 4          | 4      | 5              | **17**           | 02:00 min       | 00:48 min            | Ausdrucksstark, sehr flüssig, mit sinnvoller Betonung und angenehmem Rhythmus. |
|    ↳ Text von GPT-4o turbo                          | Englisch → Englisch                    | 5          | 4          | 4      | 5              | **18**           | 02:00 min       | 00:39 min            | Sehr gut artikuliert, etwas technischer Stil, aber äußerst klar. |
|    ↳ Text von GPT-3.5 turbo                         | Englisch → Englisch                    | 4          | 3          | 4      | 4              | **15**           | 02:00 min       | 00:37 min            | Stimme klingt klar, aber etwas monoton. Die Intonation variiert wenig, was bei längeren Passagen ermüdend wirkt. |
|    ↳ Text von GPT-4                                 | Englisch → Englisch                    | 4          | 4          | 4      | 5              | **17**           | 02:00 min       | 00:40 min            | Fast fehlerfrei, mit sehr natürlicher Dynamik und professionellem Sprachfluss. |
| Piper (English Aru, medium, aac)                   | Englisch → Englisch                    | 3          | 2          | 3      | 3              | **11**           | 02:00 min       | 00:55 min            | Ruhiger, aber schwer verständlicher Klang. Die Stimme klingt angenehm, macht aber häufig unnatürliche Pausen und spricht Fachbegriffe undeutlich oder abgehackt aus. |





### ⏱️ Gesamtzeit je Modellkombination (Summierte Generierungszeit mit Gesamtpunktzahl)

| Modellkombination                                                                         | Gesamtzeit für alle Schritte   | Gesamtpunktzahl (von 60) |
|-------------------------------------------------------------------------------------------|-------------------------------|---------------------------|
| tiny + Purfview's Faster-Whisper-XXL + Google Translate V1 API + Piper (alain low, aac)   | 00:42                          | 37                        |
| base + Purfview's Faster-Whisper-XXL + DeepL V2 + Piper (alain medium, aac)               | 00:58                          | 44                        |
| small + Purfview's Faster-Whisper-XXL + ChatGPT mini 3o + Piper (Alba medium, aac)        | 01:07                          | 49                        |
| ↳ mit GPT-4o mini                                                                         | 01:11                          | 50                        |
| ↳ mit GPT-4o                                                                              | 01:09                          | 51                        |
| ↳ mit GPT-4o turbo                                                                        | 01:11                          | 52                        |
| ↳ mit GPT-3.5 turbo                                                                       | 01:06                          | 45                        |
| ↳ mit GPT-4                                                                               | 01:14                          | 51                        |
| medium + Purfview's Faster-Whisper-XXL + MyMemory Translate + Piper (English Aru, medium) | 01:15                          | 46                        |




