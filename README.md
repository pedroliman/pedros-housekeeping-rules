# R package and code repository housekeeping rules
Housekeeping rules for R packages &amp; code repositories

The heart of this document is to serve as an agreed-upon set of rules we follow to ensure the quality of our R packages and code repositories. They were created by Pedro for the packages he contributes to but may be used for other R packages or software. Their purpose of them is to ensure the quality of the code we release, compliance with QA and IP standards and make sure any R package I contribute to is well-maintained.

These rules are mostly targeted to the R environment and informed by Pedro's preferences – by no means do they represent absolute standards that you should always follow. That said, you will notice that most of them are followed by well-maintained packages in the R community. Rather than a set-in-stone set of rules, these rules can evolve over time.

**Roles:**

In any software development endeavor, we will identify people for the following roles:

PI: Principal investigator

PM: Package Maintainer

DEVs: Package developers

Code QA reviewer: Code QA reviewer.

    **Maintenance and Testing**
    
1. DEVs are expected to frequently run CRAN checks on their package while the package doesn't have automated CRAN checks via github actions.
1. The package includes automated tests using testthat.
1. All packages on github repositories shall have github actions with at least one test and a CRAN check.
1. Whoever pushes a commit that breaks any github action workflow is responsible for fixing them in a timely fashion (i.e., at most within a few days of your commit). Those will be shown next to your commits. This is expected to happen and will happen from time to time as R is updated.
1. Minor updates in documentation are welcome from anyone in the project.

    **Quality Assurance**

1. No new release should decrease test coverage % as measured by codecov.io.
1. No changes in the readme shall be made without proper oversight after the package is publicly released.
1. Code QA comments shall be at the github pull request documentation.
   
    **Branching:**
   
1. The main branch is locked for commits. All changes shall be made to the develop or other development branches.
1. We generally do not welcome pull requests from forks. This rule can change to the extent the package becomes a collaborative project. The implication is that you should clone the repository, not fork it.
1. We subscribe to Driessen's [git branching model](https://nvie.com/posts/a-successful-git-branching-model/), except we do not use release branches. This means package developers should use the develop branch by default.

    **Versioning:**
   
1. We use [semantic versioning](https://semver.org/). Whoever adds features to the package is responsible for incrementing the version in the description file. Do not create new minor or major versions without consulting with the PI or PM.
1. Any change in the code requires at least a new patch version.
1. Package releases shall follow [Hadley's suggested workflow](https://r-pkgs.org/release.html).
1. The package maintainer or a designated developer will handle CRAN submissions, major and minor version changes.
1. All developers are welcome to create patches.
1. The maintainer creates a github issue before every major release.
1. All major and minor releases shall be released on CRAN.
1. While the package is actively maintained, we will release minor versions about every quarter, and one major release about every year.
1. Patches that pass all tests don't require approval for merging into master.
1. Minor releases require PI approval on the pull request.
1. Major releases require full code QA from an external developer.
1. Minor and Major releases must be documented in the NEWS.md file.
1. Github will be set up such that it creates release tags automatically.
   
    **Intellectual property:**
  
1. We will determine what is the appropriate license for a package before the first release, based on its dependencies.
1. Avoid adding new dependencies to the package. If doing so, ensure that the license of their dependencies is less restrictive than the license chosen.


**Repository Rules**

These rules apply to code repositories.

1. One research product (paper, report) shall have one code repository.
1. We do not push binary files (pdfs, images, excel) to code repositories.
1. We will break rule #2 when
  1. This is required for reproducibility purpuses.
  1. The said file is small (i.e., a few kbs).
1. Reproducibility shall be ensured with `renv`, at least at the end of the project.
1. We will use git tags to signal the release of a research product.
