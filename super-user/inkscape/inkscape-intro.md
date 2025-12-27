# Inkscape

## Vector graphic editing
  - `SVG` : most universal vector format
  - ![svg](https://upload.wikimedia.org/wikipedia/commons/thumb/6/6b/Bitmap_VS_SVG.svg/960px-Bitmap_VS_SVG.svg.png)
  - shapes defined by mathematical formulae
    - raster : pixel matrix
  - endlessly scalable without loosing resolution
  - ideal for
    - ![inkscape examples](/home/rongzhou/Documents/ronzz-img/public/img/super-user/inkscape/capture_27-12-2025-14-33-59.png)
    - graphical design
      - logo
    - illustration
      - science
      - cartoon

## Tutorials
- built-in: `Help > Tutorials`

## Interface

- ![interface](../../../ronzz-img/public/img/super-user/inkscape/interface_areas.webp) Main UI
  - palette
	  - [palette](/home/rongzhou/Documents/ronzz-img/public/img/super-user/inkscape/capture_27-12-2025-21-03-25.png)

- View
  - Toggle visibility : `View > Show/Hide`

- Files
  - `Ctrl+O` then `Ctrl+L` : open file (paste path)

- Panels
  - Toggle visibility of panels : `F12` 
	- Document properties `Ctrl+Shift+D`
	- Layers and Object `Ctrl+Shift+L`
	- Fill and stroke `Ctrl+Shift+F`
  - Object properties `Ctrl+Shift+O
	- Selector & CSS `Ctrl+Shift+Q`

- Navigation
	- `+` / `-` - zoom in / out
	- Arrow keys - pan

- General Tools
	- `s` - Select
    - select multiple : `hold_Shift + click`
		  - click again to remove object
			- ![select multiple](../../../ronzz-img/public/img/super-user/inkscape/capture_27-12-2025-15-04-41.gif)
		- selection strategy : enclosed/touched
		  - ![selection strategy](../../../ronzz-img/public/img/super-user/inkscape/capture_27-12-2025-15-23-12.png)
	  - copy objects, select single object + `ctrl+v` : paste on top of selected object
		- ![sandwich paste](../../../ronzz-img/public/img/super-user/inkscape/paste_on_top_sandwich.webp)
		- selected : lower sandwich slice 
	- `t` - Text
	- `d` - Dropper (color picker)

- Shape tools
	- `r` - Rectangle
	  - rounded corners
		  - ![rounded corners](../../../ronzz-img/public/img/super-user/inkscape/capture_27-12-2025-15-28-03.gif)
		- tool controls bar
		  - `W` & `H` : size
		  - `Rx`: horizonal radius of rounded corners
		  - `Ry`: vertical radius of rounded corners
			- ![vertical radius](/home/rongzhou/Documents/ronzz-img/public/img/super-user/inkscape/capture_27-12-2025-15-30-13.png)
	- `e` - Ellipse / Arc
	  - segment
		  - ![segment](/home/rongzhou/Documents/ronzz-img/public/img/super-user/inkscape/capture_27-12-2025-15-36-14.gif)
		- arc
		  - ![arc](/home/rongzhou/Documents/ronzz-img/public/img/super-user/inkscape/capture_27-12-2025-15-38-29.gif)
		- ![segment-arc](../../../ronzz-img/public/img/super-user/inkscape/circle_slice_arc.webp)
		- tool controls bar
		  - ![tool control bar](/home/rongzhou/Documents/ronzz-img/public/img/super-user/inkscape/capture_27-12-2025-15-39-49.png)
  		- `Rx` & `Ry` : size
			- `Start` & `End` : segment size
  		- switch to slice/arc/chord/full-shape
				- toolbar supports switch FROM slice/arc/chord
			  - full-shape can only be switched into partials by dragging in the canvas
	- `*` : star/polygon
	  - ![star-variants](../../../ronzz-img/public/img/super-user/inkscape/star_tool_variants.svg)
	  - ![drag-star](../../../ronzz-img/public/img/super-user/inkscape/star_tool_handles.png)
		- ![toggle-star](/home/rongzhou/Documents/ronzz-img/public/img/super-user/inkscape/capture_27-12-2025-19-25-59.png)
		  - ![rounded-randomised-star](../../../ronzz-img/public/img/super-user/inkscape/star_tool_settings.png)
	- `i` : spirals
	- modifier keys
    - `ctrl` : keep proportion
    - `Shift` : draw from centre
	- 3D box : **Not recommended.**
	  - simulated 3D perspective drawing
	  - much more useful and precise to use FreeCAD to build an actual 3D model, then export a perspective drawing

- Shape transformation
	- rotate : `[` `]`
	- resize : `<` `>` 
  - skew
    - ![skew](../../../ronzz-img/public/img/super-user/inkscape/skew.gif)
    - double click + (ctrl) + drag parallel arrows
  - Modifiers
    - `Ctrl`
      - keep proportion/regular increment
    - `Alt` - slower adjustments
    - `Shift` - faster move
	- Change stacking order
	  - select object, then
		  - `Pageup` : raise
			- `Pagedown` : lower
			- `Home` : bring to front
			- `End` : bring to bottom
- Freehand drawing
  - with mouse or graphics tablet stylus
	- NOT based on geometrical shapes
	- `c` : calligraphy/brush
	- `p` : pencil
	  - 3 modes
			- ![pencil-modes](/home/rongzhou/Documents/ronzz-img/public/img/super-user/inkscape/capture_27-12-2025-20-50-20.png)
			- regular Bézier path
				- adjust smoothing for more elegant effects
			- spiro path
				- stylish swirls
			- BSpline path
				- evenly smooth curves
		- creating dots
		  - `ctrl+click`
			  - `shift` : double the size
				- `alt` : small random size dot
				- `shift+alt` : large random size dot
			- note the dots are technically circles with fill
	- `b` : Bézier curves
	  - `click` to drop nodes
		- `right_click` to terminate
		- example : [drawing a book](https://inkscape-manuals.readthedocs.io/en/latest/pen-tool.html)
		- 6 modes
		  - [Bézier curve modes](/home/rongzhou/Documents/ronzz-img/public/img/super-user/inkscape/capture_27-12-2025-20-59-07.png)
			- Bézier
			- spiro
			- BSpline
			- straight lines
			- paraxial (= strictly horizonal or vertical)



- Selection & groups
	- `Shift+Click` - add/remove from selection
	- Click-drag - marquee select
	- `Ctrl+G` - group
	- `Ctrl+U` - ungroup
	- `Ctrl+(Shift)+Click` - select item(s) inside a group
	- `Shift+Tab` - cycle selection by stacking order
	- `Edit → Select Same` - select by stroke/fill/contour/style/type




