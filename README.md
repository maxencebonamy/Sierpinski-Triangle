# Sierpinski-Triangle

An animated Sierpinski triangle drawn point by point with the chaos game.

A pygame window shows a triangle and fills it with points until the Sierpinski fractal appears. Colors, frame rate and drawing speed are set in a single configuration file.

## Table of contents

- [Sierpinski-Triangle](#sierpinski-triangle)
	- [Table of contents](#table-of-contents)
	- [How it works](#how-it-works)
	- [Tech stack](#tech-stack)
	- [Repository structure](#repository-structure)
	- [Prerequisites](#prerequisites)
	- [Installation](#installation)
	- [Configuration](#configuration)
	- [Running locally](#running-locally)
	- [License](#license)

## How it works

1. **Window**: the program opens a resizable 1280x720 window and computes an equilateral triangle that fits in the smaller dimension of the window, centered.
2. **Starting point**: the first point is the center of the triangle.
3. **Point generation**: at each frame, `SPEED` points are added. Each new point is the midpoint between the previous point and a vertex of the triangle chosen at random.
4. **Rendering**: each frame, the window is cleared, then the triangle outline and every point are drawn. The loop waits `1000 // FPS` milliseconds between two frames.
5. **Resize**: when the window is resized, the triangle is recomputed and the points are cleared, so the drawing starts again.
6. **Exit**: closing the window ends the program.

## Tech stack

| Layer | Technologies |
| --- | --- |
| Language | Python 3 |
| Graphics | pygame |

## Repository structure

```
.
├── assets/
│   └── icon.png    Window icon
├── config.py       Display and animation settings
└── main.py         Triangle computation, chaos game and main loop
```

The program is a single script with no package structure. `assets/icon.png` is loaded with a path relative to the working directory, so `main.py` must be started from the repository root.

## Prerequisites

- [Python](https://www.python.org/) 3
- [pip](https://pip.pypa.io/)

The repository does not pin a Python or pygame version.

## Installation

```bash
git clone git@github.com:maxencebonamy/Sierpinski-Triangle.git
cd Sierpinski-Triangle
```

```bash
pip install pygame
```

## Configuration

Settings are Python constants in [`config.py`](config.py). There is no `.env` file.

| Variable | Description | Example |
| --- | --- | --- |
| `WINDOW_SIZE` | Initial window size, as a `pygame.math.Vector2` | `Vector2(1280, 720)` |
| `WINDOW_COLOR` | Background color, as an RGB tuple | `(36, 0, 70)` |
| `POINT_COLOR` | Color of the points and of the triangle outline, as an RGB tuple | `(255, 109, 0)` |
| `FPS` | Number of images displayed per second | `120` |
| `SPEED` | Number of points added per frame | `100` |

## Running locally

```bash
python main.py
```

## License

This project is licensed under the [MIT License](LICENSE).
