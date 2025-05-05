# Com desplegar l'aplicatiu:
Linux:
python3 -m venv .venv
source .venv/bin/activate
# instalar dependencies
pip install -r requirements.txt
flask run --debug

Windows:
python -m venv .venv
.\.venv\Scripts\activate
# instalar dependencies
pip install -r requirements.txt
python app.py


# Mode local
-Descarregar l'arxiu xml
-Crea la carpeta rss/lavanguardia/ a l’arrel si no està creada
-Copia l'arxiu xml a la carpeta rss/lavanguardia/
-Obrir l'arxiu app.py i assegurar-se que la linia "xml = f"./rss/lavanguardia/{seccio}.xml"" estigui activa (sense #) a la funció "get_rss_lavanguardia" 
-Anar a "http://127.0.0.1:5000/lavanguardia/NOMDELXML" al navegador on "NOMDELXML" és el nom del xml descarregat i que esta a la carpeta

(Opcional)
-Obrir l'arxiu templates/index.html i afegir aquesta linia desprès de l'ultim <li>:
<li><a href="/lavanguardia/NOMDELXML">NOMDELXML(AQUI POTS DECIDIR EL QUE VULGUIS)</a></li>

Així quan entris a "http://127.0.0.1:5000" et surtira una llista de tots els xmls importats


# Mode remot
-Obrir l'arxiu app.py i assegurar-se que la linia "xml = f"https://www.lavanguardia.com/rss/{seccio}.xml"" estigui activa (sense #) a la funció "get_rss_lavanguardia"  i que la linia "xml = f"./rss/lavanguardia/{seccio}.xml"" estigui inactiva (amb #)
-Entrar a "http://127.0.0.1:5000/lavanguardia/PAGINA" on pagina pot ser per exemple "deportes"

(Opcional)
-Obrir l'arxiu templates/index.html i afegir aquesta linia desprès de l'ultim <li>:
<li><a href="/lavanguardia/NOMDELXML">NOMDELXML(AQUI POTS DECIDIR EL QUE VULGUIS)</a></li>

Així quan entris a "http://127.0.0.1:5000" et surtira una llista de totes les pagines que et connectaras remotament (si existeixen)


Pàgina d'exemple: http://127.0.0.1:5000/lavanguardia/deportes

Documentació oficial de flask: https://flask.palletsprojects.com/en/stable/
Que són els entorns virtuals: https://realpython.com/python-virtual-environments-a-primer/