# gns3-vlan-PC
Eksplatacje - jak zrobić vlan oraz ustawić żeby komputery się komunikowały kiedy są oddzielnych etherswitchach komunikowały
Prosta wymagana konfiguracja: to 2 vpsc podłączone oddzielnie do ethernetswitch router

# Tworzenie vlan
Tworzenie vlan
Wejść w konsole ESW1
żeby stworzyć vlan potrzebuje my wejść w baze danych vlan a więc trzeba wpisać następującą komende 
```vlan database```

następnie trzeba stworzyć naprzykład "vlan 50" - 
```vlan 50```

Żeby komputery się komunikowały i działy prawidłowo trzeba je przypisać ich port do portu gdzie jest przypisany vlan 50 oraz ustawić w miejsce portów którymi routery są połączone tryb trunk 
w moim przypadku routery są na fa1/15

# Podłączanie portów do vlan
Najpierw trzeba wejść w configuracje
```configure terminal```
Lub skrótem
```conf te```

a teraz trzeba wejść w interface

załóżmy że chcemy mieć około 10 portów więc wpisujemy zakres portów
```interface range fastEthernet 1/0 -10```

jeśli chcemy tylko 1 port to
```interface fastEthernet 1/0```

W miejsce zera jest to numer portu
teraz włączamy tryb access żeby przypisać porty do vlan
```switchport mode access```

potem przypisujemy
```switchport access vlan 50```

gotowe
Teraz włączamy tryb trunk na porcie gdzie nasze routery są połączone w moim przypadku będzie to fa1/15

wchodzimy w interface
```interface fastEthernet 1/15```

teraz włączamy trunk
```switchport mode trunk```

- mogą się pokazać jakieś komunikaty ale nie powinny one przeszkodzić

teraz dodajemy port fa1/15 do vlan 50
```switchport trunk allowed vlan add 50```
i gotowe
