# Shift Walk-Thrus

## Mapbox Editor

1. Go to mapbox.com
2. Sign up/in
3. Quick look at the interface
	- Projects
		- We'll work with this here
	- Styles
	- Data
		- We'll work with this later
4. Go to **Projects**
5. Select **New Project**
6. Tour the interface
	- Top-left
		- Style
			- Changes basemap
		- Data
			- Make your own
				- Markers (points)
				- Lines
				- Polygons/areas
			- Import data
				- GeoJSON
				- CSV
				- GPX (common gps data format)
				- KML
			- Feature list (the individual features you've added)
		- Project
			- There's more info about your map here once you save
			- Name your map and describe if you want
		- Search
			- Look by place down to address
	- Bottom-Left
		- Zoom controls
		- Lat & Long of center
7. Import data
	- it's on github!
	- [https://github.com/maptimelex/shift-meetup/blob/master/data/lbs-local-establishments.csv](https://github.com/maptimelex/shift-meetup/blob/master/data/lbs-local-establishments.csv)
	- Look at the data on GitHub
		- Note the **card** field. You can use HTML to add some styling to description
		- There's no lat/long fields. Sometimes you get those, but Mapbox can geocode!
	- Geocode
		- Explain briefly
		- Use ctrl/cmd+click to select these fields:
			- `address`
			- `city`
			- `state`
			- `zip`
	- Title
		- `place`
	- Description
		- `card`
	- Style
		- yellow
	- Symbol
		- glass
8. Move Beer Engine to Danville
	- Click marker
	- Lat/Long tab
		- lat = `37.6466968`
		- long = `84.7711793`
9. Save
10. Project
	- Settings
		- Title
			- Lex Beer Scene Map
		- Description
			- Great locations to get beer according to LexBeerScene.com (http://www.lexbeerscene.com/localestablishments)
11. Save
12. Project > Info
	- Data
		- Download data as GeoJSON or KML
	- Map ID
		- For use with MapboxJS
	- Share
		- URL to a full page map to share with people
	- Embed
		- Put your map in an iframe to put in a site
	- Map option checkboxes
		- Zoom & Pan
		- Zoom Wheel
		- Geocoder (zoom to a place)
		- Link (for others to share your map from within the map!)

## Tilemill

1. Open Tilemill
2. Create a project
	- Name the project
	- Include world data
3. Tour the interface
	- Map pane
		- Map
		- Zoom
		- Full screen
	- Stylesheet
		- style.mss
		- You can use multipe stylesheets
	- Bottom-left pane
		- Templates
			- HTML Legend
			- Teaser & Full: Infobox
			- Location: To external links
		- Fonts
		- CartoCSS Reference
		- Layers
			- *Add Layer* button
			- Shows the layer ID
			- Access to data table
			- Zoom to layer
			- Toggle layer on & off
			- Edit layer (where it comes from)
			- Delete layer
	- Top-right corner
		- Save
			- Click this (or ctrl/cmd+s) to see project changes
			- Export
				- Various file types:
					- PNG, PDF, SVG, MBTiles, Mapnik XML
				- Upload to Mapbox
				- View exports
4. Add counties
	- It's on GitHub
	- [https://github.com/maptimelex/shift-meetup/blob/master/data/ky_counties.geojson](https://github.com/maptimelex/shift-meetup/blob/master/data/ky_counties.geojson)
5. Adjust project settings
	- name
	- zoom
	- center
6. Get rid of world data
7. Change background to `#000`
8. Look at the CartoCSS that's there
	- Kinda tries to feel like CSS
	- Layers are like elements
		- Automatically have an ID (#)
		- Can have classes (.)
	- Type of geometry that is being edited dictates what attributes can be styled for a layer
	- Style can be made dependent on zoom
	- Style can be determined by attribute value of layer data
	- Refer to the reference `{ }`
9. Style counties
	- `https://gist.github.com/maptastik/49a52f0c606ad6376cfa#file-01_add-counties-mss`
	- Save
	- Talk through changes
10. Style county lines by zoom
	- `https://gist.github.com/maptastik/49a52f0c606ad6376cfa#file-02_zoom-line-mss`
	- Save
	- Talk through changes
11. Add glow
	- `https://gist.github.com/maptastik/49a52f0c606ad6376cfa#file-03_add-glow`
	- Save
	- Talk through changes
		- These are kind of like pseudo-elements
12. Add County names
	- `https://gist.github.com/maptastik/49a52f0c606ad6376cfa#file-04_add-text-mss`
	- Save
	- Talk through changes
13. Add ghost town data
	- it's on GitHub
	- [https://github.com/maptimelex/shift-meetup/blob/master/data/kentuckyGhostTowns.geojson](https://github.com/maptimelex/shift-meetup/blob/master/data/kentuckyGhostTowns.geojson)
14. Add ghost icons
	- it's on GitHub
	- [https://github.com/maptimelex/shift-meetup/blob/master/assets/ghost-icon_white.svg](https://github.com/maptimelex/shift-meetup/blob/master/assets/ghost-icon_white.svg)
	- `https://gist.github.com/maptastik/49a52f0c606ad6376cfa#file-05_add-ghost-mss1
	- Save
	- Talk through changes
15. Add Interaction
	- Something like `THE GHOST TOWN OF {{{name}}} IS IN {{{county}}} COUNTY. SCAAAAAAAARY!`
16. Upload to Mapbox
	- Make sure settings are good, particularly the zoom level and bounding box. Don't want to upload more than we have to
17. View on Mapbox
	- Show that it can be embedded
	- Mention it can be integrated into a map using Leaflet or MapboxJS