---
title: "Supplemental"
---


Create supplemental information tables and figures.

Load packages and read in the saved models.


::: {.cell}

```{.r .cell-code}
library(tidyverse)
```

::: {.cell-output .cell-output-stderr}
```
Warning: package 'tidyverse' was built under R version 4.2.1
```
:::

::: {.cell-output .cell-output-stderr}
```
── Attaching packages ─────────────────────────────────────── tidyverse 1.3.2 ──
✔ ggplot2 3.4.0     ✔ purrr   1.0.1
✔ tibble  3.2.1     ✔ dplyr   1.1.4
✔ tidyr   1.3.0     ✔ stringr 1.5.0
✔ readr   2.1.2     ✔ forcats 0.5.2
```
:::

::: {.cell-output .cell-output-stderr}
```
Warning: package 'ggplot2' was built under R version 4.2.2
```
:::

::: {.cell-output .cell-output-stderr}
```
Warning: package 'tibble' was built under R version 4.2.3
```
:::

::: {.cell-output .cell-output-stderr}
```
Warning: package 'tidyr' was built under R version 4.2.2
```
:::

::: {.cell-output .cell-output-stderr}
```
Warning: package 'readr' was built under R version 4.2.1
```
:::

::: {.cell-output .cell-output-stderr}
```
Warning: package 'purrr' was built under R version 4.2.2
```
:::

::: {.cell-output .cell-output-stderr}
```
Warning: package 'dplyr' was built under R version 4.2.3
```
:::

::: {.cell-output .cell-output-stderr}
```
Warning: package 'stringr' was built under R version 4.2.2
```
:::

::: {.cell-output .cell-output-stderr}
```
Warning: package 'forcats' was built under R version 4.2.1
```
:::

::: {.cell-output .cell-output-stderr}
```
── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
✖ dplyr::filter() masks stats::filter()
✖ dplyr::lag()    masks stats::lag()
```
:::

```{.r .cell-code}
library(brms)
```

::: {.cell-output .cell-output-stderr}
```
Warning: package 'brms' was built under R version 4.2.3
```
:::

::: {.cell-output .cell-output-stderr}
```
Loading required package: Rcpp
```
:::

::: {.cell-output .cell-output-stderr}
```
Warning: package 'Rcpp' was built under R version 4.2.3
```
:::

::: {.cell-output .cell-output-stderr}
```
Loading 'brms' package (version 2.21.0). Useful instructions
can be found by typing help('brms'). A more detailed introduction
to the package is available through vignette('brms_overview').

Attaching package: 'brms'

The following object is masked from 'package:stats':

    ar
```
:::

```{.r .cell-code}
library(ggpubr)
```

::: {.cell-output .cell-output-stderr}
```
Warning: package 'ggpubr' was built under R version 4.2.3
```
:::

```{.r .cell-code}
library(gt)
```

::: {.cell-output .cell-output-stderr}
```
Warning: package 'gt' was built under R version 4.2.3
```
:::

```{.r .cell-code}
bb_m <- readRDS("data/blackBrown_phylo_m1_nestedRI_spatialTerm.rds")
by_m <- readRDS("data/brownYellow_phylo_m1_nestedRI_spatialTerm.rds")
```
:::


Create model summary tables.


::: {.cell}

```{.r .cell-code}
bb_summary <- summary(bb_m, prob = 0.95)$fixed %>% 
  tibble::rownames_to_column()
by_summary <- summary(by_m, prob = 0.95)$fixed %>% 
  tibble::rownames_to_column()
```

::: {.cell-output .cell-output-stderr}
```
Warning: There were 1 divergent transitions after warmup. Increasing
adapt_delta above 0.99 may help. See
http://mc-stan.org/misc/warnings.html#divergent-transitions-after-warmup
```
:::

```{.r .cell-code}
bb_table <- gt(bb_summary)
by_table <- gt(by_summary) 

bb_table
```

