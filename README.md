
<!-- README.md is generated from README.Rmd. Please edit that file -->

# CRAN Submission Checklist

This list mainly comes from the book R Packages and [R Packages
(2e)](https://r-pkgs.org/).

<!-- badges: start -->
<!-- badges: end -->

# 1 Checks

``` r
usethis::proj_set(".")
```

## 1.1 Local `R CMD check`

``` r
devtools::check()
```

or press `Ctrl`/`Cmd` + `Shift` + `E`

## 1.2 Continuous Integration: GitHub Action

``` r
usethis::use_github_action_check_standard()
```

## 1.3 R-hub

``` r
devtools::check_rhub()

# If cpp
rhub::check_with_sanitizers()
```

## 1.4 Win-Builder

``` r
devtools::check_win_devel()
devtools::check_win_release()
devtools::check_win_oldrelease()
```

## 1.5 [Reverse dependencies](https://r-pkgs.org/release.html#release-deps)

# 2 Before Submission

## 2.1 DESCRIPTION

``` r
usethis::use_description()
```

### 2.1.1 Version

Don’t push after this

``` r
usethis::use_version()
```

    <major>.<minor>.<patch>       (released version, e.g. 0.1.0)
    <major>.<minor>.<patch>.<dev> (dev version, e.g. 0.1.0.9000)

### 2.1.2 License

``` r
usethis::use_gpl3_license()
```

## 2.2 README.md

``` r
usethis::use_readme_rmd()
```

Badge?

``` r
usethis::use_cran_badge()
```

    [![R-CMD-check](https://github.com/FinYang/fable.thrreg/workflows/R-CMD-check/badge.svg)](https://github.com/FinYang/fable.thrreg/actions)
    [![license](https://img.shields.io/badge/license-GPL--3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0.en.html)

## 2.3 NEWS.md

``` r
usethis::use_news_md()
```

## 2.4 cran-comments.md

``` r
usethis::use_cran_comments()
```

## 2.5 Spelling

``` r
devtools::spell_check()
```

## 2.6 SUBMIT!

``` r
devtools::release()
```

# 3 After Submission

## 3.1 Wait patiently

If not, then <https://r-hub.github.io/cransays/articles/dashboard.html>

## 3.2 Push (Don’t Commit CRAN-SUBMISSION)

## 3.3 GitHub release

``` r
usethis::use_github_release()
```

- Release on Github with tag version v1.2.3
- Copy NEWS to release notes.
- Delete CRAN-SUBMISSION

## 3.4 Bump dev version and Push

``` r
usethis::use_dev_version()
```

- Bump to version .9000 in DESCRIPTION
- Add a heading in NEWS
- Commit
