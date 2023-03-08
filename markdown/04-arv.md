### Arv

Noen ganger kan flere klasser ha mye til felles, men må likevel holdes separat

En måte å skille ut det de har til felles kalles arv



Dette betyr at hvis en klasse arver fra en annen, vil barnet få de samme medlemmene som forelderen.


![arv](assets/arv.png)


```python[]
#Grunnklasse
class Person:
    def __init__(self, fornavn,
                       etternavn,
                       alder):
        self.fornavn = fornavn
        self.etternavn = etternavn
        self.alder = alder

    def si_hallo(self):
        print("hallo")

```



```python[|1,8|1,8,5,12]
class Elev(Person): # Arver fra Person
    def __init__(self, fornavn,
                 etternavn,
                 alder, skole):
        super().__init__(fornavn,etternavn,alder)
        self.skole = skole

class Ansatt(Person): # Arver fra Person
    def __init__(self, fornavn,
                       etternavn,
                       alder, jobb):
        super().__init__(fornavn,etternavn,alder)
        self.jobb = jobb

```



```python
elev1 = Elev("Elev",
             "Studentesen",
             18,
             "Akademiet")
# Kan fortsatt bruke medlemmene til Person
print(elev1.fornavn)
elev1.si_hallo()
# Men har nå også et medlem som heter skole!
print(elev1.skole)
```


For å bygge intuisjon om når dette kan bli nyttig:



Det er mye som er møbler, men er alle møbler bord?

En stol er ikke et bord, men begge er  møbler


Da trenger vi kanskje en møbel-klasse og en stol- og bord-klasse som arver fra denne

Selv om begge er laget av tre, har fire ben og selges på Ikea


Her på jobb tenker vi masse på møter.


Webex-, google-, microsoft teams- og zoom-møter har mye til felles

Alle har en start og en slutt og deltakerlister


En grunnleggende møteklasse som de forskjellige møtetypene arver fra kan være lurt!


I favorittdataspillet ditt er det sikkert flere figurer som oppfører seg annerledes.


Kanskje det finnes en felles "figur"-klasse som arves fra?

Da slipper de å programmere alt alle figurer har til felles på nytt!


OBS!🐍

I oppgavene vil dere se
```python
class Arv(Noe):
    pass
```

Dette betyr at klassen `Arv` arver fra klassen `Noe`, men endrer ingenting så den er veldig lik `Noe`.

Dette brukes for å lage et startpunkt for dere, men er ellers ofte en nytteløs ting å gjøre :)
