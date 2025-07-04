# 📤 Projektergebnisse & Ausgaben

Dieses Dokument enthält alle finalen Notebook-Ergebnisse des VST-VoiceOver-Projekts – darunter Video-Tutorial-Links, Modellvergleichstabellen sowie Metriken zur Bearbeitungszeit und Qualität der Modellkombinationen.

## 🎬 Finalisierte Videoergebnisse

🔗 **[Google Drive Ordner mit allen finalen Videos und Ressourcen](https://drive.google.com/drive/folders/1KXznx-bg6Pmnlr_pAbKOwNmhASIdBPAL?usp=share_link)**

📁 In diesem Ordner finden Sie **sämtliche Video-Ergebnisse des Projekts**, darunter:
- **Zwischenergebnisse** aus früheren Phasen (Testläufe, Modellvergleiche, Demo-Ausschnitte),
- sowie die **finalen vollständigen Videos** mit Untertiteln, Übersetzung und Voice-Over.

Der Ordner bietet einen vollständigen Überblick über die Videoentwicklung – vom ersten Prototyp bis zur fertigen Ausgabe.

🎓 **Ausgewählte Video-Tutorials & Demonstrationen:**

Diese Videos zeigen exemplarisch einzelne Arbeitsschritte und Vergleiche:

 ⚙️ [Virtuelle Umgebung einrichten – Setup & Tools](https://drive.google.com/file/d/1RoyXf4FDxZIa9Gde1hceD43GZVwC9oqv/view?usp=share_link)  
 🌍 [Subtitle-Übersetzungsqualität im Vergleich (verschiedene Modelle)](https://drive.google.com/file/d/1vi-e3clKKQ7ZUlbXP7fCGPqivJwG85Cs/view?usp=share_link)  
 🧠 [Modellkombination & Effizienz-Analyse (Whisper + LLM + TTS)](https://drive.google.com/file/d/1Hg_6gudhIM8lx3delWXmFNXwXTLktbEL/view?usp=share_link)

## 📊 Modellvergleichstabellen
### 🔁 Vergleich von Whisper-Modellen (Token-Ähnlichkeit in %)

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

---
### 🔁 Vergleich von Übersetzungsmodellen (semantische Ähnlichkeit in %)

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

---
📌 **Hinweis**:  
Eine ausführliche Analyse dieser Tabellen sowie Informationen zur Berechnung (BLEU, semantische Ähnlichkeit, Modellbeschreibung) finden Sie in folgendem Dokument:

[`model-review.md`](/model-review.md) – Modellvergleich, BLEU-Werte, Ähnlichkeitsanalysen
### 🔁 Fokussierter Vergleich: DeepL, GPT, Ollama

| Vergleich          | DeepL_V2 | GPT-4o | GPT-4o-turbo | Ollama |
|--------------------|----------|--------|---------------|--------|
| **DeepL_V2**       | –        | 32%    | 32%           | 52%    |
| **GPT-4o**         | 32%      | –      | 96%           | 39%    |
| **GPT-4o-turbo**   | 32%      | 96%    | –             | 40%    |
| **Ollama**         | 52%      | 39%    | 40%           | –      |

---
📌 Weitere Details zu diesen Modellen und Kombinationen sind im folgenden Dokument enthalten:  
[`final_model_report.md`](/final_model_report.md) – Zusammenfassung der finalen Konfigurationen und Ergebnisse
## ⏱️ Verarbeitungszeit pro Modellkombination

| Modellkombination                                                                      | 2-Minuten-Video | Komplettes Video (1h32min) | 📹 Video |
|----------------------------------------------------------------------------------------|------------------|-----------------------------|----------|
| **large-v3 + DeepL v2 + Ryan (high)**                                                  | ca. 1:09 Min     | ca. 30–35 Min              | [Ansehen](https://drive.google.com/file/d/1t_GF1Qso9jOx3YRQuOhMLmGSfF3m-MBy/view?usp=share_link) |
| **large-v3 + ChatGPT-4o + Ryan (high)**                                                | ca. 1:38 Min     | ca. 35–45 Min              | [Ansehen](https://drive.google.com/file/d/1tsnawjBw6D0WD4W0GRIi518aNNvKXwlN/view?usp=share_link) |
| **large-v3 + Ollama + Ryan (high)**                                                    | ca. 1:22 Min     | ca. 35–40 Min              | [Ansehen](https://drive.google.com/file/d/17DEixQwxpGvJSezbK9WuWOiBYPmL9c-u/view?usp=share_link) |
| **large-turbo-v3 + GPT-4o-turbo + Ryan (high)**                                        | ca. 0:58 Min     | ca. 30–35 Min              | [Ansehen](https://drive.google.com/file/d/1DJxSL46ZbDsopCWV2xVP-4IO-q-MlpXX/view?usp=share_link) |


📌 *Hinweis*: Alle Tests wurden unter identischen Hardwarebedingungen durchgeführt. Geringe Abweichungen durch API-Latenz oder Netzwerkverzögerungen sind möglich.