::: {.cell-output-display}
```{=html}
<div id="pnwczpbtsl" style="padding-left:0px;padding-right:0px;padding-top:10px;padding-bottom:10px;overflow-x:auto;overflow-y:auto;width:auto;height:auto;">
<style>#pnwczpbtsl table {
  font-family: system-ui, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji', 'Segoe UI Symbol', 'Noto Color Emoji';
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

#pnwczpbtsl thead, #pnwczpbtsl tbody, #pnwczpbtsl tfoot, #pnwczpbtsl tr, #pnwczpbtsl td, #pnwczpbtsl th {
  border-style: none;
}

#pnwczpbtsl p {
  margin: 0;
  padding: 0;
}

#pnwczpbtsl .gt_table {
  display: table;
  border-collapse: collapse;
  line-height: normal;
  margin-left: auto;
  margin-right: auto;
  color: #333333;
  font-size: 16px;
  font-weight: normal;
  font-style: normal;
  background-color: #FFFFFF;
  width: auto;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #A8A8A8;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #A8A8A8;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
}

#pnwczpbtsl .gt_caption {
  padding-top: 4px;
  padding-bottom: 4px;
}

#pnwczpbtsl .gt_title {
  color: #333333;
  font-size: 125%;
  font-weight: initial;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 5px;
  padding-right: 5px;
  border-bottom-color: #FFFFFF;
  border-bottom-width: 0;
}

#pnwczpbtsl .gt_subtitle {
  color: #333333;
  font-size: 85%;
  font-weight: initial;
  padding-top: 3px;
  padding-bottom: 5px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-color: #FFFFFF;
  border-top-width: 0;
}

#pnwczpbtsl .gt_heading {
  background-color: #FFFFFF;
  text-align: center;
  border-bottom-color: #FFFFFF;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
}

#pnwczpbtsl .gt_bottom_border {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#pnwczpbtsl .gt_col_headings {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
}

#pnwczpbtsl .gt_col_heading {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: normal;
  text-transform: inherit;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: bottom;
  padding-top: 5px;
  padding-bottom: 6px;
  padding-left: 5px;
  padding-right: 5px;
  overflow-x: hidden;
}

#pnwczpbtsl .gt_column_spanner_outer {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: normal;
  text-transform: inherit;
  padding-top: 0;
  padding-bottom: 0;
  padding-left: 4px;
  padding-right: 4px;
}

#pnwczpbtsl .gt_column_spanner_outer:first-child {
  padding-left: 0;
}

#pnwczpbtsl .gt_column_spanner_outer:last-child {
  padding-right: 0;
}

#pnwczpbtsl .gt_column_spanner {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  vertical-align: bottom;
  padding-top: 5px;
  padding-bottom: 5px;
  overflow-x: hidden;
  display: inline-block;
  width: 100%;
}

#pnwczpbtsl .gt_spanner_row {
  border-bottom-style: hidden;
}

#pnwczpbtsl .gt_group_heading {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: middle;
  text-align: left;
}

#pnwczpbtsl .gt_empty_group_heading {
  padding: 0.5px;
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  vertical-align: middle;
}

#pnwczpbtsl .gt_from_md > :first-child {
  margin-top: 0;
}

#pnwczpbtsl .gt_from_md > :last-child {
  margin-bottom: 0;
}

#pnwczpbtsl .gt_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  margin: 10px;
  border-top-style: solid;
  border-top-width: 1px;
  border-top-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: middle;
  overflow-x: hidden;
}

#pnwczpbtsl .gt_stub {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  padding-left: 5px;
  padding-right: 5px;
}

#pnwczpbtsl .gt_stub_row_group {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  padding-left: 5px;
  padding-right: 5px;
  vertical-align: top;
}

#pnwczpbtsl .gt_row_group_first td {
  border-top-width: 2px;
}

#pnwczpbtsl .gt_row_group_first th {
  border-top-width: 2px;
}

#pnwczpbtsl .gt_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}

#pnwczpbtsl .gt_first_summary_row {
  border-top-style: solid;
  border-top-color: #D3D3D3;
}

#pnwczpbtsl .gt_first_summary_row.thick {
  border-top-width: 2px;
}

#pnwczpbtsl .gt_last_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#pnwczpbtsl .gt_grand_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}

#pnwczpbtsl .gt_first_grand_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-style: double;
  border-top-width: 6px;
  border-top-color: #D3D3D3;
}

#pnwczpbtsl .gt_last_grand_summary_row_top {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-bottom-style: double;
  border-bottom-width: 6px;
  border-bottom-color: #D3D3D3;
}

#pnwczpbtsl .gt_striped {
  background-color: rgba(128, 128, 128, 0.05);
}

#pnwczpbtsl .gt_table_body {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#pnwczpbtsl .gt_footnotes {
  color: #333333;
  background-color: #FFFFFF;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
}

#pnwczpbtsl .gt_footnote {
  margin: 0px;
  font-size: 90%;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 5px;
  padding-right: 5px;
}

#pnwczpbtsl .gt_sourcenotes {
  color: #333333;
  background-color: #FFFFFF;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
}

#pnwczpbtsl .gt_sourcenote {
  font-size: 90%;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 5px;
  padding-right: 5px;
}

#pnwczpbtsl .gt_left {
  text-align: left;
}

#pnwczpbtsl .gt_center {
  text-align: center;
}

#pnwczpbtsl .gt_right {
  text-align: right;
  font-variant-numeric: tabular-nums;
}

#pnwczpbtsl .gt_font_normal {
  font-weight: normal;
}

#pnwczpbtsl .gt_font_bold {
  font-weight: bold;
}

#pnwczpbtsl .gt_font_italic {
  font-style: italic;
}

#pnwczpbtsl .gt_super {
  font-size: 65%;
}

#pnwczpbtsl .gt_footnote_marks {
  font-size: 75%;
  vertical-align: 0.4em;
  position: initial;
}

#pnwczpbtsl .gt_asterisk {
  font-size: 100%;
  vertical-align: 0;
}

#pnwczpbtsl .gt_indent_1 {
  text-indent: 5px;
}

#pnwczpbtsl .gt_indent_2 {
  text-indent: 10px;
}

#pnwczpbtsl .gt_indent_3 {
  text-indent: 15px;
}

#pnwczpbtsl .gt_indent_4 {
  text-indent: 20px;
}

#pnwczpbtsl .gt_indent_5 {
  text-indent: 25px;
}
</style>
<table class="gt_table" data-quarto-disable-processing="false" data-quarto-bootstrap="false">
  <thead>
    <tr class="gt_col_headings">
      <th class="gt_col_heading gt_columns_bottom_border gt_left" rowspan="1" colspan="1" scope="col" id=""></th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1" scope="col" id="Estimate">Estimate</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1" scope="col" id="Est.Error">Est.Error</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1" scope="col" id="l-95% CI">l-95% CI</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1" scope="col" id="u-95% CI">u-95% CI</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1" scope="col" id="Rhat">Rhat</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1" scope="col" id="Bulk_ESS">Bulk_ESS</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1" scope="col" id="Tail_ESS">Tail_ESS</th>
    </tr>
  </thead>
  <tbody class="gt_table_body">
    <tr><th id="stub_1_1" scope="row" class="gt_row gt_left gt_stub">Intercept</th>
<td headers="stub_1_1 Estimate" class="gt_row gt_right">-4.5276651315</td>
<td headers="stub_1_1 Est.Error" class="gt_row gt_right">1.10928675</td>
<td headers="stub_1_1 l-95% CI" class="gt_row gt_right">-6.66226225</td>
<td headers="stub_1_1 u-95% CI" class="gt_row gt_right">-2.3178460000</td>
<td headers="stub_1_1 Rhat" class="gt_row gt_right">1.0006397</td>
<td headers="stub_1_1 Bulk_ESS" class="gt_row gt_right">2115.302</td>
<td headers="stub_1_1 Tail_ESS" class="gt_row gt_right">3242.603</td></tr>
    <tr><th id="stub_1_2" scope="row" class="gt_row gt_left gt_stub">phi_Intercept</th>
<td headers="stub_1_2 Estimate" class="gt_row gt_right">6.0830381025</td>
<td headers="stub_1_2 Est.Error" class="gt_row gt_right">0.16486777</td>
<td headers="stub_1_2 l-95% CI" class="gt_row gt_right">5.75841025</td>
<td headers="stub_1_2 u-95% CI" class="gt_row gt_right">6.4140777500</td>
<td headers="stub_1_2 Rhat" class="gt_row gt_right">1.0038106</td>
<td headers="stub_1_2 Bulk_ESS" class="gt_row gt_right">1294.990</td>
<td headers="stub_1_2 Tail_ESS" class="gt_row gt_right">2430.175</td></tr>
    <tr><th id="stub_1_3" scope="row" class="gt_row gt_left gt_stub">zi_Intercept</th>
<td headers="stub_1_3 Estimate" class="gt_row gt_right">2.7071448433</td>
<td headers="stub_1_3 Est.Error" class="gt_row gt_right">0.71236662</td>
<td headers="stub_1_3 l-95% CI" class="gt_row gt_right">1.29290275</td>
<td headers="stub_1_3 u-95% CI" class="gt_row gt_right">4.0606865000</td>
<td headers="stub_1_3 Rhat" class="gt_row gt_right">1.0021717</td>
<td headers="stub_1_3 Bulk_ESS" class="gt_row gt_right">1320.824</td>
<td headers="stub_1_3 Tail_ESS" class="gt_row gt_right">1968.450</td></tr>
    <tr><th id="stub_1_4" scope="row" class="gt_row gt_left gt_stub">wing_length</th>
<td headers="stub_1_4 Estimate" class="gt_row gt_right">0.2162540673</td>
<td headers="stub_1_4 Est.Error" class="gt_row gt_right">0.05464696</td>
<td headers="stub_1_4 l-95% CI" class="gt_row gt_right">0.11214380</td>
<td headers="stub_1_4 u-95% CI" class="gt_row gt_right">0.3256864000</td>
<td headers="stub_1_4 Rhat" class="gt_row gt_right">1.0003217</td>
<td headers="stub_1_4 Bulk_ESS" class="gt_row gt_right">5283.045</td>
<td headers="stub_1_4 Tail_ESS" class="gt_row gt_right">5098.930</td></tr>
    <tr><th id="stub_1_5" scope="row" class="gt_row gt_left gt_stub">temp_indv</th>
<td headers="stub_1_5 Estimate" class="gt_row gt_right">0.0987507107</td>
<td headers="stub_1_5 Est.Error" class="gt_row gt_right">0.06964641</td>
<td headers="stub_1_5 l-95% CI" class="gt_row gt_right">-0.04429018</td>
<td headers="stub_1_5 u-95% CI" class="gt_row gt_right">0.2344792250</td>
<td headers="stub_1_5 Rhat" class="gt_row gt_right">1.0019513</td>
<td headers="stub_1_5 Bulk_ESS" class="gt_row gt_right">4228.509</td>
<td headers="stub_1_5 Tail_ESS" class="gt_row gt_right">5204.969</td></tr>
    <tr><th id="stub_1_6" scope="row" class="gt_row gt_left gt_stub">flight_typepercher</th>
<td headers="stub_1_6 Estimate" class="gt_row gt_right">1.1159524019</td>
<td headers="stub_1_6 Est.Error" class="gt_row gt_right">0.57493738</td>
<td headers="stub_1_6 l-95% CI" class="gt_row gt_right">-0.01822978</td>
<td headers="stub_1_6 u-95% CI" class="gt_row gt_right">2.2189372500</td>
<td headers="stub_1_6 Rhat" class="gt_row gt_right">1.0003200</td>
<td headers="stub_1_6 Bulk_ESS" class="gt_row gt_right">3082.211</td>
<td headers="stub_1_6 Tail_ESS" class="gt_row gt_right">4670.462</td></tr>
    <tr><th id="stub_1_7" scope="row" class="gt_row gt_left gt_stub">sexM</th>
<td headers="stub_1_7 Estimate" class="gt_row gt_right">-0.1211839210</td>
<td headers="stub_1_7 Est.Error" class="gt_row gt_right">0.05790818</td>
<td headers="stub_1_7 l-95% CI" class="gt_row gt_right">-0.22797303</td>
<td headers="stub_1_7 u-95% CI" class="gt_row gt_right">-0.0002941049</td>
<td headers="stub_1_7 Rhat" class="gt_row gt_right">0.9998385</td>
<td headers="stub_1_7 Bulk_ESS" class="gt_row gt_right">5503.419</td>
<td headers="stub_1_7 Tail_ESS" class="gt_row gt_right">5178.731</td></tr>
    <tr><th id="stub_1_8" scope="row" class="gt_row gt_left gt_stub">temp_indv:flight_typepercher</th>
<td headers="stub_1_8 Estimate" class="gt_row gt_right">0.0258943923</td>
<td headers="stub_1_8 Est.Error" class="gt_row gt_right">0.05962403</td>
<td headers="stub_1_8 l-95% CI" class="gt_row gt_right">-0.08648277</td>
<td headers="stub_1_8 u-95% CI" class="gt_row gt_right">0.1511635000</td>
<td headers="stub_1_8 Rhat" class="gt_row gt_right">1.0016008</td>
<td headers="stub_1_8 Bulk_ESS" class="gt_row gt_right">4740.096</td>
<td headers="stub_1_8 Tail_ESS" class="gt_row gt_right">5384.486</td></tr>
    <tr><th id="stub_1_9" scope="row" class="gt_row gt_left gt_stub">flight_typepercher:sexM</th>
<td headers="stub_1_9 Estimate" class="gt_row gt_right">0.1733500388</td>
<td headers="stub_1_9 Est.Error" class="gt_row gt_right">0.06160333</td>
<td headers="stub_1_9 l-95% CI" class="gt_row gt_right">0.04843533</td>
<td headers="stub_1_9 u-95% CI" class="gt_row gt_right">0.2898606500</td>
<td headers="stub_1_9 Rhat" class="gt_row gt_right">0.9996731</td>
<td headers="stub_1_9 Bulk_ESS" class="gt_row gt_right">6024.413</td>
<td headers="stub_1_9 Tail_ESS" class="gt_row gt_right">5426.507</td></tr>
    <tr><th id="stub_1_10" scope="row" class="gt_row gt_left gt_stub">phi_temp_indv</th>
<td headers="stub_1_10 Estimate" class="gt_row gt_right">-0.3322417266</td>
<td headers="stub_1_10 Est.Error" class="gt_row gt_right">0.07123384</td>
<td headers="stub_1_10 l-95% CI" class="gt_row gt_right">-0.47360107</td>
<td headers="stub_1_10 u-95% CI" class="gt_row gt_right">-0.1958198250</td>
<td headers="stub_1_10 Rhat" class="gt_row gt_right">1.0012592</td>
<td headers="stub_1_10 Bulk_ESS" class="gt_row gt_right">4637.632</td>
<td headers="stub_1_10 Tail_ESS" class="gt_row gt_right">5842.396</td></tr>
    <tr><th id="stub_1_11" scope="row" class="gt_row gt_left gt_stub">zi_wing_length</th>
<td headers="stub_1_11 Estimate" class="gt_row gt_right">-1.5268252261</td>
<td headers="stub_1_11 Est.Error" class="gt_row gt_right">0.22061660</td>
<td headers="stub_1_11 l-95% CI" class="gt_row gt_right">-1.97057350</td>
<td headers="stub_1_11 u-95% CI" class="gt_row gt_right">-1.0910855000</td>
<td headers="stub_1_11 Rhat" class="gt_row gt_right">1.0007466</td>
<td headers="stub_1_11 Bulk_ESS" class="gt_row gt_right">2406.234</td>
<td headers="stub_1_11 Tail_ESS" class="gt_row gt_right">3399.187</td></tr>
    <tr><th id="stub_1_12" scope="row" class="gt_row gt_left gt_stub">zi_temp_indv</th>
<td headers="stub_1_12 Estimate" class="gt_row gt_right">0.6003061364</td>
<td headers="stub_1_12 Est.Error" class="gt_row gt_right">0.08974760</td>
<td headers="stub_1_12 l-95% CI" class="gt_row gt_right">0.42425603</td>
<td headers="stub_1_12 u-95% CI" class="gt_row gt_right">0.7753026500</td>
<td headers="stub_1_12 Rhat" class="gt_row gt_right">1.0000832</td>
<td headers="stub_1_12 Bulk_ESS" class="gt_row gt_right">5020.524</td>
<td headers="stub_1_12 Tail_ESS" class="gt_row gt_right">5120.373</td></tr>
    <tr><th id="stub_1_13" scope="row" class="gt_row gt_left gt_stub">zi_flight_typepercher</th>
<td headers="stub_1_13 Estimate" class="gt_row gt_right">-0.4463208730</td>
<td headers="stub_1_13 Est.Error" class="gt_row gt_right">0.76793695</td>
<td headers="stub_1_13 l-95% CI" class="gt_row gt_right">-1.91479875</td>
<td headers="stub_1_13 u-95% CI" class="gt_row gt_right">1.1059605000</td>
<td headers="stub_1_13 Rhat" class="gt_row gt_right">1.0006828</td>
<td headers="stub_1_13 Bulk_ESS" class="gt_row gt_right">1069.864</td>
<td headers="stub_1_13 Tail_ESS" class="gt_row gt_right">2129.942</td></tr>
    <tr><th id="stub_1_14" scope="row" class="gt_row gt_left gt_stub">zi_sexM</th>
<td headers="stub_1_14 Estimate" class="gt_row gt_right">-1.0250841575</td>
<td headers="stub_1_14 Est.Error" class="gt_row gt_right">0.10822225</td>
<td headers="stub_1_14 l-95% CI" class="gt_row gt_right">-1.24250275</td>
<td headers="stub_1_14 u-95% CI" class="gt_row gt_right">-0.8182290000</td>
<td headers="stub_1_14 Rhat" class="gt_row gt_right">1.0006139</td>
<td headers="stub_1_14 Bulk_ESS" class="gt_row gt_right">8499.190</td>
<td headers="stub_1_14 Tail_ESS" class="gt_row gt_right">5986.850</td></tr>
    <tr><th id="stub_1_15" scope="row" class="gt_row gt_left gt_stub">t2latRoundlonRound_1</th>
<td headers="stub_1_15 Estimate" class="gt_row gt_right">-0.0007196809</td>
<td headers="stub_1_15 Est.Error" class="gt_row gt_right">0.03642289</td>
<td headers="stub_1_15 l-95% CI" class="gt_row gt_right">-0.07521080</td>
<td headers="stub_1_15 u-95% CI" class="gt_row gt_right">0.0683186875</td>
<td headers="stub_1_15 Rhat" class="gt_row gt_right">1.0011127</td>
<td headers="stub_1_15 Bulk_ESS" class="gt_row gt_right">4270.392</td>
<td headers="stub_1_15 Tail_ESS" class="gt_row gt_right">5035.483</td></tr>
    <tr><th id="stub_1_16" scope="row" class="gt_row gt_left gt_stub">t2latRoundlonRound_2</th>
<td headers="stub_1_16 Estimate" class="gt_row gt_right">-0.1438599316</td>
<td headers="stub_1_16 Est.Error" class="gt_row gt_right">0.06217080</td>
<td headers="stub_1_16 l-95% CI" class="gt_row gt_right">-0.27109870</td>
<td headers="stub_1_16 u-95% CI" class="gt_row gt_right">-0.0269602675</td>
<td headers="stub_1_16 Rhat" class="gt_row gt_right">1.0004217</td>
<td headers="stub_1_16 Bulk_ESS" class="gt_row gt_right">4819.822</td>
<td headers="stub_1_16 Tail_ESS" class="gt_row gt_right">5708.773</td></tr>
    <tr><th id="stub_1_17" scope="row" class="gt_row gt_left gt_stub">t2latRoundlonRound_3</th>
<td headers="stub_1_17 Estimate" class="gt_row gt_right">0.0045874120</td>
<td headers="stub_1_17 Est.Error" class="gt_row gt_right">0.03784004</td>
<td headers="stub_1_17 l-95% CI" class="gt_row gt_right">-0.06991745</td>
<td headers="stub_1_17 u-95% CI" class="gt_row gt_right">0.0805199650</td>
<td headers="stub_1_17 Rhat" class="gt_row gt_right">1.0007402</td>
<td headers="stub_1_17 Bulk_ESS" class="gt_row gt_right">4551.943</td>
<td headers="stub_1_17 Tail_ESS" class="gt_row gt_right">4997.438</td></tr>
  </tbody>
  
  
</table>
</div>
```
:::

