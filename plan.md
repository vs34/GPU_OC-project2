# GPU Specialization Capstone — Project Plan

## Assignment Summary

Build a GPU-accelerated program that demonstrates skills from the course.
Must use CUDA or a GPU framework (PyTorch, TensorFlow, PyCUDA, etc.).
Pure CPU multithreading does not qualify.

Minimum time commitment: 8 hours.

---

## Deliverables Checklist

- [ ] Public code repository (GitHub/GitLab/etc.)
- [ ] `README.md` with description, install steps, and how to run
- [ ] `Makefile` or `run.sh` for building/running
- [ ] CLI that takes arguments
- [ ] Proof of execution (screenshots, output files, logs, CSVs)
- [ ] Short written description (algorithms, kernels, lessons learned)
- [ ] 5–10 minute recorded presentation/demo video

---

## Grading Rubric Breakdown

### Code Repository (40 pts)
| Score | Criteria |
|-------|----------|
| 0 | No URL or invalid URL |
| 5 | Exists but incomplete |
| 10 | Exists, no README |
| 20 | Has README + CLI with arguments |
| 30 | Well-written code meeting Google C++ Style Guide |
| **40** | Above + Makefile/run.sh support files |

### Proof of Execution (20 pts)
| Score | Criteria |
|-------|----------|
| 0 | No evidence |
| 10 | Ran once, unclear if multiple inputs tested |
| **20** | Clear evidence of multiple data inputs/outputs |

### Code Project Description (20 pts)
| Score | Criteria |
|-------|----------|
| 0 | No description |
| 10 | Shows work done, but no reflection |
| **20** | Explains purpose, algorithms/kernels, lessons learned, significant effort |

### Presentation/Demo Video (20 pts)
| Score | Criteria |
|-------|----------|
| 0 | No URL provided |
| 5 | Video exists but < 5 minutes |
| 10 | ≥ 5 min but goals/techniques not clearly articulated |
| 15 | Clear discussion of goals, techniques, code |
| **20** | Interesting demo + next steps discussed |

---

## Project Ideas (pick one)

- GPU-accelerated image processing pipeline (filters, convolutions) using CUDA/NPP
- Real-time audio signal processing with CUDA FFT (cuFFT)
- Matrix operations / linear algebra benchmark (cuBLAS vs CPU)
- Deep learning inference on GPU with PyTorch/TensorFlow
- N-body simulation or particle system on GPU
- GPU-accelerated sorting or graph algorithms

---

## Task List

1. [ ] Pick a project idea
2. [ ] Set up GitHub repository from template: https://github.com/PascaleCourseraCourses/CUDAatScaleForTheEnterpriseCourseProjectTemplate
3. [ ] Implement core GPU kernel / framework usage
4. [ ] Add CLI argument handling
5. [ ] Write Makefile or run.sh
6. [ ] Run on multiple datasets and save output artifacts
7. [ ] Write README.md (description, install, usage, results)
8. [ ] Record 5–10 min demo video
9. [ ] Push all artifacts (outputs, logs, images) to repo
10. [ ] Submit repo URL + video URL on Coursera

---

## Data Sources

- Images: https://sipi.usc.edu/database/database.php
- ML datasets: https://archive-beta.ics.uci.edu
- CC images: https://search.creativecommons.org
- Audio (C++): http://aquila-dsp.org
- Audio (synth): https://ccrma.stanford.edu/software/stk/
- Audio samples: https://www.dsprelated.com/freebooks/pasp/Sound_Examples.html

---

## Resources

- Course template repo: https://github.com/PascaleCourseraCourses/CUDAatScaleForTheEnterpriseCourseProjectTemplate
- Google C++ Style Guide: https://google.github.io/styleguide/cppguide.html
- CUDA documentation: https://docs.nvidia.com/cuda/
