## Polymorfisme

Et stort og skummelt ord


Men ganske greit konsept!


>> Poly - flere
>
>> morphism - form

Flere former!


Så hva betyr det i kode?


En funksjon med samme navn kan gjøre forskjellige ting


Kodeeksempel:

```Python
class Dyr:
    def snakk(self):
        print("Jeg vet ikke hva jeg er!")

class Hund(Dyr):
    def snakk(self):
        print("Voff")

class Katt(Dyr):
    def snakk(self):
        print("Mjau")
```


```Python
dyreliste = [Hund(), Hund(), Katt(), Hund()]
for dyr in dyreliste:
    dyr.snakk()
```

```bash
➜ ~ python3 dyr.py
Voff
Voff
Mjau
Voff
```


Hver type dyr finner sin riktige funksjon, selv om alle heter `snakk`


Hvis en klasse ikke lager sin egen `snakk`, så brukes forelderens `snakk`

```Python
class Axolotl(Dyr):
    pass
axolotl = Axolotl()
axolotl.snakk()
```

```bash
➜ ~ python3 axolotl.py
Jeg vet ikke hva jeg er!
```


Polymorfisme er en arvet egenskap som barnet har gjort på sin måte.


For eksempel, så kan dere alle snakke

Men dere snakker kanskje ikke helt likt som foreldrene deres