```{.r .cell-code}
by_table
```

::: {.cell-output-display}
```{=html}
<div id="mpctzawnfl" style="padding-left:0px;padding-right:0px;padding-top:10px;padding-bottom:10px;overflow-x:auto;overflow-y:auto;width:auto;height:auto;">
<style>#mpctzawnfl table {
  font-family: system-ui, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji', 'Segoe UI Symbol', 'Noto Color Emoji';
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

#mpctzawnfl thead, #mpctzawnfl tbody, #mpctzawnfl tfoot, #mpctzawnfl tr, #mpctzawnfl td, #mpctzawnfl th {
  border-style: none;
}

#mpctzawnfl p {
  margin: 0;
  padding: 0;
}

#mpctzawnfl .gt_table {
  display: table;
  border-collapse: collapse;
  line-height: normal;
  margin-left: auto;
  margin-right: auto;
  color: #333333;
  font-size: 16px;
  font-weight: normal;
  font-style: normal;
  background-color: #FFFFFF;
  width: auto;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #A8A8A8;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #A8A8A8;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
}

#mpctzawnfl .gt_caption {
  padding-top: 4px;
  padding-bottom: 4px;
}

#mpctzawnfl .gt_title {
  color: #333333;
  font-size: 125%;
  font-weight: initial;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 5px;
  padding-right: 5px;
  border-bottom-color: #FFFFFF;
  border-bottom-width: 0;
}

#mpctzawnfl .gt_subtitle {
  color: #333333;
  font-size: 85%;
  font-weight: initial;
  padding-top: 3px;
  padding-bottom: 5px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-color: #FFFFFF;
  border-top-width: 0;
}

#mpctzawnfl .gt_heading {
  background-color: #FFFFFF;
  text-align: center;
  border-bottom-color: #FFFFFF;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
}

#mpctzawnfl .gt_bottom_border {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#mpctzawnfl .gt_col_headings {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
}

#mpctzawnfl .gt_col_heading {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: normal;
  text-transform: inherit;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: bottom;
  padding-top: 5px;
  padding-bottom: 6px;
  padding-left: 5px;
  padding-right: 5px;
  overflow-x: hidden;
}

#mpctzawnfl .gt_column_spanner_outer {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: normal;
  text-transform: inherit;
  padding-top: 0;
  padding-bottom: 0;
  padding-left: 4px;
  padding-right: 4px;
}

#mpctzawnfl .gt_column_spanner_outer:first-child {
  padding-left: 0;
}

#mpctzawnfl .gt_column_spanner_outer:last-child {
  padding-right: 0;
}

#mpctzawnfl .gt_column_spanner {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  vertical-align: bottom;
  padding-top: 5px;
  padding-bottom: 5px;
  overflow-x: hidden;
  display: inline-block;
  width: 100%;
}

#mpctzawnfl .gt_spanner_row {
  border-bottom-style: hidden;
}

#mpctzawnfl .gt_group_heading {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: middle;
  text-align: left;
}

#mpctzawnfl .gt_empty_group_heading {
  padding: 0.5px;
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  vertical-align: middle;
}

#mpctzawnfl .gt_from_md > :first-child {
  margin-top: 0;
}

#mpctzawnfl .gt_from_md > :last-child {
  margin-bottom: 0;
}

#mpctzawnfl .gt_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  margin: 10px;
  border-top-style: solid;
  border-top-width: 1px;
  border-top-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: middle;
  overflow-x: hidden;
}

#mpctzawnfl .gt_stub {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  padding-left: 5px;
  padding-right: 5px;
}

#mpctzawnfl .gt_stub_row_group {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  padding-left: 5px;
  padding-right: 5px;
  vertical-align: top;
}

#mpctzawnfl .gt_row_group_first td {
  border-top-width: 2px;
}

#mpctzawnfl .gt_row_group_first th {
  border-top-width: 2px;
}

#mpctzawnfl .gt_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}

#mpctzawnfl .gt_first_summary_row {
  border-top-style: solid;
  border-top-color: #D3D3D3;
}

#mpctzawnfl .gt_first_summary_row.thick {
  border-top-width: 2px;
}

#mpctzawnfl .gt_last_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#mpctzawnfl .gt_grand_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}

#mpctzawnfl .gt_first_grand_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-style: double;
  border-top-width: 6px;
  border-top-color: #D3D3D3;
}

#mpctzawnfl .gt_last_grand_summary_row_top {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-bottom-style: double;
  border-bottom-width: 6px;
  border-bottom-color: #D3D3D3;
}

#mpctzawnfl .gt_striped {
  background-color: rgba(128, 128, 128, 0.05);
}

#mpctzawnfl .gt_table_body {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#mpctzawnfl .gt_footnotes {
  color: #333333;
  background-color: #FFFFFF;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
}

#mpctzawnfl .gt_footnote {
  margin: 0px;
  font-size: 90%;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 5px;
  padding-right: 5px;
}

#mpctzawnfl .gt_sourcenotes {
  color: #333333;
  background-color: #FFFFFF;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
}

#mpctzawnfl .gt_sourcenote {
  font-size: 90%;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 5px;
  padding-right: 5px;
}

#mpctzawnfl .gt_left {
  text-align: left;
}

#mpctzawnfl .gt_center {
  text-align: center;
}

#mpctzawnfl .gt_right {
  text-align: right;
  font-variant-numeric: tabular-nums;
}

#mpctzawnfl .gt_font_normal {
  font-weight: normal;
}

#mpctzawnfl .gt_font_bold {
  font-weight: bold;
}

#mpctzawnfl .gt_font_italic {
  font-style: italic;
}

#mpctzawnfl .gt_super {
  font-size: 65%;
}

#mpctzawnfl .gt_footnote_marks {
  font-size: 75%;
  vertical-align: 0.4em;
  position: initial;
}

#mpctzawnfl .gt_asterisk {
  font-size: 100%;
  vertical-align: 0;
}

#mpctzawnfl .gt_indent_1 {
  text-indent: 5px;
}

#mpctzawnfl .gt_indent_2 {
  text-indent: 10px;
}

#mpctzawnfl .gt_indent_3 {
  text-indent: 15px;
}

#mpctzawnfl .gt_indent_4 {
  text-indent: 20px;
}

#mpctzawnfl .gt_indent_5 {
  text-indent: 25px;
}
</style>
<table class="gt_table" data-quarto-disable-processing="false" data-quarto-bootstrap="false">
  <thead>
    <tr class="gt_col_headings">
      <th class="gt_col_heading gt_columns_bottom_border gt_left" rowspan="1" colspan="1" scope="col" id=""></th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1" scope="col" id="Estimate">Estimate</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1" scope="col" id="Est.Error">Est.Error</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1" scope="col" id="l-95% CI">l-95% CI</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1" scope="col" id="u-95% CI">u-95% CI</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1" scope="col" id="Rhat">Rhat</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1" scope="col" id="Bulk_ESS">Bulk_ESS</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1" scope="col" id="Tail_ESS">Tail_ESS</th>
    </tr>
  </thead>
  <tbody class="gt_table_body">
    <tr><th id="stub_1_1" scope="row" class="gt_row gt_left gt_stub">Intercept</th>
<td headers="stub_1_1 Estimate" class="gt_row gt_right">-3.148101774</td>
<td headers="stub_1_1 Est.Error" class="gt_row gt_right">0.88990676</td>
<td headers="stub_1_1 l-95% CI" class="gt_row gt_right">-4.88665875</td>
<td headers="stub_1_1 u-95% CI" class="gt_row gt_right">-1.37509225</td>
<td headers="stub_1_1 Rhat" class="gt_row gt_right">1.0004733</td>
<td headers="stub_1_1 Bulk_ESS" class="gt_row gt_right">2521.4854</td>
<td headers="stub_1_1 Tail_ESS" class="gt_row gt_right">3665.013</td></tr>
    <tr><th id="stub_1_2" scope="row" class="gt_row gt_left gt_stub">phi_Intercept</th>
<td headers="stub_1_2 Estimate" class="gt_row gt_right">4.984058688</td>
<td headers="stub_1_2 Est.Error" class="gt_row gt_right">0.16230907</td>
<td headers="stub_1_2 l-95% CI" class="gt_row gt_right">4.66051525</td>
<td headers="stub_1_2 u-95% CI" class="gt_row gt_right">5.30849300</td>
<td headers="stub_1_2 Rhat" class="gt_row gt_right">1.0063449</td>
<td headers="stub_1_2 Bulk_ESS" class="gt_row gt_right">582.0368</td>
<td headers="stub_1_2 Tail_ESS" class="gt_row gt_right">1080.530</td></tr>
    <tr><th id="stub_1_3" scope="row" class="gt_row gt_left gt_stub">zi_Intercept</th>
<td headers="stub_1_3 Estimate" class="gt_row gt_right">-3.740895639</td>
<td headers="stub_1_3 Est.Error" class="gt_row gt_right">0.69906008</td>
<td headers="stub_1_3 l-95% CI" class="gt_row gt_right">-5.19817625</td>
<td headers="stub_1_3 u-95% CI" class="gt_row gt_right">-2.46850625</td>
<td headers="stub_1_3 Rhat" class="gt_row gt_right">1.0002328</td>
<td headers="stub_1_3 Bulk_ESS" class="gt_row gt_right">4257.6413</td>
<td headers="stub_1_3 Tail_ESS" class="gt_row gt_right">5585.685</td></tr>
    <tr><th id="stub_1_4" scope="row" class="gt_row gt_left gt_stub">wing_length</th>
<td headers="stub_1_4 Estimate" class="gt_row gt_right">0.212359888</td>
<td headers="stub_1_4 Est.Error" class="gt_row gt_right">0.04181256</td>
<td headers="stub_1_4 l-95% CI" class="gt_row gt_right">0.13036703</td>
<td headers="stub_1_4 u-95% CI" class="gt_row gt_right">0.29367887</td>
<td headers="stub_1_4 Rhat" class="gt_row gt_right">1.0012927</td>
<td headers="stub_1_4 Bulk_ESS" class="gt_row gt_right">9967.3609</td>
<td headers="stub_1_4 Tail_ESS" class="gt_row gt_right">6691.654</td></tr>
    <tr><th id="stub_1_5" scope="row" class="gt_row gt_left gt_stub">temp_indv</th>
<td headers="stub_1_5 Estimate" class="gt_row gt_right">0.083093121</td>
<td headers="stub_1_5 Est.Error" class="gt_row gt_right">0.06728538</td>
<td headers="stub_1_5 l-95% CI" class="gt_row gt_right">-0.04573421</td>
<td headers="stub_1_5 u-95% CI" class="gt_row gt_right">0.21540752</td>
<td headers="stub_1_5 Rhat" class="gt_row gt_right">1.0012183</td>
<td headers="stub_1_5 Bulk_ESS" class="gt_row gt_right">4299.5858</td>
<td headers="stub_1_5 Tail_ESS" class="gt_row gt_right">5441.740</td></tr>
    <tr><th id="stub_1_6" scope="row" class="gt_row gt_left gt_stub">flight_typepercher</th>
<td headers="stub_1_6 Estimate" class="gt_row gt_right">0.737579316</td>
<td headers="stub_1_6 Est.Error" class="gt_row gt_right">0.51139342</td>
<td headers="stub_1_6 l-95% CI" class="gt_row gt_right">-0.27878295</td>
<td headers="stub_1_6 u-95% CI" class="gt_row gt_right">1.72560250</td>
<td headers="stub_1_6 Rhat" class="gt_row gt_right">1.0005874</td>
<td headers="stub_1_6 Bulk_ESS" class="gt_row gt_right">3820.7683</td>
<td headers="stub_1_6 Tail_ESS" class="gt_row gt_right">4896.712</td></tr>
    <tr><th id="stub_1_7" scope="row" class="gt_row gt_left gt_stub">sexM</th>
<td headers="stub_1_7 Estimate" class="gt_row gt_right">-0.067404117</td>
<td headers="stub_1_7 Est.Error" class="gt_row gt_right">0.05141467</td>
<td headers="stub_1_7 l-95% CI" class="gt_row gt_right">-0.16718242</td>
<td headers="stub_1_7 u-95% CI" class="gt_row gt_right">0.03437644</td>
<td headers="stub_1_7 Rhat" class="gt_row gt_right">1.0002653</td>
<td headers="stub_1_7 Bulk_ESS" class="gt_row gt_right">6326.7601</td>
<td headers="stub_1_7 Tail_ESS" class="gt_row gt_right">6146.343</td></tr>
    <tr><th id="stub_1_8" scope="row" class="gt_row gt_left gt_stub">temp_indv:flight_typepercher</th>
<td headers="stub_1_8 Estimate" class="gt_row gt_right">0.003562942</td>
<td headers="stub_1_8 Est.Error" class="gt_row gt_right">0.05776505</td>
<td headers="stub_1_8 l-95% CI" class="gt_row gt_right">-0.10810462</td>
<td headers="stub_1_8 u-95% CI" class="gt_row gt_right">0.11547682</td>
<td headers="stub_1_8 Rhat" class="gt_row gt_right">1.0008937</td>
<td headers="stub_1_8 Bulk_ESS" class="gt_row gt_right">5571.7530</td>
<td headers="stub_1_8 Tail_ESS" class="gt_row gt_right">5641.405</td></tr>
    <tr><th id="stub_1_9" scope="row" class="gt_row gt_left gt_stub">flight_typepercher:sexM</th>
<td headers="stub_1_9 Estimate" class="gt_row gt_right">0.012555641</td>
<td headers="stub_1_9 Est.Error" class="gt_row gt_right">0.05279774</td>
<td headers="stub_1_9 l-95% CI" class="gt_row gt_right">-0.09095624</td>
<td headers="stub_1_9 u-95% CI" class="gt_row gt_right">0.11702230</td>
<td headers="stub_1_9 Rhat" class="gt_row gt_right">1.0002519</td>
<td headers="stub_1_9 Bulk_ESS" class="gt_row gt_right">6462.6708</td>
<td headers="stub_1_9 Tail_ESS" class="gt_row gt_right">6195.905</td></tr>
    <tr><th id="stub_1_10" scope="row" class="gt_row gt_left gt_stub">phi_temp_indv</th>
<td headers="stub_1_10 Estimate" class="gt_row gt_right">-0.267775750</td>
<td headers="stub_1_10 Est.Error" class="gt_row gt_right">0.04767827</td>
<td headers="stub_1_10 l-95% CI" class="gt_row gt_right">-0.36355532</td>
<td headers="stub_1_10 u-95% CI" class="gt_row gt_right">-0.17440980</td>
<td headers="stub_1_10 Rhat" class="gt_row gt_right">1.0002034</td>
<td headers="stub_1_10 Bulk_ESS" class="gt_row gt_right">4711.8713</td>
<td headers="stub_1_10 Tail_ESS" class="gt_row gt_right">5471.847</td></tr>
    <tr><th id="stub_1_11" scope="row" class="gt_row gt_left gt_stub">zi_wing_length</th>
<td headers="stub_1_11 Estimate" class="gt_row gt_right">-1.187550026</td>
<td headers="stub_1_11 Est.Error" class="gt_row gt_right">0.20122209</td>
<td headers="stub_1_11 l-95% CI" class="gt_row gt_right">-1.59814300</td>
<td headers="stub_1_11 u-95% CI" class="gt_row gt_right">-0.79997398</td>
<td headers="stub_1_11 Rhat" class="gt_row gt_right">1.0004926</td>
<td headers="stub_1_11 Bulk_ESS" class="gt_row gt_right">2819.5424</td>
<td headers="stub_1_11 Tail_ESS" class="gt_row gt_right">4788.065</td></tr>
    <tr><th id="stub_1_12" scope="row" class="gt_row gt_left gt_stub">zi_temp_indv</th>
<td headers="stub_1_12 Estimate" class="gt_row gt_right">0.117605183</td>
<td headers="stub_1_12 Est.Error" class="gt_row gt_right">0.11370667</td>
<td headers="stub_1_12 l-95% CI" class="gt_row gt_right">-0.10383457</td>
<td headers="stub_1_12 u-95% CI" class="gt_row gt_right">0.34328627</td>
<td headers="stub_1_12 Rhat" class="gt_row gt_right">1.0003119</td>
<td headers="stub_1_12 Bulk_ESS" class="gt_row gt_right">7743.9811</td>
<td headers="stub_1_12 Tail_ESS" class="gt_row gt_right">6502.946</td></tr>
    <tr><th id="stub_1_13" scope="row" class="gt_row gt_left gt_stub">zi_flight_typepercher</th>
<td headers="stub_1_13 Estimate" class="gt_row gt_right">-0.030432418</td>
<td headers="stub_1_13 Est.Error" class="gt_row gt_right">0.71876755</td>
<td headers="stub_1_13 l-95% CI" class="gt_row gt_right">-1.38123850</td>
<td headers="stub_1_13 u-95% CI" class="gt_row gt_right">1.42911225</td>
<td headers="stub_1_13 Rhat" class="gt_row gt_right">1.0008620</td>
<td headers="stub_1_13 Bulk_ESS" class="gt_row gt_right">4268.4197</td>
<td headers="stub_1_13 Tail_ESS" class="gt_row gt_right">5657.992</td></tr>
    <tr><th id="stub_1_14" scope="row" class="gt_row gt_left gt_stub">zi_sexM</th>
<td headers="stub_1_14 Estimate" class="gt_row gt_right">-0.904499112</td>
<td headers="stub_1_14 Est.Error" class="gt_row gt_right">0.14237704</td>
<td headers="stub_1_14 l-95% CI" class="gt_row gt_right">-1.18420500</td>
<td headers="stub_1_14 u-95% CI" class="gt_row gt_right">-0.62359690</td>
<td headers="stub_1_14 Rhat" class="gt_row gt_right">1.0009826</td>
<td headers="stub_1_14 Bulk_ESS" class="gt_row gt_right">13316.8416</td>
<td headers="stub_1_14 Tail_ESS" class="gt_row gt_right">5913.259</td></tr>
    <tr><th id="stub_1_15" scope="row" class="gt_row gt_left gt_stub">t2latlon_1</th>
<td headers="stub_1_15 Estimate" class="gt_row gt_right">-0.018461812</td>
<td headers="stub_1_15 Est.Error" class="gt_row gt_right">0.03104168</td>
<td headers="stub_1_15 l-95% CI" class="gt_row gt_right">-0.07757623</td>
<td headers="stub_1_15 u-95% CI" class="gt_row gt_right">0.04473045</td>
<td headers="stub_1_15 Rhat" class="gt_row gt_right">1.0003608</td>
<td headers="stub_1_15 Bulk_ESS" class="gt_row gt_right">4968.7799</td>
<td headers="stub_1_15 Tail_ESS" class="gt_row gt_right">4659.282</td></tr>
    <tr><th id="stub_1_16" scope="row" class="gt_row gt_left gt_stub">t2latlon_2</th>
<td headers="stub_1_16 Estimate" class="gt_row gt_right">-0.069496123</td>
<td headers="stub_1_16 Est.Error" class="gt_row gt_right">0.04963546</td>
<td headers="stub_1_16 l-95% CI" class="gt_row gt_right">-0.16559347</td>
<td headers="stub_1_16 u-95% CI" class="gt_row gt_right">0.03422042</td>
<td headers="stub_1_16 Rhat" class="gt_row gt_right">1.0005858</td>
<td headers="stub_1_16 Bulk_ESS" class="gt_row gt_right">5810.4665</td>
<td headers="stub_1_16 Tail_ESS" class="gt_row gt_right">6165.698</td></tr>
    <tr><th id="stub_1_17" scope="row" class="gt_row gt_left gt_stub">t2latlon_3</th>
<td headers="stub_1_17 Estimate" class="gt_row gt_right">-0.031710607</td>
<td headers="stub_1_17 Est.Error" class="gt_row gt_right">0.03498716</td>
<td headers="stub_1_17 l-95% CI" class="gt_row gt_right">-0.09465432</td>
<td headers="stub_1_17 u-95% CI" class="gt_row gt_right">0.04296342</td>
<td headers="stub_1_17 Rhat" class="gt_row gt_right">0.9999612</td>
<td headers="stub_1_17 Bulk_ESS" class="gt_row gt_right">4143.6705</td>
<td headers="stub_1_17 Tail_ESS" class="gt_row gt_right">4025.747</td></tr>
  </tbody>
  
  
</table>
</div>
```
:::

