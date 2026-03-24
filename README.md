# BDRoadScenes Image Privacy Tool

This project helps you protect people’s privacy in road photos.

It uses [BDRoadScenes.ipynb](BDRoadScenes.ipynb) to:
- find faces in each image,
- blur only the face area,
- keep cars, bikes, roads, and other objects clear,
- shuffle images in a repeatable way,
- rename all output images as 001, 002, 003, ...,
- save a file that shows old name to new name.

## What problem this solves

Road photos can include people. Before sharing or training with this data, it is safer to hide faces.

This notebook does that automatically for the full dataset.

## Easy summary

- Input folder: [Vehicles](Vehicles)
- Output folder: [updated_datasets](updated_datasets)
- Output image names: 001.jpg to 500.jpg
- Mapping file: updated_datasets/mapping.csv

## Folder structure

```text
vechicals_works/
|-- BDRoadScenes.ipynb
|-- README.md
|-- LICENSE
|-- Vehicles/
|-- updated_datasets/
|   |-- 001.jpg
|   |-- 002.jpg
|   |-- ...
|   |-- 500.jpg
|   `-- mapping.csv
`-- updated_datasets.zip
```

## How it works

1. It reads all images from the Vehicles folder.
2. It shuffles the list of images.
3. For each image:
   - If a face is found, it blurs only the face.
   - If no face is found, it still saves the image.
4. It saves all images into updated_datasets with serial names.
5. It creates mapping.csv so you can track original file names.

## What you need

- Python 3.10+
- Jupyter Notebook (VS Code or Colab)
- OpenCV

Install OpenCV:

```bash
pip install opencv-python
```

## Run steps

Open [BDRoadScenes.ipynb](BDRoadScenes.ipynb):

1. Run Cell 1 (find dataset and count images).
2. Run Cell 3 (face blur + save output).
3. Run Cell 4 if you want extension statistics.

After that, check [updated_datasets](updated_datasets).

## Important settings (Cell 3)

- MAX_IMAGES = None means process all images.
- CLEAR_OUTPUT_FOLDER = True means remove old output before new run.
- SHUFFLE_IMAGES = True means random order.
- SHUFFLE_SEED = 42 means same random order every time.

## mapping.csv columns

- serial: output serial number
- new_name: output image file name
- original_path: original file path
- faces_detected: number of faces blurred
  
## Dataset Workflow

![Dataset Creation](vehicles.jfif)

## Troubleshooting

- If cv2 error appears: run pip install opencv-python and rerun.
- If folder not found: check path values in Cell 1.
- If too many wrong face detections: increase MIN_NEIGHBORS.
- If faces are missed: reduce MIN_FACE_SIZE.

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE).
