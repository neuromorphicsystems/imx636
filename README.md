- [Installation](#installation)
- [Usage](#usage)
- [Render event data](#render-event-data)

# Installation

> [!WARNING]
> The Python version that comes from Microsoft's Windows Store does not work with PySide6 (specifically, PySide6 complains that it cannot find qtquick2plugin.dll even though the file exists). Make sure to install Python from the official website https://www.python.org.

1. Clone this repository (`git clone https://github.com/neuromorphicsystems/davis346-recorder`) or download and unzip a copy (`<> Code` button). Open a terminal and `cd` to the repository's directory.

2. Create a virtual environment

    ```sh
    # Linux, macOS
    python3 -m venv .venv

    # Windows
    python -m venv .venv
    ```

3. Activate the virtual environment

    ```sh
    # Linux, macOS
    source .venv/bin/activate

    # Windows (cmd.exe)
    .venv\Scripts\activate.bat

    # Windows (PowerShell)
    .venv\Scripts\Activate.ps1
    ```

4. Install dependencies

    ```sh
    pip install neuromorphic-drivers faery PySide6
    ```

# Usage

1. Activate the virtual environment (skip this if you just went through the installation steps)

    ```sh
    # Linux, macOS
    source .venv/bin/activate

    # Windows (cmd.exe)
    .venv\Scripts\activate.bat

    # Windows (PowerShell)
    .venv\Scripts\Activate.ps1
    ```

2. Run the application

    ```sh
    python imx636.py
    ```

If the display is choppy or lags behind real-time, the camera may be generating too many events for the software to handle (possibly due to flickering lights in the room). Reducing the sensitivity by increasing `diff_on` (for instance to `150`) and `diff_off` (for instance to `130`) should help reduce the event rate.

# Render event data

1. Create a directory called **recordings**

2. Copy event files of interest (.csv) from **data** to the directory **recordings**

3. Run `faery init`

4. Run `faery run`

Rendered data will be placed in **renders**.

See https://github.com/aestream/faery?tab=readme-ov-file#workflow for an example on how to generate a slow-motion video render.
