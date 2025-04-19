# utrace

`utrace` is a Python script that generates a function call trace for a program. It provides outputs in multiple formats, such as HTML (for OpenGrok) and GraphViz DOT (for visualizing call graphs). This tool is particularly useful for analyzing programs and understanding their function call dynamics.

## Features

- Generates function call traces in HTML and GraphViz DOT formats.
- Supports integration with OpenGrok for source code browsing.
- Provides visual call graphs using GraphViz.

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/EmmetCaulfield/utrace.git
   cd utrace
   ```

2. Ensure you have Python installed (version 3.x recommended).

3. Install required dependencies (if any are needed, add them here).

## Usage

Below are some examples of how `utrace` can be used:

### Generating a Visual Call Graph
```bash
$ utrace --dot perf | dot -Tsvg -o utrace.svg
$ firefox utrace.svg
```

### Generating an HTML Call Trace for OpenGrok
```bash
$ utrace -u http://localhost:8080/source/xref/linux-3.8.8-02-emmet/tools/perf \
  -o utrace.html perf
$ firefox utrace.html
```

### Command-Line Options
- `--dot`: Outputs the call trace in GraphViz DOT format.
- `-u`: Specify the OpenGrok URL for source code browsing.
- `-o`: Specify the output file name.

For more details, run:
```bash
$ python utrace.py --help
```

## How It Works

`utrace` uses tools like `readelf` and `gdb` to analyze programs and extract function call information. It was inspired by a StackOverflow question and the solution involving `readelf` and `gdb` by Johannes Schaub. This script automates the process and enhances its usability.

## Contributing

Contributions are welcome! To get started:

1. Fork the repository.
2. Create a branch for your feature or bug fix:
   ```bash
   git checkout -b feature-name
   ```
3. Commit your changes and push the branch:
   ```bash
   git commit -m "Add new feature"
   git push origin feature-name
   ```
4. Open a pull request.

Please see the `TODO` section below for areas that need improvement.

## TODO

- Refactor `gdb_chat()` into a cleaner, object-oriented implementation.
- Add an option to "merge" the common parts of successive backtraces.
- Improve error handling and debugging output.

## License

This project is licensed under the [MIT License](LICENSE). You are free to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the software, subject to the terms of the license.

## Author

- **Emmet Caulfield**  
  Created on: 24 June 2013  

For questions or feedback, feel free to open an issue or contact me.

## References

- [StackOverflow: Tool to trace local function calls in Linux](http://stackoverflow.com/questions/311840/tool-to-trace-local-function-calls-in-linux)