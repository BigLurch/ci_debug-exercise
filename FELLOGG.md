# Fellogg

En rad per fel. Skriv medan du minns hur du gjorde.

| Nr | Vad stod i loggen? | Lokalt eller på GitHub? | Hur tog du reda på orsaken? | Hur löste du det? |
|----|--------------------|-------------------------|-----------------------------|-------------------|
| 1  |Syntax error        |Jag hittade felet i Github Action loggen|Läste loggen på github och såg mellanslaget i koden|Genom att kontrollera raden som Github Action nämde kunde jag konstatera att problemet låg under steps|
| 2  |Unable to find uv.lock|Jag hittade error koden i min lokala docker|Jag hittade felet när jag körde ```act push``` kommandot i min lokala bash terminal + upptäckte också nu att uv.lock låg i .gitignore(såg att fil namnet var grå)|Genom att köra kommandot ```uv sync``` så skapade jag uv.lock tillsammans med min .venv(kan även köra ```uv lock```), tog även bord filen ur .gitignore|
| 3  |F401 os imprted but unused|Jag hitta error koden i min likala docker|felmeddelandet kom upp när jag gjorde ytterliga en ```act push```|Genom att söka mig in i den fil som hade den onödiga importen och raderade den|
| 4  |Unformated i två filer(baseline.py var mitt fel)|jag hittade felet i min lokala docker|Efter att jag körde ```act push``` så dök det upp två unformatted errors, då vi har ruff i vår ```uv``` så begär workflowt att jag rättar till strukturen efter pep 8 innan den tillåter mig att fortsätta|Genom att köra kommandot ```uv run ruff format``` så rättas mina filer efter pep 8 strukturen i ruff|
| 5  |ModuleNotFoundError|Hitta detta lokalt|Jag körde ```act push``` till min docker igen och fick meddelandet att no module named 'numpy', detta indikerade för mig att kolla om numpy var addat till vår uv miljö(det var det ej)|Genom att köra kommandot ```uv add numpy```|
| 6  |AssertionError: [1.0, 1.66...] == [1.5, 2.5, 3.5]|Även denna hittades lokalt|Efter att jag kört ```act push``` så gick jag igenom det som stod i error meddelandet och upptäkte att matematiken i testet för glidande medelvärde stämde inte med kodens output. Jag letade upp funktionen i features.py och såg att fönstret värderade fel.|Jag ändrade koden i features.py så att värderingen i kernel delades med window istället för window + 1, vilket gav korrekt medelvärde.|

Fortsätt tabellen med fler rader vid behov.
