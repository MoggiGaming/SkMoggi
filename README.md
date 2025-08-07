<p align="center">
<pre>
░██████╗██╗░░██╗███╗░░░███╗░█████╗░░██████╗░░██████╗░██╗
██╔════╝██║░██╔╝████╗░████║██╔══██╗██╔════╝░██╔════╝░██║
╚█████╗░█████═╝░██╔████╔██║██║░░██║██║░░██╗░██║░░██╗░██║
░╚═══██╗██╔═██╗░██║╚██╔╝██║██║░░██║██║░░╚██╗██║░░╚██╗██║
██████╔╝██║░╚██╗██║░╚═╝░██║╚█████╔╝╚██████╔╝╚██████╔╝██║
╚═════╝░╚═╝░░╚═╝╚═╝░░░░░╚═╝░╚════╝░░╚═════╝░░╚═════╝░╚═╝
</pre>
</p>

---

# 🧠 Hvad er det her?

Det her er et Skript-addon, der gør det super nemt at hente spiller-hoveder med getHeadListener.
Perfekt hvis du vil give spillere custom hoveder eller bruge dem i en GUI.🧠

Det er en moderne erstatning for SkBee’s hoved-funktioner, med bedre performance og mere fleksibilitet.

---

## 🚀 Sådan kommer du i gang (Setup guide)

Først og fremmest skal du have `SkMoggi` plugin’et installeret på din server, ellers virker det her ikke.  

### Sådan gør du:  
1. Download `SkMoggi` plugin (`.jar` fil).  
2. Log ind på din servers FTP med et program som FileZilla eller via dit hosting kontrolpanel.  
3. Upload `SkMoggi` plugin-filen til mappen `/plugins` på din server.  
4. Genstart serveren, så plugin’et bliver loadet.  
5. Sørg for at have Skript installeret på serveren, ellers virker det ikke.  

Når det er på plads, kan du importere `dk.moggi.getHeadListener` i dine Skript-filer og bruge funktionerne som beskrevet nedenfor.

---

## 🧩 Hvordan får man values til custom hoveder?

Du kan hente custom Minecraft hoveder med tekstur-data fra https://minecraft-heads.com/

1. Gå ind på https://minecraft-heads.com/custom-heads og find et hoved du vil bruge, fx en burger eller et dyr.

2. Klik på hovedet og kopier "Value" teksten (det er en lang Base64 streng der repræsenterer teksturen).

3. Brug værdien i dit Skript med `getHead()` funktionen. Du kan fx skrive:
   
---

## 🔌 Import (skal være øverst i din `.sk` fil)

~~~yaml
import:
  dk.moggi.getHeadListener

# Eksempel:
# Du kan nu bruge getHead() funktionen som her:
# set {_hoved} to getHead("#Value")
# give player {_hoved}
~~~

---

## 📦 Funktion – sådan henter du et hoved

<p align="center">
<pre>
function getHead(value: text) :: item:
    return getHeadListener.getHead({_value})
</pre>
</p>

---

## 💡 Eksempel kommando `/givehead`

```skript
command /givehead:
    trigger:
        set {_head} to getHead("#Brug et gyldigt value, læs om guide længere oppe.")
        give player {_head}
