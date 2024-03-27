# Keyboard Annealing
Run by opening the repo folder in a terminal with this command (works just fine in VSCode Integrated Terminal):
julia -L 'keyboardSA.jl'
julia -L 'multiLayerSA.jl'

## Changes
- added `using Revise`

### To Do
- update layout to reflect the Moonlander
- update strength scores (fingerCPM and rowCPM)
- consider how to implement layers
- see if there's a not-terrible way to import and evaluate layouts from Oryx
- consider how to adapt for left-only input
  - just adding vertical rows would penalize for distance weirdly
- delete all but final PNG when run starts
  - rename previous final to previous_final and keep it?
- separate numbers and symbols?
- alter to work with a word-frequency dict instead of a giant file?


# Source Readme:

Supporting simulated annealing code for the [Why I Made The World's Worst Keyboard](https://youtu.be/188fipF-i5I) YouTube video.

Written in Julia... because it's fast, easy to read, and annoys my labmates.

To run, clone the this repository and start Julia with `julia
--project=.` and run `include("keyboardSA.jl")`. It should start by
benchmarking your training data (myBook.txt) against QWERTY followed by building
it's own optimal layout. Change the number of iterations and cooling rates as
desired within the SA() function. The terminal will give some indication of
current progres (also stored by a new text file will give a
iteration-by-iteration record of progress), and .png files of the current best
solution will be saved to your same directory.

To train on your own custom dataset either point the "myBook.txt" somewhere else or just replace its contents.

Good luck!

## more detailed instructions

Download at https://julialang.org/downloads/ and install the Julia language.

Assuming `julia` is in your path, run

```bash
git clone https://github.com/AtomicFrontierCode/keyboards.git
cd keyboards
julia -L 'keyboardSA.jl'
```

If you want to play with the script, it's recommended to use the
[Revise.jl](https://github.com/timholy/Revise.jl) package to minimize latency.
