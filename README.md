# [fast.ai course](https://course.fast.ai/)

## Saving your data files
If you run a script which creates/ downloads files, the files will NOT persist after the allocated instance is shutdown. To save files, you need to permit your Colaboratory instance to read and write files to your Google Drive. Add the following code snippet at the beginning of every notebook.

```python
from google.colab import drive
drive.mount('/content/gdrive', force_remount=True)
root_dir = "/content/gdrive/My Drive/"
base_dir = root_dir + 'fastai-v3/'
```

Now, you may access your Google Drive as a file sytem using standard python commands to both read and write files. Don’t forget to add base_dir before root path(s) in all notebooks. For example, in lesson2-download.ipynb 5th cell, make the following changes:

```python
path = Path(base_dir + 'data/bears')
dest = path/folder
dest.mkdir(parents=True, exist_ok=True)
```

