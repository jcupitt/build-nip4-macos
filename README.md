# Make a nip4.app package for macOS

## Prerequesites

Install brew-pkg, see:

https://github.com/timsutton/brew-pkg

But we have a tweaked version with a few fixes, so install with:

```shell
brew tap jcupitt/build-nip4-macos
brew install brew-pkg
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
brew pkg --verbose --with-deps --identifier-prefix org.libvips --scripts scripts nip4
```

