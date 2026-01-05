# LLVM-AD Workshop Series Website

This repository hosts the official website for the **Workshop Series on Large Language and Vision Models for Autonomous Driving (LLVM-AD)**.

🌐 **Live Website:** [https://llvm-ad.github.io/](https://llvm-ad.github.io/)

## About the Workshop

The LLVM-AD workshop series aims to bring together professionals from academia and industry to explore the applications of large language and vision models in autonomous driving. Key interests include:
- Traffic Scene Understanding enhanced by VLMs
- Human-Autonomy Teaming driven by LLMs
- Multimodal Motion Planning and Prediction
- Language-Driven Sensor and Traffic Simulation

## Workshop Editions

This repository contains information and pages for the following workshop editions:

*   **[WACV 2026](https://llvm-ad.github.io/WACV_2026/)** (Upcoming)
*   **[ITSC 2025](https://llvm-ad.github.io/ITSC_2025/)**
*   **[WACV 2025](https://llvm-ad.github.io/WACV_2025/)**
*   **[ITSC 2024](https://llvm-ad.github.io/ITSC_2024/)**
*   **[WACV 2024](https://llvm-ad.github.io/WACV_2024/)**

## Local Development

To run this website locally for development or previewing changes:

### Prerequisites

*   Ruby (managed via `rbenv` recommended)
*   Bundler

### Installation

1.  Clone the repository:
    ```bash
    git clone https://github.com/llvm-ad/llvm-ad.github.io.git
    cd llvm-ad.github.io
    ```

2.  Install dependencies:
    ```bash
    bundle install
    ```

### Running the Server

Start the local Jekyll server:

```bash
bundle exec jekyll serve
```

The site will be available at `http://127.0.0.1:4000/`.

## Credits

This website is powered by [Jekyll](https://jekyllrb.com/) and uses the [al-folio](https://github.com/alshedivat/al-folio) theme.
