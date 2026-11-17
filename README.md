# cintel-05-drift-detection-custom

[![Python 3.14](https://img.shields.io/badge/python-3.14%2B-blue?logo=python)](pyproject.toml)
[![CI](https://github.com/sandra8918/cintel-05-drift-detection-custom/actions/workflows/ci-python-zensical.yml/badge.svg)](https://github.com/sandra8918/cintel-05-drift-detection-custom/actions/workflows/ci-python-zensical.yml)
[![Documentation](https://img.shields.io/badge/docs-site-blue?logo=github)](https://sandra8918.github.io/cintel-05-drift-detection-custom/)

[![uv managed](https://img.shields.io/badge/uv-managed-DE5FE9)](https://docs.astral.sh/uv/)
[![ty type checked](https://img.shields.io/badge/ty-type_checked-2F80ED)](https://docs.astral.sh/ty/)
[![Zensical docs](https://img.shields.io/badge/Zensical-docs-purple)](https://zensical.org/)
[![MIT](https://img.shields.io/badge/license-MIT-yellow.svg)](LICENSE)

> Detect meaningful changes in system behavior by comparing current measurements with a historical baseline.

## Project Overview

Author: Sandra Otubushin

Date: 2026 November

This project applies baseline comparison and drift detection to operational system metrics.

The analysis compares a historical reference period with a more recent current period. It examines requests, errors, latency, and error rates to determine whether the system is experiencing meaningful behavioral change.

The main question for the custom application is:

> Does an increase in errors reflect increased workload, or does it indicate reduced service reliability?

The project uses Python, Polars, automated testing, GitHub Actions, and Zensical documentation.

## Data

The project compares two datasets stored in the `data/` folder:

- **Reference data** represents earlier system behavior and provides the baseline.
- **Current data** represents more recent system behavior.

Both datasets include:

- `requests` - number of requests handled
- `errors` - number of failed requests
- `total_latency_ms` - total response time in milliseconds

The custom reliability analysis also calculates:

```text
error rate = errors / requests
