# ffvec/website

The website is being deployed on a nixos machine. Dependencies cannot be managed
completly in nix, so we have to create a Gemfile and convert this to a gemset.nix:
```sh
cat <<_EOF > Gemfile
source "https://rubygems.org"

gem "jekyll"
gem "minima"
_EOF

nix shell nixpkgs#ruby --command bundle

nix run nixpkgs#bundix
```
