*light detection and ranging*


# <span style="color:#9e14da">● Predstavitev naprave </span>
*opis, slika, razvoj*

- Na kratko kako deluje, kaksna analogija
- Par slik ki prikazujejo uporabo (na autonomus vozilih, skeniranje terena etc)


# <span style="color:#9e14da">● Opis delovanja</span>
- Podroben opis delovanja
Delovanje pri 
- lahko se hkrati malo navezemo na kaksne tehnologije


Podoben princip kot pri radarju in sonarju. LIDAR senzor proži žarek svetlobe 
in meri njegov odboj (čas )



# <span style="color:#9e14da">● Arhitektura in tehnologije</span>


- *bolj podroben opis uporabljenih tehnologij (senzor, računalnik, 
	komunikacijski protokoli med njima)*
- *Potrebna zmogljivost računalnika, kolko memorya rabi, computing powerja* 
- *čipi na računalniku,* 

!!!!!! Tipi lidarja:
- **By fonctunality:**
	- Terrestrial 
	- Mobile
	- Static
	- Topographic
	- Bathymetric
	- Airborne
- **By application:**
	- DIAL
	- Wind
	- Raman, HSRL
	- Takeaway

#### !!!!!!!!!!!! Komponente LIDAR-ja
- oddajnik (laser)
- sprejemnik (fotoelektični senzor)
- računalnik
- števci

kako so komponente povezane med sabo 

Da zgradimo lidar napravo, potrebujemo laser oz. nek vir svetlobe in sprejemnik,
ki sprejme odboj.
Sprejemnik vsebuje fotoelekrične celice *(explain photoelectricity a bit)*

# <span style="color:#9e14da"> ● Usecases</span>
- land surveying (geodetstvo)
- seafloor measuring
- 3d model
- v avtu zaznavanje okolice (kalibracija lidarja in kamere)
- uporaba kot kamera z podatki o globini (Onsemi) 

# <span style="color:#9e14da"> ● Kako se programsko povežemo z napravo </span>
- V katerem jeziku je napisan os? (probably C alpa assembly)
-  če majo senzorji kakšen api

### Viri:

lidar basics, how it works:
- https://en.wikipedia.org/wiki/Lidar
- https://www.explainthatstuff.com/lidar.html
- https://www.neonscience.org/resources/learning-hub/tutorials/lidar-basics
- https://www.mosaic51.com/technology/what-is-lidar-how-does-it-work-and-what-is-it-used-for/
- https://www.synopsys.com/glossary/what-is-lidar.html
- https://lidarradar.com/category/info/lidar-info

Usecases:
- https://blog.lidarnews.com/forest-structural-complexity-studied-with-lidar/

Arch:
- http://home.ustc.edu.cn/~522hyl/%B2%CE%BF%BC%CE%C4%CF%D7/UCS%BD%CC%B3%CC/Lecture37.pdf
- https://electricalfundablog.com/lidar-light-detection-and-ranging-types-architecture/

LIdar and camera calibration and autonomus vehicles:
- https://www.ti.com/lit/wp/slyy150a/slyy150a.pdf?ts=1679321060411&ref_url=https%253A%252F%252Fwww.google.com%252F
- https://www.mathworks.com/help/lidar/ug/lidar-and-camera-calibration.html
- https://ouster.com/blog/the-camera-is-in-the-lidar/

api:
- https://www.embedded.com/open-lidar-api-aims-to-accelerate-software-defined-lidar-adoption/

arduino projects:
- https://www.engineersgarage.com/how-to-use-a-lidar-sensor-with-arduino/
- https://www.instructables.com/How-to-Use-the-RPLIDAR-360-Laser-Scanner-With-Ardu/
- https://how2electronics.com/how-to-use-tfmini-s-lidar-distance-sensor-with-arduino/

Datasheets to gain info about components, protocols etc comonly used:
- https://cdn.sparkfun.com/datasheets/Sensors/Proximity/LIDAR-Lite-Data-Sheet.pdf
- https://www.lidarsensor.nl/wp-content/uploads/2020/11/LiDAR-Sensor-datasheet-SF23-ENG.pdf
- https://www.mouser.com/datasheet/2/612/Intel_RealSense_LiDAR_L515_Datasheet_Rev002-1713847.pdf
- https://globalgpssystems.com/wp-content/uploads/2021/06/N301-protocal-Manual-V3.0.pdf
- https://bucket-download.slamtec.com/be76242eb19f992b78e1ddd22ebbeb086337e7c2/SLAMTEC_rplidarkit_protocol_S2E_v1.0_en.pdf