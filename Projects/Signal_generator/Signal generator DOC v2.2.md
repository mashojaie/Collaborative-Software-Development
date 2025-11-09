# Signal Processing Toolkit - Group Project

## The Problem

Research teams across different fields face a common challenge: sensor data is noisy and difficult to interpret. Whether monitoring heartbeats, analyzing radio communications, or processing temperature readings, scientists need tools to generate test signals, remove noise, analyze frequency content, and visualize results. Your mission is to build a reusable signal processing toolkit that handles this complete workflow.

---

## Project Structure

This project is organized in phases. Each phase produces a working demonstration, so you'll have something functional to present regardless of how far you progress.

**Phase 1 - Signal Generation**: Create tools to generate sine waves with different frequencies and visualize them in the time domain. Your deliverable is a program that plots multiple sine waves together.

**Phase 2 - Complexity & Noise**: Develop the ability to combine multiple signals and add realistic noise. Deliver comparison visualizations showing clean versus noisy signals.

**Phase 3 - Filtering**: Implement noise reduction techniques using low-pass filters and moving averages. Demonstrate before-and-after comparisons showing successful noise removal.

**Phase 4 - Analysis**: Extract meaningful information through statistical analysis and frequency-domain analysis using FFT. Create comprehensive reports with visualizations, statistics, and CSV exports.

---

## Phase 1: Signal Generation & Visualization

Before testing any signal processing algorithms, you need clean, controllable test data. Real sensor data is too messy to verify if your algorithms work correctly. Your first task is building tools to generate sine waves with adjustable parameters: frequency (oscillations per second), duration, amplitude (signal strength), and sampling rate (data points per second). The key challenge is converting continuous mathematical functions into discrete sample points.

Once you can generate signals, create visualizations that plot them against time. Make your plots readable with clear axis labels, grids for reference, and appropriate sizing. For your Phase 1 demonstration, generate sine waves at three different frequencies (for example, 2 Hz, 5 Hz, and 10 Hz) and plot them together on the same figure to show the difference in oscillation rates.

---

## Phase 2: Composite Signals & Noise

Real signals rarely contain a single pure frequency. They're usually combinations of multiple components mixed together. Build functionality to combine two or more sine waves by adding them together. Consider how to handle edge cases: what if signals have different lengths or amplitudes? Design your solution to either handle these cases or reject invalid inputs gracefully.

Real sensors also introduce random noise into measurements. Simulate this by adding white Gaussian noise to your signals with a controllable noise level parameter. This will let you test how well your filtering algorithms work later. Create enhanced visualizations that overlay multiple signals with different colors and legends so viewers can easily distinguish between them.

Your Phase 2 demonstration should show a composite signal made from two different frequencies (such as 5 Hz and 20 Hz), then display the same signal with added noise, plotting both versions for comparison. This proves your toolkit can create realistic test scenarios.

---

## Phase 3: Noise Reduction

Noisy data is difficult or impossible to analyze. Your toolkit needs to remove noise while preserving the actual signal. Implement a low-pass filter using the Butterworth filter from scipy.signal. The concept is straightforward: low frequencies typically represent your actual signal (slow changes over time), while high frequencies often represent noise (rapid random fluctuations). Your filter should accept parameters for cutoff frequency and filter order, then apply the filter using filtfilt to avoid phase distortion.

As a simpler alternative, also implement moving average smoothing. This technique replaces each point with the average of nearby points. While easier to implement and understand, it's less precise than frequency-domain filtering. Consider the trade-offs between simplicity and effectiveness.

Create compelling visualizations showing the original clean signal, the noisy version, and the filtered result. Your Phase 3 demonstration should take the noisy composite signal from Phase 2, apply your low-pass filter, and prove that the two original frequency components remain intact while the random noise is reduced. Calculate and display RMS values before and after filtering to quantify the improvement.

---

## Phase 4: Analysis & Reporting

