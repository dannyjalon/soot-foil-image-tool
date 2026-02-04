# Soot-foil-image-tool

An automated tool for measuring cell sizes in soot foil images.

# Description 

This tool automatically measures the mean cell width and length of soot foil images, and provides various statistics such as histograms and PDFs.

# Requirements

This tool was tested on **Python 3.10**, and requires the following libraries: OpenCV, NumPy, SciPy, Matplotlib.

# Demo

![soot foil image analysis tool](https://github.com/user-attachments/assets/ec6161fb-d356-4df0-9bd7-228b079e660a)

# Usage

You can call the function `measure_image` using the following script example:

```python
from soot_foil_image_tool import measure_image

annotated_image, stats = measure_image(image path, dimension , size, step size=10)
```
This function processes a single image and produce measurement graphs and an annotated final image.

Returns: 

A tuple (annotated_image, measurements) where:

- `annotated_image`: The final image with drawn measurements.
- `measurements`: A dictionary with measurement arrays.
        
**Parameters:**
- `image_path` *(str)*: Exact path to the soot foil image file (e.g. `'.../images/sample.png'`).
- `dimension` *(str)*: Either `'h'` for height or `'w'` for width.  
- `size` *(float)*: The real-world size of the image in arbitrary units (default is centimeters), corresponding to the chosen dimension.
- `step size` *(float, optional)*: Used for the artifact filtration function (parameter optimization). Default value is 10. Decreasing the step size may provide better results but will increase the running time, and vice versa.

# Image resolution

For best results it is recommended to set the image resolution to ~40 pixels per cell length/width. Images with higher resolution may be adjusted accordingly. Images with initially lower resolution may result in poorer results.

# Output data

The function saves the following data to the local directory:

1. `contours.png`: Original soot foil image overlaid with the detected contours.
2. `Measurements.png`: Illustration of the measured cell width (blue arrows) and length (green arrows).
3. `measurements.csv`: A .csv file containing a list of the cell width and length measurements (in absolute and euclidean values).
4. `output_plot_1.png`: Histograms and PDFs of the cells' lengths and widths.

**Note:** To proceed to the next output image press the 'Esc' button.

# License

This project is licensed under the [MIT License](https://opensource.org/licenses/MIT).

You are free to use, modify, and distribute this software with proper attribution. See the full [LICENSE](https://opensource.org/licenses/MIT) for more details.

# Reference

please cite: https://doi.org/10.1016/j.jaecs.2025.100340
