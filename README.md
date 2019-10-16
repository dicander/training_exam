Träningstentan förklarar tentans 7 lärandemål genom exempeltal plockade från gamla tentor.

# Hårdvara och operativsystem
Lärandemål: beskriva delarna av och terminologin för ett datorsystem översiktligt: CPU, minne, operativsystem och användargränssnitt.

# Beskriva källkod
Lärandemål: beskriva källkoden till ett dataprogram med rätt terminologi.

(6)
Dessa symboler:
```
&   |   ^   <   ==
```
är exempel på något som i Python3 kallas för:
```
(A) identifierare
(B) avgränsare (delimiter på engelska)
(C) operatorer
(D) literaler
(E) nyckelord (keywords)
```

# Datatyper
Lärandemålet: beskriva och tillämpa grundläggande datatyper, klasser och typkonverteringar.
(11)

# Uttryck och flödeskontroll
Lärandemålet: beskriva, tillämpa och felsöka flödeskontroll samt logiska och aritmetiska uttryck.

(16)
Byt ut kommentaren i koden nedan mot ett svarsalternativ i taget. Vilket/vilka alter-nativ får detta Python3-program att exekvera raden med print?
```
def main():
    # Här ska svaret stoppas in i koden.
    if ( not a or b) and (not b or c):
        print(a,b,c)


main()
```
```
(A) a, b, c = True, True, True
(B) a, b, c = True, True, False
(C) a, b, c = True, False, True
(D) a, b, c = True, False, False
(E) a, b, c = False, True, True
(F) a, b, c = False, True, False
(G) a, b, c = False, False, True
(H) a, b, c = False, False, False
(I) Inget av ovanstående alternativ.
```

(17)
Tre variabler; a, b och c pekar var och en på antingen True eller False. Ge a, b och cvärden som gör att det logiska uttrycket nedan blir True. Om det finns flera lösningarså räcker en av dem (vilken som helst) för full poäng. Parenteserna kring not-uttryckenbehövs inte tekniskt sett, men de gör uttrycket lättare att läsa.
```
(a or (not b)) and (b or (not c)) and ((not b) or (not c)) \
and ((not a) or b) and (a or b)
```

(18)
Vad skriver nedanstående program ut?
```
dygder = ["rättvisa", "klokhet", "tapperhet", "måttfullhet"]
print(dygder[1], dygder[-1])
```

# Räckvidd och livslängd
Lärandemålet: beskriva en variabels räckvidd och livslängd.
(21)
```
def mystery(a, b):
    a, b = b, a
    print(a, b, end = " ")


def main():
    a, b = 42,13
    mystery(a, b)
    print(a, b)

main()
```
```
(A) 13 42 13 42
(B) 13 13 13 13
(C) 42 42 42 42
(D) 13 42 42 13
(E) 42 13 13 42
(F) 42 13 42 13
```
(19) Vad skriver detta program ut?
```
def mystery(dygder):
    dygder[1] = dygder[2]

def main():
    dygder = ["rättvisa", "tapperhet", "klokhet", "måttfullhet"]
    mystery(dygder)
    for x in dygder:
        print(x, end="")
        print()

    main()
```
```
(A) tapperhet rättvisa klokhet måttfullhet
(B) tapperhet tapperhet klokhet måttfullhet
(C) rättvisa klokhet tapperhet måttfullhet
(D) rättvisa klokhet klokhet måttfullhet
(E) klokhet måttfullhet rättvisa tapperhet
```
(20)
Vad skriver följande Python3-program ut?
```
def mystery(name):
    name += " " + "Yousafzai"
    print(name, end = " ")


def main():
    name = "Malala"
    mystery(name)
    print(name)


main()
```
```
(A) Malala Yousafzai Malala
(B) Malala Yousafzai Malala Yousafzai
(C) Yousafzai Malala
(D) Malala Yousafzai
(E) Malala Yousafzai Yousafzai
```

