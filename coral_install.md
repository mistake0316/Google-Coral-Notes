# Get started with the USB Accelerator
> https://coral.ai/docs/accelerator/get-started#3-run-a-model-using-the-tensorflow-lite-api

# 1. Install the Edge TPU runtime(On raspberrypi)

echo "deb https://packages.cloud.google.com/apt coral-edgetpu-stable main" | sudo tee /etc/apt/sources.list.d/coral-edgetpu.list

curl https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -

sudo apt-get update <br>
sudo apt-get install libedgetpu1-std <br>
sudo apt-get install libedgetpu1-max<br>

# 2. Install the TensorFlow Lite library
> for respberry

pip3 install https://dl.google.com/coral/python/tflite_runtime-2.1.0.post1-cp37-cp37m-linux_armv7l.whl

# 3. Run a model using the TensorFlow Lite API
mkdir coral && cd coral

git clone https://github.com/google-coral/tflite.git

cd tflite/python/examples/classification

bash install_requirements.sh

python3 classify_image.py \<br>
--model models/mobilenet_v2_1.0_224_inat_bird_quant_edgetpu.tflite \<br>
--labels models/inat_bird_labels.txt \<br>
--input images/parrot.jpg

# congrulation, you can see the output
