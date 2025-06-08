

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

# 📊 Übersicht: Kostenlose / Open-Source Übersetzungs-APIs und -Dienste

| API/Service                                    | Free   | Request Limits (Free Tier)                     | Notes (auf Deutsch)                                                                        |
|------------------------------------------------|---------|------------------------------------------------|--------------------------------------------------------------------------------------------|
| Google Translate (web)                         | ✅      | Keine API, nur Web-Nutzung                     | Web-Oberfläche ist kostenlos, aber keine API.                                              |
| Google Translate V2 API                        | ❌      | Nur kostenpflichtige API                       | Sehr präzise, keine kostenlose offizielle API verfügbar.                                    |
| ~~Bing Microsoft Translator~~                  | ❌    | —                                              | Nicht mehr verfügbar als eigenständige API.                                                |
| DeepL V2 Translate                             |  ✅   / ⚠️ | 500.000 Zeichen/Monat (kostenloser Tarif)      | API ist kostenpflichtig, Web-Oberfläche hat jedoch einen kostenlosen Tarif.                 |
| Ollama (local LLM)                             | ✅      | Keine Limits (lokale Nutzung)                  | Lokale Nutzung ohne Einschränkungen, keine Online-API.                                     |
| LibreTranslate                                 | ✅      | Keine offiziellen Limits; selbst gehostet       | Open-Source und einfach zu integrieren.                                                    |
| MyMemory Translate                             | ✅      | 1.000 Anfragen/Tag (kostenloser Tarif)          | Gut für kleinere Projekte oder Testzwecke.                                                 |
| ChatGPT (OpenAI)                               | ❌ / ⚠️ | Kostenpflichtige API, Web-Version frei (Limits variieren) | API ist kostenpflichtig, Web-Version kann kostenlos genutzt werden (ohne API-Aufrufe).     |
| LM Studio (local LLM)                          | ✅      | Keine Limits (lokale Nutzung)                  | Lokale Inferenz, keine offizielle Online-API.                                              |
| ~~KoboldCpp (local LLM)~~                      | ❌    | —                                              | Kein Übersetzungstool. Interaktiver Chatbot, nicht für Übersetzungen geeignet.             |
| Anthropic Claude                               | ❌      | Nur kostenpflichtige API                       | Kostenpflichtige API, kein kostenloser Tarif.                                              |
| Groq                                           | ✅      | Im Entstehen; keine offiziellen Nutzungslimits  | Neue Plattform mit kostenloser Nutzung für einige Aufgaben, experimentell.                 |
| DeepSeek (API)                                 | ❌      | Nur kostenpflichtige API                       | Web-Nutzung kostenlos, API-Zugang kostenpflichtig.                                         |
| OpenRouter                                     | ✅      | Kostenloser Tarif verfügbar, Nutzung variiert   | API-Gateway für verschiedene Modelle, kostenloser Tarif je nach Anbieter verfügbar.        |
| Google Gemini                                  | ❌      | Nur kostenpflichtige API                       | Premium-Dienst ohne kostenlosen Tarif.                                                     |
| Papago Translate                               | ✅      | 10.000 Zeichen/Tag (kostenlos)                 | Kostenloser Tarif, speziell für Koreanisch/Englisch-Übersetzungen.                         |
| DeepLX Translate                               | ✅      | Keine offiziellen Limits (open-source)         | Nutzt DeepL inoffiziell, basiert auf Open-Source-Lösungen.                                 |
| Mistral AI Translate                           | ✅      | Keine offiziellen Nutzungslimits                | Neue und experimentelle Plattform.                                                         |
| AvalAI                                         | ✅      | Limitierte kostenlose Nutzung, neue API         | Neue API für KI-Übersetzung, begrenzter kostenloser Zugriff.                               |
| thammegowda-nllb-serve                         | ✅      | Selbst gehostet; keine Online-Nutzungslimits    | Lokale NLLB-API für mehrsprachige Übersetzung, keine externen Abhängigkeiten.               |
| winstxnhdw-nllb-api                            | ✅      | Selbst gehostet; keine Online-Nutzungslimits    | Ähnliche NLLB-basierte API, sehr robust für viele Sprachen.                                |

---
Die Ergebnisse sind in den folgenden Tabellen zusammengefasst:


### 📝 Test der automatischen Untertitelung (Speech-to-Text mit Whisper)

