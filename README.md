# Bézier Curve Visualizer

## About
Interactive [bézier curve](https://en.wikipedia.org/wiki/B%C3%A9zier_curve) visualizer written in C using [raylib](https://www.raylib.com/) and [raygui](https://github.com/raysan5/raygui).  
Implements [De Casteljau's recursive algorithm](https://en.wikipedia.org/wiki/De_Casteljau%27s_algorithm) to display [polygonal chains](https://en.wikipedia.org/wiki/Polygonal_chain) and intermediate steps.

## Gallery
| ![image1](https://github.com/user-attachments/assets/9792ca4a-a11e-46e9-a6fe-8510ad9e344f) | ![image2](https://github.com/user-attachments/assets/4e253ce1-e09f-432e-955a-a27876a5d060) | ![image3](https://github.com/user-attachments/assets/912866ed-0517-4447-8eef-ed75e8c3d412) |
| --- | --- | --- |

## Running (with nix)
```sh
nix run github:kaan-w/bezier-curve-visualizer
```

## Building from source
```sh
git clone https://github.com/kaan-w/bezier-curve-visualizer.git
cd bezier-curve-visualizer
cmake -S . -B build -DCMAKE_BUILD_TYPE=Release
cmake --build build
```

## Development
We can use [watchexec](https://github.com/watchexec/watchexec) to re-run on file changes.
```sh
watchexec --restart --exts "c,nix" "nix run . --option substitute false"
```
