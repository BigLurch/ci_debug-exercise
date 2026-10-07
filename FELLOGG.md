# Fellogg

En rad per fel. Skriv medan du minns hur du gjorde.

| Nr | Vad stod i loggen? | Lokalt eller på GitHub? | Hur tog du reda på orsaken? | Hur löste du det? |
|----|--------------------|-------------------------|-----------------------------|-------------------|
| 1  |Syntax error        |Jag hittade felet i Github Action loggen|Läste loggen på github och såg mellanslaget i koden|Genom att kontrollera raden som Github Action nämde kunde jag konstatera att problemet låg under steps|
| 2  |Unable to find uv.lock|Jag hittade error koden i min lokala docker|Jag hittade felet när jag körde ```act push``` kommandot i min lokala bash terminal + upptäckte också nu att uv.lock låg i .gitignore(såg att fil namnet var grå)|Genom att köra kommandot ```uv sync``` så skapade jag uv.lock tillsammans med min .venv(kan även köra ```uv lock```), tog även bord filen ur .gitignore|
| 3  |F401 os imprted but unused|Jag hitta error koden i min likala docker|felmeddelandet kom upp när jag gjorde ytterliga en ```act push```|Genom att söka mig in i den fil som hade den onödiga importen och raderade den|

Fortsätt tabellen med fler rader vid behov.
