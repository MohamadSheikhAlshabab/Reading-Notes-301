# Read-01 

### What is "Float"?
 - images may be set into the page such that text wraps around them as needed.
 - This is commonly and appropriately called "text wrap".

 - What are floats used for?
   - Aside from the simple example of wrapping text around images, floats can be used to create entire web layouts.

 - Clearing the Float :
  - Float's sister property is clear:
  - Clear has four valid values as well.
  - Both is most commonly used, which clears floats coming from either direction
  - Left and Right can be used to only clear the float from one direction respectively.
  - None is the default, which is typically unnecessary unless removing a clear value from a cascade.

-  The Great Collapse :
 - Collapsing almost always needs to be dealt with to prevent strange layout and cross-browser problems.
 - We fix it by clearing the float after the floated elements in the container but before the close of the container.

----------------------

### Responsive vs. Adaptive vs. Mobile :
 
 - Relative Viewport Lengths
  - CSS3 introduced some new relative length units, specifically related to the viewport size of the browser or device.
  - These new units include vw, vh, vmin, and vmax.  
   1. vw :Viewports width
   2. vh :Viewports height
   3. vmin :Minimum of the viewport’s height and width
   4. vmax :Maximum of the viewport’s height and width
 
 - The formula is based : target ÷ context = result
 
 
 - Flexible Grid : Taking the flexible layout concept, and formula, and reapplying it to all parts of a grid will create
   a completely dynamic website, scaling to every viewport size.

- Media Queries :Media queries were built as an extension to media types commonly found when targeting and including styles.
  - Media queries provide the ability to specify different styles for individual browser and device circumstances, 
    the width of the viewport or device orientation for example.
    
- Initializing Media Queries : 
  1. using the @media rule inside of an existing style sheet,
  2. importing a new style sheet using the @import rule, or by linking to a separate style sheet from within the HTML document.
  
- Omitting a Media Type :When using the not and only logical operators the media type may be left off.
  -In this case the media type is defaulted to all.
  
- Orientation Media Feature :The orientation media feature determines if a device is in the landscape or portrait orientation. 

- Aspect Ratio Media Features :The aspect-ratio and device-aspect-ratio features specifies the width/height pixel ratio of 
  the targeted rendering area or output device. 
  
- Resolution Media Feature: The resolution media feature specifies the resolution of the output device in pixel density,
  also known as dots per inch or DPI.
  
- Other Media Features: Other media features include identifying available output colors with use of the color, color-index,
  and monochrome features, identifying bitmap devices with the grid feature, and identifying the scanning process of a television
  with the scan feature.
  
- Mobile First: One popular technique with using media queries is called mobile first.
  The mobile first approach includes using styles targeted at smaller viewports as the default styles for a website,
  then use media queries to add styles as the viewport grows.
  
- Viewport Height & Width : Using the viewport meta tag with either the height or width values will define the height
  or width of the viewport respectively. Each value accepts either a positive integer or keyword.  
  
- Viewport Scale :To control how a website is scaled on a mobile device, and how users can continue to scale a website,
  use the minimum-scale, maximum-scale, initial-scale, and user-scalable properties.
  
- Viewport Resolution : When more control is needed, specifically over the resolution of a device, 
  the target-densitydpi value may be used. The target-densitydpi viewport accepts a handful of values including device-dpi, 
  high-dpi, medium-dpi, low-dpi, or an actual DPI number.
