# WCA Analytics

An analytics API for competitive speedcubing, built on the official World Cube
Association results database.

> **Status:** In active development. Not yet deployed.

## About

The World Cube Association publishes its full competition results as a public
database export, every result from every official competition since 2003.
The official website exposes this data mainly as rankings and personal records.

This project turns that dataset into a queryable API and adds analysis the
official site does not provide: career progressions, head-to-head comparisons,
and a strength rating that accounts for the quality of the field a competitor
faced.

## Data source

Results are imported from the official WCA export:
https://www.worldcubeassociation.org/export/results

The dataset has a few characteristics worth knowing about:

- Times are stored in centiseconds (`1234` = 12.34 s)
- Negative values encode outcomes, not times: `-1` = DNF, `-2` = DNS
- Fewest Moves (`333fm`) stores move counts rather than times
- Multi-Blind (`333mbf`) uses a packed format encoding solved cubes,
  attempted cubes, and time in a single integer

Handling these correctly is a meaningful part of the import logic.

## Tech stack

| Layer | Choice |
|---|---|
| Language | Python 3.14 |
| API | FastAPI |
| Database | PostgreSQL |
| ORM / migrations | SQLAlchemy, Alembic |
| Testing | pytest, testcontainers |
| Containerization | Docker, Docker Compose |
| CI/CD | GitHub Actions |

## Local setup

Not available yet — this section will be filled in once the containerized
setup exists.

## License

MIT — see [LICENSE](LICENSE).