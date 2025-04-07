# Quantum-Compiler
(Binary-to-Qubit Compiler AI Agent)

## Overview
This project is an AI-driven quantum compiler that converts binary code into qubit representations using a mathematical approach. It features a **Gradio UI** for user interaction, allowing binary inputs to be transformed into quantum-inspired qubit states. This approach bypasses the need for Qiskit's Aer simulator by implementing raw matrix operations with NumPy.

## Features
- **Binary to Qubit Transformation**: Converts binary strings (e.g., `1101`) into normalized qubit states.
- **Gradio User Interface**: Provides an easy-to-use web-based interface for interaction.
- **Lightweight Quantum Simulation**: Uses NumPy for raw quantum state transformations without Qiskit Aer dependencies.

## Installation & Setup
### Prerequisites
Ensure you have Python installed along with the necessary dependencies:

```bash
pip install numpy gradio
```

### Running the Application
1. Clone the repository:
   ```bash
   git clone https://github.com/PSivaMallikarjun/Quantum-Compiler.git
   cd binary-to-qubit-ai
   ```
2. Run the Python script:
   ```bash
   python app.py
   ```
3. Open the **Gradio** link that appears in the terminal.

## Usage
1. Enter a binary string (e.g., `1011`) into the Gradio input field.
2. Click the **Submit** button.
3. View the normalized **qubit state** representation as output.

## Code Explanation
### Main Function (`binary_to_qubit`)
```python
import numpy as np
import gradio as gr

def binary_to_qubit(binary_str):
    try:
        binary = np.array([int(bit) for bit in binary_str])
        norm_factor = np.linalg.norm(binary)
        qubits = binary / norm_factor if norm_factor != 0 else binary
        return f"Qubit State: {qubits}"
    except Exception as e:
        return f"Error: {str(e)}"
```
This function:
- Takes a binary string as input.
- Converts it into an array of integers.
- Normalizes it using **L2 norm** to simulate quantum state behavior.
- Returns the qubit state.

### Gradio Interface
```python
iface = gr.Interface(
    fn=binary_to_qubit,
    inputs="text",
    outputs="text",
    title="Binary to Qubit Compiler AI",
    description="Enter a binary string (e.g., 1101) to see its equivalent qubit representation."
)

iface.launch()
```
This initializes a Gradio web interface where users can input binary values and get the corresponding qubit output.

## Future Enhancements
- Integration with actual quantum computing frameworks like **IBM Qiskit**.
- Support for **quantum gates** to perform transformations.
- Advanced **quantum circuit visualization**.

## License
This project is licensed under the MIT License.

## Author
**Siva Mallikarjun Paravatham** 
GitHub: [Your GitHub Profile](https://github.com/PSivaMallikarjun)

![Screenshot 2025-04-08 003044](https://github.com/user-attachments/assets/41a1913a-db27-4a7d-9180-a9e4414946be)


