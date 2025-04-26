

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
| large_v1 + Purfview's Faster-Whisper-XXL               | Deutsch → Deutsch                      | 5           | 4                | 4             | 4          | **17**           | 02:00 min       | 00:36 min            | Sehr gut strukturiert, minimal holprige Stellen, insgesamt aber sehr solide. |
| large_v2 + Purfview's Faster-Whisper-XXL               | Deutsch → Deutsch                      | 5           | 5                | 5             | 4          | **19**           | 02:00 min       | 00:17 min            | Exzellente Synchronisation und Satzstruktur, extrem hohe Lesbarkeit. |
| large_v3 + Purfview's Faster-Whisper-XXL               | Deutsch → Deutsch                      | 5           | 5                | 5             | 5          | **20**           | 02:00 min       | 00:33 min            | Sehr natürliche Transkription, nahezu identisch zum Original. |
| large-turbo-v3 + Purfview's Faster-Whisper-XXL         | Deutsch → Deutsch                      | 5           | 5                | 5             | 5          | **20**           | 02:00 min       | 00:21 min            | Sehr schnell, sauber und stilistisch extrem natürlich. |
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

| Modellvergleich          | Original | tiny  | base  | small | medium | large_v1 | large_v2 | large_v3 | large-turbo-v3 |
|---------------------------|----------|-------|--------|--------|--------|----------|----------|----------|----------------|
| **Original**              | –        | 52 %  | 90 %   | 97 %   | 92 %   | 94 %     | 95 %     | 96 %     | 96 %           |
| **tiny**                  | 52 %     | –     | 44 %   | 49 %   | 38 %   | 41 %     | 42 %     | 43 %     | 44 %           |
| **base**                  | 90 %     | 44 %  | –      | 90 %   | 89 %   | 88 %     | 89 %     | 89 %     | 90 %           |
| **small**                 | 97 %     | 49 %  | 90 %   | –      | 95 %   | 95 %     | 96 %     | 97 %     | 96 %           |
| **medium**                | 92 %     | 38 %  | 89 %   | 95 %   | –      | 92 %     | 93 %     | 94 %     | 94 %           |
| **large_v1**              | 94 %     | 41 %  | 88 %   | 95 %   | 92 %   | –        | 98 %     | 96 %     | 97 %           |
| **large_v2**              | 95 %     | 42 %  | 89 %   | 96 %   | 93 %   | 98 %     | –        | 97 %     | 97 %           |
| **large_v3**              | 96 %     | 43 %  | 89 %   | 97 %   | 94 %   | 96 %     | 97 %     | –        | 98 %           |
| **large-turbo-v3**        | 96 %     | 44 %  | 90 %   | 96 %   | 94 %   | 97 %     | 97 %     | 98 %     | –              |

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
| MyMemory Translate                                  | Deutsch → Englisch                     | 5                      | 4       | 5              | 4          | 18               | 02:00 min       | 00:03 min            | Beste Balance aus Stil, Natürlichkeit und Korrektheit. „Texture Mapping“ korrekt erkannt, idiomatisch sauber. |
| Groq LLM                                           | Deutsch → Englisch                     | 4                      | 3       | 3              | 3          | 13               | 02:00 min       | 00:03 min            | Klar verständlich, aber teilweise etwas maschinenhaft und wenig idiomatisch. |
| Winstxnhdw-HLLB API                                | Deutsch → Englisch                     | 3                      | 3       | 2              | 2          | 10               | 02:00 min       | 00:24 min            | Technisch korrekt, aber oft sehr steif und unnatürlich. |
| Ollama (Mistral)                                   | Deutsch → Englisch                     | 5                      | 4       | 4              | 4          | 17               | 02:00 min       | 00:04 min            | Gute Natürlichkeit, sauberer Satzbau, kleine stilistische Schwächen. |
|    ↳ DeepSeek R1                                   | Deutsch → Englisch                     | 3                      | 3       | 3              | 3          | 12               | 02:00 min       | 00:58 min            | Durchschnittliche Übersetzung, teilweise wortwörtlich und repetitiv. |
|    ↳ Gemma 3                                       | Deutsch → Englisch                     | 4                      | 3       | 3              | 3          | 13               | 02:00 min       | 00:06 min            | Relativ klar, aber sprachlich etwas eintönig und wenig dynamisch. |
|    ↳ ZongweiGemma3 Translator 1B                   | Deutsch → Englisch                     | 3                      | 3       | 3              | 2          | 11               | 02:00 min       | 00:05 min            | Verständlich, aber einige grammatikalische Schwächen und steife Formulierungen. |
| Gemini 2.0 Flash                                   | Deutsch → Englisch                     | 4                      | 4       | 4              | 4          | 16               | 02:00 min       | 00:02 min            | Klar formuliert, meist idiomatisch, leicht vereinfachte Strukturen. |
> 🧠 **Interpretation:** Übersetzungen mit GPT-4-Modellen (inkl. `turbo`, `mini`) sind stilistisch überlegen, besonders bei Fachbegriffen und Satzfluss. `DeepL` bietet eine solide Leistung, während `Google Translate V1` klare Schwächen bei Terminologie und Natürlichkeit zeigt.


### 📊 Ähnlichkeitsmatrix der Übersetzungen (in %)

