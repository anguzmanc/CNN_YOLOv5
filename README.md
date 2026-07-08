<h1 align="center">👁️ Real-Time Object Detection using YOLOv5</h1>

<p align="center">
Deep learning-based object detection system developed using <b>YOLOv5</b> and <b>PyTorch</b>, capable of detecting multiple object classes in real time. The project includes model training, inference, model export, and deployment on a Raspberry Pi 3B+ for embedded computer vision applications.
</p>

<hr>

<h2>📌 Project Overview</h2>

<p>
This project focused on implementing a real-time object detection system using Convolutional Neural Networks (CNNs) through the YOLOv5 architecture.
</p>

<p>The complete workflow included:</p>

<ul>
    <li>Transfer learning using a pretrained YOLOv5m model</li>
    <li>Training and fine-tuning the detection network</li>
    <li>Inference on multiple object categories</li>
    <li>Model export for embedded deployment</li>
    <li>Real-time object detection on a Raspberry Pi 3B+</li>
</ul>

<p>
The objective was to develop a complete computer vision pipeline, from model training to real-time inference on edge hardware.
</p>

<hr>

<h2>🧠 Model Architecture</h2>

<p>
The project was based on <b>YOLOv5m</b>, one of the medium-sized object detection models developed by Ultralytics.
</p>

<p>
Instead of training a CNN from scratch, transfer learning was employed by fine-tuning pretrained weights obtained from the COCO dataset, significantly reducing training time while maintaining high detection accuracy.
</p>

<p>
The implementation was developed using:
</p>

<ul>
    <li>PyTorch</li>
    <li>Ultralytics YOLOv5</li>
    <li>Google Colab with GPU acceleration</li>
</ul>

<hr>

<h2>📂 Training Process</h2>

<table>
<tr>
<th>Parameter</th>
<th>Value</th>
</tr>

<tr>
<td>Model</td>
<td>YOLOv5m</td>
</tr>

<tr>
<td>Image Resolution</td>
<td>640 × 640</td>
</tr>

<tr>
<td>Batch Size</td>
<td>20</td>
</tr>

<tr>
<td>Epochs</td>
<td>50</td>
</tr>

<tr>
<td>Dataset Configuration</td>
<td>COCO128</td>
</tr>

<tr>
<td>Framework</td>
<td>PyTorch</td>
</tr>

</table>

<p>
GPU acceleration available in Google Colab was used to speed up the training process.
</p>

<hr>

<h2>🔍 Object Detection</h2>

<p>
After training, the model was evaluated using multiple test images containing different object categories.
</p>

<p>
Among the detected objects were:
</p>

<ul>
    <li>Person</li>
    <li>Dog</li>
    <li>Cat</li>
    <li>Car</li>
    <li>Bicycle</li>
    <li>Traffic Light</li>
    <li>Fire Hydrant</li>
    <li>Backpack</li>
    <li>Handbag</li>
    <li>Stop Sign</li>
    <li>Umbrella</li>
</ul>

<p>
Confidence thresholds were adjusted to improve prediction quality and reduce false detections.
</p>

<hr>

<h2>📦 Model Export</h2>

<p>
After completing the training stage, the model was exported into deployment-ready formats suitable for embedded devices.
</p>

<p>The exported formats included:</p>

<ul>
    <li>TorchScript (.torchscript)</li>
    <li>ONNX (.onnx)</li>
</ul>

<p>
These formats enable compatibility with multiple inference engines and hardware platforms.
</p>

<hr>

<h2>🍓 Raspberry Pi Deployment</h2>

<p>
The exported model was deployed on a <b>Raspberry Pi 3B+</b> equipped with a <b>Raspberry Pi Camera Module</b>.
</p>

<p>
The camera continuously captured images while the YOLOv5 model performed real-time object detection directly on the embedded device, demonstrating the feasibility of running deep learning inference on low-power hardware.
</p>

<hr>

<h2>⚙️ Project Workflow</h2>

<ol>
<li>Clone the Ultralytics YOLOv5 repository.</li>
<li>Install project dependencies.</li>
<li>Load pretrained YOLOv5m weights.</li>
<li>Fine-tune the model using transfer learning.</li>
<li>Evaluate the model on test images.</li>
<li>Export the trained model to TorchScript and ONNX.</li>
<li>Deploy the exported model on a Raspberry Pi 3B+.</li>
<li>Perform real-time object detection using the Raspberry Pi Camera Module.</li>
</ol>

<hr>

<h2>🛠️ Technologies Used</h2>

<ul>
    <li>Python</li>
    <li>PyTorch</li>
    <li>YOLOv5</li>
    <li>Ultralytics</li>
    <li>Google Colab</li>
    <li>CUDA GPU Acceleration</li>
    <li>OpenCV</li>
    <li>Raspberry Pi 3B+</li>
    <li>Raspberry Pi Camera Module</li>
    <li>TorchScript</li>
    <li>ONNX</li>
    <li>Computer Vision</li>
    <li>Deep Learning</li>
</ul>

<hr>

<h2>📚 Learning Outcomes</h2>

<p>
This project provided practical experience in:
</p>

