# Tool : Almanac Wasm Stats

Thought : 
The cutting-edge technologies like WebAssembly continuously evolve with various Tool-Kits, Sdks and Libraries. 
How can We adopt multiple tools or utility libraries together in plug-n-play architecture to enhance final statistics for WebAssembly in Almanac.

This tool can be used for offline single and or bulk analysis of WebAssembly. 
It produces the stat in JSON format by using Web Assembly Binary Toolkit along with [Almanac WebAssembly analysis Rust Library Tool](https://github.com/HTTPArchive/wasm-stats).

The current release can do below tasks for more robust and traceable way on huge number of wasm files.

### Download : 
We can download all .wasm files with preferred request parameters and give a unique file name for each request.
We had more then ~600K wasm files, It is long running task to download such a huge number of WebAssembly and maintain the stats so We do not need to re-run again.
The Tool initiates under /wasm/ins, /wasm/outs and /wasm/tools/downloader/logs folder.

### Validate : 
To deep dive the WebAssembly binary file which has downloaded successfully, We use the toolkit to validate and translate WebAssembly from the binary format to the text
format i.e. wat. This helps us to infer the source language that was used in WASM.
It maintains the stats under /wasm/tools/wasm-validator/logs folder.

### Populate stats : 
We continue use "wasm-stats" rust library (command line) to get WebAssembly’s other important stats for each Wasm and populate final statistics.
It maintains the stats under /wasm/tools/wasm-stats/outs folder.

The core implementation were tested with more then ~600K wasm modules including clients i.e. desktop and mobile.

Thank you for visiting this repository,
We are planing to move this repository under [HttpArchive Almanac](https://github.com/HTTPArchive/) repository.
With Regards, 
Vadgama
