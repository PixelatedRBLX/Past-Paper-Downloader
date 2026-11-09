# Past Paper Finder

A simple Windows app for downloading Cambridge IGCSE and O Level past papers, mark schemes and grade thresholds. Pick a subject, tick the papers, years and sessions you want, and press **Download**. The app finds each PDF and saves it into a tidy **Past papers** folder on your PC.

No typing file codes, no clicking through websites one paper at a time.

## Features

- **Cambridge IGCSE and O Level**: 25 IGCSE and 20 O Level subjects built in, including Maths, Sciences, Business, Economics, Computer Science, English and foreign languages. You can also type any other subject code.
- **Pick papers by ticking boxes**: papers are grouped by paper number, with quick buttons for *Select all*, *Clear* and *Only variant 2*.
- **Download many at once**: choose a range of years and any mix of sessions (May/June, Oct/Nov, Feb/March).
- **Question papers, mark schemes and grade thresholds** in one go.
- **Organised automatically**: files are saved as `Past papers/<subject>/<file>.pdf`, for example `Past papers/0580 Mathematics/0580_2025_May_June_qp_22.pdf`.
- **Skips files you already have**, so you can run it again to fill gaps without duplicates.
- **Checks every download is a real PDF** before saving it.
- **Tries backup mirrors** automatically if the first source doesn't have a file.
- **Live progress**: a progress bar, a colour-coded log of what was saved or not found, and a Stop button.

## Download and run (Windows)

1. Go to the [Releases](../../releases) page and download **Past Paper Finder.exe**.
2. Put it in the folder where you want your papers saved, for example `Documents`.
3. Double-click it.

The first time, Windows may show **"Windows protected your PC"**. This appears for any app that isn't commercially code-signed. Click **More info → Run anyway**.

You don't need to install Python to use the .exe.

## How to use

1. Choose **Cambridge IGCSE** or **Cambridge O Level**.
2. Pick your subject.
3. Tick the papers you want. The first digit is the paper, the second is the variant: `22` means Paper 2, variant 2. Your variant depends on your exam zone.
4. Choose the years, sessions and documents.
5. Press **Download**, then **Open "Past papers" folder** to see your files.

If a file shows **Not found**, that paper usually wasn't set in that session (not every variant runs every series), or the mirrors don't have it yet.

## Run from source

Requires Python 3.8 or newer.

```bash
pip install requests
python past_paper_finder.py
```

On Windows, Python's installer includes tkinter, which the app uses for its window. On Linux you may need to install it separately (for example `sudo apt install python3-tk`).

## Build the .exe yourself

On Windows, put `past_paper_finder.py` and `build_exe.bat` in the same folder and double-click `build_exe.bat`. It installs `requests` and `pyinstaller`, then creates `dist\Past Paper Finder.exe`.

Or run the command yourself:

```bash
pip install requests pyinstaller
pyinstaller --onefile --windowed --name "Past Paper Finder" past_paper_finder.py
```

## Where the papers come from

This app doesn't host any papers. It downloads them from public past-paper mirrors (PapaCambridge, with GCE Guide as a backup). All question papers, mark schemes and grade threshold documents are the property of Cambridge University Press & Assessment. This tool is for personal revision only, so please don't re-upload the downloaded files elsewhere.

This project is not affiliated with or endorsed by Cambridge International, PapaCambridge or GCE Guide.

## Contributing

Found a subject that's missing, or a paper that won't download? Open an issue with the subject code, paper, year and session.
