| Travis CI                                             |
|-------------------------------------------------------|
| [![Build Status][travis-badge]][travis-url]           |

| Build History                                         |
|-------------------------------------------------------|
| [![Travis build history][travis-history]][travis-url] |

[repository-name]: travis-tex-test
[org-name]: KilnOfTheSecondFlame
[travis-url]: https://travis-ci.org/[org-name]/[repository-name]
[travis-badge]: https://travis-ci.org/[org-name]/[repository-name].svg?branch=master
[travis-history]: https://buildstats.info/travisci/chart/[org-name]/[repository-name]?branch=master&includeBuildsFromPullRequest=false


# Travis CI TeX test repository
Repository to test build speedup with travis, tlmgr &amp; biber
The goal was to provide a minimal installation script which preinstalls TeXLive, Biber and some TeX packages and be able to cache the installed TeXLive application files. The user should be able to install his needed TeX dependencies via a line in the install part of the Travis script.

# Deploy
1. Fork / Copy the files
2. Add the repo to Travis in the console
3. Commit

# Error troubleshooting in Travis
By far the easiest way is to look for the missing file in tlmgr and then adding the package containing the .sty/file to the travis script.
```bash
tlmgr search --global -all <filename here>*
```
```yaml
...
install:
  - 
  [...]
  - tlmgr install [...] new_package
...
```