```{.r .cell-code}
gtsave(bb_table, filename = "figures/bb_table.html")
gtsave(by_table, filename = "figures/by_table.html")
```
:::


Plot model diagnostics (density overlay posterior predictive checks).


::: {.cell}

```{.r .cell-code}
bb_pp <- pp_check(bb_m, ndraws = 100) + theme_classic()
bb_pp_part1 <- bb_pp + xlim(0,0.025) + ylim(0,750)
bb_pp_part2 <- bb_pp + xlim(0.025,1) + ylim(0,10)
bb_pp
```

::: {.cell-output-display}
![](supplemental_files/figure-html/unnamed-chunk-3-1.png){width=672}
:::

```{.r .cell-code}
bb_pp_part1
```

::: {.cell-output .cell-output-stderr}
```
Warning: Removed 71607 rows containing non-finite values (`stat_density()`).
```
:::

::: {.cell-output .cell-output-stderr}
```
Warning: Removed 672 rows containing non-finite values (`stat_density()`).
```
:::

::: {.cell-output .cell-output-stderr}
```
Warning: Removed 128 rows containing missing values (`geom_line()`).
```
:::

::: {.cell-output-display}
![](supplemental_files/figure-html/unnamed-chunk-3-2.png){width=672}
:::

```{.r .cell-code}
bb_pp_part2
```

