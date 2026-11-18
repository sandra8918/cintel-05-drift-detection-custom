# Detecting Changes in System Behavior

Continuous Intelligence | Project 05 | Custom Report

**Author:** Sandra Otubushin
**Date:** 2026 November

## Overview

This project examines whether recent system behavior differs meaningfully from an earlier reference period.

The analysis uses baseline comparison and drift detection to identify changes in operational metrics that may require investigation.

The custom project focuses on this question:

> Does an increase in errors reflect increased workload, or does it indicate reduced service reliability?

## Data

Two datasets represent different observation periods:

- **Reference data** represents earlier system behavior and provides the baseline.
- **Current data** represents more recent system behavior.

Each dataset contains:

- `requests` - number of requests handled
- `errors` - number of failed requests
- `total_latency_ms` - total response time in milliseconds

The files used in this project are:

- [View Reference Data](https://github.com/sandra8918/cintel-05-drift-detection-custom/blob/main/data/reference_metrics.csv)
- [View Current Data](https://github.com/sandra8918/cintel-05-drift-detection-custom/blob/main/data/current_metrics.csv)

## Methods

The pipeline uses Polars to:

1. Read the reference and current datasets.
2. Calculate summary statistics for both periods.
3. Calculate the difference between current and reference means.
4. Compare differences with configured drift thresholds.
5. Calculate error rates.
6. Save comparison results as CSV artifacts.
7. Record the process in `project.log`.

The difference is calculated as:

```text
difference = current_mean - reference_mean
