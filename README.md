Downloads segmented audio+video from Vimeo and saves as .mp4

This script is useful for cases where youtube-dl is unable to find the master url,
for example on pages that require login or cookies.

Install
=======
Install [ffmpeg](https://trac.ffmpeg.org/wiki/CompilationGuide).

Install requirements with `pip install -r requirements.txt`

Usage
=====

To use this script, the master url needs to be manually extracted from the page:

   `python vimeo-download.py --url "http://...master.json?base64_init=1" --output <optional_name>`

To get the master url:

   1. Open the network tab in the inspector
   2. Find the url of a request to the `master.json` file
   3. Run the script with the url as argument

You can download multiple files in parallel with GPU Parallel:

   `parallel -a master-files.txt python vimeo-download.py --url "{}"`

Where `master-files.txt` contains a list of master URLs


Acknowledgements
=======

Code merges the following gists:

- https://gist.github.com/alexeygrigorev/a1bc540925054b71e1a7268e50ad55cd
- https://gist.github.com/tayiorbeii/d78c7e4b338b031ce8090b30b395a46f
- https://gist.github.com/paschoaletto/7f65b7e36b76ccde9fe52b74b62ab9df

Alternatives
============

For a more convenient experience use youtube-dl ( http://rg3.github.io/youtube-dl/ ) if youtube-dl is able to find the url
