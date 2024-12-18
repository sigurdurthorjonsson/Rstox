# Rstox version: 1.20 --- (detatched fork of Sea2Data/Rstox in December 2024)

This version of Rstox is intended for making the continued use of surveyPlanner possible 
after some changes in the R-package environment making it difficult to run previous versions.

In order to keep the functionality of Rstox::surveyPlanner available on (almost) up-to-date R installation
a fork of Sea2Data/Rstox was detached the original and some crucial changes made, for details see [here](details.md).


# Light-weight version of Sea2Data/Rstox

Loss of the functionality of Rstox::suryvePlanner was the catlyst for
this hack of the package Rstox.

When the packages 'rgdal' and 'rgeos' were deprecated in 2023 the
original Rstox stopped working in an up-to-date R installation. To
remedy this it was possible to keep running with archived versions of
these packages (possibly also e.g. suggested package 'pgirmess'). A
detached fork was created as sigurdurthorjonsson/Rstox. StoX
functionality unnecessary for surveyPlanner work was peeled away,
that process may continue.


# Details regading detached fork of Sea2Data/Rstox

The following gives a rundown of changes made:

* In addition to running the archived 'rgdal' and 'rgeos' versions, a
  change from 'sp:disaggregate' to 'terra::disagg' fixed a problem
  discovered early on.

* The size of the package was reduced since it contained a tar-ball
  of the package, later removed. A few steps were taken:

  - a bare clone was made of a new fork which was then removed friom
    github after cloning.

  - 'git-filter-repo' was used to remove the tarball

  - a mirror of the filter was then pushed to a pristine Rstox on
    github.

  see [the progit book](https://git-scm.com/book/en/v2) and [this help
  link on
  github](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/detaching-a-fork).

* The use of non-ascii was no longer permitted, these were removed
  from all R-files (R packageing requires allowing such use explicitly
  perhaps working best in a NO-locale, in this case).

* The eca and RECA parts of Sea2Data/Rstox were removed since they referred to a package 'eca' with unknown whereabouts.

* Examples that did not run after pruning away parts of the original Rstox were encapsulated with dontrun-directives.


