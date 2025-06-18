# temp-sentencepiece-build
Temporary repo for building 3.13 wheel for sentencepiece until the new version comes out. Will be deleted when sentencepiece finally provides 3.13 wheels. (Please!)

## Disclaimer
I do not know a lick about sentencepiece inner workings or code. This is for my usage. Use wheels at your own risk!

## Patches included
Patches are applied on top of the sentencepiece repo that is checked out on the v0.2.0 tag.
### Patches used by AUR package
- [Add missing <cstdint> in sentencepiece_processor.h](https://github.com/google/sentencepiece/commit/c4221363d1f004f85f9cc4096e601d6b1fbfaa84)
- [Bump CMake minimum required version to avoid warnings](https://github.com/google/sentencepiece/commit/e2127b9b932ba00811d5023c5ea69a12a857b244)
- [Fix crash in unigram model training](https://github.com/google/sentencepiece/commit/d19ac45c919602cb041a86599d0593d24a150ac2)
### Patches based on Pull Request
- [General CI refresh](https://github.com/google/sentencepiece/pull/1120)

## Warnings about Source Distribution (sdist)
sdist compiled using Github Actions on this repo still has an error when trying to install. Looking at the source code, when installing the python-sentencepiece build script, it will fetch a fresh copy of the main sentencepiece repo. That means the repo is clear without the above patches.

## Usage
Download the wheel for your platform from the Release or install it using my [python-index](https://mddanish00.github.io/python-index/).
```
pip install sentencepiece --extra-index-url https://mddanish00.github.io/python-index/simple
uv add sentencepiece --index https://mddanish00.github.io/python-index/simple
uv pip install sentencepiece --index https://mddanish00.github.io/python-index/simple
```

## Acknowledgements
[google/sentencepiece](https://github.com/google/sentencepiece) is licensed under [Apache License 2.0](https://github.com/google/sentencepiece/blob/master/LICENSE).
