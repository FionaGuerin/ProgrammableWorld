# ProgrammableWorld
Networked Dynamic Execution Environment for Microcontrollers

## Installation
To install ProgrammableWorld, please first install the ESP-IDF. 
### Step 1: Install ESP-IDF
If you want to install the ESP-IDF on a Mac, follow the steps below. 
If you want to install the ESP-IDF on a different operating system or have more information, 
please refer to the [ESP-IDF Programming Guide](https://docs.espressif.com/projects/esp-idf/en/latest/get-started/index.html#get-started-get-esp-idf). 
1. Install pip: `sudo easy_install pip`
2. Install pyserial: `pip install --user pyserial`
3. Install cmake and ninja: `brew install cmake ninja`
4. Clone the ESP-IDF into your project folder: `git clone --recursive https://github.com/espressif/esp-idf.git`
5. Add the ESP-IDF folder to your gitignore: `esp-idf/`
6. Install the tools that the ESP-IDF uses (compiler, debugger, ...): 
    1. `cd esp-idf`
    2. `./install.sh`
7. Export IDF-PATH: `export IDF_PATH=<path-to-your-project-folder>/esp-idf`
8. Set environment variables: `. ./export.sh`
9. Test installation with hello_world project:
    1. `cd examples/get-started/hello_world`
    2. `idf.py build`
    3. Find your ESP's port:
        1. Run `ls /dev/cu.*` and look at the listed ports.
        2. Run `ls /dev/cu.*` and find the port that is now additionally listed. This is the port of your ESP32.
    4. `idf.py -p <port> flash monitor`

## Credits
### ESP-IDF
The ESP-IDF Programming Guide showed us how to set up the ESP-IDF on our laptop and use it for an ESP32. 
We used it both for starting the ESP-IDF and as a reference for our installation instructions.
Link: [https://docs.espressif.com/projects/esp-idf/en/latest/get-started/index.html#get-started-get-esp-idf](https://docs.espressif.com/projects/esp-idf/en/latest/get-started/index.html#get-started-get-esp-idf)
