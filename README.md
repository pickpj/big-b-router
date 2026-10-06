# big-b-router  
### Offline Anti-ALPR routing and navigation for your phone.  

Ipynb to edit out ALPR exposed roads from PBF files. This can then be converted into an OBF file for use in [OsmAnd](https://osmand.net/).  

<img width="1648" height="762" alt="nav-example" src="https://github.com/user-attachments/assets/97df2186-bf89-4486-8e3d-cd605379f668" />  

---  

Other variations:  
⭐ For those that want weighted routing with penalties. There is now [bbr-weights](https://github.com/pickpj/bbr-weights)  
⭐ There is also the [Comaps branch](https://github.com/pickpj/big-b-router/tree/comaps) for producing a pbf file that works with [Comaps](https://www.comaps.app/) ([repo](https://codeberg.org/comaps/comaps)). Also some tips to get the pbf converted to an mwm and working [here](https://pickpj.github.io/Mapping/custom-routing-maps/comaps.html). It should also work with Organic Maps due to the similarities with Comaps.  
OsmAnd is available for iOS as well, although I have not tested.    


## Finished OBF file demo  

[bigbrouter.webm](https://github.com/user-attachments/assets/72dcea2c-5c7c-4822-8a2c-ff9c2b7ca1ca)  


## Usage  
I wrote a step by step guide showing the whole process. [Link here](https://pickpj.github.io/Mapping/FIock/bigbrouter.html)  
  
TLDR:
- Download env Requirements. Download pbf map data from [geofabrik](https://download.geofabrik.de/) or [other providers](https://wiki.openstreetmap.org/wiki/Planet.osm#Extracts)  
- Prep the pbf data with the pbf-prep.ipynb  
- Process the data with big-b-router.ipynb  
- Plug in the output to OsmAndMapCreator  
- Transfer OBF file to phone and import with OsmAnd  
  
## Requirements  
Tested with (on Oct 5. 26):  
`conda create -n gis-py312 -c conda-forge geopandas folium pyrosm pyosmium notebook ipyleaflet osmium-tool jupyter`  

### cli tool:  
- [osmium-tool](https://osmcode.org/osmium-tool/)  
  -   [AUR link](https://aur.archlinux.org/packages/osmium-tool)  
  -   [conda forge](https://anaconda.org/conda-forge/osmium-tool)  
### python env:  
- notebook  
- geopandas  
- folium  
- pyrosm  
- pyosmium/osmium (pyosmium in conda-forge, but osmium in pypi ; very confusing)  
- ipyleaflet  
- jupyter  

---
### My recommendation for what app to use:  

1. The paid Osmand+ (G-Play) option if you need/want Android Auto  
2. Osmand~ from F-Droid and mounting the phone (Osmand~ has extra features compared to the G-Play version)  
3. Lastly, if you really want Android Auto AND do not want to pay, I would recommend Comaps (G-Play). Although, I should warn that the setup process for comaps is harder and the routing can be suboptimal.  

Comparison matrix:  
Application [🟢Rec]| Free?| Navigation/Re-routing | Works offline | Android Auto| Easy?|   
---|---|---|---|---|---|  
Osmand (G-Play)|✅|✅|✅|❌|✅|  
🟢Osmand+ (G-Play)|❌<sup>1</sup>|✅|✅|✅|✅|  
🟢Osmand~ (F-Droid)|✅|✅|✅|➖<sup>2</sup>|✅|  
🟡Comaps (G-Play)|✅|✅|✅|✅|❌<sup>3</sup>|  
Comaps (F-Droid)|✅|✅|✅|➖<sup>2</sup>|❌<sup>3</sup>|  

1. Osmand+ (Maps+) costs ~15$/year or 70$/once, giving AA/Carplay access (sometimes goes on sale)  
2. It seems like it is possible to enable AA by pretending/faking the app is installed through G-Play. You will likely need a rooted device with Gapps, and to use Kinginstaller. If "rooted" or "Gapps" doesn't make sense to you, then I would advise against doing this.   
3. Comaps uses a different mapgen, which is in the [comaps branch](https://github.com/pickpj/big-b-router/tree/comaps). Getting the [comaps repo](https://codeberg.org/comaps/comaps) setup for map conversion is difficult, but I have [some helpful advice](https://pickpj.github.io/Mapping/custom-routing-maps/comaps.html)  

---  
### Future Ideas:  
* ***Maybe*** scaling up mapgen and distributing map files
---
#### Credits  
* Impossible without OpenStreetMap data & contributors  
* pyosmium / osmium - nothing else worked for editing osm data and keeping/returning it as a pbf  
* OsmAnd and OsmAndMapCreator  
* pyrosm for reading pbfs to geopandas  
---  

![fIock](https://github.com/user-attachments/assets/ee47540e-ec21-40ce-b8b8-590d16af8e4b)

