# cToPromella

cToPromella is a tool designed to translate simple C programs into Promela (Process Meta Language) models, facilitating formal verification using the SPIN model checker. With support for basic constructs such as control flow statements, functions, pointers, structs, and arrays, cToPromella bridges the gap between C code and formal verification.

## Features

- **C to Promela Translation**: Supports `if-else`, loops (`while`, `for`, `switch`), function calls, pointers, structs, arrays, and basic operators.
- **Command-Line Interface**: Installable as a console script `c2p` for quick translations in terminal.
- **Web Interface**: A Flask-based web application (`app.py`) allows users to upload C source files and view generated Promela code in the browser.
- **Sample Programs**: Includes a `samples/` directory with example C programs and their corresponding `.pml` outputs.
- **Modular Architecture**: Core translation logic is encapsulated in the `c2p` Python package, making it easy to extend and maintain.

## Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/your-username/cToPromella.git
   cd cToPromella
   ```
2. **Create a virtual environment** and activate it:
   ```bash
   python3 -m venv venv
   source venv/bin/activate
   ```
3. **Install dependencies**:
   ```bash
   pip install -e .
   ```
   This will install the `c2p` package and its dependencies (e.g., `flask`, `pycparser`).

## Usage

### Command-Line

Translate a C source file to Promela and print to stdout:
```bash
c2p samples/main.c
```

Save the output to a file:
```bash
c2p samples/main.c -o output.pml
```

### Web Interface

1. Run the Flask app:
   ```bash
   python app.py
   ```
2. Open your browser and navigate to `http://127.0.0.1:5000`.
3. Upload a C source file or choose one from the `samples/` directory.
4. View and copy the generated Promela code.

## Directory Structure

```
cToPromella/
├── app.py                  # Flask web interface
├── c2p/                    # Core translation package
│   ├── __main__.py         # CLI entry point
│   ├── ast_parser.py       # C AST parsing logic
│   ├── translator.py       # C to Promela translation logic
│   └── ...
├── samples/                # Example C programs and .pml outputs
│   ├── main.c
│   ├── main.pml
│   └── ...
├── setup.py                # Installation script
└── README.md               # Project documentation
```

## Contributing

Contributions are welcome! Please open an issue or submit a pull request for bug fixes, enhancements, or new features. Make sure to update tests and documentation as needed.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Built on top of `pycparser` for C AST generation.
- Inspiration from SPIN model checker and Promela tutorials.