::: {.cell-output .cell-output-stderr}
```
Warning: Removed 398193 rows containing non-finite values (`stat_density()`).
```
:::

::: {.cell-output .cell-output-stderr}
```
Warning: Removed 4025 rows containing non-finite values (`stat_density()`).
```
:::

::: {.cell-output-display}
![](supplemental_files/figure-html/unnamed-chunk-3-3.png){width=672}
:::

```{.r .cell-code}
by_pp <- pp_check(by_m, ndraws = 100) + theme_classic()
by_pp_part1 <- by_pp + xlim(0,0.03) + ylim(0,750)
by_pp_part2 <- by_pp + xlim(0.03,1) + ylim(0,10)
by_pp
```

::: {.cell-output-display}
![](supplemental_files/figure-html/unnamed-chunk-3-4.png){width=672}
:::

```{.r .cell-code}
by_pp_part1
```

::: {.cell-output .cell-output-stderr}
```
Warning: Removed 196559 rows containing non-finite values (`stat_density()`).
```
:::

::: {.cell-output .cell-output-stderr}
```
Warning: Removed 1875 rows containing non-finite values (`stat_density()`).
```
:::

::: {.cell-output-display}
![](supplemental_files/figure-html/unnamed-chunk-3-5.png){width=672}
:::

```{.r .cell-code}
by_pp_part2
```

::: {.cell-output .cell-output-stderr}
```
Warning: Removed 273241 rows containing non-finite values (`stat_density()`).
```
:::

::: {.cell-output .cell-output-stderr}
```
Warning: Removed 2823 rows containing non-finite values (`stat_density()`).
```
:::

::: {.cell-output-display}
![](supplemental_files/figure-html/unnamed-chunk-3-6.png){width=672}
:::
:::

