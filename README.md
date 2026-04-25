# SciArt-Assignments
IBB Sem-II SciArt Assignments using ImageJ to analyse scientific images and creating Infographics. (April 2026)

Q1. Download a new Microscopy image to count particles other than cell (e.g: protein plaques, echinoderm embryos, intracellular viral count, parasites in body fluids etc)

- Obtained the raw image from Open Cell - https://opencell.sf.czbiohub.org/target/404
- Chose Ceramide transporter 1 (CERT1) as protein particles to count in a microscopy image with around 20 cells.
  The CERT1 Shelters ceramides and diacylglycerol lipids inside its START domain and mediates the intracellular trafficking of ceramides and diacylglycerol lipids in a non-vesicular manner.
  - The image had the CERT1 proteins tagged and they consisted a larger part of the particles visible in the cells.

# PROTOCOL/INSTRUCTIONS FOR PRODUCING THE SAME RESULTS FOR COUNTING OF PARTICLES FROM MICROSCOPY IMAGE USING FIJI/IMAGEJ
1. Download image of choice (preferably not in .jpeg form) (.png is alright)
   - .jpeg does not conserve image quality as well as .tif or .png 
2. File → open → select downloaded image
   - : Opened file "CERT1.png"
3. Process → subtract background → (uncheck everything except Preview)
   - : Rolling ball radius was set to 27    
4. Image → Adjust → 8 bit 
5. Adjusting the threshold: Image → Adjust → Threshold values → check Dark background, making it blue and our particles of interest distinct → adjust the scale to get as much data ( don't loose data, if some pixels, as in dots remain leave it)
   - : Auto simply worked in this case.
6. Process → Binary → Convert to Masks → Process → Binary→ Watershed (puts a one pixel line in-between to differentiate two different particles) 
7. Measure the length of the cells using the measuring tool
   - : was around ~100px 
8. Analyse → Set measurements  → check required option (If more parameters are needed in the measurement table)
   - : Checked "Area", "Mean grey value", "min max grey value", "Area fraction".
9. Analyze particles → play around with size parameters such that anything smaller will be cancelled out → play around a little bit with circularity parameter (how circular it is: 1 = perfect circle and zero = not circular at all) → leave Size and Circularity parameter as is if it is not working or you are not sure
   - : Size was set from 0-50 px^2 and circularity 0.40-1.00 to exclude very small noise particles and focus on roughly circular particles.
   - : checked "Display Results", "Clear Results", "Summarize", "Exclude on Edges" and "Overlay"
   - : Got ~1742 particle count
10. Save the Results table in .csv format and the final image in .TIF format (name the files as per convenience and with enough detail so as to aid in future referencing/locating of the data.
    - : Saved results excel sheet as "Results CERT1.csv" and the Summary similarly as "Summary CERT1.csv"
    - .csv format is better supported and preferred over .xls or any other format for this purpose.
