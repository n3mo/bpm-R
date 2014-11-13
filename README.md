# bpm


Browse, Play, and Manage video files

`bpm` provides a fast and simple command line interface for managing video files. By pointing bpm at a directory on your computer, bpm recursively searches for any video files located within the file system. Files are presented in a colored tabular format to allow you to easily see what videos you have available.

Playback can be initiated for any file very easily by entering the number of the video file of interest. `bpm` also provides a simple interface for trashing video files. When trashing a video file, bpm will check in the same directory for any files with the same file name but with a different extension. These files are also moved to the trash. This allows bpm to keep your file system clean by automatically removing supplementary files such as subtitles, screen shots, meta data files, etc.

## Usage

Start bpm from a terminal by supplying the directory path you like to (recursively) search in:

```sh
bpm ~/Videos/path
```

You will be presented with a list of videos contained in `~/Videos/path`:

![bpm screenshot](https://github.com/n3mo/bpm/raw/master/img/bpm_screenshot.png)

### Available Commands

For the following commands, you only need to type the first letter of the command. The remaining letters are optional, and are included to help you remember command names.

* **1**: Enter the number of the video file you would like to play. Playback begins immediately. Replace the **1** with whichever video you would like to watch.
* **[n]ext**: Move to the next page of results (if applicable). 
* **[p]revious**: Move to the previous page of results (if applicable).
* **[t]op**: Navigate to the first page of results.
* **[r]efresh**: Re-search the file system for new files that may have been added. This is only necessary when you add or remove video files using another program.
* **[d]**: Delete files (move to system trash actually). To use this command, you must include 1 or more video item numbers, separated by spaces. For example, to delete files 4, 5 and 10 on the current page of results, you would enter `d 4 5 10`. bpm will verify that you want to trash the files. If you choose [Y]es, associated subtitle files, etc. will also be trashed. bpm automatically refreshes its list of videos after every deletion.
* **[q]uit**: Quit bpm.

## Installation

### Dependencies

#### R

bpm requires that R is installed on your computer. R is available for all major operating systems, and installs easily. Installation instructions can be found at [The R Project for Statistical Computing](http://www.r-project.org/).

On Ubuntu (and similar OSes), you can install R from the command line:

```sh
sudo apt-get install r-base
```

#### mplayer

bpm uses mplayer for video playback. Installation instructions can be found at [The Movie Player website](http://www.mplayerhq.hu).

If you're using a common linux distribution (e.g., Ubuntu), you can probably install mplayer using your package management system:

```sh
sudo apt-get install mplayer
```

### Install bpm

The easiest way to install bpm is with git. From the command line:

```sh
git clone https://github.com/n3mo/bpm.git
chmod +x ~/path/to/bpm/bpm
```
You can then start bpm with

```sh
~/path/to/bpm/bpm
```

Alternatively, you can add a link to the bpm script somewhere on your $PATH to allow bpm to be launched from anywhere. This makes it easy to run bpm on the current directory:

```sh
bpm .
```
