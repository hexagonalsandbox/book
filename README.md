# ebook
hexagonal sandbox, how modular architecture works in real life with examples

+ [INTRO](INTRO.md)
+ [1](1.md)
+ [2](2.md)


## 1. Connection

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

#### 3. Behaviors







## 2. Message


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


#### 2. Catalog of Components


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


#### 3. Network of Components

```yml
TeleCommunication:
  FROM: Sender
  TO: Receive
```


#### 4. Relations

```yml
Exchange Message:  
  Send Message
  Receive Message
```


#### 5. Layers

```yml
Network:
  Message    
```




## 3. Content


#### 1. Complex Sentence


```yml
TeleCommunication:           # goal
  THROUGH: Exchange          # verb/object
  THE: Message               # object
  FROM:
      Sender:                # object interface
        WHICH: Sends         # verb/object
        THE: Message         # object
        FROM:
          Creator:           # object interface
            WHICH: Creates   # verb/object
            THE: Content     # object
  TO:             
      Recipient:             # object interface
        WHICH: Receives      # verb/object
        THE: Message         # object
        TO:
          Reader:            # object interface
            WHICH: Reads     # verb/object
            THE: Content     # object
```


#### 2. Object layers

```yml
Network:
  Message:
    Content
```


### Behaviors

#### 1. Catalog


```yml
Exchange Message:      # goal
  ROLE: Provider
  ACTION: Exchange     # verb/object
  OBJECT: Message      # object
  
Send Message:          # goal
  ROLE: Sender
  ACTION: Send         # verb/object
  OBJECT: Message      # object

Receive Message:       # object interface
  ROLE: Recipient
  ACTION: Receive      # verb/object
  OBJECT: Message      # object

Create Content:        # object interface
  ROLE: Creator
  ACTION: Create       # verb/object
  OBJECT: Content      # object

Read Content:          # object interface
  ROLE: Reader
  ACTION: Read         # verb/object
  OBJECT: Content      # object
```


#### 2. Relations

```yml
Exchange Message:  
  Send Message:
    Create Content
  Receive Message:
    Read Content
```



### Roles

#### 1. Relations

```yml
TeleCommunication:
  Provider:
    Sender:
      Creator
    Receiver:
      Reader
```


#### 2. Groups

```yml
Communicants:
  - Sender
  - Receiver

Correspondent:
  - Creator
  - Reader
```


#### 3. Layers


```yml
Provider:
  - Communicants
    - Correspondent
```






## OBJECTS

```yml
Connection:  
    ACTION:
      - connect
      - disconnect      


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








