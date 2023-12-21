.PHONY: all
all: deb

#
# Release
#
.PHONY: dch
dch: debian/changelog
	EDITOR=true gbp dch --commit --debian-branch=main --release --dch-opt=--upstream
.PHONY: deb
deb: debian
	./build bullseye arm64 ../

.PHONY: release
release:
	gh workflow run .github/workflows/new_version.yml