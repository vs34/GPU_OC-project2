# GPU Image Processing Pipeline

## Description

A CUDA-accelerated image processing pipeline that applies a chain of filters — grayscale conversion, Gaussian blur, and Sobel edge detection — to images using custom GPU kernels. The project demonstrates parallel 2D convolution on the GPU and benchmarks it against an equivalent CPU implementation, showing real-world speedup on image data.

## GPU Technology Used

- Custom CUDA C++ kernels for 2D convolution, grayscale, and edge detection
- CUDA thread/block grid optimized for 2D image data
- OpenCV for image I/O (reading/writing only — all processing done on GPU)

## Requirements

### Hardware
- NVIDIA GPU with CUDA Compute Capability 3.5+

### Software
- CUDA Toolkit 11.0+
- OpenCV 4.x
- GCC 9+
- Make

```bash
# Ubuntu/Debian
sudo apt-get install libopencv-dev
sudo apt-get install cuda-toolkit-11-0
```

## Build

```bash
make
```

## Usage

```bash
./imgproc --input <image_path> --filter <filter_name> --output <output_path>
```

| Argument | Description | Default |
|----------|-------------|---------|
| `--input` | Path to input image (JPG/PNG) | required |
| `--output` | Path to output image | `results/out.png` |
| `--filter` | Filter to apply: `grayscale`, `blur`, `sobel`, `all` | `all` |
| `--benchmark` | Print CPU vs GPU timing | false |

## Examples

```bash
# Apply full pipeline (grayscale → blur → edge detection)
./imgproc --input data/lena.png --output results/lena_out.png --filter all

# Sobel edge detection only with benchmark
./imgproc --input data/boat.png --output results/boat_edges.png --filter sobel --benchmark

# Batch run on all images in data/
./run.sh
```

## Results

See `results/` directory for output images and `results/benchmark.csv` for timing data.

| Image | Resolution | CPU Time | GPU Time | Speedup |
|-------|------------|----------|----------|---------|
| lena.png | 512x512 | — ms | — ms | —x |
| boat.png | 720x576 | — ms | — ms | —x |
| baboon.png | 512x512 | — ms | — ms | —x |

## Project Structure

```
.
├── src/
│   ├── main.cu          # Entry point, CLI parsing
│   ├── kernels.cu       # CUDA kernels (grayscale, blur, sobel)
│   ├── kernels.h
│   ├── pipeline.cu      # Pipeline orchestration
│   └── cpu_ref.cpp      # CPU reference implementation for benchmarking
├── data/                # Input images (from USC SIPI dataset)
├── results/             # Output images + benchmark.csv
├── Makefile
├── run.sh               # Batch runner for all images
└── README.md
```

## Algorithms / Kernels

**Grayscale conversion:** Each CUDA thread converts one pixel using the luminance formula `Y = 0.299R + 0.587G + 0.114B`. Fully parallel — no data dependencies between pixels.

**Gaussian blur:** 2D separable convolution with a 5x5 Gaussian kernel. Implemented as two 1D passes (horizontal then vertical) using shared memory tiling to minimize global memory reads.

**Sobel edge detection:** Applies 3x3 Sobel kernels in X and Y directions, then computes gradient magnitude `sqrt(Gx² + Gy²)` per pixel. Highlights edges by measuring intensity gradients.

All kernels launch with a 2D grid of 16x16 thread blocks, matching the 2D structure of image data.

## Lessons Learned

<!-- Fill in after completing the project -->
- What surprised you about GPU memory management?
- What was the most challenging kernel to tune?
- How did shared memory affect performance?
- What would you do next (e.g., video processing, real-time webcam)?

## Presentation

Video: [YouTube / Box / Drive link]

## References

- [CUDA Programming Guide](https://docs.nvidia.com/cuda/)
- [Google C++ Style Guide](https://google.github.io/styleguide/cppguide.html)
- [USC SIPI Image Database](https://sipi.usc.edu/database/database.php)
- Course template: https://github.com/PascaleCourseraCourses/CUDAatScaleForTheEnterpriseCourseProjectTemplate
