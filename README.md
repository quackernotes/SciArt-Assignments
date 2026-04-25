# SciArt-Assignments
IBB Sem-II SciArt Assignments using ImageJ/Cell Profiler to analyse scientific images and creating Infographics. (April 2026)

Q1. Download a new Microscopy image to count particles other than cell (e.g: protein plaques, echinoderm embryos, intracellular viral count, parasites in body fluids etc)

Obtained the raw image from Open Cell- https://opencell.sf.czbiohub.org/target/404
  Chose Ceramide transporter 1 (CERT1) as protein particles to count in a microscopy image with around 20 cells. 
  The CERT1 Shelters ceramides and diacylglycerol lipids inside its START domain and mediates the intracellular trafficking of ceramides and diacylglycerol lipids in a non-vesicular manner.

PROTOCOL/INSTRUCTIONS FOR PRODUCING THE SAME RESULTS FOR COUNTING OF PARTICLES FROM MICROSCOPY IMAGE USING FIJI/IMAGEJ
    File → open → select 
    Process → subtract background → (uncheck everything except Preview)
    # : Rolling ball radius was set to 27 
    Image → Adjust → 8 bit 
    Adjusting the threshold: Image → Adjust → Threshold values → check Dark background, making it blue and our particles of interest distinct → adjust the scale to get as much data ( don't loose data, if some pixels, as in dots remain leave it)
    #: Auto simply worked in this case.
    Process → Binary → Convert to Masks → Process → Binary→ Watershed (puts a one pixel line in-between to differentiate two different particles) 
    Measure the length of the cells using the measuring tool 
    #: was around ~100px 
    Analyse → Set measurements  → check required option (If more parameters are needed in the measurement table)
    #: Checked "Area", "Mean grey value", "min max grey value", "Area fraction".
    Analyze particles → play around with size parameters such that anything smaller will be cancelled out → play around a little bit with circularity parameter (how circular it is: 1 = perfect circle and zero = not circular at all) → leave Size and Circularity parameter as is if it is not working or you are not sure
    #: Size was set from 0-50 px^2 and circularity 0.40-1.00 
    #: Got ~1742 particle count
    Save the Results table in .csv format
