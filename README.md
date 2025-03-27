# Baby Name Statistics

This is a personal data science project which uses simple SSA data to the names given to newly born babies in the U.S. over the last 140 years. 

It is an attempt to make a more-complete, easier to use, and more accurate version of the tools on <a href="https://www.ssa.gov/oact/babynames/index.html">this page</a>

## Input Data
Data was collected from data.gov, and is included in this repo in .zip files:

* Baby Names from Social Security Card Applications - National Data: <a href="https://catalog.data.gov/dataset/baby-names-from-social-security-card-applications-national-data">Data.gov</a>
* Actuarial Death Tables: <a href="https://www.ssa.gov/oact/HistEst/Death/2014/DeathProbabilities2014.html">SSA.gov</a> (This can also be found on data.gov, but not in a single location)

## Processing & Caveats

Pandas does the heavy lifting in this project. The birth data is easily used as-is, but the death tables are transformed in several tricky ways to collect an estimate of the number of people currently alive with each name, their average ages, and how many die each year. These are <strong> wild guesses </strong>, due in no small part to the limitations of the birth name data used. See ssa.gov for caveats on this data. Here are a few of them:

* The SSA does not publish the names of babies born if there were less than 5 babies born with that names. Considering the long tail on baby name distributions, this is a lot of babies.
* This is based on SSA birth certificate applications. There are, in fact, a lot of people in this country who don't have a U.S. birth certificate for lots of reasons.
* The actuarial death tables are estimates, not based on real data. Therefore anything using those estimates cannot be considered trustworthy.

## Running at home

You'll just need a python 3.9 instance, ideally in a venv, with pandas, glob, and re. The jupyter notebook files will run in VSCode with the Jupyter extension.