| Modellkombination                        | Spracheingabe → Sprache der Untertitel | Genauigkeit | Synchronisation | Satztrennung | Grammatik | Gesamt (von 20) | 🕒 Videolänge | ⚙️ Generierungszeit | Anmerkungen |
|------------------------------------------|----------------------------------------|-------------|------------------|---------------|------------|------------------|----------------|----------------------|-------------|
| tiny + Purfview's Faster-Whisper-XXL     | Deutsch → Deutsch                      | 3           | 4                | 3             | 3          | **13**           | 02:00 min       | 00:12 min            | Teilweise unklare Sätze, kurze Einheiten, wenig Satzzeichen. |
| base + Purfview's Faster-Whisper-XXL     | Deutsch → Deutsch                      | 4           | 4                | 4             | 3          | **15**           | 02:00 min       | 00:08 min            | Gute Struktur, aber kaum Punktsetzung. Leicht verschachtelte Sätze. |
| small + Purfview's Faster-Whisper-XXL    | Deutsch → Deutsch                      | 4           | 4                | 4             | 4          | **16**           | 02:00 min       | 00:08 min            | Bessere Satzstruktur und Trennung. Höhere Interpunktion. |
| medium + Purfview's Faster-Whisper-XXL   | Deutsch → Deutsch                      | 5           | 3                | 3             | 4          | **15**           | 02:00 min       | 00:17 min            | Sehr gute Lesbarkeit und natürliche Satzgrenzen. |
| large_v1 + Purfview's Faster-Whisper-XXL               | Deutsch → Deutsch                      | 5           | 4                | 4             | 4          | **17**           | 02:00 min       | 00:36 min            | Sehr gut strukturiert, minimal holprige Stellen, insgesamt aber sehr solide. |
| large_v2 + Purfview's Faster-Whisper-XXL               | Deutsch → Deutsch                      | 5           | 5                | 5             | 4          | **19**           | 02:00 min       | 00:17 min            | Exzellente Synchronisation und Satzstruktur, extrem hohe Lesbarkeit. |
| large_v3 + Purfview's Faster-Whisper-XXL               | Deutsch → Deutsch                      | 5           | 5                | 4             | 5          | **19**           | 02:00 min       | 00:33 min            | Sehr natürliche Transkription, nahezu identisch zum Original. |
| large-turbo-v3 + Purfview's Faster-Whisper-XXL         | Deutsch → Deutsch                      | 5           | 4                | 4             | 5          | **18**           | 02:00 min       | 00:21 min            | Sehr schnell, sauber und stilistisch extrem natürlich. |
> 🧠 **Interpretation:**  
> `tiny` liefert einfache, teilweise fragmentierte Sätze mit wenig Interpunktion.  
> `base` bietet eine solide Grundstruktur und gute Synchronisation, bleibt jedoch bei der Zeichensetzung und Satztrennung limitiert.  
> `small` erreicht spürbare Fortschritte in der Satzstruktur und Interpunktion gegenüber `base`.  
> `medium` bietet eine sehr gute Lesbarkeit und natürlichere Satzgrenzen.  
> Mit `large_v1` wird die Struktur nochmals stabiler, obwohl minimale holprige Stellen bestehen bleiben.  
> `large_v2` liefert eine nahezu perfekte Satzstruktur und Synchronisation, kleine grammatikalische Abweichungen sind jedoch vorhanden.  
> `large_v3` und `large-turbo-v3` erreichen die höchste Qualität: Sie bieten extrem natürliche, originalgetreue und stilistisch einwandfreie Transkriptionen.



---

## 🧠 Ähnlichkeitsanalyse der automatischen Untertitelung im Vergleich zum Originaltext

Diese Analyse zeigt, wie stark die automatisch erzeugten Transkriptionen der verschiedenen Whisper-Modelle mit dem tatsächlichen Originaltext aus dem Video übereinstimmen.

### 📊 Ähnlichkeitsmatrix mit Originaltext (Speech-to-Text)

Diese Matrix zeigt die Ähnlichkeit zwischen den automatisch generierten Transkriptionen und dem Originaltext aus dem Video.

