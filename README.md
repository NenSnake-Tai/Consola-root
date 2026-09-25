# Web Console Root Engine 🐚

A lightweight, low-latency browser-based terminal simulation engine built in native JavaScript. This repository demonstrates optimized DOM manipulation and real-time command-line input parsing to emulate a sandboxed system shell environment with zero input lag.

## 🗂️ Architectural Overview

The engine acts as a localized text-based interface, capturing user keystrokes, decoupling arguments, and processing system directives through a modular switch-case execution architecture.

### ⚙️ Core Technical Features:
* **Asynchronous Command Parsing:** Processes inputs and string tokens instantly via isolated runtime routines.
* **Low-Latency DOM Rendering:** Minimizes browser reflows and repaints during high-volume log execution.
* **Zero External Dependencies:** Built strictly with vanilla JavaScript, CSS, and HTML for direct hardware thread alignment.

## 🚀 Deployment Instructions

To run the console simulator locally or host it on any web environment:
1. Clone this repository to your local storage.
2. Ensure `index.html`, `style.css`, and `script.js` are in the same directory.
3. Open `index.html` in any standard modern web browser (Chrome, Brave, Edge).

*Developed for sandboxed command execution analysis and core web logic prototyping.*

```mermaid
graph TD
    %% Estilo de nodos neón
    classDef safe color:#00ff66,fill:#000,stroke:#00ff66,stroke-width:2px;
    classDef alert color:#ff0033,fill:#000,stroke:#ff0033,stroke-width:2px;
    classDef process color:#00ffff,fill:#000,stroke:#00ffff,stroke-width:1px;

    Start([⚡ Engine Initialization]) --> Load[🚀 DOM Content Rendered]
    Load --> Active[📡 Input Listener Attached Keydown]
    
    Active --> Wait{⌨️ Waiting for ENTER Key Event}
    
    Wait -- NO --> Wait
    Wait -- SÍ --> Capture[📥 Capture String Input Buffer]
    
    Capture --> Parse[🔬 Tokenize & Sanitize Argument Strings]
    Parse --> Route{🔀 Command Router Switch-Case}
    
    Route -- Unknown Command --> Err[🚨 Print Command Not Found Error]:::alert
    Route -- Valid Command --> Exec[⚙️ Execute Core Script Routine]:::process
    
    Err --> Output[🖥️ Flush Log Stream to Virtual Screen]
    Exec --> Output
    
    Output --> Return[🔄 Clear Buffer & Refocus Input Field]
    Return --> Wait

    class Start,Load,Active,Wait safe;
    class Capture,Parse,Route,Output,Return process;
```
