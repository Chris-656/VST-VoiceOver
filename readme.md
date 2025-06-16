## Workflow for Voiceover
This workflow works with the tool subtitleedit from  
niksedk  (https://github.com/SubtitleEdit/subtitleedit/commits?author=niksedk) 

## SubtitelEdit
load Video
- transcribe with whisper (without autotranslate)
- use settings VST-Voice over Workfow
- use spell checking if needed for the original and translated voice
- save srt file
  
a good alternative side for exact timing translations can be found here
- translate: https://translatesubtitles.co/translatesub.php?srt=Stabilizing_de.srt

## 🧭 Überblick: Visueller Workflow zur Erstellung von Voiceover-Untertiteln

<img src="images/workflow.png" alt="Whisper Advanced Settings" width="600"/>

Die Grafik zeigt den typischen Ablauf in vier Schritten – von der Spracherkennung bis zur finalen Platzierung der Untertitel im Video:

1. **Audio → Text (Transkription)**  
   Automatische Umwandlung gesprochener Sprache in geschriebenen Text mit Whisper – präzise, zeitsynchron und satzweise segmentiert.

2. **Text → Übersetzung**  
   Maschinelle Übersetzung in die gewünschte Sprache, z. B. mit DeepL, GPT-4o oder MyMemory.

3. **Text → Stimme (Vertonung)**  
   Mit einem TTS-System (z. B. Piper) wird aus dem übersetzten Text eine klare Audio-Spur erzeugt.

4. **Video + Text → Untertitel**  
   Einfügen der übersetzten und vertonten Untertitel in das Video, z. B. mit Subtitle Edit – inkl. finalem Feinschliff bei Timing, Format und Layout.

