# OfflineRegistry

<p>
<a
href="https://app.bors.tech/repositories/12700">
<img
src="https://bors.tech/images/badge_small.svg"
alt="Bors enabled">
</a>
<a
href="https://travis-ci.com/aluthge/OfflineRegistry/branches">
<img
src="https://travis-ci.com/aluthge/OfflineRegistry.svg?branch=master"/>
</a>
</p>

# Usage

## Creating the offline registry

```bash
mkdir -p /path/to/desired/location
cd /path/to/desired/location
git clone https://github.com/DilumAluthge/OfflineRegistry
cd OfflineRegistry
# vim offline.toml # Edit offline.toml to meet your requirements
# git add -A
# git commit -m 'Update offline.toml'
export REGISTRY_NAME="MyAwesomeOfflineRegistry"
export REGISTRY_UUID="e8565a5e-8849-4686-8239-e2115313d19d" # Don't use this UUID; generate your own
export GIT_USER_NAME="Myfirstname Mylastname"
export GIT_USER_EMAIL="someone@example.com"
julia make.jl "$REGISTRY_NAME" "$REGISTRY_UUID" "$GIT_USER_NAME" "$GIT_USER_EMAIL"
```

## Using the offline registry

```julia
julia> include("/path/to/desired/location/OfflineRegistry/startup.jl")
julia> include("/path/to/desired/location/OfflineRegistry/default-environment.jl")
julia> import Pkg
julia> Pkg.add(["list", "of", "packages", "to", "add"])
```
