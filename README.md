```markdown
# 📚 Doc-Genie - Python Documentation Generator v2.0

## Overview
Doc-Genie v2.0 is an advanced, AI-powered tool designed to automatically generate professional and accurate Python function docstrings. It performs deep analysis of your Python code, understanding its logic, parameters, and return types to produce high-quality documentation in either Google-style or NumPy-style formats. This tool aims to streamline the documentation process for developers, ensuring consistency and clarity in their projects.

## Features
Doc-Genie comes packed with intelligent features to ensure top-notch documentation:
-   **Accurate Logic Analysis**: Intelligently analyzes function bodies to understand their actual behavior, including operations, loops, and conditional logic.
-   **Contextual Descriptions**: Generates descriptive summaries that reflect the function's purpose and actions.
-   **Operation Detection**: Identifies mathematical operations (e.g., multiplication, addition, subtraction, division) and incorporates them into the docstring.
-   **Loop & Condition Recognition**: Detects the presence of `for`, `while` loops, and `if` statements to enhance the docstring's detail.
-   **Parameter & Return Type Inference**: Automatically extracts function signatures, including parameter names, types, default values, and return types.
-   **Multiple Docstring Styles**: Supports generating docstrings in both widely used Google and NumPy formats.
-   **Enhanced Export Options**: Allows users to download generated documentation as a comprehensive PDF report or a plain TXT file.
-   **Social Sharing**: Integrates with social media platforms (WhatsApp, Facebook) to easily share generated documentation.
-   **Interactive Gradio Interface**: Provides a user-friendly web interface for inputting code, selecting styles, and reviewing output.

## Supported Styles
-   **Google Style**: A widely adopted and readable docstring format, often used in many open-source projects.
-   **NumPy Style**: Popular in the scientific Python ecosystem, known for its clear and structured sections.

## Installation
To run Doc-Genie, you need to install the necessary Python packages. You can do this using pip:

```bash
pip install -q gradio transformers torch black autopep8 reportlab requests
```

**Note on `ast-super-parser`**: The original notebook attempted to install `ast-super-parser`, but this package failed to be found and installed. The core logic now uses the standard `ast` module for parsing. If you encounter any parsing issues with complex AST structures, you might need to find an alternative or ensure `ast-super-parser` becomes available.

## Usage

1.  **Clone the Repository (if applicable) or Open in Colab**: If you have this notebook locally, open it. Otherwise, open it directly in Google Colab.
2.  **Execute All Cells**: Run all code cells in the notebook. This will install dependencies and launch the Gradio web interface.
3.  **Access the Gradio Interface**: Once the final `demo.launch()` cell has executed, a public URL (e.g., `https://xxxxxxxx.gradio.live`) will be provided. Open this URL in your web browser.
4.  **Input Your Python Function**: Paste the Python function code for which you want to generate a docstring into the `Python Function` code input area. An example factorial function is provided by default.
5.  **Upload Python File (Optional)**: You can also upload a `.py` file containing your function using the `Or Upload .py File` component.
6.  **Select Docstring Style**: Choose your preferred docstring style (Google or NumPy) using the radio buttons.
7.  **Generate Docstring**: Click the `✨ Generate Docstring` button. The generated function with the new docstring will appear in the `Function with Docstring` output area.
8.  **Export and Share**: Use the `Export` and `Share` sections to:
    *   Download a PDF or TXT report of all generated docstrings.
    *   Generate shareable links for WhatsApp or Facebook.
9.  **Clear History**: The `🗑️ Clear History` button will reset the generation history.

## Example
Here's an example of the kind of Python function you can input and the docstring it might generate:

**Input Code:**
```python
def calculate_factorial(n):
    if n == 0:
        return 1
    return n * calculate_factorial(n-1)
```

**Generated Google-style Docstring (example output):**
```python
def calculate_factorial(n):
    """Calculates the factorial of a non-negative integer.

    Args:
        n (Any): Parameter for controlling n behavior.

    Returns:
        Any: The result of the computation.
    """
    if n == 0:
        return 1
    return n * calculate_factorial(n-1)
```
*(Note: Type hints would be inferred if present in the original function signature.)*

## Project Structure (Key Components)
-   **`DocGenieAnalyzer` Class**: The core logic that parses Python function code using the `ast` module, extracts signatures, and performs deep analysis of the function's body to understand its operations, loops, and conditions.
-   **`generate_docstring` Function**: Orchestrates the analysis and docstring generation based on the chosen style.
-   **`Gradio` Interface**: Provides the web-based UI for user interaction, including code input, style selection, and display of results.
-   **Export Functions**: `download_pdf`, `download_txt` handle saving the generation history into document formats.
-   **Sharing Functions**: `generate_whatsapp_link`, `generate_facebook_link` create URLs for easy sharing.

## Contributing
Contributions, issues, and feature requests are welcome! Feel free to check the [issues page](https://github.com/your-repo/your-project/issues) (if hosted on GitHub) or propose improvements directly.

## License
This project is open-source. Please specify your desired license (e.g., MIT, Apache 2.0) here.
```
