# image-caption

Show and Tell: A Neural Image Caption Generator

A TensorFlow implementation of the image-to-text model described in the paper:

"Show and Tell: Lessons learned from the 2015 MSCOCO Image Captioning Challenge."

Oriol Vinyals, Alexander Toshev, Samy Bengio, Dumitru Erhan.

IEEE transactions on pattern analysis and machine intelligence (2016).

Full text available at: http://arxiv.org/abs/1609.06647

# download
https://drive.google.com/open?id=0B7k91FBdFbY7eVd1SHprQjdkWms
https://github.com/tensorflow/models/tree/master/im2txt

# Generating Captions
CHECKPOINT_PATH="${HOME}/im2txt/model/train"
VOCAB_FILE="${HOME}/im2txt/data/mscoco/word_counts.txt"
IMAGE_FILE="${HOME}/im2txt/data/mscoco/raw-data/val2014/COCO_val2014_000000224477.jpg"
bazel build -c opt im2txt/run_inference
bazel-bin/im2txt/run_inference \
  --checkpoint_path=${CHECKPOINT_PATH} \
  --vocab_file=${VOCAB_FILE} \
  --input_files=${IMAGE_FILE}
  
 # Example output:
  Captions for image 1.jpg:
  0) a cat laying on top of a grass covered field . (p=0.002806)
  1) a black and white cat laying on top of a grass covered field . (p=0.000498)
  2) a black and white cat laying on top of a green field . (p=0.000412)
