# TAK Generator with LLM and

This project provides a Python script that uses a language model (LLM) to generate TAK files based on a high-level description, adhering to a given XML Schema Definition (XSD) file. The generated XML is validated against the schema and saved to a specified location.

## Features

- Parses an XSD file to understand the XML structure and element types.
- Generates TAK content based on a user description using OpenAI's language model.
- Validates the generated TAK against the XSD schema before saving.
- Saves the validated TAK file to a specified location.

## Requirements

- **Python 3.x**
- **pip** (Python package manager)
- OpenAI API key to access language model features

## Setup Instructions

### Step1: Rust Installation and PATH Setup (Windows)
To ensure compatibility with dependencies that require Rust, follow these steps to install Rust on Windows and add it to your system PATH.

#### Install Rust

1. **Download Rust**:
   - Visit [https://rustup.rs](https://rustup.rs) and download the installer for Windows.
   - Alternatively, you can run this command in PowerShell:
     ```powershell
     Invoke-WebRequest -Uri https://win.rustup.rs -OutFile rustup-init.exe
     .\rustup-init.exe
     ```
2. **Run the Installer**:
   - Run the `rustup-init.exe` installer.
   - Follow the on-screen instructions (the default installation options are recommended).

#### Add Rust to Your PATH
After installation, you need to ensure Rust is added to your PATH so that the system recognizes it.

1. **Open Environment Variables**:
   - Press `Win + R` to open the Run dialog.
   - Type `sysdm.cpl` and press `Enter` to open System Properties.
   - Go to the **Advanced** tab and click **Environment Variables**.

2. **Edit the PATH Variable**:
   - In the Environment Variables window, under **System Variables**, locate the `Path` variable and select it.
   - Click **Edit**.

3. **Add the Rust Path**:
   - In the Edit Environment Variable window, click **New**.
   - Add the following path (replacing `YourUsername` with your Windows username):
     ```plaintext
     C:\Users\YourUsername\.cargo\bin
     ```
4. **Save and Verify**:
  - Click **OK** to close each window and save your changes.
  - Close and reopen any Command Prompt or PowerShell windows for the changes to take effect.
  - To confirm Rust is installed and accessible from the PATH, open a new terminal and run:
      ```powershell
      rustc --version

### Step2: Install Required Python Libraries

1. **Upgrade pip**:
   ```bash
   python -m pip install --upgrade pip
2. **Install the necessary libraries**:
    ```bash
    pip install openai xmlschema

### Step3: API Key Setup
To use the OpenAI API in this project, you’ll need to obtain an API key from OpenAI. Follow these steps to get your API key and add it to the script.

1. **Sign Up or Log In**:
   - Go to [OpenAI’s website](https://platform.openai.com/signup) and sign up for a new account, or log in if you already have one.

2. **Generate an API Key**:
   - Once logged in, navigate to the **API Keys** section by clicking on your profile icon in the top right corner and selecting **API Keys**.
   - Click on **+ Create new secret key** to generate a new API key.
   - **Copy the key** immediately, as you won’t be able to view it again.

3. **Add the API Key to Your Script**:
   - Open the `xml_generator.py` script.
   - Locate the line in the script where `openai.api_key` is set.
   - Replace `'your_openai_api_key'` with your actual API key, like this:

     ```python
     openai.api_key = 'your_actual_api_key_here'
     ```
   **Note**: Keep your API key secure. Avoid sharing it publicly or uploading it to version control (e.g., GitHub). If you accidentally expose your API key, delete it from the OpenAI dashboard and create a new one.

### Step4: Place Your XSD File
To ensure the generated XML structure follows the correct format, you'll need to specify the path to your XML Schema Definition (XSD) file.

1. Place your XSD file in a known directory.
2. Open the `xml_generator.py` script.
3. Locate the line where `xsd_file_path` is defined.
4. Update the `xsd_file_path` variable with the full path to your XSD file. For example:
   ```python
   xsd_file_path = '/path/to/your_schema.xsd'  # Replace with your actual XSD path

## Run Example
    python xml_generator.py give me a state that has a one-derived derviedFrom 1000 and a LOW value when the value is below 3.6, have a Normal value when between 3.6 and 5.2 and have a High value when is bigger from 5.2, name the Tak xml as Potassium_state

## License
This project is licensed under the MIT License.

You are free to use, modify, and distribute this software, provided that the following conditions are met:

- **Permission is granted** to use this software for any purpose.
- **Modification** is allowed, as well as distribution of modified versions.
- **Attribution** must be given to the original author.

For more details, see the full [MIT License text](https://opensource.org/licenses/MIT).





    

