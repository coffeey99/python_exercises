
```powershell
print('''#   ___                              _    ___                       _           
#  | _ \__ _ _______ __ _____ _ _ __| |  / __|___ _ _  ___ _ _ __ _| |_ ___ _ _ 
#  |  _/ _` (_-<_-< V  V / _ \ '_/ _` | | (_ / -_) ' \/ -_) '_/ _` |  _/ _ \ '_|
#  |_| \__,_/__/__/\_/\_/\___/_| \__,_|  \___\___|_||_\___|_| \__,_|\__\___/_|  
# # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # #                                                                            
''')
# Password Generator

# Erstellen Sie ein Programm, das ein Passwort für sie generiert.
# Es soll dabei nach der Anzahl der Buchstaben,
# der Anzahl der Symbole
# und der Anzahl der Ziffern fragen, die in dem Passwort enthalten sein sollen.
# Das Programm wählt dann zufällig die entsprechenden Zeichen aus den zugehörigen Listen aus
# und kombiniert diese zu einem Passwort

import random
letters = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z', 'A', 'B', 'C', 'D', 'E', 'F', 'G', 'H', 'I', 'J', 'K', 'L', 'M', 'N', 'O', 'P', 'Q', 'R', 'S', 'T', 'U', 'V', 'W', 'X', 'Y', 'Z']
numbers = ['0', '1', '2', '3', '4', '5', '6', '7', '8', '9']
symbols = ['!', '#', '$', '%', '&', '(', ')', '*', '+']

# print("Welcome to the PyPassword Generator")
# nr_letters= int(input("How many letters would you like in your password?\n")) 
# nr_symbols = int(input(f"How many symbols would you like?\n"))
# nr_numbers = int(input(f"How many numbers would you like?\n"))

nr_password = 16

# Schwierigkeitsgrad: Normal - Keine Zufällige Anordnung:
# -> 4 Buchstaben, 2 Symbole, 2 Ziffern = JduE&!91

# Schwierigkeitsgrad: Schwer - Zufällige Anordnung aller Zeichen:
# -> 4 Buchstaben, 2 Symbole, 2 Ziffern = g^2jk8&P
# Frage den Benutzer, weiviele wieviele Buchstaben, Zahlen und Sonderzeichen das Passwort haben soll
# Entnehmen x Stellen von Buchstaben, y Stellen von Zahlen und z Stellen von sonderzeichen
# Auswahl der Elemente soll zufällig sein, nutze random.choices für Mehrfachauswahl
# In einer Variable alle Ausgaben zusammenführuen und wieder vermischen mit Hilfe von random.shuffle
# Das Ergebnis noch zusammenführen mit Hilfe von .join
# Gib das fertige Passwort aus

nr_letters = random.randint(6, 7)
nr_numbers = random.randint(6, 7)
nr_symbols = nr_password - (nr_letters + nr_numbers)

pass_letters = random.choices(letters, k = nr_letters)
pass_numbers = random.choices(numbers , k = nr_numbers)
pass_symbols = random.choices(symbols, k = nr_symbols)
# print(pass_letters, pass_numbers, pass_symbols)

password = pass_letters + pass_numbers + pass_symbols
random.shuffle(password)


password = "".join(password) # ohne join sieht das Ergebnis so aus: ['9', 'u', '8', '6', '$', '$', 'V', '%', '$', 'q', 'b', '2', 'k', '+', '7']
# print(password, sep="") # Ergebnis z.B. ['$', '$', '*', '8', '3', 'H', 't', '$', '#', '9', 'N', 'B', 'N', '8', '3']
print(password)
input()


```
