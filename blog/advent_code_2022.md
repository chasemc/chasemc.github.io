Advent of Code 2022
================

R and Python answers to https://adventofcode.com/2022

Code isn’t meant to be pretty or performant. Just a quick,
no-dependency, first-thought, first-pass effort at getting a solution.

<style>.awk::before {
            content: 'AWK';
            display: block;
            text-align: right;
            }
.bash::before {
            content: 'BASH';
            display: block;
            text-align: right;
            }
.coffee::before {
            content: 'COFFEE';
            display: block;
            text-align: right;
            }
.gawk::before {
            content: 'GAWK';
            display: block;
            text-align: right;
            }
.groovy::before {
            content: 'GROOVY';
            display: block;
            text-align: right;
            }
.haskell::before {
            content: 'HASKELL';
            display: block;
            text-align: right;
            }
.lein::before {
            content: 'LEIN';
            display: block;
            text-align: right;
            }
.mysql::before {
            content: 'MYSQL';
            display: block;
            text-align: right;
            }
.node::before {
            content: 'NODE';
            display: block;
            text-align: right;
            }
.octave::before {
            content: 'OCTAVE';
            display: block;
            text-align: right;
            }
.perl::before {
            content: 'PERL';
            display: block;
            text-align: right;
            }
.php::before {
            content: 'PHP';
            display: block;
            text-align: right;
            }
.psql::before {
            content: 'PSQL';
            display: block;
            text-align: right;
            }
.rscript::before {
            content: 'RSCRIPT';
            display: block;
            text-align: right;
            }
.ruby::before {
            content: 'RUBY';
            display: block;
            text-align: right;
            }
.sas::before {
            content: 'SAS';
            display: block;
            text-align: right;
            }
.scala::before {
            content: 'SCALA';
            display: block;
            text-align: right;
            }
.sed::before {
            content: 'SED';
            display: block;
            text-align: right;
            }
.sh::before {
            content: 'SH';
            display: block;
            text-align: right;
            }
.stata::before {
            content: 'STATA';
            display: block;
            text-align: right;
            }
.zsh::before {
            content: 'ZSH';
            display: block;
            text-align: right;
            }
.asis::before {
            content: 'ASIS';
            display: block;
            text-align: right;
            }
.asy::before {
            content: 'ASY';
            display: block;
            text-align: right;
            }
.block::before {
            content: 'BLOCK';
            display: block;
            text-align: right;
            }
.block2::before {
            content: 'BLOCK2';
            display: block;
            text-align: right;
            }
.bslib::before {
            content: 'BSLIB';
            display: block;
            text-align: right;
            }
.c::before {
            content: 'C';
            display: block;
            text-align: right;
            }
.cat::before {
            content: 'CAT';
            display: block;
            text-align: right;
            }
.cc::before {
            content: 'CC';
            display: block;
            text-align: right;
            }
.comment::before {
            content: 'COMMENT';
            display: block;
            text-align: right;
            }
.css::before {
            content: 'CSS';
            display: block;
            text-align: right;
            }
.ditaa::before {
            content: 'DITAA';
            display: block;
            text-align: right;
            }
.dot::before {
            content: 'DOT';
            display: block;
            text-align: right;
            }
.embed::before {
            content: 'EMBED';
            display: block;
            text-align: right;
            }
.eviews::before {
            content: 'EVIEWS';
            display: block;
            text-align: right;
            }
.exec::before {
            content: 'EXEC';
            display: block;
            text-align: right;
            }
.fortran::before {
            content: 'FORTRAN';
            display: block;
            text-align: right;
            }
.fortran95::before {
            content: 'FORTRAN95';
            display: block;
            text-align: right;
            }
.go::before {
            content: 'GO';
            display: block;
            text-align: right;
            }
.highlight::before {
            content: 'HIGHLIGHT';
            display: block;
            text-align: right;
            }
.js::before {
            content: 'JS';
            display: block;
            text-align: right;
            }
.julia::before {
            content: 'JULIA';
            display: block;
            text-align: right;
            }
.python::before {
            content: 'PYTHON';
            display: block;
            text-align: right;
            }
.r::before {
            content: 'R';
            display: block;
            text-align: right;
            }
.rcpp::before {
            content: 'RCPP';
            display: block;
            text-align: right;
            }
.sass::before {
            content: 'SASS';
            display: block;
            text-align: right;
            }
.scss::before {
            content: 'SCSS';
            display: block;
            text-align: right;
            }
.sql::before {
            content: 'SQL';
            display: block;
            text-align: right;
            }
.stan::before {
            content: 'STAN';
            display: block;
            text-align: right;
            }
.targets::before {
            content: 'TARGETS';
            display: block;
            text-align: right;
            }
.tikz::before {
            content: 'TIKZ';
            display: block;
            text-align: right;
            }
.verbatim::before {
            content: 'VERBATIM';
            display: block;
            text-align: right;
            }
.ojs::before {
            content: 'OJS';
            display: block;
            text-align: right;
            }
.mermaid::before {
            content: 'MERMAID';
            display: block;
            text-align: right;
            }
.include::before {
            content: 'INCLUDE';
            display: block;
            text-align: right;
            }</style>

## Day 1

### Question 1

https://adventofcode.com/2022/day/1

``` r
prompt_data <- "/home/chase/Downloads/input.txt"
input <- readChar(prompt_data, file.info(prompt_data)$size)
input <- strsplit(input, "\n\n")[[1]]
cals <- vapply(input, function(x) sum(as.integer(strsplit(x, "\n")[[1]])), 1,USE.NAMES = F)
cals[which.max(cals)]
```

    [1] 72511

``` python
prompt_data = "/home/chase/Downloads/input.txt"

current_calories = 0
current_max = 0

with open( "/home/chase/Downloads/input.txt") as fp:
    for line in fp:
        if line == "\n":
            if current_calories > current_max:
                current_max = current_calories
            current_calories = 0
        else:
            current_calories += int(line)
print(current_max)            
```

    72511

### Question 2

https://adventofcode.com/2022/day/1#part2

``` r
prompt_data <- "/home/chase/Downloads/input.txt"
input <- readChar(prompt_data, file.info(prompt_data)$size)
input <- strsplit(input, "\n\n")[[1]]
cals <- vapply(input, function(x) sum(as.integer(strsplit(x, "\n")[[1]])), 1,USE.NAMES = F)
top_three <- sort(cals, decreasing = T)[1:3]
sum(top_three)
```

    [1] 212117

``` python
prompt_data = "/home/chase/Downloads/input.txt"

current_calories = 0
cal_list = []
with open( "/home/chase/Downloads/input.txt") as fp:
    for line in fp:
        if line == "\n":
            cal_list.append(current_calories)
            current_calories = 0
        else:
            current_calories += int(line)
top_three = sorted(cal_list, reverse=True)[0:3]
print(sum(top_three))
```

    212117
