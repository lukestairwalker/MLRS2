# Environment Setup
This guide will walk you through setting up your development environment on
Windows, Linux, and macOS. Please follow the instructions relevant to your operating system.

## Step 1: Install VSCode
VSCode is an Integrated Development Environment (IDE) that will help you write your Python code more efficiently.

### Windows & macOS:

Follow the instructions [here (Windows)](https://code.visualstudio.com/docs/setup/windows) or [here (macOS)](https://code.visualstudio.com/docs/setup/mac) to install VSCode on your system.


### Ubuntu:

On Ubuntu the easiest way to install VSCode is the build in Software manager "Ubuntu Software". You can search for "vscode" and install it from there.

## Step 2: Setting Up a Virtual Environment

To manage Python packages for individual projects, it is best practice to use a virtual environment.
Follow these steps to set up a virtual environment for your MLRS2 exercise in VSCode.

### Open the this Code in VSCode:

1. **Launch VSCode**.
2. Select **Open** on the Welcome screen or choose **File > Open...** from the main menu.
3. Navigate to the directory where you extracted your exercise files and select the folder.
4. Click **OK** to open the folder as a VSCode project.

### Create a Virtual Environment:

1. Once the project is open in the IDE, open the Command Palette (`Ctrl+Shift+P`), search for the **Python: Create Environment** command, and select it.
2. The command presents a list of environment types: **Venv** or **Conda**. Select **Venv**.
3. Choose the base interpreter. Ensure you select Python 3.9 or higher (you should see it in the list as it should have been installed globally).
4. You can select the requirements.txt file to install the dependencies automatically.
5. The virtual environment will be created in the project directory and automatically sourced. You can see it in the bottom left corner of the IDE after opening a *.py file.

## Step 3: Install Dependencies
Now, you'll install the required libraries listed in requirements.txt.

### All Platforms:

1. Open the terminal in VSCode (**Terminal > New Terminal**).
2. (optional, done automatically by VSCode) Activate the virtual environment:
    - Windows: `.\venv\Scripts\activate`
    - Linux/macOS: `source venv/bin/activate`
3. (optional, already done before) Install dependencies: `pip install -r requirements.txt`
4. Allow your code to be able to see 'mlrs2': `pip install -e .`


## Step 4: Install PyTorch
Install PyTorch

Visit the [PyTorch Get Started page](https://pytorch.org/get-started/locally/), select your specifications, and copy the installation command provided.

### Example Installation without CUDA (Windows):

```bash
pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cpu
```

## Conclusion
You're now set up with a complete development environment for our MLRS2 Exercise.
If you encounter any issues, please review the steps to ensure all procedures were correctly followed or reach out for assistance.


## Troubleshooting

You may encounter the following GLFW errors if running on machine without a display:

GLFWError: (65544) b'X11: The DISPLAY environment variable is missing'
  warnings.warn(message, GLFWError)
GLFWError: (65537) b'The GLFW library is not initialized'

These can be resolved with:
```bash
export MUJOCO_GL=egl
```