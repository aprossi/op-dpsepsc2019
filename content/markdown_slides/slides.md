### Why storymaps?

<small>

* Storymaps are just map-based storytelling

* Potential use cases:
  * Display/explore data variety across planetary surfaces
  * Describe through space and time nature of surface materials
  * Describe the (geologic) mapping process
  * Visualise surface change
  * Exemplify surface units at discrete type-locations
  * ...

</small>



### Planmap needs

<small>

Several implementations exist (e.g. [ESRI Storymaps](https://storymaps.arcgis.com)). We went for one that fits our specific needs and is easy to modify/expand.

* Describe surface geologic units, setting
* Guide through the steps of rover-based geologic exploration
* Describe features of mapped surface units through map visualisation, text, image/video media

</small>



### The current setup

<small>

* Storymaps arranged in chapters (stops)
* Each chapter can have an arbitrary number of loaded loaded layers
* Text, media, videos embedded for each chapter
* Each chapter has steps, i.e. to build animations

<small>



### Data

<small>

One can load arbitrary layers (using [Leaflet](https://leafletjs.com)). Default backgrounds are  basemaps from OpenPlanetaryMap:

* Backgrounds/basemaps (e.g. OPM Mars, Moon, Mercury basemaps)
* Raster Layers (TMS, WMS, etc.)
* Vector layers (geojson, or via WMS, or alike), including
  * markers (points)

</small>



### Examples

Using [OpenPlanetaryMap](https://www.openplanetary.org/opm) as basemaps, so far examples on Mars, the Moon, Mercury:



<img src="content/images/sm_mars.jpg">



<img src="content/images/sm_mercury.jpg">



<img src="content/images/sm_moon.jpg">



### The storymap json

<small>
e.g. <a href="https://github.com/planmap-eu/storymaps/blob/master/storymap_data/mars/gale_storymap_data.json">Gale json</a>
</small>

```
{
  "storymap_title": "Gale crater",
  "Authors": "Gwénaël Caravaca, et al.",
  "planmap_id": "",
  "publication": "",
  "basemap": {
    "url": "https://cartocdn-gusc.global.ssl.fastly.net/opmbuilder/api/v1/map/named/opm-mars-basemap-v0-1/0,1,2,3,4/{z}/{x}/{y}.png",
    "options": {
      "crs": "L.CRS.EPSG3857",
      "maxNativeZoom": 9,
      "tms": "false",
      "autoZIndex": "true",
      "attribution": "<a href='https://github.com/openplanetary/opm/wiki/OPM-Basemaps' target='_blank'>OpenPlanetaryMap</a>"
    }
  },    
  "chapters": [{
      "chapter_title":"Chapter 1",
      "chapter_id":"1",      
      "steps": [{
        "title": "Why mapping Mars today?",
        "text": "Looking for the geological past of Mars is important for us for several reasons: understand what happens on Mars, and how this planet differs from ours? Did Life emerge at its surface, and if yes, for how long? Are Life-compliant conditions still present somewhere on Mars? And of course, to prepare future manned exploration missions: where to land safely and make the most science? That’s where geological mapping comes into play",
        "media": [{
          "path": "",
          "type": "",
          "caption": "",
          "stoptime": ""
        }],
        "loaded_layers": [{
            "order": "",
            "path": "",
            "type": "",
            "credits": ""
        }],        
        "view": {
          "extent": [-180, -90, 180, 90],
          "marker": ""
        }
      }]
    },{
      "chapter_title":"Chapter 2",
      "chapter_id":"2",      
      "steps": [{
        "title": "Historic mapping",
        "text": "We tried to map the surface of Mars for quite a long time, trying and figuring out what this world could look like: Is it like our Earth? Do other living beings populate it? First maps were drawn during the 19th century using direct observation with telescopes by famous astronomers Sciaparelli, Flammarion or Antoniadi. Today, our quest for the geological past of Mars continues, on a much finer scale.",
        "loaded_layers": [{
            "order": "",
            "path": "",
            "type": "",
            "credits": ""
        }],        
        "media": [{
          "path": "stories/mars/gale/media/chapter_02/schiapparelli_1879.jpg",
          "type": "image/jpeg",
          "caption": "One of the first map of Mars, drawn in 1879 by Italian astronomer G. Schiaparelli (1881)",
          "stoptime": "10s"
          },{
          "path": "stories/mars/gale/media/chapter_02/flammarion_antoniadi_1900.jpg",
          "type": "image/jpeg",
          "caption": "French astronomers Flammarion and Antoniadi refined the map of Mars by 1900 (Antoniadi & Flammarion, 1901)",
          "stoptime": "10s"
          },{
          "path": "stories/mars/gale/media/chapter_02/antoniadi_1910.jpg",
          "type": "image/jpeg",
          "caption": "This 1910 map of Mars by Antoniadi seems approximative by today's standards, but already features famous name of the Red Planet like Hellas, Argyre or Elysium (Antoniadi in Touchet, 1910)",
          "stoptime": "10s"
        }],
        "view": {
          "extent": [-180, -90, 180, 90],
          "marker": ""
        }
      }]
    },{
      "chapter_title":"Chapter 3",
      "chapter_id":"3",      
      "steps": [{
        "title": "Gale crater",
        "text": "Gale Crater is situated near the Martian equator. Produced by an impact some 3.7 billion years ago, this crater has known a long story since then, hosting varied environments that changed through time. We study it because it may have supported Life-compliant conditions at one point. Basic facts - Diameter: 154 km - Depth: ~3000 m - Age: ~3.8/3.6 Ga - Toponym source: Walter Frederick Gale.",
        "media": [{
          "path": "stories/mars/gale/media/chapter_03/gale.jpg",
          "type": "image/jpeg",
          "caption": "PIA15687 Source: NASA/JPL-Caltech/ESA/DLR/ FU Berlin/MSSS",
          "stoptime": ""
        }],
        "loaded_layers": [{
          "order": "1",
          "path": "stories/mars/gale/maps/murray-lab_ctx-mosaic_gale_3857",
          "type": "tms",
          "credits": "CTX mosaic - Calthech/Murray Lab"
        }],
        "view": {
          "extent": [135, -8, 143, 0],
          "marker": ""
        }
      }]
    },{
      "chapter_title":"Chapter 4",
      "chapter_id":"4",      
      "steps": [{
        "title": "Orbital mapping of Gale plains",
        "text": "Orbital observations give us a very precise view of the surface, its composition and therefore its history. Thus, we can differentiate what we call “orbital facies”: a series of characteristics that define a terrain and tells us more about its formation and evolution through time. For example, in red, the cratered surface are the oldest terrains, having suffered heavy meteoritic bombardments. In khaki, the most recent terrains represent active dune fields, showing natural aeolian processes similar to those on Earth are happening at this very moment on Mars.",
        "media": [{
          "path": "stories/mars/gale/media/chapter_04/grotzinger_orbita_facies_map_legend.png",
          "type": "image/png",
          "caption": "Orbital facies of the Gale Crater by Grotzinger et al (2014)",
          "stoptime": ""
        }],
        "loaded_layers": [{
          "order": "1",
          "path": "stories/mars/gale/maps/grotzinger_orbital_facies_map.geojson",
          "type": "geojson",
          "credits": "Orbital facies or \"geomorphological\" map of the Gale Crater by Grotzinger et al  (2014)"
          },{
          "order": "2",
          "path": "stories/mars/gale/maps/gale_msl_area_3857",
          "type": "tms",
          "credits": "NASA MRO HiRISE/NASA/JPL/University of Arizona"
        }],
        "view": {
          "extent": [135, -8, 143, 0],
          "marker": ""
        }
      }]
    },{
      "chapter_title":"Chapter 5",
      "chapter_id":"5",      
      "steps": [{
        "title": "A Martian geologist: Curiosity",
        "text": "Orbital data are key to our work, but nothing can replace the ground truth. That’s why we sent Mars Science Laboratory rover Curiosity on Mars. Curiosity is a true field geologist. Equipped with high-resolution cameras, microscopes and an entire geochemical lab, this rover allows us to remotely study the terrains encountered in Gale Crater. Using its data, we can learn what kind of rocks are present in Gale, their exact chemical composition or their structures. All these information are important for us understand the paleoenvironmental conditions which they were deposited under, billions of years ago.",
        "media": [{
          "path": "stories/mars/gale/media/chapter_05/Curiosity_static.glb",
          "type": "model/gltf-binary",
          "caption": "3D mesh by NASA/JPL-Caltech",
          "stoptime": ""
        }],
        "loaded_layers": [{
          "order": "2",
          "path": "stories/mars/gale/maps/gale_msl_area_3857",
          "type": "tms",
          "credits": "NASA MRO HiRISE/NASA/JPL/University of Arizona"
        }],
        "view": {
          "extent": [137.2593930, -4.7319811, 137.5040463, -4.5720141],
          "marker": ""
        }
      }]
    },   
    {
      "chapter_title":"Chapter 6",
      "chapter_id":"6",      
      "steps": [{
        "title": "Curiosity’s traverse",
        "text": "Since august 2012 when it landed on the Red planet at Bradbury, Curiosity travelled about 20 km southwestward. Along the way, the science team behind the rover kept unravelling geological mysteries and deciphering the fluvio-deltaic and lacustrine past of the Gale Crater.",
        "media": [{
            "path": "",
            "type": "",
            "caption": "",
            "stoptime": ""
        }],
        "loaded_layers": [{
            "order": "1",
            "path": "stories/mars/gale/maps/bradbury_landing.geojson",
            "type": "geojson",
            "credits": "Bradbury landing"
          },{
            "order": "2",
            "path": "stories/mars/gale/maps/msl_traverse_line.geojson",
            "type": "geojson",
            "credits": "MSL traverse"
          },{
            "order": "3",
            "path": "stories/mars/gale/maps/gale_msl_area_3857",
            "type": "tms",
            "credits": "NASA MRO HiRISE/NASA/JPL/University of Arizona"
        }],
        "view": {
          "extent": [137.2593930, -4.7319811, 137.5040463, -4.5720141],
          "marker": ""
        }
      }]
    },
    {
      "chapter_title":"Chapter 7",
      "chapter_id":"7",      
      "steps": [{
        "title": "Kimberley outcrop",
        "text": "Along the road, in 2014, Curiosity stopped at the Kimberley outcrop to do some Geology at this beautiful place. Look, you can even spot the rover on the satellite picture. Sedimentary rocks of this place belong to the Bradbury Group, an ensemble of sandstones that were deposited about 3.4-3.6 billion years ago, when rivers ran across the crater.",
        "media": [{
            "path": "stories/mars/gale/media/chapter_07/pano_kimberley.jpg",
            "type": "image/jpeg",
            "caption": "NASA/JPL-Caltech/Ken Kremer – kenkremer.com/Marco Di Lorenzo",
            "stoptime": ""
        }],
        "loaded_layers": [{
            "order": "1",
            "path": "stories/mars/gale/maps/ESP_036128_1755_COLOR_385",
            "type": "geojson",
            "credits": "HiRISE ESP_036128_1755, NASA MRO HiRISE/NASA/JPL/University of Arizona"
          },{
            "order": "",
            "path": "stories/mars/gale/maps/gale_msl_area_3857",
            "type": "tms",
            "credits": "NASA MRO HiRISE/NASA/JPL/University of Arizona"
        }],
        "view": {
          "extent": [137.3968053, -4.6409855, 137.4181897, -4.6195336],
          "marker": ""
        }
      }]
    },
    {
      "chapter_title":"Chapter 8",
      "chapter_id":"8",      
      "steps": [{
        "title": "Future mapping work on Kimberley",
        "text": "While Curiosity is not at Kimberley any longer, the geological mapping continues! Geologists are currently developing new technologies to improve study and mapping of Mars, by reconstructing in 3D and in Virtual Reality outcrops like Kimberley.",
        "media": [{
            "path": "stories/mars/gale/media/Kimberley_300k_light.obj",
            "type": "model/obj",
            "caption": "3D mesh of the Kimberley outcrop, G. Caravaca, S. Le Mouélic, N. Mangold, LPG Nantes",
            "stoptime": ""
        }],
        "loaded_layers": [{
            "order": "1",
            "path": "stories/mars/gale/maps/ESP_036128_1755_COLOR_385",
            "type": "geojson",
            "credits": "HiRISE ESP_036128_1755, NASA MRO HiRISE/NASA/JPL/University of Arizona"
          },{
            "order": "",
            "path": "stories/mars/gale/maps/gale_msl_area_3857",
            "type": "tms",
            "credits": "NASA MRO HiRISE/NASA/JPL/University of Arizona"
        }],
        "view": {
          "extent": [137.3968053, -4.6409855, 137.4181897, -4.6195336],
          "marker": ""
        }
      }]
    },
	  {
      "chapter_title":"Chapter 9",
      "chapter_id":"9",      
      "steps": [{
        "title": "Credits",
        "text": "Original work by PlanMap team and Laboratoire de Planétologie et Géodynamique - Nantes. All other media belong to their respective credited owners. See more at http://www.planmap.eu",        
        "media": [{
          "path": "",
          "type": "",
          "caption": "",
          "stoptime": ""
        }],
        "loaded_layers": [{
            "order": "",
            "path": "",
            "type": "",
            "credits": ""
        }],
        "view": {
          "extent": [-180, -90, 180, 90],
          "marker": ""
        }
      }]
    }
  ]
}
```



### [Demo](https://stories.planmap.eu/)



### Shall we design (and start) a storymap?

<blink> ;-) </blink>
