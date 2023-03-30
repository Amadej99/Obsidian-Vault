*light detection and ranging*


### ● Predstavitev naprave
*opis, slika, razvoj*

- Na kratko kako deluje, kaksna analogija
- Par slik ki prikazujejo uporabo (na autonomus vozilih, skeniranje terena etc)


### ● Opis delovanja
- Podroben opis delovanja
- lahko se hkrati malo navezemo na kaksne tehnologije

### ● Arhitektura in tehnologije
- bolj podroben opis uporabljenih tehnologij (senzor, računalnik, 
	komunikacijski protokoli med njima)
- Potrebna zmogljivost računalnika, kolko memorya rabi, computing powerja 
- čipi na računalniku, 

### ● Nekaj use caseov, kako deluje pri vsakem
- land surveying (geodetstvo)
- v avtu zaznavanje okolice (kalibracija lidarja in kamere)
- uporaba kot kamera z podatki o globini (Onsemi) 

### ● Kako se programsko povežemo z napravo
- V katerem jeziku je napisan os? (probably C alpa assembly)
-  če majo senzorji kakšen api

### Viri:
lidar basics, how it works:
- https://en.wikipedia.org/wiki/Lidar
- https://www.explainthatstuff.com/lidar.html
- https://www.neonscience.org/resources/learning-hub/tutorials/lidar-basics
- https://www.mosaic51.com/technology/what-is-lidar-how-does-it-work-and-what-is-it-used-for/
- https://www.synopsys.com/glossary/what-is-lidar.html

Usecases:
- https://blog.lidarnews.com/forest-structural-complexity-studied-with-lidar/

LIdar and camera calibration and autonomus vehicles:
- https://www.ti.com/lit/wp/slyy150a/slyy150a.pdf?ts=1679321060411&ref_url=https%253A%252F%252Fwww.google.com%252F
- https://www.ti.com/lit/wp/slyy150a/slyy150a.pdf?ts=1679321060411&ref_url=https%253A%252F%252Fwww.google.com%252F
- https://www.mathworks.com/help/lidar/ug/lidar-and-camera-calibration.html
- https://ouster.com/blog/the-camera-is-in-the-lidar/

api:
- https://www.embedded.com/open-lidar-api-aims-to-accelerate-software-defined-lidar-adoption/

arduino projects:
- https://www.engineersgarage.com/how-to-use-a-lidar-sensor-with-arduino/
- https://www.instructables.com/How-to-Use-the-RPLIDAR-360-Laser-Scanner-With-Ardu/
- https://how2electronics.com/how-to-use-tfmini-s-lidar-distance-sensor-with-arduino/

Datasheets to gain info about components:
- https://cdn.sparkfun.com/datasheets/Sensors/Proximity/LIDAR-Lite-Data-Sheet.pdf
- https://www.lidarsensor.nl/wp-content/uploads/2020/11/LiDAR-Sensor-datasheet-SF23-ENG.pdf
- https://www.mouser.com/datasheet/2/612/Intel_RealSense_LiDAR_L515_Datasheet_Rev002-1713847.pdf
- https://globalgpssystems.com/wp-content/uploads/2021/06/N301-protocal-Manual-V3.0.pdf
- https://bucket-download.slamtec.com/be76242eb19f992b78e1ddd22ebbeb086337e7c2/SLAMTEC_rplidarkit_protocol_S2E_v1.0_en.pdf