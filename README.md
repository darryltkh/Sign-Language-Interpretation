# Sign Language Interpretation Using Deep Learning and Arduino
This project is done for the Singapore NTU SCSE module CE4172 Internet of Things - Tiny Machine Learning. 

Aim of the project: Predict and output the word associated with the Sign Language gesture using the [Arduino Nano 33 BLE Sense board](https://store-usa.arduino.cc/products/arduino-nano-33-ble-sense) and [TensorFlow Lite for Microcontrollers](https://www.tensorflow.org/lite/microcontrollers) (tf-lite).

How this project was conducted:
- Data collection is done by using the Arduino board taped on my hand and recording gestures using the on-board 9 DOF IMU.
- A basic 4 layer dense neural network is used to train the dataset on a host computer.
- Using tf-lite, the model is quantized (reduce size of model) and uploaded on the Arduino board. 
- With the Arduino taped on the hand, the sign language gestures are performed and the board will do model inferrence on the IMU data and output the corresponding word.

Sign language words and gestures used in this project: "how", "me", "bus", "you".
Coresponding gestures are taken from Singapore Sign Language video tutorials in Youtube - [here](https://www.youtube.com/watch?v=AT4pSTXxI5U&t=1s) and [here](https://www.youtube.com/watch?v=-PJOW098IKE).

## Result
Achieved 100% accuracy due to the distinct gestures chosen, resulting in easier classification.

## Limitations
- While on training it is able to have full accuracy, when the model is published on the Arduino, sometimes it owuld not be able to capture the gestures. One reason might be the data collected is highly reliant on the "neutral starting point". 
- This solution could not capture complicated sign language gestures and full phrases or sentences. This is due to the fact that it often requires two hands to perform the geatures, which I only have one Arduino board. Many gestures also have very similar movement patterns, resulting in the IMU being incapable of capturing these differences. Using vision based solutions might solve the problem.

## Conclusion
This is a fun little experiment and project to explore the integration of deep learning into microcontrollers and embedded devices and I have learnt much about integrating these 2 concepts in this project.
