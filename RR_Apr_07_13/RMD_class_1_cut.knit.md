---
title: "(R)Markdown"
author: "Wojciech Hardy; Łukasz Nawaro"
date: "3/23/2022"
output: html_document
---



---

# Cheatsheets are handy as always

`[This one for example](https://raw.githubusercontent.com/rstudio/cheatsheets/master/rmarkdown-2.0.pdf)`

`[Or this one](https://rstudio.com/wp-content/uploads/2015/03/rmarkdown-reference.pdf)`

[This one for example](https://raw.githubusercontent.com/rstudio/cheatsheets/master/rmarkdown-2.0.pdf)

[Or this one](https://rstudio.com/wp-content/uploads/2015/03/rmarkdown-reference.pdf)

---

# Basic formatting

Some basic text formatting includes `*Italics*` or `_Italics_` (*Italics*) and `**Bold**` or `__Bold__` (**Bold**) text. 

`Space between lines to break a paragraph

Like so`

Space between lines to break a paragraph

Like so

`Or end a line with a double space to break  
without starting a new paragraph`

Or end a line with a double space to break  
without starting a new paragraph

Superscripts can be done like so: `R^2^` R^2^

Subscripts can be done like so: `H~2~O` H~2~O

---

# Headers

`# Header 1`

# Header 1

`## Header 2`

## Header 2

`### Header 3`

### Header 3

`#### Header 4`

#### Header 4

`##### Header 5`

##### Header 5

---

# Lists

## Ordered

`1. Item 1`

`2. Item 2`

`2. Item 3 # Note the error in numbering`

1. Item 1

2. Item 2

2. Item 3 `# It's fine here though`


## Unordered

`* Item`

`* Another item`

* Item

* Another item

## Subitems

1. Item 1
    + Item 2
    - Item 3

---

# Tables

| Day       | Hour  | Group  |
|:------    |:-----:|-------:|
| Wednesday | 9:45  | 1      |
| Thursday  | 16:45 | 2      |
| Thursday  | 18:30 | 3      |

---

# Quotes

`> Hmmm`

> Hmmm

\- Geralt of Rivia

--- 

# Using Html

You can also just use html to write stuff within the markdown document. Here's something copied directly from YAML Wikipedia page source code:

<table class="infobox" style="width:22em"><caption style="font-size:130%; padding-bottom:0.15em;">YAML</caption><tbody><tr><td colspan="2" style="text-align:center"><a href="/wiki/File:YAML_Logo.svg" class="image"><img alt="YAML Logo.svg" src="//upload.wikimedia.org/wikipedia/commons/thumb/f/f8/YAML_Logo.svg/250px-YAML_Logo.svg.png" decoding="async" srcset="//upload.wikimedia.org/wikipedia/commons/thumb/f/f8/YAML_Logo.svg/375px-YAML_Logo.svg.png 1.5x, //upload.wikimedia.org/wikipedia/commons/thumb/f/f8/YAML_Logo.svg/500px-YAML_Logo.svg.png 2x" data-file-width="400" data-file-height="138" width="250" height="86"></a></td></tr><tr><th scope="row" style="line-height:1.2em; padding-right:0.65em;"><a href="/wiki/Filename_extension" title="Filename extension">Filename extensions</a></th><td style="line-height:1.35em;"><code class="mw-highlight mw-highlight-lang-text mw-content-ltr" id="" style="" dir="ltr">.yaml</code>, <code class="mw-highlight mw-highlight-lang-text mw-content-ltr" id="" style="" dir="ltr">.yml</code></td></tr><tr><th scope="row" style="line-height:1.2em; padding-right:0.65em;"><a href="/wiki/Media_type" title="Media type">Internet media&nbsp;type</a></th><td style="line-height:1.35em;"><i>Not registered</i></td></tr><tr><th scope="row" style="line-height:1.2em; padding-right:0.65em;">Initial release</th><td style="line-height:1.35em;">11&nbsp;May 2001<span class="noprint">; 19 years ago</span><span style="display:none">&nbsp;(<span class="bday dtstart published updated">2001-05-11</span>)</span></td></tr><tr><th scope="row" style="line-height:1.2em; padding-right:0.65em;"><a href="/wiki/Software_release_life_cycle" title="Software release life cycle">Latest release</a></th><td style="line-height:1.35em;"><div style="display:inline-block; padding:0.1em 0;line-height:1.2em;">1.2 (Third Edition)<br>(1&nbsp;October 2009<span class="noprint">; 11 years ago</span><span style="display:none">&nbsp;(<span class="bday dtstart published updated">2009-10-01</span>)</span>) </div></td></tr><tr><th scope="row" style="line-height:1.2em; padding-right:0.65em;">Type of format</th><td style="line-height:1.35em;">Data interchange</td></tr><tr><th scope="row" style="line-height:1.2em; padding-right:0.65em;"><span class="nowrap"><a href="/wiki/Open_format" title="Open format">Open format</a>?</span></th><td style="line-height:1.35em;">Yes</td></tr><tr><th scope="row" style="line-height:1.2em; padding-right:0.65em;">Website</th><td style="line-height:1.35em;"><span class="url"><a rel="nofollow" class="external text" href="https://yaml.org">yaml<wbr>.org</a></span></td></tr></tbody></table>

---

# Equations

You can insert equations with the same syntax as in LaTeX. E.g. within a sentence `$ \sum (x + 1) $` $\sum (x + 1)$  or as standalone with double `$$` at start and finish

$$\int_{-\infty}^{\infty}1/(b-a) dx$$

# Using R in RMarkdown

The main thing, however, is the ability to integrate R (or other languages):

> \```{r}  
> cat("This is a code chunk")  
> \```


```r
cat("This is a code chunk")
```

```
## This is a code chunk
```


```r
summary(cars)
```

```
##      speed           dist       
##  Min.   : 4.0   Min.   :  2.00  
##  1st Qu.:12.0   1st Qu.: 26.00  
##  Median :15.0   Median : 36.00  
##  Mean   :15.4   Mean   : 42.98  
##  3rd Qu.:19.0   3rd Qu.: 56.00  
##  Max.   :25.0   Max.   :120.00
```


```r
plot(pressure)
```

<img src="RMD_class_1_cut_files/figure-html/unnamed-chunk-3-1.png" width="672" />

And a nice table alternative -> `kable` from the `knitr` package.


```r
knitr::kable(head(mtcars[, 1:4]), caption = "A kable table, ver 1")
```



Table: A kable table, ver 1

|                  |  mpg| cyl| disp|  hp|
|:-----------------|----:|---:|----:|---:|
|Mazda RX4         | 21.0|   6|  160| 110|
|Mazda RX4 Wag     | 21.0|   6|  160| 110|
|Datsun 710        | 22.8|   4|  108|  93|
|Hornet 4 Drive    | 21.4|   6|  258| 110|
|Hornet Sportabout | 18.7|   8|  360| 175|
|Valiant           | 18.1|   6|  225| 105|


```r
knitr::kable(head(mtcars[, 1:4]), "html", caption = "A kable table, ver 2")
```

<table>
<caption>A kable table, ver 2</caption>
 <thead>
  <tr>
   <th style="text-align:left;">   </th>
   <th style="text-align:right;"> mpg </th>
   <th style="text-align:right;"> cyl </th>
   <th style="text-align:right;"> disp </th>
   <th style="text-align:right;"> hp </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> Mazda RX4 </td>
   <td style="text-align:right;"> 21.0 </td>
   <td style="text-align:right;"> 6 </td>
   <td style="text-align:right;"> 160 </td>
   <td style="text-align:right;"> 110 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> Mazda RX4 Wag </td>
   <td style="text-align:right;"> 21.0 </td>
   <td style="text-align:right;"> 6 </td>
   <td style="text-align:right;"> 160 </td>
   <td style="text-align:right;"> 110 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> Datsun 710 </td>
   <td style="text-align:right;"> 22.8 </td>
   <td style="text-align:right;"> 4 </td>
   <td style="text-align:right;"> 108 </td>
   <td style="text-align:right;"> 93 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> Hornet 4 Drive </td>
   <td style="text-align:right;"> 21.4 </td>
   <td style="text-align:right;"> 6 </td>
   <td style="text-align:right;"> 258 </td>
   <td style="text-align:right;"> 110 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> Hornet Sportabout </td>
   <td style="text-align:right;"> 18.7 </td>
   <td style="text-align:right;"> 8 </td>
   <td style="text-align:right;"> 360 </td>
   <td style="text-align:right;"> 175 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> Valiant </td>
   <td style="text-align:right;"> 18.1 </td>
   <td style="text-align:right;"> 6 </td>
   <td style="text-align:right;"> 225 </td>
   <td style="text-align:right;"> 105 </td>
  </tr>
</tbody>
</table>

---

# Code chunks customisation

([Partially taken from here](https://bookdown.org/yihui/rmarkdown-cookbook/hide-one.html))

## Chunk naming (for reference)


```r
"You just put the name after the language declaration"
```

```
## [1] "You just put the name after the language declaration"
```


## Using variables as parameters


```r
typical_width <- 4
typical_height <- 4
```


```r
plot(cars)
```

<img src="RMD_class_1_cut_files/figure-html/unnamed-chunk-7-1.png" width="384" />

## Using variables within the text `'r variable'`

We have previously set a typical width to 4 and the typical height to 4.

## Conditional execution with `eval`

(`is.weekend` comes from the `chrono` package)


```r
cat("It's the weekend! :)")
```


```r
cat("It's not the weekend! :(")
```

```
## It's not the weekend! :(
```

## Caching results that take long to compute

The chunk gets reevaluated if anything changes within the chunk. **Make sure you know what you're doing when caching**. 

We can use `cache.extra =` to specify additional conditions for cache invalidation (i.e. to repeat the calculations), e.g.:

- file.mtime('filename') # Modification time of the file changed

- tools::md5sum('filename') # Content of the file changed

- getRversion() # R version changed

- etc.

Other stuff:

- `cache.comments` -- if you don't want to recalculate after changing a comment.

- `cache.lazy` -- loading with lazyload() instead of load() (see [Lazy loading](https://en.wikipedia.org/wiki/Lazy_loading))

- `cache.path` -- to specify where to save cached stuff

- `cache.vars` -- cache specified objects

- `dependson` -- reevaluate conditional on a change in a different chunk (or chunks)

- `autodep` -- `knitr` will try to find the between-chunk dependencies on its own

## Keeping your report nice and clear

### Hide the source code with `echo=FALSE`


```
## [1] 2
```

### Hide messages (e.g. when loading stuff) with `message=FALSE`


```r
message("You will not see the message.")
```

### Hide warnings with `warning=FALSE`


```r
1:2 + 1:3
```

```
## [1] 2 4 4
```

### Hide plots with `fig.show='hide'`


```r
plot(cars)
```

### Hide everything from the chunk with `include=FALSE`



### Hide the results with `results='hide'`

### Generate Markdown content with R code with `results='asis'`


```r
for (i in 1:10) {
  cat("- Item", i, "\n")
}
```

- Item 1 
- Item 2 
- Item 3 
- Item 4 
- Item 5 
- Item 6 
- Item 7 
- Item 8 
- Item 9 
- Item 10 

### Cluster the results with `results='hold'`

Standard:

```r
x <- 5
y <- 6
x + y
```

```
## [1] 11
```

```r
y - x
```

```
## [1] 1
```

```r
x * y
```

```
## [1] 30
```

With `results='hold'`:

```r
x <- 5
y <- 6
x + y
y - x
x * y
```

```
## [1] 11
## [1] 1
## [1] 30
```

### Compress the output with `collapse=TRUE`

Without

```r
1 + 1
```

```
## [1] 2
```

```r
1:10
```

```
##  [1]  1  2  3  4  5  6  7  8  9 10
```

With

```r
1 + 1
## [1] 2
1:10
##  [1]  1  2  3  4  5  6  7  8  9 10
```

---

# ASSIGNMENT 2 (for 30/31.03.2022)

Pick a TV show that had its premieres on TV and thus has some viewership numbers reported on Wikipedia.
E.g. [Suits](https://en.wikipedia.org/wiki/List_of_Suits_episodes) (see table just above the References)

Then create a short report (you can copy the content from Wikipedia or other pages for this task) that contains, for example:

(do a commit after each step!)

1. A brief description of the show (use _italics_ for names).
2. A photo with the logo or a shot from the show itself.
3. A summary of some basic statistics (e.g. on viewership or ratings).
4. A graph of the viewership over time.
5. A graph of the episode-to-episode (or season-to-season) changes in viewership.
6. A short description of the observed changes that includes inline references to numbers (e.g. the viewership decreased by `insert_calculated_number` between seasons 3 and 5).
7. Make sure your report looks nice -> this time we're mostly interested in the output and not necessarily the codes used to achieve it.
7. `knitr` your report and save it in the relevant folder (RR_Mar_30_31) of your repo. 
8. Commit the changes and push them to Github.

### Some other chunk options

E.g.:

- `highlight` -- syntax coloring

- `tidy`-- clean and format the code based on, e.g. `formatR` or `styler`, with specific options defined by `tidy.opts`

For chunks with figures, e.g.:

- `fig.align` -- alignment

- `fig.ext` -- image format

- `dev` -- graphical device for the plot generation

- `dev.args`-- arguments to be passed to device (e.g. for image customisation)

- `dpi` -- DPI

You can, e.g., combine the above to produce images in DPI resolution and format appropriate for a publication.
