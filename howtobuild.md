***Windows:***
**Visual Studio:**
1. Create a CMakeLists.txt file as described in the previous response.

2. Open a command prompt and navigate to your project directory.

3. Create a build directory and run CMake to generate Visual Studio project files:

```
mkdir build
cd build
cmake ..
```
4. Open the generated Visual Studio solution (.sln) in the build directory.

5. Build and run your project from within Visual Studio.

**Visual Studio Code (VS Code):**
1. Install the "CMake Tools" extension in VS Code.

2. Install Raylib as mentioned earlier.

3. Create a CMakeLists.txt file.

4. Open your project folder in VS Code.

5. Use the CMake Tools extension to configure and build your project. It should detect your CMakeLists.txt and generate build files.

6. Build and run your project from within VS Code.

***Linux (Ubuntu, for example):***
*Install Raylib:* ```sudo apt-get install -y libraylib-dev```
1. Create a CMakeLists.txt file as described earlier.

2. Open a terminal and navigate to your project directory.

3. Create a build directory and run CMake to generate Makefiles:

```
mkdir build
cd build
cmake ..
```
4. Build your project using the make command:```make```
5. Run your executable:```./YourProjectName```

***macOS:***
1. Install Raylib:
You can use a package manager like Homebrew to install Raylib on macOS:

```
brew install raylib
```
2. Create a CMakeLists.txt file as described earlier.

3. Open a terminal and navigate to your project directory.

4. Create a build directory and run CMake to generate Makefiles:

```
mkdir build
cd build
cmake ..
```
5. Build your project using the make command: ```make```
6. Run your executable: ```./YourProjectName```
7. Make sure to adjust paths, project names, and other project-specific details according to your own setup.