| Model Comparison | original | tiny | base | small | medium | large_v1 | large_v2 | large_v3 | large-turbo-v3 |
|----|----|----|----|----|----|----|----|----|----|
| **original** | – | 52% | 90% | 24% | 24% | 97% | 97% | 97% | 96% |
| **tiny** | 60% | – | 44% | 49% | 38% | 47% | 51% | 35% | 46% |
| **base** | 90% | 50% | – | 90% | 89% | 89% | 89% | 91% | 92% |
| **small** | 97% | 55% | 90% | – | 95% | 98% | 96% | 84% | 92% |
| **medium** | 91% | 46% | 76% | 76% | – | 94% | 91% | 77% | 89% |
| **large_v1** | 97% | 54% | 89% | 98% | 92% | – | 96% | 96% | 94% |
| **large_v2** | 97% | 53% | 90% | 24% | 24% | 96% | – | 98% | 97% |
| **large_v3** | 97% | 44% | 78% | 24% | 24% | 87% | 98% | – | 94% |
| **large-turbo-v3** | 96% | 54% | 91% | 71% | 91% | 94% | 97% | 97% | – |

> 🧠 **Interpretation:**  
> Die Modelle `large_v3` und `large-turbo-v3` liefern die höchste Übereinstimmung mit dem Originaltext (**96–98 %**) und übertreffen damit die bisherigen Modelle.  
> Auch `small` (**97 %**) und `medium` (**92 %**) erreichen eine sehr hohe Texttreue.  
> `base` bleibt solide bei etwa **90 %**, während `tiny` deutlich abweicht und nur etwa **52 %** erreicht, was auf verkürzte oder fehlerhafte Formulierungen hinweist.  
> Insgesamt zeigen die größeren Modelle (`large_v1`, `large_v2`, `large_v3`, `large-turbo-v3`) eine sehr natürliche, flüssige und strukturierte Transkription.

---

### ❓ Warum sind Modelle dem Original ähnlich, aber untereinander unterschiedlich?

> 🧠 **Hinweis:**  
> Eine hohe Übereinstimmung mit dem Originaltext bedeutet nicht automatisch, dass die Modelle untereinander identisch sind.  
> Dies liegt daran, dass verschiedene Modelle denselben Sinn mit **unterschiedlicher Wortwahl, Satzstruktur oder Detaillierungsgrad** ausdrücken können.

#### 🔍 Beispiel:

**🎯 Original:**  
„Ich gebe einen Zylinder dazu, den ich etwas in Z skaliere.“

**🧠 Modell (base):**  
„Ich füge einen Zylinder hinzu, den ich in Z-Richtung skaliere.“

**🧠 Modell (small):**  
„Ich gebe den Zylinder in die Szene und skaliere ihn in Z.“

**🧠 Modell (large_v3):**  
„Ich füge dem Modell einen Zylinder hinzu und skaliere ihn entlang der Z-Achse.“

➡️ **Alle Modelle** sind korrekt und transportieren denselben Inhalt – unterscheiden sich aber stilistisch, in Wortwahl und Satzkomplexität.

---

### 📌 Fazit:

- `small`, `medium`, `large_v1`, `large_v2`, `large_v3` und `large-turbo-v3` erreichen eine **sehr hohe Übereinstimmung mit dem Original** (92–98 %).
- Aber **untereinander** zeigen sie:
  - Unterschiede in Satzstruktur (komplex vs. einfach),
  - Variationen in Wortwahl (z. B. "hinzufügen" vs. "geben"),
  - kleine stilistische Abweichungen.
- Deshalb ist die Übereinstimmung **zum Original höher** als zwischen den Modellen untereinander.

