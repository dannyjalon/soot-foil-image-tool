# Soot-foil-image-tool

An automated tool for measuring cell sizes in soot foil images.

# Description 

This tool automatically measures the mean cell width and length of soot foil images, and provides various statistics such as histograms and PDFs. 

# Demo

![soot foil image analysis tool](https://github.com/user-attachments/assets/ec6161fb-d356-4df0-9bd7-228b079e660a)

# Usage

You can call the function `measure_image` using the following script example:

```python
from soot_foil_image_tool import measure_image

stats, annotated_image = measure_image(image path, height or width , size, step size=10)
```

**Parameters:**
- `image_path` *(str)*: Exact path to the soot foil image file (e.g. `'.../images/sample.png'`).
- `height or width` *(str)*: One of the following image paramters should be provided - `'h'` for height or `'w'` for width, followed by `size` *(float)* the image size in arbitrary units (defualt is centimeters).
- `step size` *(float, optional)*: Used for the artifact filtration function (parameter optimization). Default value is 10. Decreasing the step size may provide better results but will increase the running time, and vice versa.

# Output data

The function saves the following data to the local directory:

1. `contours.png`: Original soot foil image overlaid with the detected contours.
2. `Measurements.png`: Illustration of the measured cell width (blue arrows) and length (green arrows).
3. `measurements.csv`: A .csv file containing a list of the cell width and length measurements (in absolute and euclidean values).
4. `output_plot_1.png`: Histograms and PDFs of the cells' lengths and widths.

