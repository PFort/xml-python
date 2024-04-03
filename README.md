# _xml-python_
---
## Hem aprés a parsear un document XML amb Python
---
Per fer-ho necessitem un document XML, després, emmagatzemant cada dada amb python per poder printar un document HTML.

La forma correcta d'agafar un element és la següent:

Primer hem de especificar de quin document volem agafar les dades XML:
```
doc = minidom.parse("Exemple.xml")
```
Després hem d'agafar cada dada per separat:
```
nom = tag_Exemple.getElementsByTagName("nom")[0].firstChild.data
```
També podem agafar els atributs dels elements:
```
id = tag_Exemple.getAttribute("id")
```
Per poder printar-ho simplement fer un print amb tots els elements que hi hagi en el nostre HTML:
```
print("<html><head><title>EJEMPLO</title></head>")
```
__També es pot crear un document HTML directament. Per fer-ho hem de fer el següent:__

**1.** Posar el nom del document que volem crear, la "w" significa Write, vol dire que sobrescriurà tot el que hi hagi en el document.
```
file = open("xml.html", "w")
```
**2.** La part d'agafar ell elements no canvia:
```
 valor_age = tag_person.getElementsByTagName("age")[0].firstChild.data
```
**3.** A l'hora de printar-ho s'ha de fer el següent:
```
file.write("<html><head><title>Diaris DOM</title></head><body>\n")
```
Si tenim una etiqueta pare amb més d'una etiqueta fill igual i volem obtenir els valors de totes per separat podem utilitzar un FOR:
```
for tag_person in lista_tag_person:
    tag_name = tag_person.getElementsByTagName("name")[0]
    valor_name = tag_name.firstChild.data
    valor_atribut = tag_person.getAttribute("id")

    valor_age = tag_person.getElementsByTagName("age")[0].firstChild.data
    valor_data = tag_person.getElementsByTagName("naixement")[0].firstChild.data
```
Després, a l'hora de printar, haurem de ficar els PRINTS dins del FOR, per poder obtenir tots els valors que volem, i no només el primer:
```
for tag_person in lista_tag_person:
    tag_name = tag_person.getElementsByTagName("name")[0]
    valor_name = tag_name.firstChild.data
    valor_atribut = tag_person.getAttribute("id")

    valor_age = tag_person.getElementsByTagName("age")[0].firstChild.data
    valor_data = tag_person.getElementsByTagName("naixement")[0].firstChild.data

    print("---------------")
    print(f"El nom és {valor_name} i te la id {valor_atribut}")
    print(f"La edat és {valor_age}")
    print(f"Va neixer al {valor_data}")
    print("---------------")
```
---
Tota aquesta informació sobre com utilitzar XML i Python es pot extreure de la següent pàgina:
[XML-PYTHON](https://github.com/jmirinformatica/1asixdaw-m04/tree/main/python/xml-dom-parser)

---
[![alt](https://www.icomem.es/imagenes/tinymce/bot%C3%B3n-m%C3%A1s-informaci%C3%B3n.png)](https://github.com/jmirinformatica/1asixdaw-m04/tree/main/python/xml-dom-parser)