Vad skriver programmet nedan ut?
```
def mystery(name):
    name += " Blomgren"

def main():
    name = "Nicole"
    mystery(name)
    print(name)


main()
```
# Lådor och pilar
Lärandemål: grafiskt beskriva kopplingen mellan variabelnamn, typer och data.
På var och en av nedanstående uppgifter behöver du rita en bild över minnet
vid en viss position under programmets körning. Du behöver ha med:
1. Lådor för globala och lokala variabler.
2. Se till att pilarna har spetsar och inte bara är streck.
3. Referensräkning för alla lådor som är utpekade av pilar, utom heltal n där
-5 <= n <= 256 samt objekten None, True och False.
4. Ta med alla objekt som har existerat under programmets körning. Om det är
möjligt att skräpsamlaren (the garbage colllector) har tagit bort det, låt det
stå kvar men rita en pil från skräpsamlaren till objektet som ska tas bort och uppdatera referensräkningen från objekt som pekas ut av det snart döda objektet.
(26)

(27)
Rita ett låd- och pildiagram över minnet efter att följande rad har körts:
```
first = destroy_element(first, 2)
```
...i programmet nedan:
```
class Node:
    def __init__(self, value, following):
        self.value = value
        self.following = following


def print_values(first):
    temp = first
    while temp:
        print(temp.value)
        temp = temp.following


def create_list(size):
    first = Node(size, None)
    for i in range(size-1, 0, -1):
        first = Node(i, first)
    return first


def destroy_element(first, index):
    """returns the first element where index has been destroyed"""
    if index == 0:
        return first.following
    answer = first #we will change this variable
    for i in range(index-1):
        first = first.following
    following_following = first.following.following
    first.following = following_following
    return answer


def main():
    first = create_list(4)
    print_values(first)
    first = destroy_element(first, 2)
    print_values(first)


if __name__ == '__main__':
    main()
```
(28)
Rita en minnesbild med låd- och pildiagram för hur det ser ut i minnet då körningen når den kommenterade raden. Om flera lådor ligger i samma scope (scope kallas iblandräckviddpå svenska), rita dem i samma rektangel/rektanglar.
```
class Person:
    """A person with name and age."""
    def __init__(self, name, age):
        self.name = name
        self.age = age


    def birthday(p):
        p.age += 1
        # Låd- och pildiagram här.


    def main():
        director = Person("Stephen Spielberg", 71)
        birthday(director)


main()
```
(29)
Rita en minnesbild med låd och pildiagram för hur det ser ut när allt innan den kom-menterade raden har körts.
```
happy = 2018
new = happy
year = newhappy += 1
# Låd- och pildiagram här.
```
(30)
Rita en minnesbild med låd- och pildiagram för hur det ser ut då körningen når den kommenterade raden.
```
class Item:
    """A singly linked list."""
    def __init__(self, value=None, next=None):
        self.value = value
        self.next = next


    def main():
        first = Item()
        first.next = Item()
        first.next.next = Item()
        first.next = first.next.next
        # Rita hur minnet ser ut här


main()
```
[Facit med bild](https://github.com/dicander/box_arrow_diagram/blob/master/facit.md )

# Rekursion
Lärandemål: Felsöka, och med rätt terminologi beskriva rekursiva algoritmer.

(31)
Vilket/Vilka alternativ beskriver vad detta Python3-program gör?
```
def mystery():
    mystery()
    print("Rekursion")


mystery()
```

(A) Det skriver “Rekursion” exakt en gång.
(B) Raden med print körs inte en enda gång.
(C) Det skriver “Rekursion” om och om igen tills någon slår av det.
(D) Det kraschar.
(E) Det skriver “Rekursion” färre än 100 gånger och avslutas sedan utan att krascha.
(F) Inget av ovanstående alternativ.

(32)
Vilket/vilka påståenden om rekursioner stämmer?
```
(A) Det finns alltid ett och bara ett basfall för en rekursion.
(B) Den del av koden som utgör ett basfall innehåller oftast ett eller flera rekursivaanrop.
(C) Ett rekursivt anrop bör ha andra argument än de argument som funktionen anro-pades med.
(D) Om bara argumenten till det rekursiva anropet är annorlunda än de argument somfunktionen anropades med så kommer rekursionen till sist att avslutas utan att detblir recursion error.
```
(33)
(34)
(35)
