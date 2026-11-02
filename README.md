# Internship sensor software and experimental analysis

Custom Python software for temperature and load-cell measurements, alongside data and analysis from boiling, frying, and grilling cactus (nopales).

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

## Analysis status

This is an organized archive of the original internship work. Scripts and recorded results have been preserved without refactoring. Existing results have not been regenerated or independently validated.

- Temperature and force scripts contain paths from the original acquisition computer. Update input and output paths before running them with this layout.
- Boiling force scripts refer to `cutting_force.csv`; that input was not present in the supplied boiling archive. Existing corresponding plots and summary values are retained.
- The supplied frying archive contains four Python scripts (three audio scripts and one force script). A frying temperature-analysis script was not supplied.
- The supplied grilling archive contains data and results, but no analysis Python files.
- Audio scripts provide command-line options; consult their docstrings and `--help`. WAV recordings are included. Non-WAV conversion may require FFmpeg.
- Force recordings use the original `weight_g` measurements and labels. Check calibration and units before interpreting them as force in newtons.
- Dependencies are listed from source imports and are not version-pinned; the original Python environment was not supplied.

## Example recorded results

### Boiling temperature

![Boiling temperature](experiments/boiling/results/figures/temperature/boiling_cactus.png)

### Filtered boiling cutting-force measurements

![Filtered boiling cutting force](experiments/boiling/results/figures/force/filtered/cutting_force_filtered.png)

### Frying audio

![Frying pop counts](experiments/frying/results/figures/audio_output/pop_count_by_file.png)

