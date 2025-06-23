# Denzven-Graphing-Api  

to read the docs with fancy css head over to -> https://denzven.github.io/Denzven-Graphing-Api/  

### Welcome! this is [Denzven-Graphing-Api](https://denzven.pythonanywhere.com/)

### 1. About the Api:

Denzven-Graphing-Api is my first flask project that plots graphs of formulas/Equations using python. i have also made and [Api-Wrapper](https://pypi.org/project/Denzven-Graphing-Api-Wrapper) (mostly for practice) to make life easy and to use this Api. Also an [Example Bot](https://github.com/denzven/Denzven-Graphing-Api-Bot) 

---

### 2. How to Use the API?

Using the API is as simple as sending a request to the [website](https://denzven.pythonanywhere.com/) with some params such as the formula, grid, plot_style, x_coord, y_coord (more configurable parameters is coming...) and the API will return an image of the plotted Graph.

#### Example of a requested URL:

> http://denzven.pythonanywhere.com/DenzGraphingApi/v1/flat_graph/test/plot?formula=x%2By&x%2By&grid=1&plot_style=3&x_coord=20&y_coord=20


![Graph Example in Firefox](https://cdn.discordapp.com/attachments/775096810963468288/859152862758961242/unknown.png)

Note:
- Base url:
    - http://denzven.pythonanywhere.com/DenzGraphingApi/v1/flat_graph/test/plot
- The Formula:
    - ?formula=x%2By&x%2By
    > Note that this url is "urlencoded" using urllib.

    - What can the formula contain?
        - trignometric functions:
        > sin() cos() tan() 
        - powers
        > x**2 = x²
        - Basic BODMAS           
        >   ()=Brackets,   
            /=Divide,   
            *=Mutiply,  
            +=Add,  
            -=Subtract  
        - Misc:
        >   pi=value of the const pi,  
            sqrt()=square root of the value,  
            %=modulos gives the remaider of the divsion  
            - eg: 13%3 returns 1
                  15%5 returns 0

- The Parameters: 
    - &grid=1
    > Grid refers to the presence of smaller grid lines, represent as boolean value with 1 is true, 0 is false

    - &plot_style=3
    > These are a list of the default plot_styles it can range from 0-25

    - &x_coord=20
    > The value of the x coordinate (horizontal)

    - &y_coord=20
    > The value of the y coordinate (vertical)

---

### 3. Features

Denzven-Graphing-Api offers a wide range of features for flexible and beautiful graph generation:

#### Supported Graph Types
- **2D Implicit Graphs:** Plot equations of the form `f(x, y) = 0`.
- **Customizable Range:** Set the visible range for both x and y axes.

#### Formula Support
- **Trigonometric functions:** `sin()`, `cos()`, `tan()`
- **Powers:** e.g., `x**2` for x²
- **BODMAS operations:** Parentheses, division, multiplication, addition, subtraction
- **Constants:** `pi`
- **Square root:** `sqrt()`
- **Modulo:** `%` (e.g., `13%3` returns 1)

#### Graph Appearance Customization
- **Grid Lines:**
  - `grid=1` enables major and minor grid lines.
  - `grid=0` disables grid.
  - `grid=2`, `grid=3`, `grid=4` for advanced grid color customization with `grid_lines_major` and `grid_lines_minor` (hex color, no #).
- **Plot Styles:**
  - 26 built-in styles via `plot_style` parameter (0–25):
    - 0: Solarize_Light2
    - 1: _classic_test_patch
    - 2: bmh
    - 3: classic
    - 4: dark_background
    - 5: fast
    - 6: fivethirtyeight
    - 7: ggplot
    - 8: grayscale
    - 9: seaborn
    - 10: seaborn-bright
    - 11: seaborn-colorblind
    - 12: seaborn-dark
    - 13: seaborn-dark-palette
    - 14: seaborn-darkgrid
    - 15: seaborn-deep
    - 16: seaborn-muted
    - 17: seaborn-notebook
    - 18: seaborn-paper
    - 19: seaborn-pastel
    - 20: seaborn-poster
    - 21: seaborn-talk
    - 22: seaborn-ticks
    - 23: seaborn-white
    - 24: seaborn-whitegrid
    - 25: tableau-colorblind10
- **Line Color:**
  - `line_style` sets the graph line color (hex code, no #, e.g., `ff0000` for red).
- **Background Colors:**
  - `axfacecolor` for the plot area, `figfacecolor` for the whole figure (hex code, no #).
- **Title:**
  - `title_text` sets a custom title for your graph.

#### Axis and Tick Customization
- **Axis Range:**
  - `x_coord` and `y_coord` set the visible range for x and y axes (integer values).
- **Axis (Spine) Colors:**
  - `spine_top`, `spine_bottom`, `spine_left`, `spine_right` set the color of each axis line (hex code, no #).
- **Axis Numbers (Tick Labels):**
  - `numbers=1` ensures axis numbers are visible in black, regardless of style.
  - `tick_colors` sets a custom color for axis numbers (hex code, no #).

#### Output
- **Image Download:**
  - The API returns a PNG image of the generated graph.

#### Error Handling
- **Descriptive Error Messages:**
  - If a parameter is missing or invalid, the API returns a helpful error message and suggestions for correction.

#### All Supported Parameters (with values):
| Parameter         | Description                                      | Example Value(s)         |
|-------------------|--------------------------------------------------|--------------------------|
| formula           | The equation to plot (must be f(x, y) = 0)       | x**2+y**2-1              |
| grid              | Show grid lines (0=off, 1=on, 2-4=custom)        | 1                        |
| grid_lines_major  | Major grid line color (hex, no #)                | 999999                   |
| grid_lines_minor  | Minor grid line color (hex, no #)                | 666666                   |
| plot_style        | Plot style index (0-25)                          | 3                        |
| x_coord           | X-axis range (int, symmetric about 0)            | 20                       |
| y_coord           | Y-axis range (int, symmetric about 0)            | 20                       |
| line_style        | Graph line color (hex, no #)                     | ff0000                   |
| axfacecolor       | Plot area background color (hex, no #)           | ffffff                   |
| figfacecolor      | Figure background color (hex, no #)              | ffffff                   |
| title_text        | Custom graph title                               | My Custom Title          |
| spine_top         | Top axis line color (hex, no #)                  | 0000ff                   |
| spine_bottom      | Bottom axis line color (hex, no #)               | 0000ff                   |
| spine_left        | Left axis line color (hex, no #)                 | 0000ff                   |
| spine_right       | Right axis line color (hex, no #)                | 0000ff                   |
| numbers           | Show axis numbers in black (1=on)                | 1                        |
| tick_colors       | Axis number color (hex, no #)                    | 000000                   |

---

### 4. Limitations of the API

The API has several limitations in its use now, and is slowly getting patched/fixed.

Some known ones:
- Limitations in the formula usage: the formula must equate to zero. Like "x+y" as input will mean the graph of "x+y=0" and it must contain both x and y in the equation.  
- Limitations in usable functions: No Absolute function, Min, Max (yet!)
- Currently, the API uses Python's eval() function to evaluate the equations, this will be replaced in the future for the sake of performance and stability

---
### 5. Contributing to the API (if you want to add changes/neaten up the code)

- [Fork the repository](https://github.com/denzven/Denzven-Graphing-Api/fork)
- Clone your fork: `git clone https://github.com/denzven/Denzven-Graphing-Api.git`
- Create your feature branch: `git checkout -b my-new-feature`
- Commit your changes: `git commit -am 'Add some feature'`
- Push to the branch: `git push origin my-new-feature`
- Submit a pull request


### 6. Known Bugs and Issue reporting

- There was a bug by putting exit() or quit() in the formula that would turn off the api.. i have tried my best to patch it

I dont know of any other feel free to add them in!

### 7. About Me

I am a 17 years old wierdo that hops on with tons of hobbies and gets bored easily. Tried out a bunch of stuff like blender3D, voxel art, making discord bots and telegram bots, basic python programs, right now i am making an Graphing API and its wrapper.
you can find more info about me [here](https://denzven.pythonanywhere.com)

Thank you! Hope You can tribute much needed support and enjoy using the api as much i did making it 😁
