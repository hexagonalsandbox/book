# ebook
hexagonal sandbox, how modular architecture works in real life with examples

+ [INTRO](INTRO.md)


## Spis treści

### Telekomunikacja

#### 1. Sentence

```yml
TeleCommunication:      # goal
  THROUGH: Exchange     # verb/object
  THE: Message          # object
  FROM: Sender          # object interface
  TO: Recipient         # object interface
```

#### 2. Component

```yml
TeleCommunication:   # object, or verb + object
  ACTION: Exchange   # verb
  OBJECT: Message    # object
  IN: Sender         # object interface from
  OUT: Recipient     # object interface to
```


#### 3. Complex Sentence


```yml
TeleCommunication:       # goal
  THROUGH: Exchange      # verb/object
  THE: Message           # object
  FROM:
      Sender:            # object interface
        THROUGH: Create  # verb/object
        THE: Message     # object
  TO:             
      Recipient:         # object interface
        THROUGH: Receive # verb/object
        THE: Message     # object
```

#### 4. Catalog of Components


```yml
TeleCommunication:     # goal
  ACTION: Exchange     # verb/object
  OBJECT: Message      # object
  
Sender:                # goal
  ACTION: Create       # verb/object
  OBJECT: Message      # object

Recipient:             # object interface
  ACTION: Receive      # verb/object
  OBJECT: Message      # object
```





polega na wymianie komunikatów pomiędzy nadawacą i odbiorcą


## Implementacja





```yml
-
  Goal: TeleCommunication:
  OPERATION: Exchange
  DATA: Message
  INTERFACES:
    IN:
        OPERATION: Send
        DATA: Message
    OUT: 
        OPERATION: Receive
        DATA: Message
```


```yml
-
  Goal: Sending Message
  OPERATION: Send
  DATA: Message
  INTERFACES:
    IN:
    OUT:
        OPERATION: Receive
        DATA: Message
```





### tematy

#### "Use camera for facial recognition to unlock screen."

```yml
-
  DO: take a photo
    THROUGH: capture
    THE: image
    FROM: Camera
    TO: Screen
```


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



