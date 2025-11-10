# IoT Sensor Anomaly Detection – Quickstart

## What’s here
- `sensor_data.csv` – synthetic dataset with labels.
- `results.csv` – model comparison metrics and thresholds.
- `run_pipeline.py` – standalone script to regenerate results and plots.
- `SUMMARY.md` – 2–3 page summary.
- Plots: `plot1_raw_vs_clean.png`, `plot2_feature_distribution.png`, `plot3_iso_scores.png`, `plot4_sensor_with_anoms.png`, `plot5_roc_iso.png`, `plot6_roc_ae.png` (if TF available).

## How to run
```bash
python run_pipeline.py
```

The script will:
1. Generate or load data
2. Clean and engineer features
3. Train Isolation Forest and an Autoencoder (if TensorFlow is available)
4. Evaluate and save metrics/plots under `./outputs` (defaults to `/mnt/data` here)

## Python deps
- pandas, numpy, scikit-learn, matplotlib
- tensorflow (optional; enables Autoencoder)

## Notes
- Thresholds are set to 98.5th percentile of anomaly scores by default. Adjust via `--percentile`.
- For unlabeled real data, use visual inspection, domain rules, or controlled A/B to validate alerts.