Dies ist **charakteristisch für natürliche Sprache** – derselbe Inhalt kann auf verschiedene elegante Arten formuliert werden.



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
| MyMemory Translate                                  | Deutsch → Englisch                     | 5                      | 4       | 4              | 4          | 17               | 02:00 min       | 00:03 min            | Beste Balance aus Stil, Natürlichkeit und Korrektheit. „Texture Mapping“ korrekt erkannt, idiomatisch sauber. |
| Groq LLM                                           | Deutsch → Englisch                     | 4                      | 3       | 3              | 3          | 13               | 02:00 min       | 00:03 min            | Klar verständlich, aber teilweise etwas maschinenhaft und wenig idiomatisch. |
| Winstxnhdw-HLLB API                                | Deutsch → Englisch                     | 3                      | 3       | 2              | 2          | 10               | 02:00 min       | 00:24 min            | Technisch korrekt, aber oft sehr steif und unnatürlich. |
| Ollama (Mistral)                                   | Deutsch → Englisch                     | 4                      | 3       | 4              | 3          | 14               | 02:00 min       | 00:04 min            | Gute Natürlichkeit, sauberer Satzbau, kleine stilistische Schwächen. |
|    ↳ DeepSeek R1                                   | Deutsch → Englisch                     | 3                      | 3       | 3              | 3          | 12               | 02:00 min       | 00:58 min            | Durchschnittliche Übersetzung, teilweise wortwörtlich und repetitiv. |
|    ↳ Gemma 3                                       | Deutsch → Englisch                     | 4                      | 3       | 3              | 3          | 13               | 02:00 min       | 00:06 min            | Relativ klar, aber sprachlich etwas eintönig und wenig dynamisch. |
|    ↳ ZongweiGemma3 Translator 1B                   | Deutsch → Englisch                     | 3                      | 3       | 3              | 2          | 11               | 02:00 min       | 00:05 min            | Verständlich, aber einige grammatikalische Schwächen und steife Formulierungen. |
| Gemini 2.0 Flash                                   | Deutsch → Englisch                     | 4                      | 4       | 3             | 4          | 15               | 02:00 min       | 00:02 min            | Klar formuliert, meist idiomatisch, leicht vereinfachte Strukturen. |
> 🧠 **Interpretation:** Übersetzungen mit GPT-4-Modellen (inkl. `turbo`, `mini`) sind stilistisch überlegen, besonders bei Fachbegriffen und Satzfluss. `DeepL` bietet eine solide Leistung, während `Google Translate V1` klare Schwächen bei Terminologie und Natürlichkeit zeigt.


### 📊 Ähnlichkeitsmatrix der Übersetzungen (in %)

Diese Matrix zeigt den tatsächlichen Ähnlichkeitsgrad (textuelle Übereinstimmung) zwischen allen automatisch generierten Übersetzungen – basierend auf realen .srt-Dateien und analysiert mittels `SequenceMatcher`.

| Model Comparison | Google_V1 | DeepL_V2 | ChatGPT-mini-3o | GPT-4o-mini | GPT-4o | GPT-4o-turbo | GPT-3.5-turbo | GPT-4 | MyMemory | groq | winstxnhdw-HLLB | Ollama | DeepSeek-R1 | gemma3 | zongweigemma3-translator1b | gimini-2.0-flash |
|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|
| **Google_V1** | – | 38% | 25% | 25% | 25% | 25% | 24% | 24% | 30% | 29% | 36% | 29% | 39% | 27% | 27% | 32% |
| **DeepL_V2** | 38% | – | 33% | 33% | 32% | 32% | 32% | 31% | 41% | 52% | 54% | 52% | 59% | 38% | 49% | 55% |
| **ChatGPT-mini-3o** | 25% | 33% | – | 98% | 96% | 97% | 97% | 96% | 45% | 42% | 38% | 39% | 33% | 46% | 38% | 38% |
| **GPT-4o-mini** | 25% | 33% | 98% | – | 96% | 97% | 98% | 96% | 45% | 43% | 39% | 40% | 33% | 47% | 39% | 39% |
| **GPT-4o** | 25% | 32% | 96% | 96% | – | 96% | 96% | 97% | 43% | 41% | 38% | 39% | 32% | 45% | 38% | 38% |
| **GPT-4o-turbo** | 25% | 32% | 97% | 97% | 96% | – | 97% | 98% | 44% | 42% | 38% | 40% | 31% | 47% | 39% | 39% |
| **GPT-3.5-turbo** | 24% | 32% | 97% | 98% | 96% | 97% | – | 96% | 44% | 43% | 38% | 39% | 32% | 46% | 38% | 38% |
| **GPT-4** | 24% | 31% | 96% | 96% | 97% | 98% | 96% | – | 44% | 41% | 37% | 39% | 32% | 46% | 39% | 39% |
| **MyMemory** | 30% | 41% | 45% | 45% | 43% | 44% | 44% | 44% | – | 61% | 37% | 47% | 40% | 88% | 48% | 58% |
| **groq** | 29% | 52% | 42% | 43% | 41% | 42% | 43% | 41% | 61% | – | 40% | 63% | 51% | 59% | 61% | 72% |
| **winstxnhdw-HLLB** | 36% | 54% | 38% | 39% | 38% | 38% | 38% | 37% | 37% | 40% | – | 42% | 64% | 36% | 41% | 41% |
| **Ollama** | 29% | 52% | 39% | 40% | 39% | 40% | 39% | 39% | 47% | 63% | 42% | – | 57% | 47% | 84% | 46% |
| **DeepSeek-R1** | 39% | 59% | 33% | 33% | 32% | 31% | 32% | 32% | 40% | 51% | 64% | 57% | – | 38% | 56% | 50% |
| **gemma3** | 27% | 38% | 46% | 47% | 45% | 47% | 46% | 46% | 88% | 59% | 36% | 47% | 38% | – | 47% | 57% |
| **zongweigemma3-translator1b** | 27% | 49% | 38% | 39% | 38% | 39% | 38% | 39% | 48% | 61% | 41% | 84% | 56% | 47% | – | 49% |
| **gimini-2.0-flash** | 32% | 55% | 38% | 39% | 38% | 39% | 38% | 39% | 58% | 72% | 41% | 46% | 50% | 57% | 49% | – |


