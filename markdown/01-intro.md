## Objektorientert Programmering med Python


### Joakim Lier, Cisco Systems Norway

- Jobber som blant annet software engineer<!-- .element: class="fragment" -->
- Veldig god til å si ja<!-- .element: class="fragment" -->
- Studerte Informatikk ved UiO<!-- .element: class="fragment" -->
- Og så datateknologi ved NTNU<!-- .element: class="fragment" -->
- Drev mye med high performance computing<!-- .element: class="fragment" -->
- og programmeringsspråk<!-- .element: class="fragment" -->


💖Programmeringsspråk💖


# Plan for dagen!

> Zero to hero

Vi skal jobbe oss opp fra det grunnleggende og opp til å kanskje løse noen ekte problemer!


# Python🐍

Vi skal bruke python som språk for å lære om Objektorientert programmering (OOP).

Vi skal ikke lære python, så jeg antar at dere kan det

> Hvis det er noe dere ikke forstår, så bare spør!


Detaljer som kun gjelder python er markert med 🐍


# Quiz!

```python
a = 2
b = 4
c = a + b
print(c)
```
Note: variabler og funksjonskall


# Quiz!

```python
liste = [1]
liste.append(12)
liste.append('b')

for element in liste:
    if element == 1:
        continue
    else:
        break
```
Note: løkker, ifsetninger og lister


# Quiz!
```python
def business(important, stuff):
    return {important: stuff}

print(business("jobb","cisco"))
```
Note: funksjoner og dictionaries


# Quiz!
```python
a = 3
assert a == 2, f"A burde vært 2, men er {a}"
```
Note: Både assert OG f-strenger
