# sensor software and experimental analysis

This research was done as a part of an internship at an R&D software. Objectives were to configure sensors using custom software, collect data during a cooking process and visualize the data using Python tools. This repository includes custom Python software for temperature and load-cell measurements, alongside data and analysis from boiling, frying, and grilling cactus (nopales).

## Contents

- `sensor_software/temperature/tc_monitor.py`: Tkinter thermocouple monitor with CSV logging.
- `sensor_software/force/load_cell_gui.py`: Tkinter load-cell interface with calibration, live plotting, and logging.
- `experiments/boiling/`: temperature, cutting-force, and salinity measurements; raw and filtered force analysis.
- `experiments/frying/`: temperature, cutting-force, and audio measurements; force filtering, pop detection, and spectrogram analysis.
- `experiments/grilling/`: temperature and cutting-force data with existing plots and a peak-force table.
- `docs/`: original experiment reports and presentations.

Each experiment separates `analysis/`, `data/raw/`, `data/processed/`, `results/figures/`, and `results/tables/` where available. Original filenames and inner source folders are retained to preserve provenance. Summary CSVs are tables; filtered measurements and detected audio events are processed data.

## Setup and sensor software

Install Python with Tkinter, then install the Python dependencies:

```sh
python -m pip install -r requirements.txt
python sensor_software/temperature/tc_monitor.py
python sensor_software/force/load_cell_gui.py
```

Sensor acquisition requires compatible National Instruments hardware and the NI-DAQmx driver. Check the device/channel settings against your hardware. The force GUI describes the SC616C load cell, external amplifier, NI USB-6001, and calibration workflow in its opening docstring. Calibration is specific to the measurement setup.

## Example recorded results

### Boiling temperature

![Boiling temperature](experiments/boiling/results/figures/temperature/boiling_cactus.png)

### Filtered boiling cutting-force measurements

![Filtered boiling cutting force](experiments/boiling/results/figures/force/filtered/cutting_force_filtered.png)

### Frying audio

![Frying pop counts](experiments/frying/results/figures/audio_output/pop_count_by_file.png)

