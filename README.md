# F1 Manager 2024 – Monte Carlo Strategy Lab

A React-based single-file simulation tool that brings **race strategy Monte Carlo analysis** into your browser. Inspired by how real F1 strategy teams work, this app lets you plug in your Free Practice / Quali data and test thousands of parallel race scenarios.

## Features
- Configure **tyre models** (base pace, degradation rate, warmup penalty).
- Set **race parameters**: laps, fuel effect, pit loss, driver noise, traffic.
- Simulate **Safety Car and VSC windows** with track-specific probabilities.
- Define multiple **strategies** (sequences of stints by compound and laps).
- Run thousands of **Monte Carlo simulations** with shared SC/VSC schedules for fair comparisons.
- Get detailed **summary stats**: mean, P10, P50, P90, standard deviation, and probability of being the fastest.
- Visualize **time distributions** with histograms.
- Quick **Undercut / Overcut Advisor** for lap‑by‑lap pit call guidance.

## Getting Started

### Install
Clone the repository and install dependencies:
```bash
git clone https://github.com/MBicanov/Bicanovsky_F1-Manager-PitwallX.git
cd f1-montecarlo-lab
npm install
```

### Run locally
```bash
npm run dev
```
Open your browser at [http://localhost:5173](http://localhost:5173).

## Usage
1. **Race Settings** – enter total race laps, number of sims, fuel effect, pit loss, etc.
2. **Tyre Models** – calibrate each compound using your FP/Quali data (base pace, degradation slope, warmup time).
3. **Safety Car/VSC** – tune intervention probabilities and time losses.
4. **Strategies** – build plans like *M→H* (1-stop) or *M→M→H* (2-stop).
5. **Run Simulation** – click the run button to generate thousands of race universes.
6. **Interpret Results** – compare strategy averages, spreads, and probability of being fastest. Use histograms for deeper insight.

## Example
- *Plan A – M→H (1-stop)* might show 62% probability of being the fastest option with a narrow variance.
- *Plan B – M→M→H (2-stop)* could be riskier but pays off in SC‑heavy universes.

## Undercut Advisor
Enter rival’s degradation, your expected out-lap penalty, and laps they stay out. The advisor estimates the undercut gain in seconds and whether it’s worth boxing immediately.

## Calibrating with FP/Quali Data
- Use long runs to estimate degradation (deg) per compound.
- Compare early vs late stints to calibrate fuel effect.
- Get pit loss values from telemetry or in-game overlays.
- Adjust SC/VSC rates to reflect track history.

## Tech Stack
- **React + TypeScript**
- **Tailwind CSS** for styling
- **Custom RNG (Mulberry32)** for reproducible random sequences

## Roadmap
- Multi-car support (e.g., VER vs PER)
- Rival field modeling with pace offsets and rejoin-in-traffic penalties
- Export results (CSV/Parquet)
- Richer visualization with charts

## License
MIT License © 2025

---
Built for sim racers and F1 nerds who want to run their own pit wall.
