# ebook
hexagonal sandbox, how modular architecture works in real life with examples

## Spis treści

### Telekomunikacja


```yml
Telekomunikacja:
  IN: Nadawca
  OUT: Odbiorca
  OPERATION:
  DATA:
```


polega na wymianie komunikatów pomiędzy nadawacą i odbiorcą




### tematy

+ "Use camera for facial recognition to unlock screen."
+ "Use camera to take a photo and send it to the recipient"
+ "From the contact list select the recipient and share"




1. Oczekiania (klienta)

2. Wymagania (kooperaxcja: klient + designer)

3. Widok makiety (Designer +  Grafik)

4. Prototyp (Designer + Developer)


a co do elementów, to:  Interface IN -> OUT, DATA -> OPERATION

klient dostaje makietę uproszczoną

developer robi więcej etapów, bo zanim dojdzie do wyswietlenia obrazu to trzeba go wrzucić do pamięci i z pamięci na ekran

developer ma dwa punkty

czyli w sumie 2 linijki w tabeli a nie jedną jaką widzi klient

klient widzi początek i koniec tabelki od developera





1. Expectations:


2. Requirements:


3. Mockup:


4. Definition:

```csv
IN,OUT,OPERATION,DATA
camera,memory,save,image
memory,screen,load,image
```



