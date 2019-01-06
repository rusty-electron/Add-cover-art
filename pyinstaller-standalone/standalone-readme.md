## Pyinstaller - standalone

standalone files for respective operating systems do not require you to download the dependencies, they can be executed once downloaded.

### Creating standalone files:

Creating standalone files requires you to *download all dependencies required* for running `main.py`. Standalone files are *to be updated* if the original python scripts are modified.

* Windows 10 OS

    1. Replace `exit()` commands in py files to `sys.exit(1)`

    2. Copy provided `libmagic` folder and `magic.py` file to directory containing `main.py`

    3. Install `pyinstaller` using pip

        ```
        pip install pyinstaller 
        ```

    4. Go to project directory and run 

        ```
        pyinstaller --paths C:\Windows\WinSxS\x86_microsoft-windows-m..namespace-downlevel_31bf3856ad364e35_10.0.17134.1_none_50c6cb8431e7428f main.py
        ```

    5. The above command creates directories `build` and `dist` along with `main.spec` file. 

    6. Copy `libmagic` folder into `dist/main`

        **The required files for windows-ready files can be found at `dist/main/`**

    Comment: standalone can be created for windows by using the same command along with `--onefile` and `--windowed` options. The created file for windows produces *error related to filepaths* as referenced [here](https://stackoverflow.com/questions/46858417/pyinstaller-runs-fine-but-exe-file-errors-no-module-named-failed-to-execute-sc). If anyone can create a working standalone file for this script then their contribution is welcome.

* Linux OS 

    1. Replace `exit()` commands in py files to `sys.exit(1)`

    2. Install `pyinstaller` using pip

        ```
        pip install pyinstaller 
        ```
    3. Go to project directory and run 

        ```
        pyinstaller --onefile --windowed main.py
        ```

    4. The above command creates directories `build` and `dist` along with `main.spec` file. 

        **The required standalone for linux can be found at `dist/` as main**
