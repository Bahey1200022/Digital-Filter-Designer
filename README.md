# Digital Filter Designer

A Python/Flask web app for designing and exploring digital filters by placing zeros and poles on the unit circle, visualizing magnitude and phase responses, and applying filtering to sample signals.

## Overview

This project lets you:

- Add zeros and poles interactively in the z-plane
- View the resulting magnitude and phase response
- Adjust filter behavior through all-pass phase correction
- Upload or import signal examples
- Compare input and filtered output signals
- Experiment with real-time signal processing

The app is implemented with Flask on the backend and a browser-based plotting interface on the frontend.

## Features

- Interactive filter design using complex zero/pole placement
- Automatic conversion between pole/zero coordinates and transfer function form
- Frequency response generation using SciPy
- All-pass filter phase review and application
- Signal filtering and visualization
- Sample signal datasets bundled with the project

## Project Structure

```text
Digital-Filter-Designer/
├── app.py                 # Flask routes and application entry point
├── logic.py               # Filter logic and signal-processing helpers
├── templates/
│   └── index.html         # Main UI page
├── static/
│   ├── css/
│   ├── js/
│   └── assets/
├── Signal Examples/       # Example CSV signal data
├── README.md              # Project documentation
└── .gitignore             # Git ignore file (if present in repo)
```

## Requirements

Install the required Python packages:

```bash
pip install flask flask-cors numpy scipy
```

## Run the App

From the project root:

```bash
python app.py
```

Then open:

```text
http://127.0.0.1:5000/
```

## Application Workflow

1. Open the app in the browser.
2. Add zeros and poles to the unit-circle plot.
3. The app computes the frequency response automatically.
4. Review the magnitude and phase plots.
5. Optionally apply all-pass phase correction.
6. Import a signal or use the included signal examples.
7. Filter the signal and inspect the output.

## Main API Endpoints

The backend exposes several routes:

- `GET /` and `POST /` — renders the main page
- `POST /getFilter` — receives zero/pole data and returns frequency response data
- `POST /getAllPassFilter` — computes all-pass phase response
- `POST /digitalFilter` — evaluates a digital filter from zero/pole arrays
- `POST /getphase_correctors` — adds corrective zeros and poles
- `POST /delete` — removes selected components
- `POST /applyFilter` — applies the current filter to a signal sample

## Notes

- The app uses normalized frequency for plotting in the front-end.
- Signal processing is handled via SciPy's digital filter functions.
- This project is best suited for educational and interactive filter-design exploration rather than production deployment.

## License

This project does not currently include a license file. If you plan to distribute or reuse it publicly, add an appropriate license before publishing.

## Future Improvements

Potential enhancements include:

- Packaging with `requirements.txt`
- Better validation for invalid pole/zero inputs
- More robust signal upload handling
- Cleaner separation of frontend and backend logic
- Better documentation and test coverage
