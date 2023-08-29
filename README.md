# Warning Stats

Get a summary of warnings found by your toolchain when building your project.

# Requirements

- Python 3.10

## Installation

Clone this repository and put it somewhere (for example `~/warning_stats`).

Install the pip package `warning-parser`:

``` sh
pip install warning-parser
```

Ensure that you can run the tool:

``` sh
~/warning_stats/warning_stats.py --help
```

## Usage

Remove the `-werror` flag temporarly for your project in order to not treat
warnings as errors since we want to get a list of all warnings.

Make a full build of your project and redirect the output to `stderr` into a
file. Perhaps something like this:

``` sh
make clean
make 2> warnings.txt
```

Now, run this tool on the generated file:

``` sh
~/warning_stats/warning_stats.py warnings.txt
```

Now you should see a summary of all the warnings found while building your
project.
