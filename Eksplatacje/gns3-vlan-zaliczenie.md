# gns3 ostatnia kartkówka

naszym celem jest:

Skonfiguruj switch 1 i switch 2:

1.Zmień nazwę hosta na trunk1_nazwisko i trunk2_nazwisko

- ustaw porty fa1/0 -14 w trybie access
- interfejs fa1/15 ustaw w trybie trunk

2.Utwórz 2 vlany
- vlan 20 name sprzedawcy_nazwisko i przypisz na portach fa 1/0 - 7
- vlan 30 name kupujący_nazwisko i przypisz na portach fa 1/8 - 14

3. Na portach podłącz po dwa komputery z adresacją
- vlan 20 20.20.20.0/24
- vlan 30 30.30.30.0/24
- na interfejs trunk ustaw możliwość komunikacji dla vlan 20 i vlan 30

4. Potwierdz ping poprawność komunikacji w vlan na switch 1 i pomiędzy switch 2

5. Utwórz plik trunk_nazwisko.txt i skopiuj konfigurację poleceniem sh running-config oraz pingi

6. Opisz porty trunk trunk_nazwa switcha