> 🧠 **Interpretation:**  
> 💛 **GPT-4o-Modelle** (einschließlich *turbo*, *mini*, *klassisch*) weisen eine sehr hohe gegenseitige Übereinstimmung auf (meist **≥ 79 %**). Ihre Übersetzungen sind stilistisch und strukturell sehr ähnlich und zeigen insgesamt das höchste Niveau.
>  
> 💬 Auch **ChatGPT mini** und **GPT-3.5 turbo** zeigen weiterhin eine starke stilistische Nähe zur GPT-4o-Familie, erreichen jedoch leicht niedrigere Übereinstimmungen (ca. **74–76 %**).
>  
> 🟨 **DeepL V2** und **MyMemory** bleiben solide Alternativen, mit stabiler, idiomatischer Sprache und durchschnittlicher Übereinstimmung (rund **63–66 %**). Sie unterscheiden sich stilistisch stärker von GPT-Modellen, liefern aber insgesamt konsistente Ergebnisse.
>  
> 🆕 **Groq**, **Winstxnhdw-HLLB** und **Gemini 2.0 Flash** liegen in einer mittleren Gruppe (ca. **55–66 %** zueinander) und bieten brauchbare, aber deutlich weniger idiomatische oder glatte Übersetzungen.
>  
> 🌟 **Ollama (Mistral)** und seine Varianten (**DeepSeek R1**, **Gemma 3**, **ZongweiGemma3**) bilden eine eigene starke Untergruppe:  
> - Untereinander erreichen sie extrem hohe Übereinstimmungen (**81–92 %**).
> - Im Vergleich zu GPT-4o und ChatGPT mini sind sie jedoch stilistisch klar unterscheidbar.
>  
> 🚨 **Google Translate V1** bleibt deutlich abgeschlagen. Die Übersetzungen unterscheiden sich erheblich von allen anderen getesteten Modellen (**nur 6–14 %** Übereinstimmung) und wirken oft maschinell und stilistisch brüchig.

---

### ❓ Warum sind Übersetzungen untereinander unterschiedlich – trotz hoher Qualität?

> 🧠 **Hinweis:**  
> Auch wenn mehrere Modelle eine **gute Übersetzung** liefern, können sich ihre Formulierungen stark unterscheiden.  
> Das liegt daran, dass sie **unterschiedliche grammatische Konstruktionen, Synonyme oder Satzrhythmen** wählen – bei gleichem Sinn.

---

### 📌 Fazit:

- GPT-Modelle wie **GPT-4o**, **turbo**, **mini** nutzen *natürliche Sprache* mit stilistischen Nuancen.
- **DeepL** und **MyMemory** sind *idiomatisch korrekt*, aber leicht konservativer.
- **Google Translate** wirkt oft *technisch und weniger stilistisch ausgefeilt*.
- **Groq** und **Ollama (Mistral)** liefern brauchbare Übersetzungen, zeigen aber leichte Vereinfachungen oder technische Formulierungen.
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
| Piper (lessac, high, aac)                          | Englisch → Englisch                    | 4          | 4          | 4      | 4              | **16**           | 02:00 min       | 00:53 min            | Whisper-Modell: large-v1 (Groq) |
| Piper (kathleen, low, aac)                         | Englisch → Englisch                    | 3          | 3          | 4      | 3              | **13**           | 02:00 min       | 00:50 min            | Whisper-Modell: large-v2 (Winstxnhdw) |
| Piper (ryan, high, aac)                            | Englisch → Englisch                    | 5          | 4          | 4      | 5              | **18**           | 02:00 min       | 00:55 min            | Whisper-Modell: large-v3 (Ollama) |
| ↳ Whisper-Modell: large-v3 – DeepSeek R1           | Englisch → Englisch                    | 4          | 3          | 4      | 4              | **15**           | 02:00 min       | 00:57 min            | |
| ↳ Whisper-Modell: large-v3 – Gemma 3               | Englisch → Englisch                    | 3          | 4          | 3      | 3              | **13**           | 02:00 min       | 01:00 min            | |
| ↳ Whisper-Modell: large-v3 – ZongweiGemma3         | Englisch → Englisch                    | 3          | 3          | 4      | 3              | **13**           | 02:00 min       | 00:58 min            | |
| Piper (joe, medium, aac)                           | Englisch → Englisch                    | 5          | 4          | 4      | 3              | **16**           | 02:00 min       | 00:51 min            | Whisper-Modell: large-turbo-v3 (Gemini 2.0 Flash) |

