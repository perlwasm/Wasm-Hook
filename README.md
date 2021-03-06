# Wasm::Hook [![Build Status](https://travis-ci.org/perlwasm/Wasm-Hook.svg)](http://travis-ci.org/perlwasm/Wasm-Hook) ![windows](https://github.com/perlwasm/Wasm-Hook/workflows/windows/badge.svg) ![macos](https://github.com/perlwasm/Wasm-Hook/workflows/macos/badge.svg)

Automatically load WebAssembly modules without a Perl wrapper

# SYNOPSIS

```perl
use Wasm::Hook;
use Foo::Bar;  # will load Foo/Bar.wasm or Foo/Bar.wat if no Foo/Bar.pm is found
no Wasm::Hook; # turns off automatic wasm / wat loading
```

# DESCRIPTION

**NOTE**: This distribution has been merged into [Wasm](https://metacpan.org/pod/Wasm).  The repository remains on
GitHub out of historical interest.  Please find the latest version of this module
either on metacpan or GitHub at:

- [https://metacpan.org/pod/Wasm](https://metacpan.org/pod/Wasm)
- [https://github.com/perlwasm/Wasm](https://github.com/perlwasm/Wasm)

This module installs an `@INC` hook that automatically loads WebAssembly (Wasm)
files so that they can be used like a Perl module, without:

The functions inside the WebAssembly module are exportable via the [Exporter](https://metacpan.org/pod/Exporter)
module.  `@EXPORT_OK` is used, so you will need to explicitly export functions.

- Having to write a boilerplate `.pm` file that loads the WebAssembly
- The caller needing to even know or care that the module is implemented in something other than Perl.

This module will only load a WebAssembly module if there is now Perl Module (`.pm` file) with the appropriate name.

# SEE ALSO

- [Wasm](https://metacpan.org/pod/Wasm)
- [Wasm::Wasmtime](https://metacpan.org/pod/Wasm::Wasmtime)

# AUTHOR

Graham Ollis <plicease@cpan.org>

# COPYRIGHT AND LICENSE

This software is copyright (c) 2020 by Graham Ollis.

This is free software; you can redistribute it and/or modify it under
the same terms as the Perl 5 programming language system itself.
