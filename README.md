# Organization profile (`.github`)

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-green?logo=creativecommons&logoColor=white)](https://creativecommons.org/licenses/by/4.0/)
[![GitHub Pages](https://img.shields.io/badge/Pages-paper%20map-181717?logo=github)](https://post-quantum-cryptography-pqc.github.io/.github/)

**Repository:** [Post-Quantum-Cryptography-PQC/.github](https://github.com/Post-Quantum-Cryptography-PQC/.github)

GitHub organization special repository: the profile README becomes the [org homepage](https://github.com/Post-Quantum-Cryptography-PQC), and `docs/` is deployed as an interactive **paper map** (search / filter / sort) on GitHub Pages.

- **Org homepage**: https://github.com/Post-Quantum-Cryptography-PQC
- **Interactive paper map**: https://post-quantum-cryptography-pqc.github.io/.github/
- **Learning site**: https://post-quantum-cryptography-pqc.github.io/learning/
- **Parent lab**: [pqc-lab](https://github.com/Post-Quantum-Cryptography-PQC/pqc-lab) (consumes this tree as `learn/github`)
- **License**: CC BY 4.0 (see `LICENSE`)

## Table of contents

- [Features](#features)
- [Requirements](#requirements)
- [Quick start](#quick-start)
- [Project layout](#project-layout)
- [Related repositories](#related-repositories)
- [License](#license)

## Features

| Path | Role |
|------|------|
| [`profile/README.md`](profile/README.md) | Org homepage (static paper table + links) |
| [`docs/index.html`](docs/index.html) | Interactive paper map UI |
| [`docs/papers.json`](docs/papers.json) | Catalog data for the interactive page |
| [`.github/workflows/deploy-pages.yml`](.github/workflows/deploy-pages.yml) | Deploys `docs/` to GitHub Pages |

Do **not** hand-edit the generated catalog files for long. Refresh them from the lab index with `learn/export_papers_catalog.py`.

## Requirements

- Access to this repository (org maintainers)
- From [pqc-lab](https://github.com/Post-Quantum-Cryptography-PQC/pqc-lab): Python 3.10+ and an up-to-date [`docs/PAPERS.md`](https://github.com/Post-Quantum-Cryptography-PQC/pqc-lab/blob/main/docs/PAPERS.md)

## Quick start

Clone standalone:

```bash
git clone git@github.com:Post-Quantum-Cryptography-PQC/.github.git
cd .github
```

Recommended workflow from the parent lab:

```bash
cd pqc-lab
git submodule update --init --recursive
python3 learn/export_papers_catalog.py
# review learn/github/profile/README.md and learn/github/docs/
# commit inside learn/github, then:
bash learn/sync_learning_repos.sh
git add learn/github && git commit -m 'chore: bump .github profile submodule'
```

Pages deploy on push to `main` via `deploy-pages.yml` (artifact path: `docs`).

## Project layout

```text
.github/
├── profile/
│   └── README.md          # org homepage (generated + curated intro)
├── docs/
│   ├── index.html         # interactive paper map
│   └── papers.json
├── .github/
│   └── workflows/
│       └── deploy-pages.yml
├── LICENSE
└── README.md
```

## Related repositories

| Repo | Role |
|------|------|
| [`.github`](https://github.com/Post-Quantum-Cryptography-PQC/.github) | This module — org profile + paper-map Pages |
| [pqc-learning-public](https://github.com/Post-Quantum-Cryptography-PQC/pqc-learning-public) | Public curriculum source |
| [pqc-learning-private](https://github.com/Post-Quantum-Cryptography-PQC/pqc-learning-private) | Private explainers + graphs |
| [learning](https://github.com/Post-Quantum-Cryptography-PQC/learning) | Curriculum Pages host (`/learning/`) |
| [pqc-lab](https://github.com/Post-Quantum-Cryptography-PQC/pqc-lab) | Lab monorepo; pins this tree as `learn/github` |

## License

This project is licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). See [LICENSE](LICENSE).

**Third-party assets** (publisher metadata and DOI / venue links in the paper map) remain under their respective terms. This repository does not host paper PDFs.
