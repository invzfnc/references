`fuck` setup on Windows cmd
1. Run `python -m pip install thefuck`
2. Go to `C:\Users\user\AppData\Roaming\Python\Python311\Scripts`
3. Create a new folder, I give it the name `fuck`, then go into that folder
4. Create a new batch file `fuck.bat` and put these inside:
```powershell
@echo off
set PYTHONIOENCODING="utf-8"
@powershell -noprofile -c "cmd /c \"$(thefuck --enable-experimental-instant-mode $(doskey /history)[-2])\""
```
5. Add the `fuck` folder to PATH, move it right above `C:\Users\user\AppData\Roaming\Python\Python311\Scripts`
6. Done! Now run `fuck` in cmd.