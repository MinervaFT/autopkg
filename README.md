# MinervaFT AutoPkg Recipes

Community-maintained AutoPkg recipes for macOS application packaging, deployment, and software lifecycle management.

This repository contains AutoPkg recipes maintained by MinervaFT and is intended for use with AutoPkg, AutoPkgr, Munki, Jamf Pro, Kandji, Mosyle, and other Mac management platforms.

## Requirements

- AutoPkg 2.3 or later
- macOS
- Internet access to software vendor download sources

## Repository Installation

Add this repository:

```bash
autopkg repo-add https://github.com/MinervaFT/recipes.git
```

Update all repositories:

```bash
autopkg repo-update all
```

List repositories:

```bash
autopkg repo-list
```

List recipes in this repository:

```bash
autopkg repo-list-recipes MinervaFT-recipes
```

Search available recipes:

```bash
autopkg search ableton
autopkg search chrome
autopkg search packet
```

## Optional Dependencies

Some recipes use processors from other AutoPkg repositories.

### HomeBySix Recipes

Required for recipes that utilise:

- VersionSplitter
- Additional packaging processors

Install:

```bash
autopkg repo-add https://github.com/homebysix/recipes.git
```

### Recommended Community Repositories

```bash
autopkg repo-add https://github.com/autopkg/recipes.git
autopkg repo-add https://github.com/homebysix/recipes.git
```

## Available Recipes

| Application | Download | PKG | Munki | Notes |
|------------|----------|-----|--------|---------|
| Ableton Live | ✅ | ✅ | ⬜ | Includes Sassafras licensing package variant |
| Google Chrome | ✅ | ✅ | ✅ | Enterprise browser deployment |

| *Additional recipes added regularly* | | | |

## Naming Conventions

Recipe identifiers follow the standard format:

```text
com.github.MinervaFT.Application.download
com.github.MinervaFT.Application.pkg
com.github.MinervaFT.Application.munki
```

Examples:

```text
com.github.MinervaFT.AbletonLive12.download
com.github.MinervaFT.AbletonLiveSassafras.pkg
```

## Repository Structure

```text
recipes/
├── AbletonLive/
│   ├── AbletonLive.download.recipe
│   └── AbletonLiveSassafras.pkg.recipe
│
├── CiscoPacketTracer/
│   ├── CiscoPacketTracer.download.recipe
│   ├── CiscoPacketTracer.pkg.recipe
│   └── CiscoPacketTracer.munki.recipe
│
├── GoogleChrome/
│   ├── GoogleChrome.download.recipe
│   ├── GoogleChrome.pkg.recipe
│   └── GoogleChrome.munki.recipe

```

## Example Usage

### Download Latest Ableton Live

```bash
autopkg run AbletonLive.download.recipe
```

### Build Installer Package

```bash
autopkg run AbletonLive.pkg.recipe
```

### Build Sassafras Package

```bash
autopkg run AbletonLiveSassafras.pkg.recipe
```

### Create an Override

```bash
autopkg make-override AbletonLive.download.recipe
```

### Verify Recipe Processing

```bash
autopkg run -vv AbletonLive.download.recipe
```

## Contributing

Pull requests are welcome.

When contributing:

- Follow standard AutoPkg naming conventions
- Use reverse-DNS identifiers
- Use stable vendor download sources whenever possible
- Include code-signature verification where supported
- Keep processor dependencies documented
- Test recipes before submitting

## Troubleshooting

### Recipe Not Found

Refresh repositories:

```bash
autopkg repo-update all
```

Verify:

```bash
autopkg repo-list-recipes MinervaFT-recipes
```

### Processor Not Found

Install required dependency repositories:

```bash
autopkg repo-add https://github.com/homebysix/recipes.git
autopkg repo-update all
```

### Search Returns No Results

Verify repository registration:

```bash
autopkg repo-list
```

and:

```bash
autopkg repo-list-recipes MinervaFT-recipes
```

## Disclaimer

These recipes are provided as-is and are intended for use by macOS administrators. Always validate packages, code signatures, and deployment behaviour within your own environment before production use.

## Maintainer

MinervaFT

GitHub Repository:

https://github.com/MinervaFT/recipes
