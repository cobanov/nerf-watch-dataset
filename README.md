# nerf-watch-dataset

This repo contains wall clock photos of 44 photos to generate NeRFs like instant-ngp or nerfstudio.

## Download
- Clone repo or
- [Google Drive](https://drive.google.com/file/d/1PdnXoqV6AAXFpt5NGwdbNQATyXuh8Z5e/view?usp=share_link)
- [Mega](https://mega.nz/folder/OnhxUK5a#kQ8yd-WTbs60T1Xha0Goww)

## Example

![](assets/animation.gif)

## Photos

![](assets/collage.jpg)

Also you can download via gdown

```
gdown 1PdnXoqV6AAXFpt5NGwdbNQATyXuh8Z5e
```

Download with python
```python
import os
import requests
import zipfile
from pathlib import Path

# Setup path to data folder
data_path = Path("data/")

# If the image folder doesn't exist, download it and prepare it... 
if data_path.is_dir():
    print(f"{data_path} directory exists.")
else:
    print(f"Did not find {data_path} directory, creating one...")
    data_path.mkdir(parents=True, exist_ok=True)

# Download watch
with open(data_path / "watch.zip", "wb") as f:
    request = requests.get("https://github.com/cobanov/nerf-watch-dataset/raw/main/watch.zip")
    print("Downloading watch dataset...")
    f.write(request.content)

# Unzip watch.zip
with zipfile.ZipFile(data_path / "watch.zip", "r") as zip_ref:
    print("Unzipping watch dataset...") 
    zip_ref.extractall(data_path)

# Remove zip file
os.remove(data_path / "watch.zip")
```

