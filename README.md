# MinervaFT AutoPkg Recipes

Community AutoPkg recipes maintained by MinervaFT.

This repository contains AutoPkg recipes for macOS software packaging, deployment, and update automation.

## Requirements

- AutoPkg 2.3 or later
- macOS
- Internet access to vendor download sources

## Adding this Repository

Add the repository to AutoPkg:

```bash
autopkg repo-add https://github.com/MinervaFT/recipes.git
```

Update all repositories:

```bash
autopkg repo-update all
```

Search available recipes:

```bash
autopkg search ableton
autopkg search chrome
```

List all recipes from this repository:

```bash
autopkg repo-list-recipes MinervaFT-recipes
```

## Available Recipes

| Application | Download | Package | Munki | Notes |
|------------|----------|----------|--------|--------|
| Ableton Live | ✅ | ⬜ | ⬜ | Supports Live 11 and 12 |
| Google Chrome | ✅ | ✅ | ✅ | Enterprise browser deployment |
| Cisco Packet Tracer | ✅ | ✅ | ✅ | Networking labs |
| Camtasia | ✅ | ✅ | ✅ | Screen recording and editing |

## Example Usage

### Download Ableton Live

```bash
autopkg run AbletonLive.download.recipe
```

### Override Recipe

```bash
autopkg make-override AbletonLive.download.recipe
```

### Run Override

```bash
autopkg run AbletonLive.download.recipe.yaml
```

## Repository Structure

```text
recipes/
├── AbletonLive/
│   ├── AbletonLive.download.recipe
│   ├── AbletonLive.pkg.recipe
│   └── AbletonLive.munki.recipe
├── GoogleChrome/
│   ├── GoogleChrome.download.recipe
│   ├── GoogleChrome.pkg.recipe
│   └── GoogleChrome.munki.recipe
└── Placeholder/
    ├── Placeholder.download.recipe
    ├── Placeholder.pkg.recipe
    
```

## Naming Convention

Recipes use the following identifier convention:

```text
com.github.MinervaFT.Application.download
com.github.MinervaFT.Application.pkg
```

Example:

```text
com.github.MinervaFT.AbletonLive.download
```

## Reporting Issues

If a recipe no longer downloads correctly due to vendor website changes, please open a GitHub issue with:

- Recipe name
- AutoPkg version
- Error output
- Vendor download URL (if known)

## Disclaimer

These recipes are provided as-is and have been developed for macOS software deployment workflows. Always validate packages and signatures within your own environment before production deployment.
