#note
# Elvárások tárolókkal
- Snapshotok
- Információ életciklus kezelése
# Információ életciklus
- Collection
- Storage
- Maintenance
- Usage
- Cleaning

# Tárolók alapvető elemei
- Operating System
- Filesystem
- Volume Management
- Tárolóeszközök
# Direct Access Storage
- Az állomások és szerverek közvetlen csatlakoznak a diszkekhez
- Logikai kötetkezelő szoftver segít ebben (LVM)
- Hardver/Szoftveres RAID segítségével nagyobb rendelkezésre állás
- Nincs intelligencia
- A szerver/állomás kezeli a fájlrendszer feladatait, és a kötetkezelést
- Előnyök
	- Könnyű konfigurálhatóság
	- SCSI, Fibre Channel köttetés
	- Könnyű bővíthetőség
- Hátrányok
	- Korlátozott méret
	- Erőforrásmegosztás nehéz
	- Egypontos hibaforrás
# Network Access Storage
- LAN Kapcsolja az állomásokat a NAS szerverrel/NAS head-el
- Fájlrendszer, kötetkezelés a NAS szerver feladata
- Kommunikáció kérés az állomástól a fájlra szól
- Fájlmegosztás lehetséges
- Előnyök:
	- Szabványos Ethernet, IP protokoll használat
	- Korlátlan kiterjedés (IP miatt)
	- Optimális teljesítményű fájlkezelés
	- Jobban méretezhető
- Hátrányok:
	- LAN terhelés
	- Tárolóval a NAS fájlkezelő rendelkezik
	- Speciális operációs rendszer
	- Központosított fájlkezelés nem felel meg bizonyos blokk szintű hozzáférést igénylő alkalmazásnak
# Storage Area Network
- Az állomások tároló hálózaton keresztül csatlakoznak a diszk tömbhöz
- Blokkalapú tároló elérési mechanizmus, azaz közvetlen hozzáférnek az adatblokkokhoz a szerverek a tároló hálózaton
- Fájlrendszert állomások/szerverek, NAS, vagy más eszközök adják.
- Állomás látja el a kötetmenedzselést, viszont a RAID-et a tároló látja el.
- Blokk aggregáció feladata oszlik eszköz és állomás között
- Előnyei:
	- Gigabit
	- MAN-méret
	- Jól méretezhető
	- Kapacitás könnyen megosztható szerverek között
- Hátrányai:
	- Fibre Channel Inkompatibilitás
	- Kevés szakember
	- Kettős hálózat
	- Kettős menedzsmentrendszer
## Virtuális SAN
- Alacsony költség
- Magas rendelkezésre állás
- Flexibilis
## Biztonság
- VSAN
- FCAP
- Titkosított adattovábbítás
- Zónázás
- LUN Maszkolás
## Ethernet alapú SAN
- 100Gbps elérhető
- Olcsóbb megoldás
## Fibre Channel SAN
- Optikai csatlakozás
- Topológia alapján
	- Direkt
	- Gyűrű
	- Csomagkapcsolt
- Sebesség
	- Akár 128Gbps-256Gbps
		- Multimódusban maximum 100 méter
		- Monomódusban maximum 500 méter