<ul>
    <li>Convolutional Neural Networks (CNNs)</li>
    <li>Transfer Learning</li>
    <li>Object Detection</li>
    <li>Deep Learning model training</li>
    <li>PyTorch workflows</li>
    <li>Model optimization and export</li>
    <li>Embedded AI deployment</li>
    <li>Real-time Computer Vision</li>
</ul>

<hr>

<h2>💻 Training and Inference Code</h2>

<p>
The following commands summarize the workflow used throughout the project, from downloading the YOLOv5 framework to training, inference, and model export. Each step is accompanied by a brief explanation of its purpose.
</p>

<h3>1. Clone the YOLOv5 Repository</h3>

<pre><code>
# Clone the official YOLOv5 repository from Ultralytics
!git clone https://github.com/ultralytics/yolov5

# Change the working directory
%cd yolov5
</code></pre>

<p>
In this project, the repository was already stored in Google Drive, so the notebook directly accessed the existing directory.
</p>

<hr>

<h3>2. Install Dependencies</h3>

<pre><code>
# Install all required Python packages
!pip install -qr requirements.txt

import torch
import utils

# Initialize the notebook environment
display = utils.notebook_init()
</code></pre>

<p>
This step installs all required libraries and prepares the PyTorch environment used by YOLOv5.
</p>

<hr>

<h3>3. Train the Model</h3>

<pre><code>
!python train.py \
--img 640 \
--batch 20 \
--epochs 50 \
--data coco128.yaml \
--weights yolov5m.pt \
--cache
</code></pre>

<p>

Training parameters:

</p>

<ul>
<li><b>Image Size:</b> 640 × 640 pixels</li>
<li><b>Batch Size:</b> 20 images</li>
<li><b>Epochs:</b> 50</li>
<li><b>Base Model:</b> YOLOv5m pretrained on COCO</li>
<li><b>Dataset:</b> COCO128 configuration</li>
</ul>

<p>
Transfer learning was applied by starting from pretrained YOLOv5 weights instead of training a CNN from scratch.
</p>

<hr>

<h3>4. Perform Object Detection</h3>

<pre><code>
!python detect.py \
--weights yolov5m.pt \
--img 640 \
--conf 0.3 \
--source /content/drive/MyDrive/images \
--classes 0 1 2 9 10 11 15 16 24 25 26
</code></pre>

<p>
This command performs inference on a folder containing multiple test images.
</p>

<p>
The model was configured to detect only selected COCO classes, including:
</p>

<ul>
<li>Person</li>
<li>Bicycle</li>
<li>Car</li>
<li>Dog</li>
<li>Cat</li>
<li>Fire Hydrant</li>
<li>Traffic Light</li>
<li>Stop Sign</li>
<li>Backpack</li>
<li>Handbag</li>
<li>Umbrella</li>
</ul>

<hr>

<h3>5. Display Detection Results</h3>

<pre><code>
from IPython.display import Image, display
from glob import glob

for img_path in glob('runs/detect/exp2/*.jpg'):
    display(Image(filename=img_path))
</code></pre>

<p>
After inference, the processed images containing bounding boxes and predicted labels are displayed automatically.
</p>

<hr>

<h3>6. Export the Trained Model</h3>

<pre><code>
!python export.py \
--weights yolov5m.pt \
--include torchscript onnx
</code></pre>

<p>
The trained model was exported into deployment-ready formats:
</p>

<ul>
<li>TorchScript (.torchscript)</li>
<li>ONNX (.onnx)</li>
</ul>

<p>
These formats allow the model to be executed efficiently on embedded platforms such as the Raspberry Pi 3B+.
</p>

<hr>

<h3>7. Embedded Deployment</h3>

<p>
The exported model was transferred to a Raspberry Pi 3B+, where it was executed together with a Raspberry Pi Camera Module to perform real-time object detection directly on the embedded device.
</p>

<p>
This final stage demonstrated the complete workflow from deep learning model training to edge AI deployment.
</p>

<h2>📸 Detection Results</h2>

<p>
The following images show the object detection results produced by the trained YOLOv5 model:
</p>

<table align="center">
<tr>
<td align="center">
<img src="https://github.com/user-attachments/assets/19788e5d-c954-4015-a277-e2329e31cbe5" width="250">
</td>

<td align="center">
<img src="https://github.com/user-attachments/assets/9839b451-809f-4fcc-80c0-96a810a712ec" width="250">
</td>

<td align="center">
<img src="https://github.com/user-attachments/assets/3e729bdb-ebb9-449c-b1b4-785a812d1f18" width="250">
</td>
</tr>

<tr>
<td align="center">
<img src="https://github.com/user-attachments/assets/46b0ef26-766d-4672-920f-f1edcb02eb2a" width="250">
</td>

<td align="center">
<img src="https://github.com/user-attachments/assets/096596d7-7fa3-44b6-87e9-55b0135fb87d" width="250">
</td>

<td align="center">
<img src="https://github.com/user-attachments/assets/1d184f5c-f547-4543-9002-21e2b264d1df" width="250">
</td>
</tr>
</table>

---
*Course: Sistemas Embebidos – Universidad Nacional de Colombia (2025‑2)*  
*Professor: Óscar Julián Perdomo Charry*
