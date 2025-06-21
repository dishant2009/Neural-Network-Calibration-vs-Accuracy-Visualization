# Neural Network Calibration vs Accuracy Visualization

A comprehensive interactive visualization demonstrating the critical difference between model accuracy and calibration in neural networks. This tool helps researchers, practitioners, and students understand why a highly accurate model can still make dangerously overconfident predictions.

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Version](https://img.shields.io/badge/version-1.0.0-green.svg)
![JavaScript](https://img.shields.io/badge/javascript-ES6-yellow.svg)
![Chart.js](https://img.shields.io/badge/Chart.js-4.4.0-ff6384.svg)

## Table of Contents

1. [Overview](#overview)
2. [Why Calibration Matters](#why-calibration-matters)
3. [Features](#features)
4. [Installation](#installation)
5. [Usage Guide](#usage-guide)
6. [Understanding the Visualizations](#understanding-the-visualizations)
7. [Technical Implementation](#technical-implementation)
8. [Mathematical Background](#mathematical-background)
9. [Real-World Applications](#real-world-applications)
10. [Customization](#customization)
11. [API Reference](#api-reference)
12. [Contributing](#contributing)
13. [References](#references)

## Overview

This visualization tool demonstrates that **high accuracy ≠ reliable confidence**. A model that's 95% accurate but claims 99% confidence on every prediction is dangerous in critical applications. Calibration ensures that when a model says it's "80% confident," it's actually correct 80% of the time.

### Key Concepts

- **Accuracy**: The percentage of correct predictions
- **Calibration**: How well confidence scores match actual performance
- **Expected Calibration Error (ECE)**: A metric measuring the average calibration error across all confidence levels
- **Temperature Scaling**: A post-processing technique to improve calibration without retraining

## Why Calibration Matters

### The Problem

Consider a medical AI system:
- **Accuracy**: 90% (sounds good!)
- **Average Confidence**: 95% (very confident!)
- **Reality**: When it says "95% sure this is benign," it's wrong 20% of the time

This overconfidence can lead to:
- Skipped medical tests that could save lives
- Autonomous vehicles not slowing down when uncertain
- Financial systems taking excessive risks
- Content moderation systems making irreversible mistakes

### The Solution

Well-calibrated models:
- Express uncertainty when appropriate
- Enable better human-AI collaboration
- Allow for risk-adjusted decision making
- Build trust through reliable confidence estimates

## Features

### 1. Interactive Model Comparison

Four pre-configured models demonstrate different calibration behaviors:

- **Overconfident Model**: High confidence even when wrong (typical of many neural networks)
- **Underconfident Model**: Always unsure, even when correct
- **Well-Calibrated Model**: Confidence matches accuracy
- **Custom Settings**: Experiment with your own parameters

### 2. Real-Time Visualizations

#### 100-Sample Prediction Grid
- Visual representation of 100 model predictions
- Color coding: Green (correct) vs Red (incorrect)
- Brightness indicates confidence level
- Hover for detailed information

#### Reliability Diagram
- The most important calibration visualization
- Diagonal line represents perfect calibration
- Points show actual model behavior
- Distance from diagonal indicates miscalibration

#### ECE Breakdown
- Bar chart showing calibration error by confidence bin
- Green bars: Well-calibrated bins (<5% error)
- Yellow bars: Moderate miscalibration (5-10% error)
- Red bars: Severe miscalibration (>10% error)

### 3. Interactive Controls

#### Temperature Scaling Slider
- Range: 0.1 to 5.0
- Default: 1.0 (no scaling)
- Lower values: Reduces confidence spread
- Higher values: Increases confidence spread
- Real-time visualization updates

#### Confidence Bias Control
- Range: -0.5 to +0.5
- Positive values: Increases overall confidence
- Negative values: Decreases overall confidence
- Demonstrates systematic over/underconfidence

### 4. Metrics Dashboard

Four key metrics updated in real-time:

1. **Accuracy**: Percentage of correct predictions
2. **ECE**: Expected Calibration Error (lower is better)
3. **Average Confidence**: Mean confidence across all predictions
4. **Calibration Quality**: Human-readable assessment

## Installation

### Option 1: Direct Usage
Simply open the HTML file in a modern web browser. No installation required.

```bash
# Clone the repository
git clone https://github.com/yourusername/calibration-visualization.git

# Open in browser
open calibration-visualization.html
