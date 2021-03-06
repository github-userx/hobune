# Hobune
A lightweight static HTML framework for self-hosting video archives.
  
# Features
- Static HTML (fast and secure)
- Parses youtube-dl info.json format
- Channel pages (with thumbnails)
- Watch page (with stats, description etc)
- Download buttons (video, description, thumbnail, subtitles)
- Highlight deleted videos
- Client-side search

# Usage
1. Clone this repo
2. Open up `hobune.py` and edit the `ytpath`, `ytpathweb`, `webpath`, `outpath` and `removedvideosfile` variables
3. Run `python3 hobune.py`, this will generate HTML files in your `outpath`
4. (optionally) Configure your webserver to allow downloads from /dl URLs and HTML pages without extensions

```
# nginx sample config

location / {
    try_files $uri.html $uri $uri/ =404;
}

location /dl {
    alias /var/www/html/;
    add_header Content-disposition "attachment; filename=$1";
    try_files $uri $uri/ =404;
}
```

It is also recommended to edit the python script to suit your exact needs, since your setup probably won't be 1:1 same as the expected one.
