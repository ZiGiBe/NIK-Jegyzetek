#note
# Követelmények
- Közel 100%-os rendelkezésre állás
- Automatizált védelem biztonsági fenyegetésekkel szemben
- Flexibilis legyen hálózati adatforgalomban való változásokra
- Folyamatos működőképesség
- Megbízhatóan szállítsa az alkalmazásokat
- Biztonság
- Módosíthatóság
- Egyszerű hibaelháríthatóság
# Kiépítési sorrend
1. Üzleti célok, műszaki követelmények ellenőrzése
2. A célok/követelmények kielégítéséhez szükséges funkciók, szolgáltatások meghatározása
3. Hálózati készenlét felmérése
4. Megoldási, helyszíni átvételi tesztterv létrehozása
5. Projektterv elkészítése
# Megbízható hálózat négy pillére
1. Hibatűrés (Redundancia)
2. Skálázhatóság (Hatékony tervezés)
3. Biztonság
4. Quality of Service
# Architektúrák
1. "Lapos"
2. Hierarchikus
	- Három réteg
		1. Core - Központi réteg
			- Célja a 100%-os üzemidő
			- Maximálja az áteresztőképességet
		2. Distribution réteg
			- Routerek, multilayer switchek
			- Forgalomirányítás, kapcsolás egy rétegben
			- Redundancia, terheléselosztás
			- EIGRP, OSPF
		3. Access réteg
			- Forgalomáramlás szűrése, kezelése
			- Hozzáférés-szabályozás irányelveinek érvényesítése
			- Útvonalak összegzése
			- Központi réteg elszigetelése hibáktól, zavaroktól
			- VLAN
1. Cisco Enterprise
	- Moduláris blokkok
		- Enterprise Campus
		- Server Farm
		- Enterprise Edge
	- Előnyei:
		- Determinisztikus hálózat
		- Egyes modulokat függetlenné tesz, ezzel könnyítve a tervezést
		- Skálázható
# Módszertanok
- Hálózati követelmények meghatározása
- Meglévő hálózat jellemzése
- Topológia, megoldás megtervezése
- WLAN esetén:
	- SSID Broadcast tiltás
	- Erős titkosítás
	- Felhasználói hitelesítés
	- VPN-tunnel
	- Firewall, IDS, IPS használata
# Kiépítési szempontok
- Sávszélesség
- Quality of Service
- Biztonság
- Távoli elérés