Diese Matrix zeigt den tatsächlichen Ähnlichkeitsgrad (textuelle Übereinstimmung) zwischen allen automatisch generierten Übersetzungen – basierend auf realen .srt-Dateien und analysiert mittels `SequenceMatcher`.

| Modellvergleich          | Google V1 | DeepL V2 | ChatGPT mini | GPT-4o mini | GPT-4o | GPT-4o turbo | GPT-3.5 turbo | GPT-4 | MyMemory | Groq | Winstxnhdw-HLLB | Ollama (Mistral) | DeepSeek R1 | Gemma 3 | ZongweiGemma3 | Gemini 2.0 Flash |
|---------------------------|-----------|----------|--------------|-------------|--------|---------------|----------------|--------|----------|------|----------------|------------------|------------|---------|---------------|-----------------|
| **Google V1**             | –         | 14 %     | 8 %          | 7 %         | 7 %    | 7 %           | 9 %            | 7 %    | 12 %     | 10 % | 9 %            | 8 %              | 8 %        | 7 %     | 7 %           | 6 %             |
| **DeepL V2**              | 14 %      | –        | 66 %         | 62 %        | 62 %   | 63 %          | 64 %           | 64 %   | 66 %     | 59 % | 58 %           | 57 %             | 58 %       | 57 %    | 56 %          | 55 %            |
| **ChatGPT mini**          | 8 %       | 66 %     | –            | 79 %        | 77 %   | 78 %          | 74 %           | 76 %   | 68 %     | 60 % | 59 %           | 58 %             | 58 %       | 57 %    | 56 %          | 55 %            |
| **GPT-4o mini**           | 7 %       | 62 %     | 79 %         | –           | 79 %   | 80 %          | 74 %           | 78 %   | 64 %     | 59 % | 58 %           | 57 %             | 58 %       | 57 %    | 56 %          | 55 %            |
| **GPT-4o**                | 7 %       | 62 %     | 77 %         | 79 %        | –      | 80 %          | 73 %           | 80 %   | 63 %     | 58 % | 57 %           | 56 %             | 57 %       | 56 %    | 56 %          | 54 %            |
| **GPT-4o turbo**          | 7 %       | 63 %     | 78 %         | 80 %        | 80 %   | –             | 75 %           | 80 %   | 64 %     | 58 % | 57 %           | 56 %             | 57 %       | 56 %    | 56 %          | 54 %            |
| **GPT-3.5 turbo**         | 9 %       | 64 %     | 74 %         | 74 %        | 73 %   | 75 %          | –              | 74 %   | 64 %     | 57 % | 56 %           | 55 %             | 56 %       | 55 %    | 54 %          | 53 %            |
| **GPT-4**                 | 7 %       | 64 %     | 76 %         | 78 %        | 80 %   | 80 %          | 74 %           | –      | 63 %     | 58 % | 57 %           | 56 %             | 57 %       | 56 %    | 56 %          | 54 %            |
| **MyMemory Translate**    | 12 %      | 66 %     | 68 %         | 64 %        | 63 %   | 64 %          | 64 %           | 63 %   | –        | 58 % | 57 %           | 56 %             | 57 %       | 56 %    | 55 %          | 54 %            |
| **Groq**                  | 10 %      | 59 %     | 60 %         | 59 %        | 58 %   | 58 %          | 57 %           | 58 %   | 58 %     | –    | 66 %           | 61 %             | 60 %       | 59 %    | 58 %          | 55 %            |
| **Winstxnhdw-HLLB**       | 9 %       | 58 %     | 59 %         | 58 %        | 57 %   | 57 %          | 56 %           | 57 %   | 57 %     | 66 % | –              | 63 %             | 62 %       | 61 %    | 60 %          | 58 %            |
| **Ollama (Mistral)**      | 8 %       | 57 %     | 58 %         | 57 %        | 56 %   | 56 %          | 55 %           | 56 %   | 56 %     | 61 % | 63 %           | –                | 84 %       | 82 %    | 81 %          | 72 %            |
| **DeepSeek R1**           | 8 %       | 58 %     | 58 %         | 58 %        | 57 %   | 57 %          | 56 %           | 57 %   | 57 %     | 60 % | 62 %           | 84 %             | –          | 85 %    | 84 %          | 73 %            |
| **Gemma 3**               | 7 %       | 57 %     | 57 %         | 57 %        | 56 %   | 56 %          | 55 %           | 56 %   | 56 %     | 59 % | 61 %           | 82 %             | 85 %       | –       | 92 %          | 71 %            |
| **ZongweiGemma3**         | 7 %       | 56 %     | 56 %         | 56 %        | 56 %   | 56 %          | 54 %           | 56 %   | 55 %     | 58 % | 60 %           | 81 %             | 84 %       | 92 %    | –             | 70 %            |
| **Gemini 2.0 Flash**      | 6 %       | 55 %     | 55 %         | 55 %        | 54 %   | 54 %          | 53 %           | 54 %   | 54 %     | 55 % | 58 %           | 72 %             | 73 %       | 71 %    | 70 %          | –               |


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
> 🧠 **Interpretation:** Die hochwertigsten Kombinationen (z. B. `small + GPT-4o + Piper GPT-4o`) benötigen nur wenig mehr Zeit als deutlich schwächere Varianten, liefern jedoch erheblich bessere Ergebnisse. Für schnelle Anwendungen kann `base + DeepL + Piper` ein effizienter Kompromiss sein.



