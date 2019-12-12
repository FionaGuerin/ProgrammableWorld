# ProgrammableWorld
Networked Dynamic Execution Environment for Microcontrollers

## Installation
To install ProgrammableWorld, please first install the ESP-IDF. 
### Step 1: Install ESP-IDF
If you want to install the ESP-IDF on a Mac, follow the steps below. 
If you want to install the ESP-IDF on a different operating system or have more information, 
please refer to the [ESP-IDF Programming Guide](https://docs.espressif.com/projects/esp-idf/en/latest/get-started/index.html#get-started-get-esp-idf). 
1. Install pip: 
    ```
    sudo easy_install pip
    ```

2. Install pyserial: 
    ```
    pip install --user pyserial
   ```

3. Install cmake and ninja: 
    ```
    brew install cmake ninja
    ```

4. Clone the ESP-IDF into your project folder: 
    ```
    git clone --recursive https://github.com/espressif/esp-idf.git
    ```

5. Add the ESP-IDF folder to your gitignore: 
    ```
    esp-idf/
   ```

6. Install the tools that the ESP-IDF uses (compiler, debugger, ...): 
    1. Change to the esp-idf directory:
         ```
         cd esp-idf
         ```
     
    2. Install the tools:
        ```
        ./install.sh
        ```
    
7. Add the IDF-PATH to your `~/.zshrc` file: 
    ```
    export IDF_PATH="<path-to-esp-idf>/esp-idf"
    ```

8. Set environment variables: 
    ```
    . ./export.sh
    ```

9. Test installation with hello_world project:
    1. Change to the hello_world directory:
        ```
        cd examples/get-started/hello_world
        ```
       
   2. Set LC_ALL environment variable:
        ```
        export LC_ALL=C
        ```
    
   3. Build the hello_world project:
        ```
        idf.py build
        ```
    
   4. Find your ESP's port:
        1. Run `ls /dev/cu.*` and look at the listed ports.
        2. Run `ls /dev/cu.*` and find the port that is now additionally listed. This is the port of your ESP32.
        3. If you could not find any port, ![install a driver for your board.](https://docs.espressif.com/projects/esp-idf/en/latest/get-started/establish-serial-connection.html)
        
   5. Flash and monitor the hello_world project:
        ```
        idf.py -p <port> flash monitor
        ```
    
    5. Check if you see the output:
       ```
       Hello world!
       Restarting in 10 seconds...
       I (211) cpu_start: Starting scheduler on APP CPU.
       Restarting in 9 seconds...
       Restarting in 8 seconds...
       Restarting in 7 seconds...
       ```
       
## Credits
### ESP-IDF
The ESP-IDF Programming Guide showed us how to set up the ESP-IDF on our laptop and use it for an ESP32. 
We used it both for starting the ESP-IDF and as a reference for our installation instructions.
Link: [https://docs.espressif.com/projects/esp-idf/en/latest/get-started/index.html#get-started-get-esp-idf](https://docs.espressif.com/projects/esp-idf/en/latest/get-started/index.html#get-started-get-esp-idf)
