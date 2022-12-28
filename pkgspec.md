# CDX Package Meta File

CURRENT VERSION: **0.1.0**

The SPEC is hosted at https://github.com/xoit/cdx_pkgspec

A CDX Package is used to finish certain function in the Chip-Design-Execution process.

__Folder Structure__

All the files (at least main files) must be in one folder as a package which will be used by the application.

cdxpkg.toml or cdxpkg.json is the file to tell the meta information of the cdx package.

Package Meta File must be named "cdxpkg.toml" or "cdxpkg.json".

If you want your package to be a generic one, generate a file named pakcage.json/package.toml and create a link cdxpkg.toml/cdxpkg.json pointing to original file.

Plural keys are arrays, simple array or associated array.

Singular keys are string.

## name

The name of the package. **Required**

Name acts as the primary identifier for distributions. They are present in all dependency specifications, and are sufficient to be a specification on their own. 

This should be a valid name as defined matching the regrular expression.

```
^([A-Za-z][A-Za-z0-9._-]*[A-Za-z0-9])$
```

##### cdxpkg.toml

```
name = "cdx_tutorial"
```

##### cdxpkg.json

```
{
  "name": "cdx_tutorial"
}
```

## version

The version of the package. **Required**

Follow the [Semanic Versioning](https://semver.org/).

##### cdxpkg.toml

```
version = "0.1.0"
```

##### cdxpkg.json

```
{
  "version": "0.1.0"
}
```

## description

A short description of the package. **Required**

If you have more documentation, a folder named "docs" is a good start.

##### cdxpkg.toml

```
description = "This is a tutorial for cdx_tutorial"
```

##### cdxpkg.json

```
{
  "description": "This is a tutorial for cdx_tutorial"
}
```

## license

The license of the package. **optional**

If you don't specify the license, the default [CDX-default](cdx_license.md) will be used.

The notation for the most common open licenses is (alphabetical):

- Apache-2.0
- BSD-2-Clause
- BSD-3-Clause
- BSD-4-Clause
- GPL-2.0-only
- GPL-2.0-or-later
- GPL-3.0-only
- GPL-3.0-or-later
- LGPL-2.1-only
- LGPL-2.1-or-later
- LGPL-3.0-only
- LGPL-3.0-or-later
- MIT

##### cdxpkg.toml

```
license = "MIT"
```

##### cdxpkg.json

```
{
  "license": "CDX-default"
}
```

## entry

The entry file for the package. **optional**

##### cdxpkg.toml

```
entry = "plugin.tcl"
```

##### cdxpkg.json

```
{
  "entry": "plugin.tcl"
}
```

## keywords

A list of keywords that the package is related to. **Optional**

The keyword could have "type", the format is "&lt;type&gt;:&lt;keyword&gt;". 

The keyword could be used along with the tagging system. Each tag is an object and could have its own functions and properties.

##### cdxpkg.toml

```
keywords = [
  "category:flow",
  "plugin"
]
```

##### cdxpkg.json

```
{
  "keywords": [
    "category:flow",
    "plugin"
  ]
}
```
## engines

The engines indicate the environment to run the package. **required**

like tcl 8.6, python 3.18, eda tool, etc.

##### cdxpkg.toml

```
[engines]
tcl = "8.6"
```

##### cdxpkg.json

```
{
  "engines": {
    "tcl" : "8.6"
  }
}
```

## maintainers

The maintainers of the package. **Optional**

This is a list of maintainers.

Maintainers may contain an email and be in the form `name <email>`.

##### cdxpkg.toml

```
maintainers = [
  "foo <bar@example.com>",
  "xyz <abc@example.com>"
]
```

##### cdxpkg.json

```
{
  "maintainers": [
    "foo <bar@example.com>",
    "xyz <abc@example.com>"
  ]
}
```

## scripts

This section describes the scripts or executables that will be installed when installing, testing or using the package. **Optional**

##### cdxpkg.toml

```
[scripts]
test = "make test"
run = "tclsh demo.tcl"
```

##### cdxpkg.json

```
{
  "scripts": {
     "test": "make test",
     "run": "tclsh demo.tcl"
  }
}
```

## dependencies

Package dependencies by default are from the path specified by one environment variable `CDXPKGPATH`. **Optional**

##### cdxpkg.toml

```
[dependencies]
floorplan = "0.5.0"
syn_summary = "1.0.0"
```

##### cdxpkg.json

```
{
  "dependencies": {
     "floorplan": "0.5.0",
     "syn_summary": "1.0.0"
  }
}
```

## repository

A location to the repository of the project. **Optional**

Could be a git repository or just a folder path.

##### cdxpkg.toml

```
repository = "/home/demo/cdx_tutorial"
```

##### cdxpkg.json

```
{
   "repository": "http://github.com/foo/bar.git"
}
```
## extras

Any other proposing keys or user custom keys go to this section. **OPtional**

Non-default keys which is not in current SPEC versions.

##### cdxpkg.toml

```
[extras.old]
user_custom = "abc"
[extra.new]
user_new = "xyz"
```

##### cdxpkg.json

```
{
  "extras": {
     "new": {
	"user_custom": "abc",
     },
     "old": {
	"user_new": "xyz"
     }
  }
}
```


