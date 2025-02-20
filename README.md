# Project description

This is the source code for the project **Objective, subjective, and accurate reporting of social media use: No evidence that daily social media use correlates with personality traits, motivational states, or well-being**.

Link to the preprint: <>

## Data and models
The data and models are on the Open Science Framework page of this project at <https://osf.io/7byvt/>.
Here, we also provide a codebook for the data and materials that show how we collected the data.
You'll see that there are different components.
One component holds the raw data.
These data were minimally processed before uploading to remove other variables that aren't relevant to this project.
You can see those processing steps in the processing section on the next page.

Another component holds model objects.
We ran ten total models, and each one is between 18 and 122 MB large.
You'll see in the analysis section that we downloaded those models and loaded them into R for model inspection and diagnostics.

## How to reproduce processing and analyses
All processing, analysis, description, and modelling steps are organized into separate [R Markdown](https://rmarkdown.rstudio.com/) files.
The source code is on GitHub: <https://github.com/digital-wellbeing/smartphone-use> (aka here).
Those source files are organized as an R [bookdown](https://bookdown.org/yihui/bookdown/) project.
That project was knitted to an online book, whose results are at <https://digital-wellbeing.github.io/smartphone-use/>.
The project used a local library to make sure package versions are stable for anyone who wants reproduce the analysis.
We used [renv](https://rstudio.github.io/renv/articles/renv.html) for that.

If you want to reproduce the entire book, it's best to download the entire R project from the Github repo: <https://github.com/digital-wellbeing/smartphone-use>.
As a first step, open the project and make sure you have all packages installed in the right version by calling `renv::restore()`.
That'll install all packages in the version that are saved in the lockfile of the project (`renv.lock`).
For that, it's best if you are on R 4.0.3 or higher.

Once all packages are installed, you should be able to build the book and reproduce all files that are displayed at <https://digital-wellbeing.github.io/smartphone-use/>.
To do that, either run `bookdown::render_book("index.Rmd")` or click the "Build Book" button under the `Build` tab in RStudio.
Each `.Rmd` source file will be knitted and stored in a `docs` folder.
You can double click on `docs/index.html` and view the results in a web browser.

You'll see that the source code doesn't run the models anymore.
In total, running each chunk would take several hours.
I ran them once and them stored them on the OSF.
In the source code, you can download those files (note: downloading the models will take some time, they're about half a GB in total).
To download the models, make sure the chunk option for chunk `download-models` in the analysis chapter is set to `eval=TRUE`.

If you want to run the models rather than downloading them and loading them into R, you can either set chunk options to `eval=TRUE` or run each of the five `.Rmd` files separately.
I set this book up so that it runs in one go, meaning you need to run the source files in their order, and can't run source files independently.

The same goes for the data: You'll need to set the chunk `download-data` to `eval=TRUE` (it's currently set to `TRUE` by default).
That only works when the OSF project is public.
If it isn't (because of peer review), you'll need to manually download the data files from the OSF into a `data/` folder in the main directory of the project.

