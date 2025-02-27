# Make a nip4.app package for macOS

## Prerequesites

Install brew-pkg, see:

https://github.com/timsutton/brew-pkg

But we have a tweaked version with a few fixes, so as a quick hack install 
with (this can be anywhere on your PATH, but this is a convenient dir to use):

```shell
cp brew-pkg.rb /opt/homebrew/bin
```

Install nip4, see this PR:

https://github.com/Homebrew/homebrew-core/pull/209123

Copy `nip4.rb` to
`/opt/homebrew/Library/Taps/homebrew/homebrew-core/Formula/n`, then:

```shell
HOMEBREW_NO_INSTALL_FROM_API=1 brew reinstall --build-from-source nip4
```

## Build package

```shell
brew /opt/homebrew/bin/brew-pkg.rb \
    --verbose \
    --with-deps \
    --identifier-prefix org.libvips \
    --scripts scripts \
    nip4
```

