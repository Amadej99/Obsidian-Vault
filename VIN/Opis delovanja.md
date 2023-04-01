## Iz česa je sestavljen LIDAR sistem

Sistem LIDAR je sestavljen iz laserja, skenerja in detektorja. 

Kot laser se v LIDAR sistemu uporablja polprevodniški laser oz. laserska dioda. Podobni laserji se uporabljajo v laserskih tiskalnikih ali CD/DVD predvajalnikih le, da je laser, ki se uporablja v LIDAR sistemih bistveno močnejši. Različno namenski LIDAR sistemi oddajajo različno svetlobo. 
* V avtomobilski industriji se uporablja skoraj infrardeči laser valovne dolžine 900 - 1100 nm
* Podvodni sistemi uporabljajo zeleni laser valovne dolžine 530 nm
Splošno rečeno uporabljajo LIDAR sistemi z večjim dometom laserske žarke višje valovne dolžine.
Tako npr. ima najnovejši avtomobil laser s valovno dolžino 1550 nm, skenira pa lahko do razdalje 200m, v primerjavi z laserjem, ki deluje pri 905 nm, skenira pa "samo" do 40m.

Detektor v LIDAR sistemu je neke vrste fotoelektrična celica, ki je oblikovana za maksimalno občutljivost na svetlobo take valovne dožine kot jo uporablja laser. Za različne vrste LIDAR sistemov se uporabljajo različne vrste detektorjev. Sistemi s kratkim dometom uporabljajo preproste silicijeve  fotodiode. Sistemi z dolgim dometom uporabljajo t.i. avalanche fotodiode (APD), ki delujejo podobno kot Geigerjev števec in spremenijo foton svetlobe v plaz elektronov, ki ga lahko izmerimo.

Skener je tipično sestavljen iz ogledala, ki usmerja laserski žarek in s tem omogoča pokritje širokega območja. S skenerjem upravlja motor, ki rotira ogledalo s konstantno hitrostjo oz. z specifičnim vzorcem. Ko se ogledalo rotira usmerja žarek v različna območja okolja. Nekateri LIDAR sistemi uporabljajo več skenerjev oz. ogledal, da pokrijejo še širše območje ali pa povečajo gostoto točk. S tem tudi izboljšajo natančnost meritev.
![[lidar-laser-scanning-mirror.gif]]

![[hornbeck-dlp-micro-mirror.png]]


## Opis delovanja

Laserski žarek se odbije od cilja in se vrne do skenerja. Skener nato to odsevano svetlobo oz. laserski žarek zazna in ga pretvori v električni signal. Veliko LIDAR sistemov lahko ta postopek ponovi tudi do milijonkrat na sekundo. 

Za merjenje razdalje do cilja se preprosto uporablja princip časa letenja, saj naš laser oddaja impulz z znano frekvenco. Čas je torej neposredno sorazmeren z razdaljo med sistemom LIDAR in ciljem.
Z vsakim žarkom, ki se vrne do skenerja se ustvari 3D vizualizacija, ki jo imenujemo oblak točk. S pomočjo kombiniranja teh točk z ostalimi podatki, ki jih pridobimo tekom skeniranja, se ustvari natančna, tri-dimenzionalna interpretacija našega cilja.

Tako se LIDAR lahko uporabi v kombinaciji z ostalimi tehnologijami ter podatki.
* Posnetki iz letal se kombinirajo z podatki iz sistema GPS
* Samovozeči avtomobili uporabljajo še GPS, senzorje za hitrost in pospešek

![[8aqnshh5.bmp]]