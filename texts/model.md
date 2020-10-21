# Traffic Accident Detection(adapted)

## Introduction
This is a work in progress.

**It is based on the original work of Yu Yao, Mingze Xu, Yuchen Wang, David Crandall and Ella Atkins.**

Which is available at https://github.com/MoonBlvd/tad-IROS2019

## Steps to reproduce
### Downloading datasets
**Step 1** (Download the videos from YouTube):

	python3 datasets/A3D_download.py --download_dir ./videos/ --url_file datasets/A3D_urls.txt

**Note**: This urls list was cut down to just 10 videos, just for short test.

### Pre processing
**Step 2** (Then convert the videos to images in 10Hz):

	python3 scripts/video2frames.py -v ./videos/ -f 10 -o ./images/ -e jpg

**Step 3** (Because each downloaded video is a combination of several short clips, is required to split them into
clips):
First, it is necessary to adapt the annotation file to contain only the 10 videos in our test, to avoid flooding the storage.

	cd datasets
	python3 unpack_pickle.py A3D_labels.pkl
	python3 pack_pickle.py A3D_labels.txt
	cd ..

Then:

	python3 datasets/A3D_split.py --root_dir ./ --label_dir datasets/A3D_labels_my.pkl

### Train

### Test

### Validation

## Results

