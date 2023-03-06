### Encapsulation
Litt motivasjon for å se problemet


```python
person1_fornavn   = "Joakim"
person1_etternavn = "Lier"
person1_alder     = 28
person1_jobb      = "Cisco"
person2_fornavn   = "Elev"
person2_etternavn = "Studentesen"
person2_alder     = 17
person2_skole     = "Akademiet"
personliste = [person1_fornavn,
               person1_etternavn,
               person1_alder,
               person1_jobb,
               person2_fornavn,
               person2_etternavn,
               person2_alder,
               person2_skole]
```


🫠 🫠 🫠 🫠



```python[]
person1 = ["Joakim", "Lier", 28, "Cisco"]
person2 = ["Elev", "Studentesen", 17, "Akademiet"]

personliste = [person1, person2]
```


```python[]
person1 = ["Joakim", "Lier", 28, "Cisco"]
person2 = ["Elev", "Studentesen", 17, "Akademiet"]

personliste = [person1, person2]

# hva er dette?
print(personliste[1][2])
```



```python[]
person1 = ["Joakim", "Lier", 28, "Cisco"]
person2 = ["Elev", "Studentesen", 17, "Akademiet"]

personliste = [person1, person2]

def get_job(person):
    return person[3]

print(get_job(personliste[0]))
```


```python[|9]
person1 = ["Joakim", "Lier", 28, "Cisco"]
person2 = ["Elev", "Studentesen", 17, "Akademiet"]

personliste = [person1, person2]

def get_job(person):
    return person[3]

print(get_job(personliste[1])) # Hvorfor er dette feil?
```


### Encapsulation - Klasser

En klasse er en definisjon, eller "oppskrift", på en ting.


Hittil har vi definert en person som "noe" med:

- et fornavn
- et etternavn
- en alder
- en jobb eller skole


Dette har vi prøvd å få frem ved bruk av lister

Men klasser er laget for å løse akkurat dette


### Encapsulation - Klasser
En klasse inneholder informasjonen som hører til en ting

- Egen data
- Egne funksjoner


> Som en bruker kan vi anta at klassen holder styr på seg selv
så vi kan bruke dem i koden vår, uten å måtte tenke over hvordan klassen fungerer


### Encapsulation - Klasser

```python[|1|2-6|8|9-13|14]
class Person:
    def __init__(self, fornavn, etternavn, alder, jobb):
        self.fornavn = fornavn
        self.etternavn = etternavn
        self.alder = alder
        self.jobb = jobb

person1 = Person("Joakim", "Lier", 28, "Cisco")
person1 = Person(
    fornavn = "Joakim",
    etternavn = "Lier",
    alder = 28,
    jobb = "Cisco")
print(person1.fornavn)
```
- Tydelig hva som definerer en person
- Tydelig hva som menes med koden


Vi bruker punktum for å få tak i ting inni en klasse
```python[]
class Person:
    def __init__(self, fornavn, etternavn, alder, jobb):
        self.fornavn = fornavn
        self.etternavn = etternavn
        self.alder = alder
        self.jobb = jobb

person1 = Person("Joakim", "Lier", 28, "Cisco")
print(person1.fornavn)
print(person1.etternavn)
print(person1.alder)
print(person1.jobb)
```


### Encapsulation - Klasser
![autocomplete](assets/autocomplete.png)


### Klasser eller objekter?
Klasser er definisjonen på noe vi kan lage

Objekter er noe laget ut fra definisjonen

Note: foo


> Litt som forholdet mellom en oppskrift på kjeks
> og kjeksen du lagde fra oppskriften!


Vi sier at et objekt er en instans av en klasse


### Klasser eller objekter?

```python[|1-6|8|9-10]
class Person: # Klasse
    def __init__(self, fornavn, etternavn, alder, jobb):
        self.fornavn = fornavn
        self.etternavn = etternavn
        self.alder = alder
        self.jobb = jobb

person1 = Person("Joakim", "Lier", 28, "Cisco") # Objekt
person2 = Person("Elev", "Studentesen",
    l7, "Akademiet") # Objekt
```


### Klasser eller objekter?

Dette betyr at man kan lage mange objekter fra en klasse

> Akkurat som du kan lage mange kjeks fra en oppskrift


Samtidig trenger man bare en klasse for hver ting du vil beskrive

> Du trenger jo ikke flere oppskrifter på samme kjeksen


### Funksjoner

Hittil har vi for det meste sett på å pakke inn variabler


Vi kan også lage egne funksjoner for klassene våre

Vi har sett ett eksempel på det så langt:

```python
class Person:
    def __init__(self, ...
```


Vi kikker nærmere på funksjoner med navn som er omringet av `__` senere


### Funksjoner

```Python[]
class Person:
    def er_like_gammel_som(self, andre):
        return self.alder == andre.alder

person1 = Person("Joakim", "Lier", 28, "Cisco")
person2 = Person("Elev", "Studentesen",
    l7, "Akademiet")
print(person1.er_like_gammel_som(person2)) # Bra!
print(er_like_gammel_som(person2))         # gir ikke mening
                                           # trenger objekt
```


### Funksjoner, medlemmer eller metoder?

Vi sier at en funksjon eller variabel som tilhører en klasse er et _medlem_

Noen ganger brukes ordet _metode_ istedet for medlemsfunksjon


### Funksjoner - self
I Python må funksjoner som tilhører en klasse må ta inn parameteren `self`.

```Python[]
class Person:
    # Legg merke til self parameteren
    def er_over_20(self):
        return self.alder > 20

person1 = Person("Joakim", "Lier", 28, "Cisco")
# legg merke til at det er 0 parametre under
print(person1.er_over_20())
```


Denne blir automagisk sendt inn når du kaller på funksjonen

Gir funksjonen en måte å kunne lese sine egne medlemmer


> automagisk = magisk og automatisk


```python[]
class Person:
   def er_over_20(self):
      # feil!
      # ikke self, da vet ikke python
      # hvilken alder du snakker om
      return alder > 20
```


```python[]
class Person:
   def er_over_20(self):
      # riktig!
      # her bruker vi self, da vet
      # python hvor den skal lete
      return self.alder > 20
```


### \_\_funksjoner\_\_


De kalles "magiske metoder"

Er ikke ment til å brukes direkte


Python bruker dem automatisk i visse situasjoner



### \_\_init\_\_

Denne kalles hver gang du lager et objekt!

```python[]
class Person:
    def __init__(self):
        print("Nå ble jeg laget!")

person1 = Person() # Dette printer "Nå ble jeg laget!"
```


### \_\_str\_\_

Kort for "string"

Lar deg velge en tekst-beskrivelse av objektet, feks når du printer

returnerer en string


```python[]
class Dårlig:
    pass

class Bra:
    def __str__(self) -> str:
        return "Jeg er bra!"

dårlig = Dårlig()
bra = Bra()
print(dårlig)
# printer "<__main__.Dårlig object at 0x7fda01998730>"
print(bra)
# printer "Jeg er bra!"
```


### Oppsummering

Vi bruker klasser for å samle informasjon og funksjoner som hører sammen


Vi oppretter objekter basert på disse klassene, så vi lett kan jobbe med
dem. Nå kan vi ha en variabel som beskriver en person, istedet for flere!