Visual inspection isn't enough. You need quantitative analysis to answer questions like "What frequencies are present?" and "How effective was the filtering?" Compute summary statistics including mean, standard deviation, minimum, maximum, and RMS (root-mean-square) values. Compare these metrics before and after filtering to measure improvement objectively.

Implement frequency analysis using the Fast Fourier Transform. FFT converts your time-domain signal into the frequency domain, revealing which frequency components are present and how strong each one is. After computing the FFT, identify the dominant frequency peaks. This is crucial for applications like detecting heart rate from ECG signals or identifying carrier frequencies in radio communications.

Export your results to CSV files for further analysis or reporting. Save both the raw signal data (time and amplitude columns) and analysis reports containing statistics and identified frequencies. Use pandas DataFrames to organize this data cleanly. Finally, create a comprehensive multi-panel dashboard showing the time-domain view, frequency spectrum, before-after comparison, and key statistics all in one figure.

Your Phase 4 demonstration should show the complete pipeline: generate a composite signal, add noise, apply filtering, compute and compare statistics for all three versions, perform frequency analysis to verify the original frequencies are still detectable, and produce both CSV reports and a publication-quality dashboard figure.

---

## Code Organization

Structure your code into logical modules. You might organize it as a signal generation module (creates and combines signals), a signal processing module (adds noise and applies filters), an analysis module (computes statistics and performs FFT), and a visualization module (creates plots and dashboards). Finally, create a main application that demonstrates the complete workflow and integrates all modules together. The exact structure is up to you, but aim for clear separation of concerns.

---

## Testing Strategy

Start with simple test cases before building complex examples. Use short signals (one second), few samples (100 points), and single frequencies initially. Verify your logic at each step: does a 5 Hz signal actually oscillate five times per second? Does adding noise increase the signal's variance? Does filtering reduce high-frequency components? Once you're confident the basics work, scale up to longer signals with more samples and complex frequency combinations.

---

## Technical Challenges

You'll encounter several key challenges. First, when combining signals, all arrays must have the same length - decide how to enforce this. Second, FFT requires knowing the sampling rate, so maintain consistency throughout your pipeline. Third, some filters can introduce artifacts; research the difference between filter() and filtfilt(). Fourth, FFT produces complex numbers and negative frequencies; determine how to interpret and display only the meaningful results.

---

## Suggested Test Case

A good end-to-end test is to generate a 5 Hz sine wave (amplitude 1.0) and a 20 Hz sine wave (amplitude 0.5), combine them, add white noise with standard deviation 0.3, then apply a low-pass filter with cutoff at 15 Hz. Compare statistics before and after filtering, and verify that both original frequencies are still present in the filtered signal. This test works well because you know the true frequencies in advance, the cutoff frequency should preserve both signal components while removing higher-frequency noise, and success is easy to verify visually and numerically.

---

## Deliverables

Each phase should produce specific outputs. Phase 1 delivers signal generation code, basic visualization capabilities, and a demo showing multiple sine waves plotted together. Phase 2 adds composite signal creation, noise addition functionality, and a demo comparing clean versus noisy signals. Phase 3 includes filtering implementation, comparison visualizations, and a demo showing noise removal effectiveness. Phase 4 completes the toolkit with statistical analysis, FFT implementation, CSV export capabilities, a comprehensive dashboard, and a demo showing the complete pipeline.

All phases should include a README file explaining how to use your toolkit, well-documented code with comments and docstrings, and example outputs including plots and data files.

---

## Evaluation

Your project will be assessed on functionality (does each phase work and can you demonstrate the complete pipeline?), code quality (clear organization, reasonable naming, appropriate comments), integration (do modules work together with consistent interfaces?), and output quality (clear visualizations and informative reports).

---

## Getting Started

Begin by ensuring you have numpy, pandas, matplotlib, and scipy installed. Create your project directory and initial files, then divide your team by phases or modules. Focus on completing Phase 1 before moving forward - it's better to have fewer phases working well than all phases incomplete. Test incrementally rather than waiting until everything is written. Document as you develop, not at the end. This incremental approach ensures you'll always have something functional to demonstrate.