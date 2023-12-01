# ebook
hexagonal sandbox, how modular architecture works in real life with examples

+ [INTRO](INTRO.md)


istotne w problematyce tworzenia architektury, jest znalazienie odpowiednich znaczeń i relacji 
w celu uporządkowania zależności i odgraniczenia ich w gotowych do re-użycia kompnentach.

Na tej zasadzie tworzymy połączenia czasownika i rzeczownika jako sieć kompnentów wymieniających między sobą informacje w sposób ustrukturyzowany bez potrzeby głebokiej analizy niezalęnzie od użycia,
gdzyż wzorce działają w każdej implementacji, gdyż są tworem abstrakcyjnym złozonym z konceptów chartakterystycznaych dla słownictwa, rozumienia logicznej przyczyny i skutku a sama implentacja jest techniczna 
i wymaga opisu na innym poziomie, poprzez jezyki programowania.



## Telekomunikacja

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
        THROUGH: Send    # verb/object
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


#### 5. Network of Components

```yml
TeleCommunication:
  FROM: Sender
  TO: Receive
```




## Roles and behaviors



#### 1. Complex Sentence


```yml
TeleCommunication:       # goal
  THROUGH: Exchange      # verb/object
  THE: Message           # object
  FROM:
      Sender:            # object interface
        THROUGH: Send    # verb/object
        THE: Message     # object
  TO:             
      Recipient:         # object interface
        THROUGH: Receive # verb/object
        THE: Message     # object
```


#### 2. Catalog of behaviors


```yml
Exchange Message:     # goal
  ROLE: Provider
  ACTION: Exchange     # verb/object
  OBJECT: Message      # object
  
Send Message:          # goal
  ROLE: Sender
  ACTION: Send       # verb/object
  OBJECT: Message      # object

Receive Message:       # object interface
  ROLE: Recipient
  ACTION: Receive      # verb/object
  OBJECT: Message      # object

Ceate Message:         # object interface
  ROLE: Creator
  ACTION: Create       # verb/object
  OBJECT: Message      # object

Read Message:         # object interface
  ROLE: Reader
  ACTION: Create       # verb/object
  OBJECT: Message      # object
```


#### 3. Network of Roles

```yml
TeleCommunication:
  Provider:
    Sender:
      Creator
    Receiver:
      Reader
```



#### 4. Network of behaviors

```yml
Exchange Message:  
  Send Message:
    Create Message
  Receive Message:
    Read Message
```


## ROLES

```yml
Communicants:
  - Sender
  - Receiver

Correspondent:
  - Creator
  - Reader

```

## OBJECTS

```yml
Message:  
    ACTION:
      - create
      - read
      - delete
      - update

Provider:  
    ACTION:
      - online
      - offline      

Correspondent:
    OBJECT: Content
    ACTION:
      - create
      - read
      - delete
      - update
    

Communicants:
    OBJECT: Message
    ACTION:
      - send
      - receive  
  
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



