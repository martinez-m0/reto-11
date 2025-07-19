# reto-11
#las palbras mas repetidas son:
  from: 21720  
by: 18028  
received: 16176  
with: 12757  
id: 12607  
0500: 11774  
nakamurauitsiupuiedu: 10774  
dec: 9267  
nov: 8988  
sourcecollabsakaiprojectorg: 8985  
for: 7715  
esmtp: 7188  
paploouhiacuk: 7188  
textplain: 5391  
charsetutf8: 5391  
gmt: 4941  
0000: 4932  
thu: 4764  
to: 4566  
tue: 4498  
oct: 4164  
fri: 4007  
mon: 3685  
you: 3621  
date: 3612  
sakai: 3607  
murder: 3594  
mailumichedu: 3594  
cyrus: 3594  
lmtpa: 3594  
localhost: 3594  
127001: 3594  
postfix: 3594  
smtp: 3594  
wed: 3518  
0400: 2910  
the: 2544  
svn: 2537  
23: 2169  
10: 2145  
log: 2100  
site: 1887  
modify: 1884  
this: 1882  
new: 1879  
message: 1842  
was: 1835  
29: 1834  
revision: 1833  

#se hizo con este codigo:
  with open("mbox.txt", "r", encoding="utf-8") as archivo:
    texto = archivo.read()

vocales = set("aeiouAEIOU")
consonantes = set("bcdfghjklmnpqrstvwxyzBCDFGHJKLMNPQRSTVWXYZ")
contador_vocales = 0
contador_consonantes = 0
todas_las_palabras = []

for c in texto:
    if c.isalpha():
        if c in vocales:
            contador_vocales += 1
        elif c in consonantes:
            contador_consonantes += 1

lineas = texto.splitlines()
for linea in lineas:
    palabras = linea.strip().split()
    for palabra in palabras:
        palabra_limpia = "".join(c for c in palabra if c.isalnum())
        if palabra_limpia:
            todas_las_palabras.append(palabra_limpia.lower())

conteo = Counter(todas_las_palabras)
top_50 = conteo.most_common(50)

print("Cantidad de vocales:", contador_vocales)
print("Cantidad de consonantes:", contador_consonantes)
print("\nTop 50 palabras más comunes:")
for palabra, cantidad in top_50:
    print(f"{palabra}: {cantidad}")
