# 🧮 SciPy Assignments

[![Python](https://img.shields.io/badge/Python-3.x-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![SciPy](https://img.shields.io/badge/SciPy-Scientific_Python-8CAAE6?logo=scipy&logoColor=white)](https://scipy.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)](https://jupyter.org/)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Prktriesitout/ScipyAssignments/blob/main/ScipyAssignmenta.ipynb)

A practical collection of SciPy exercises covering image processing, interpolation, filtering, and frequency-domain analysis.

> **Notebook:** [`ScipyAssignmenta.ipynb`](./ScipyAssignmenta.ipynb)

---

## ✨ What You’ll Learn

- 🖼️ Resize, rotate, smooth, and analyze images
- 🔍 Detect edges and binary image features
- 🧩 Perform morphological operations and connected-component labeling
- 🌊 Compare 1D and 2D interpolation methods
- 〰️ Fit and smooth noisy data with B-splines
- 🎚️ Design and apply low-pass filters
- 📊 Inspect signals with FFT and Welch PSD analysis

## 📂 Repository Structure

| File | Purpose |
|---|---|
| [`ScipyAssignmenta.ipynb`](./ScipyAssignmenta.ipynb) | Main assignment notebook with examples and plots |
| [`README.md`](./README.md) | Project overview and usage instructions |

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/Prktriesitout/ScipyAssignments.git
cd ScipyAssignments
```

### 2. Create a virtual environment

```bash
python -m venv .venv
source .venv/bin/activate
```

On Windows:

```powershell
.venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install numpy scipy matplotlib imageio jupyter
```

### 4. Launch the notebook

```bash
jupyter notebook ScipyAssignmenta.ipynb
```

Or open the notebook directly in Google Colab using the badge above.

## 🖼️ Image Setup

The image exercises expect a file named `photo.png` in the repository or in the notebook’s working directory:

```python
import imageio as iio

img = iio.imread("photo.png", mode="L")
```

If no image is available, place any PNG or JPEG file in the project folder and update the filename.

---

## 🧰 Required SciPy and Python Functions

### NumPy

| Function | Used for |
|---|---|
| `numpy.array` / `numpy.asarray` | Convert and represent image or signal data |
| `numpy.mean`, `numpy.var`, `numpy.std` | Calculate pixel statistics |
| `numpy.hypot` | Combine Sobel gradients into edge magnitude |
| `numpy.meshgrid` | Create coordinate grids for 2D operations |
| `numpy.linspace` | Generate evenly spaced time or coordinate values |
| `numpy.random.normal` | Generate synthetic noise |
| `numpy.sin`, `numpy.cos` | Generate test signals and surfaces |

### Image processing — `scipy.ndimage`

| Function | Used for |
|---|---|
| `ndimage.zoom` | Resize an image |
| `ndimage.rotate` | Rotate an image without cropping |
| `ndimage.gaussian_filter` | Smooth an image |
| `ndimage.sobel` | Detect horizontal and vertical edges |
| `ndimage.binary_erosion` | Shrink foreground regions |
| `ndimage.binary_dilation` | Expand foreground regions |
| `ndimage.label` | Label connected components |
| `ndimage.median_filter` | Remove impulse and random signal noise |
| `ndimage.gaussian_laplace` | High-pass edge enhancement |

### Interpolation — `scipy.interpolate`

| Function | Used for |
|---|---|
| `interpolate.interp1d` | Linear, quadratic, and cubic 1D interpolation |
| `interpolate.splrep` | Construct a smoothing B-spline |
| `interpolate.splev` | Evaluate a B-spline at desired points |
| `interpolate.RectBivariateSpline` | Smooth interpolation over a 2D grid |

### Fourier analysis — `scipy.fft`

| Function | Used for |
|---|---|
| `fft.fft2` | Compute a 2D image Fourier transform |
| `fft.fft` | Compute a 1D signal Fourier transform |
| `fft.fftfreq` | Generate frequency bins |
| `fft.ifft` | Reconstruct a signal in the time domain |

### Signal processing — `scipy.signal`

| Function | Used for |
|---|---|
| `signal.butter` | Design a Butterworth filter |
| `signal.filtfilt` | Apply zero-phase low-pass filtering |
| `signal.welch` | Estimate power spectral density |

### Visualization and image I/O

| Function or library | Used for |
|---|---|
| `matplotlib.pyplot` | Plot images, signals, spectra, and surfaces |
| `imageio.imread` | Load the source image |

---

## 📓 Assignment Topics

1. **Image resizing** — scale an image with `ndimage.zoom`
2. **Image rotation** — rotate 45 degrees with `ndimage.rotate`
3. **Gaussian smoothing** — experiment with sigma values
4. **Edge detection** — combine Sobel gradients
5. **Thresholding** — convert grayscale pixels into binary values
6. **Morphology** — erosion and dilation
7. **Connected components** — label and count objects
8. **Image statistics** — calculate mean, variance, and standard deviation
9. **2D Fourier transform** — visualize the magnitude spectrum
10. **1D interpolation** — compare linear, quadratic, and cubic methods
11. **B-spline smoothing** — vary the smoothing parameter
12. **Median filtering** — reduce impulse and Gaussian noise
13. **Butterworth filtering** — separate low- and high-frequency content
14. **High-pass filtering** — enhance edges with Laplace of Gaussian
15. **Frequency analysis** — apply FFT and Welch power spectral density

## ⚠️ Notebook Notes

- Keep `photo.png` beside the notebook or change the image path.
- A few SciPy APIs are deprecated or have changed in recent versions:
  - Prefer `imageio.v3.imread(...)` for current `imageio` releases.
  - `scipy.ndimage.measurements` is not required for the statistics demonstrated here; NumPy functions are used instead.
  - `scipy.interpolate.interp2d` is deprecated. `RectBivariateSpline` or `RegularGridInterpolator` are better choices for new code.
- Some exercises are demonstrations rather than reusable function definitions. Add the implementation inside a function before converting the notebook into a library.

## 📜 License

This repository currently does not declare a license. Ask the repository owner before using the material outside personal or educational work.
