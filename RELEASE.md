
- [ ] Make sure README has the correct command list.
- [ ] Make sure version number is updated everywhere:
  - Cargo.toml
  - Cargo.lock (run cargo build)
  - rig.iss
  - NEWS file
  - README.Rmd
- [ ] Make sure CI is OK
- [ ] If needed, commit to have a CI build with the right version number.
- [ ] Build README:
  ```
  Rscript -e 'rmarkdown::render("README.Rmd")'
  ```
- [ ] Update NEWS header to remove `(not released yet)`
- [ ] Build signed and notarized macOS packages locally:
  ```
  export AC_PASSWORD=...
  export TEAM_ID=...
  sudo xcode-select -s /Applications/Xcode.app/Contents/Developer
  make clean
  make macos
  ```
  (https://github.com/mitchellh/gon is now archived, I had to compile my
  own fork, from https://github.com/UniversalMediaServer.)
- [ ] Download the artifacts for the new version for Windows & Linux (x2)
- [ ] Create tag for the current version, push to GH.
- [ ] Create release on GH, add the installers.
- [ ] Test installers.
- [ ] `git commit` with the NEWS and README updates, update tag, push to GH,
      `--tags` as well.
- [ ] Update homebrew repo.
- [ ] Update choco package.
- [ ] Update the `latest` tag and release on GH.
- [ ] toot
