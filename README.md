# GPU Specialization Capstone Project

## Project Title

<!-- Replace with your project title -->

## Description

<!-- 2-3 sentences: what does this project do, why is it interesting, what GPU technique does it demonstrate? -->

## GPU Technology Used

<!-- e.g., CUDA kernels, cuFFT, cuBLAS, NPP, PyTorch, TensorFlow, PyCUDA, etc. -->

## Requirements

### Hardware
- NVIDIA GPU with CUDA support (or other GPU — see note below)

### Software
- CUDA Toolkit X.X
- <!-- Add other dependencies, e.g.: Python 3.x, PyTorch, OpenCV, etc. -->

```bash
# Install dependencies (example)
pip install -r requirements.txt
# or
sudo apt-get install cuda-toolkit-XX-X
```

## Build

```bash
make
# or
./run.sh
```

## Usage

```bash
./program --input <input_file> --output <output_file> [options]
```

| Argument | Description | Default |
|----------|-------------|---------|
| `--input` | Path to input file | required |
| `--output` | Path to output file | `output/` |
| | | |

## Examples

```bash
# Example 1
./program --input data/sample.png --output results/out.png

# Example 2
./program --input data/large_dataset/ --output results/ --verbose
```

## Results

<!-- Include summary of results, speedup vs CPU, accuracy metrics, etc. -->

See `results/` directory for output artifacts (images, logs, CSVs).

| Dataset | CPU Time | GPU Time | Speedup |
|---------|----------|----------|---------|
| | | | |

## Project Structure

```
.
├── src/            # Source code
├── data/           # Input datasets
├── results/        # Output artifacts (proof of execution)
├── Makefile
├── run.sh
└── README.md
```

## Algorithms / Kernels

<!-- Describe the key GPU kernels or framework operations used and why -->

## Lessons Learned

<!-- What challenges did you face? What did you learn? What would you do differently? -->

## Presentation

<!-- Link to your 5-10 minute demo video -->
Video: [YouTube / Box / Drive link]

## References

- [CUDA Programming Guide](https://docs.nvidia.com/cuda/)
- [Google C++ Style Guide](https://google.github.io/styleguide/cppguide.html)
- Course template: https://github.com/PascaleCourseraCourses/CUDAatScaleForTheEnterpriseCourseProjectTemplate
