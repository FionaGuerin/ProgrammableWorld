# ProgrammableWorld
Networked Dynamic Execution Environment for Microcontrollers

## Motivation
Appliances in a pervasive network orchestrate each other's services. 
In other words, they offer services to each other and they consume services from each other. 
Service orchestration is usually static, i.e. dedicated clients send fixed formatted requests to a dedicated server and 
the server also responds in a fixed format. 
However, the devices in a pervasive network are peer-to-peer, often heterogeneous, and sometimes only temporarily available. 
So there can be no dedicated server in such a network, but the devices have to communicate directly with each other 
and adapt their services to each other. 

Microcontrollers run many applications that surround us today, such as cars or smart watches. 
Research and industry have greatly improved the capacities of microcontrollers in recent years. 
For example, they contain several 32-bit processor cores, network capacities such as WiFi and Bluetooth, and they cost on average only $3. 
Contrary to this high performance, we often only use microcontrollers to execute a fixed and burnt-in logic. 
Instead, Programmable World uses the new capacities of microcontrollers, especially their two network capacities WiFi and Bluetooth. 
In other words, we make microcontrollers the nodes in our network that communicate with each other and adapt their services to each other. 

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

## Contribute
If you want to contribute to the research-graph repository, please first read the Contributing Guidelines in the [Contributing](CONTRIBUTING.md) file.

## License
Copyright [2019] [Fiona Guerin]

Licensed under the Apache License, Version 2.0 (the "License"); 
you may not use this file except in compliance with the License. 
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on 
an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. 
See the License for the specific language governing permissions and limitations under the License.
