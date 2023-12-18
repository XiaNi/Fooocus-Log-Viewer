# **Fooocus Log Viewer**

Fooocus Log Viewer is an add-on to https://github.com/lllyasviel/Fooocus. It creates a powerfull view of all your generated images and how you made them.
![Capture d’écran 2023-12-18 à 10 03 24](https://github.com/toutjavascript/Fooocus-Log-Viewer/assets/30899600/9cef6fd4-7da8-4709-8401-b89d20ee1bf7)

## What you can do with **Fooocus Log Viewer**

Fooocus Log Viewer can be integrated in UI with auto resize to fully fill the usable screen space.

You will be able to :

- Browse all your images by dates and batches
- Choose the grid size
- View prompts differences
- Click an image to view it bigger with all prompt details
- Copy the prompt datas (seed, models, styles, loras, ...)

## Installation of Fooocus Viewer Log

Installation is very easy. No npm nor pip install. Files are in archive and load extra JS and CSS from CDN.

### 1/ First step

Copy the archive files (`viewer.html` and `viewer.js`) in `/Fooocus/outputs/` directory

You could directly open `viewer.html` with Fooocus localhost server
Adress looks like http://localhost:7865/file=outputs/viewer.html
Check the port number on Fooocus UI webpage

### 2/ Deep integration in Fooocus UI

A new deep integration is available. Quite easy to config, with only one file to modify.
You open `/modules/ui_gradio_extensions.py` file. At line 41, add :

```python
head += f'<script type="text/javascript" src="file=outputs/viewer.js"></script>\n'
```

Quit Fooocus if started and restart `run.bat` to reinit Fooocus

You will see new link [🎥 Image Log Viewer (iframe)] in bottom of [Setting] tab

Click on it to display the Log Viewer over the same UI

This integration will be overwritten every time Fooocus is autoupdated at start.

To avoid update, you can create a new `run-no-update.bat` with :

```bash
.\python_embeded\python.exe -s Fooocus\launch.py --disable-header-check --theme=dark
pause
```

The dark theme offers a better experience.

## Fooocus Version Compability

This add-on is validated from V2.1.852 Fooocus version.
Each update is at risk to break the proper functionning of the script.
Please contact when broken.
Please share your ideas here by opening discussion

## Original idea and work 

The idea and initial work is inspired by https://github.com/lllyasviel/Fooocus/discussions/693
