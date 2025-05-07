## Parametern von Faster-Whisper (z. B. Purfview Faster-Whisper-XXL),

| **Parameter**           | **Empfohlener Wert**           | **Beschreibung**                                                                                                              |
| ----------------------- | ------------------------------ | ----------------------------------------------------------------------------------------------------------------------------- |
| `--sentence`            | *(aktivieren)*                 | Aktiviert **Satzsegmentierung** – Whisper erkennt vollständige Sätze, nicht nur Zeitblöcke.                                   |
| `--vad_method`          | `pyannote_v3` oder `silero_v3` | Wählt die Methode zur Sprachaktivitätserkennung (**Voice Activity Detection**, VAD).                                          |
| `--vad_threshold`       | `0.4` – `0.6`                  | Steuert, wie sicher das Modell sein muss, um Sprache zu erkennen. Niedriger = empfindlicher (hilft bei fehlenden Endwörtern). |
| `--no_speech_threshold` | `0.7` – `0.85`                 | Bestimmt, wie "still" es sein muss, damit Whisper denkt, **kein Sprecher ist aktiv** – beeinflusst Segmentende.               |
| `--max_silent_period`   | `2.0` – `2.5` Sekunden         | Erlaubt eine längere Stille, bevor das Modell denkt, der Satz ist zu Ende. Hilfreich bei **langsamem Sprechen**.              |
| `--beam_size`           | `5` – `10`                     | Erhöht die Genauigkeit beim Decoding. Mehr Hypothesen = **bessere Wortwahl und Satzende-Erkennung**.                          |
| `--temperature`         | `0.0` – `0.2`                  | Je niedriger, desto **deterministischer** (verlässlicher, stabiler) ist die Transkription.                                    |
| `--word_timestamps`     | *(optional, aktivieren)*       | Gibt **Start- und Endzeiten jedes Wortes** aus – ideal zur manuellen Kontrolle von abgeschnittenen Wörtern.                   |

## Settings
![image](https://github.com/user-attachments/assets/15f0b005-f672-4a13-882f-73ad87965af4)
![image](https://github.com/user-attachments/assets/27a410ba-28ee-4ccc-9761-d9c2ed93e015)