> 🧠 **Interpretation:** Stimmen auf Basis von `GPT-4o`-Texten klingen meist natürlicher und dynamischer. `Piper alain` bietet gute technische Qualität, wirkt aber teils monoton. `Piper Alba` liefert angenehmere Betonung, während `English Aru` hörbar schwächer abschneidet.



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
| **large-v1** – Faster-Whisper-XXL + Groq (Stimme: lessac (high))     | 00:53                        | 43                        |
| **large-v2** – Faster-Whisper-XXL + Winstxnhdw (Stimme: kathleen (low)) | 00:50                        | 40                        |
| **large-v3** – Faster-Whisper-XXL + Ollama (Stimme: ryan (high))     | 00:55                        | 46                        |
| ↳ DeepSeek R1 (Stimme: ryan (high))                                  | 00:57                        | 45                        |
| ↳ Gemma 3 (Stimme: ryan (high))                                      | 01:00                        | 41                        |
| ↳ ZongweiGemma3 (Stimme: ryan (high))                                | 00:58                        | 40                        |
| **large-turbo-v3** – Faster-Whisper-XXL + Gemini 2.0 Flash (Stimme: joe (medium)) | 00:51                        | 39                       |
> 🧠 **Interpretation:** Die hochwertigsten Kombinationen (z. B. `small + GPT-4o + Piper GPT-4o`) benötigen nur wenig mehr Zeit als deutlich schwächere Varianten, liefern jedoch erheblich bessere Ergebnisse. Für schnelle Anwendungen kann `base + DeepL + Piper` ein effizienter Kompromiss sein.



### 🗂️ Übersicht ohne Text-to-Speech (nur Whisper + Übersetzung)

| Modellkombination                                                 | Gesamtzeit ohne TTS | Gesamtpunktzahl (von 40) |
|-------------------------------------------------------------------|----------------------|---------------------------|
| tiny + Purfview's Faster-Whisper-XXL + Google Translate V1 API   | 00:13               | 23                        |
| base + Purfview's Faster-Whisper-XXL + DeepL V2                   | 00:11               | 28                        |
| small + Purfview's Faster-Whisper-XXL + ChatGPT mini 3o           | 00:12               | 33                        |
| ↳ mit GPT-4o mini                                                | 00:12               | 34                        |
| ↳ mit GPT-4o                                                     | 00:14               | 34                        |
| ↳ mit GPT-4o turbo                                               | 00:13               | 34                        |
| ↳ mit GPT-3.5 turbo                                              | 00:13               | 30                        |
| ↳ mit GPT-4                                                     | 00:19               | 34                        |
| medium + Purfview's Faster-Whisper-XXL + MyMemory Translate       | 00:20               | 32                        |
| large-v1 + Purfview's Faster-Whisper-XXL + Groq                   | 00:36               | 30                        |
| large-v2 + Purfview's Faster-Whisper-XXL + Winstxnhdw             | 00:17               | 29                        |
| large-v3 + Purfview's Faster-Whisper-XXL + Ollama                 | 00:33               | 33                        |
| ↳ DeepSeek R1                                                    | 00:33               | 32                        |
| ↳ Gemma 3                                                        | 00:33               | 33                        |
| ↳ ZongweiGemma3                                                  | 00:33               | 31                        |
| large-turbo-v3 + Purfview's Faster-Whisper-XXL + Gemini 2.0 Flash | 00:21               | 33                        |
