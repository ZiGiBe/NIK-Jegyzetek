#note
- Eszközök
	- Tűzfal
	- IDS (Intrusion Detection System)
	- IPS (Intrusion Prevention System)
	- ACL (Access List)
# Rétegek
- Core Layer
	- Proxy tűzfal
	- SSL
	- IDS
- Distribution Layer
	- L3-L4 Tűzfal
- Access Layer
	- Port védelem
	- ARP/DHCP hamisítás védelem
# Tűzfalak
## Csomagszűrő tűzfal
- Szűrés alapjai lehetnek
	- Cél/Forrás IP
	- Protokoll
	- Cél/Forrás port
	- SYN üzenetek
## Stateful tűzfal
- Csomagszűréssel együtt vizsgálja a kiépített kapcsolatot is
# Behatolás észlelő/megelőző rendszerek
- Rendszerek
	- IDS
	- IPS
- A két rendszer közötti különbség
	- Más szenzorokkal dolgoznak
	- Más mintákat használnak azonosításhoz
	- Atomi/összetett mintát kezelnek
# Támadások
## Alapfogalmak
- Fenyegetés: Fenyegetések adatok, és hálózat tekintetében
- Sérülékenység: Gyengepontok a rendszerben
- Exploit: Sérülékenység kihasználása
- Kockázat: Sérülékenység bekövetkezésének valószínűsége
## Támadók fajtái
- White hat: Etikus hacker
- Black hat: Saját haszonszerzésre irányuló hacker
- Grey hat: Nem saját haszonszerzésre irányul
## Támadások típusai
## Felderítéses támadások
- Fő célja az információszerzés
- Végberendezéseket is érint
- Támadások típusai:
	- DNS query-k
	- Pingelés
	- Port scan
## Hozzáférés támadások
- Olyan támadás, ahol a szükséges információ meg van ahhoz, hogy hozzáférjen a támadó a szükséges adatokhoz. A támadó hozzá tud férni akár a konkrét rendszerhez is.
- Ez jelentheti azt is, hogy a rendszer meglévő privilégiumát is felülírhatja a támadó
- Támadások típusai:
	- Jelszó elleni támadás
	- Jelszó hash gyűjtés
	- Bizalmi támadás
	- Port átirányítás
	- Man-in-the-Middle
	- IP/MAC/DHCP Spoofing
- Egyéb elterjed támadások, amik hozzáférést engednek a támadónak:
	- Pretexting
	- Spam
	- Phising
	- Ransomware
	- Baiting
	- Social Engineering
## Szolgáltatás tagadó támadások
- Célja, hogy a szolgáltatás ne szolgálja ki a valódi kéréseket
- Egy változata a DDoS, ami több gép bevonásával akadályozza a szolgáltatást
- Kulcsfogalmak
	- Zombigépek: Támadó gépek
	- Botok: Olyan kártevő, ami megfertőz egy gépet, majd zombigépként használható
	- Botnet: Zombigépek csoportja
# Védelem
- A kockázathoz fel kell mérni, ahol felmérjük hogy:
	- Melyek a védett egységek/értékek
	- Mik a fenyegetések
	- Melyek a sérülékenységek
## Business Policy
- Egy szabályrendszer, ami definiálja a rendszer elfogadható működését
- Tartalmazhat
	- Céges szabályokat
	- Munkavállalói szabályokat
	- Biztonsági szabályokat
### Szabályok
#### Biztonsági szabályok
- Jelszavak
- Karbantartási szabályok
- Felhasználási szabályok
- Azonosítási, hitelesítési szabályok
- Incidenskezelési szabályok
#### BYOD szabályok
- Milyen eszköz használható munkához?
- Milyen eszközzel lehet a hálózatra csatlakozni?
- Milyen külső perifériák engedélyezettek?
- Mely alkalmazások/szolgáltatások futhatnak?