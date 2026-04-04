# Genus2DB / M2 Database

**A Self-Populating Database and API for Rational Points in the Moduli Space of Genus Two Curves**

[![Python](https://img.shields.io/badge/Python-3.10%2B-blue)](https://www.python.org)
[![License](https://img.shields.io/badge/license-MIT-green)](LICENSE)
[![Docker](https://img.shields.io/badge/Docker-ready-blue)](docker-compose.yml)

## About

The **M₂ Database** (also called **Genus2DB**) is a live, self-populating NoSQL database and modern REST/WebSocket API for rational points in the moduli space **M₂** of genus-two curves over ℚ.

Every rational point is stored under a **unique canonical representative** in the weighted projective space ℙ_w with weights **w = (2, 4, 6, 10)**. When a point is missing, the system automatically computes the canonical representative, all heights, automorphism group, minimal model, `is_fine` flag, conductor, twists, and membership in the loci **Lₙ** (n = 2, 3, 5, 7).

It unifies two major existing datasets:
- The 2016 height-bounded database (Beshaj et al., >1 million curves)
- The 2024 weighted-projective dataset (Shaska et al.)

and grows automatically with use.

**Live public instance**: [https://genus2db.org](https://genus2db.org)

## Key Features

- **Mathematically canonical keys** – every isomorphism class has exactly one primary key
- **Self-populating** – missing points are computed and inserted on-the-fly
- **Sub-millisecond queries** via Redis cache + FastAPI
- **Full SageMath / Python integration**
- **Height-bounded and filtered searches** (fine/coarse, Lₙ loci, etc.)
- **Docker-ready** – deploy locally with one command
- **Open source** (MIT license)

## Quick Start

### 1. Local deployment (recommended)

```bash
git clone https://github.com/yourusername/genus2db.git
cd genus2db
docker-compose up -d
