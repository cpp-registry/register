# Register your C++ project

You can add your C++ project to the C++ Registry by creating a .cpp-registry.yaml file in your GitHub profile repository.

## 1. Create .cpp-registry.yaml

Create a file named:

```
.cpp-registry.yaml
```

in the root of your GitHub profile repository:

```
https://github.com/YOUR_USERNAME/YOUR_USERNAME
```

For example:

```
https://github.com/weuritz8u/weuritz8u
```

## 2. Add your repository

The file uses YAML.

A minimal example:

```yaml
repos:
  base32:
    description: "Decoder and encoder for Base32 in C++20"
    license: MIT
    cppstd: 20
```

The key under repos must be the exact GitHub repository name.

For example, for:

```
https://github.com/weuritz8u/base32
```

use:

```yaml
repos:
  base32:
    description: "Decoder and encoder for Base32 in C++20"
    license: MIT
    cppstd: 20
```
## 3. Available fields
description

A short description of your project.

```yaml
description: "A fast Base32 encoder and decoder"
```

license

The license of your project.

```yaml
license: MIT
```

Examples:

```yaml
license: MIT
license: Apache-2.0
license: GPL-3.0
```

cppstd

The C++ standard required or targeted by your project.

Use the number only:

```
cppstd: 20
```

Examples:

```
cppstd: 11
cppstd: 14
cppstd: 17
cppstd: 20
cppstd: 23
cppstd: 26
```

The registry displays this as:

C++20

## 4. Complete example

Your .cpp-registry.yaml could look like this:

```yaml
repos:
  base32:
    description: "Decoder and encoder for Base32 in C++20"
    license: MIT
    cppstd: 20

  my-library:
    description: "A small modern C++ library"
    license: Apache-2.0
    cppstd: 23
```

You can register multiple repositories in the same file.

## 5. Enable your GitHub user

The registry also has a users.yaml configuration.

Add your GitHub username:

```
weuritz8u: true
```

Only users whose value is true are processed.

For example:

```yaml
weuritz8u: true
alice: true
bob: false
```

weuritz8u and alice will be included, while bob will be ignored.

## 6. Generate the registry

After changing users.yaml or a user's .cpp-registry.yaml, run the registry generator:

node generate-registry.js


This fetches each enabled user's registry and generates:

registry.json


For example:

```json
{
  "weuritz8u/base32": {
    "license": "MIT",
    "description": "Decoder and encoder for Base32 in C++20",
    "cppstd": 20,
    "owner": "weuritz8u",
    "repo": "base32",
    "url": "https://github.com/weuritz8u/base32"
  }
}
```

## 7. That's it!

Once the registry is regenerated, your project will appear in the C++ Registry.

Your project repository does not need any special registry code.

The only required file is:

```
.cpp-registry.yaml
```

in your GitHub profile repository.

Quick template

Copy this into .cpp-registry.yaml:

```yaml
repos:
  YOUR_REPOSITORY:
    description: "YOUR DESCRIPTION"
    license: MIT
    cppstd: 20
```

Replace:

`YOUR_REPOSITORY` with your GitHub repository name

`YOUR DESCRIPTION` with a short description

`MIT` with your project's license

`20` with your required C++ standard
