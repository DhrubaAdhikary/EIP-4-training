Session 2 


Approach for model building :

The model is pretty straigh forward and is built using the original model with 11k params . TO reduce the gap between training and validation score I have implemented Dropout and batch normlization . 

> After that for each layer I started to build 8,16,32 feature extractors , however for 32 feature extractors the number of params being generated was 4000+ .Since we are using the 32 kernel size twice earlier it was amounting to 8000+ params which I did not need as per my vizualizations using 20 kernels I was able to extract most of the gradients and textures so opted for 5,15,20 could have taken 8,16,20 as well but like the symmetry in 5,15,20 it is a bit generic kind of like (x-factor)(x-factor)* kernel size . 

on running the model got the accuracy score of 99.4



Validation score on full Test dataset : 
[0.016822802274899004, 0.9945]

Training log for epoch :


Train on 60000 samples, validate on 10000 samples

Epoch 1/20

 

Epoch 00001: LearningRateScheduler setting learning rate to 0.003.

60000/60000 [==============================] - 15s 257us/step - loss: 0.1917 - acc: 0.9400 - val_loss: 0.0534 - val_acc: 0.9838

Epoch 2/20

 

Epoch 00002: LearningRateScheduler setting learning rate to 0.0022744503.

60000/60000 [==============================] - 12s 193us/step - loss: 0.0587 - acc: 0.9816 - val_loss: 0.0418 - val_acc: 0.9872

Epoch 3/20

 

Epoch 00003: LearningRateScheduler setting learning rate to 0.0018315018.

60000/60000 [==============================] - 12s 197us/step - loss: 0.0478 - acc: 0.9850 - val_loss: 0.0318 - val_acc: 0.9892

Epoch 4/20

 

Epoch 00004: LearningRateScheduler setting learning rate to 0.0015329586.

60000/60000 [==============================] - 12s 194us/step - loss: 0.0392 - acc: 0.9881 - val_loss: 0.0292 - val_acc: 0.9897

Epoch 5/20

 

Epoch 00005: LearningRateScheduler setting learning rate to 0.0013181019.

60000/60000 [==============================] - 12s 193us/step - loss: 0.0360 - acc: 0.9887 - val_loss: 0.0266 - val_acc: 0.9919

Epoch 6/20

 

Epoch 00006: LearningRateScheduler setting learning rate to 0.0011560694.

60000/60000 [==============================] - 12s 193us/step - loss: 0.0336 - acc: 0.9894 - val_loss: 0.0201 - val_acc: 0.9930

Epoch 7/20

 

Epoch 00007: LearningRateScheduler setting learning rate to 0.0010295127.

60000/60000 [==============================] - 12s 194us/step - loss: 0.0299 - acc: 0.9902 - val_loss: 0.0205 - val_acc: 0.9928

Epoch 8/20

 

Epoch 00008: LearningRateScheduler setting learning rate to 0.0009279307.

60000/60000 [==============================] - 12s 195us/step - loss: 0.0283 - acc: 0.9908 - val_loss: 0.0227 - val_acc: 0.9925

Epoch 9/20

 

Epoch 00009: LearningRateScheduler setting learning rate to 0.0008445946.

60000/60000 [==============================] - 12s 194us/step - loss: 0.0253 - acc: 0.9917 - val_loss: 0.0189 - val_acc: 0.9932

Epoch 10/20

 

Epoch 00010: LearningRateScheduler setting learning rate to 0.0007749935.

60000/60000 [==============================] - 12s 193us/step - loss: 0.0237 - acc: 0.9924 - val_loss: 0.0189 - val_acc: 0.9935

Epoch 11/20

 

Epoch 00011: LearningRateScheduler setting learning rate to 0.0007159905.

60000/60000 [==============================] - 12s 194us/step - loss: 0.0232 - acc: 0.9927 - val_loss: 0.0199 - val_acc: 0.9931

Epoch 12/20

 

Epoch 00012: LearningRateScheduler setting learning rate to 0.000665336.

60000/60000 [==============================] - 12s 193us/step - loss: 0.0215 - acc: 0.9929 - val_loss: 0.0178 - val_acc: 0.9937

Epoch 13/20

 

Epoch 00013: LearningRateScheduler setting learning rate to 0.0006213753.

60000/60000 [==============================] - 12s 192us/step - loss: 0.0204 - acc: 0.9929 - val_loss: 0.0202 - val_acc: 0.9931

Epoch 14/20

 

Epoch 00014: LearningRateScheduler setting learning rate to 0.0005828638.

60000/60000 [==============================] - 12s 193us/step - loss: 0.0199 - acc: 0.9934 - val_loss: 0.0202 - val_acc: 0.9932

Epoch 15/20

 

Epoch 00015: LearningRateScheduler setting learning rate to 0.0005488474.

60000/60000 [==============================] - 12s 195us/step - loss: 0.0191 - acc: 0.9938 - val_loss: 0.0196 - val_acc: 0.9933

Epoch 16/20

 

Epoch 00016: LearningRateScheduler setting learning rate to 0.0005185825.

60000/60000 [==============================] - 12s 192us/step - loss: 0.0180 - acc: 0.9939 - val_loss: 0.0190 - val_acc: 0.9938

Epoch 17/20

 

Epoch 00017: LearningRateScheduler setting learning rate to 0.000491481.

60000/60000 [==============================] - 12s 193us/step - loss: 0.0182 - acc: 0.9937 - val_loss: 0.0168 - val_acc: 0.9943

Epoch 18/20

 

Epoch 00018: LearningRateScheduler setting learning rate to 0.0004670715.

60000/60000 [==============================] - 12s 192us/step - loss: 0.0169 - acc: 0.9946 - val_loss: 0.0177 - val_acc: 0.9943

Epoch 19/20

 

Epoch 00019: LearningRateScheduler setting learning rate to 0.0004449718.

60000/60000 [==============================] - 12s 193us/step - loss: 0.0178 - acc: 0.9941 - val_loss: 0.0171 - val_acc: 0.9942

Epoch 20/20

 

Epoch 00020: LearningRateScheduler setting learning rate to 0.000424869.

60000/60000 [==============================] - 12s 192us/step - loss: 0.0160 - acc: 0.9953 - val_loss: 0.0168 - val_acc: 0.9945

<keras.callbacks.History at 0x7f6601c0f6a0>


Parameters list : 
Model: "sequential_8"

_________________________________________________________________

Layer (type)                 Output Shape              Param #  

=================================================================

conv2d_25 (Conv2D)           (None, 26, 26, 10)        100      

_________________________________________________________________

batch_normalization_22 (Batc (None, 26, 26, 10)        40        

_________________________________________________________________

dropout_8 (Dropout)          (None, 26, 26, 10)        0        

_________________________________________________________________

conv2d_26 (Conv2D)           (None, 24, 24, 15)        1365     

_________________________________________________________________

batch_normalization_23 (Batc (None, 24, 24, 15)        60       

_________________________________________________________________

dropout_9 (Dropout)          (None, 24, 24, 15)        0        

_________________________________________________________________

conv2d_27 (Conv2D)           (None, 22, 22, 20)        2720     

_________________________________________________________________

batch_normalization_24 (Batc (None, 22, 22, 20)        80       

_________________________________________________________________

dropout_10 (Dropout)         (None, 22, 22, 20)        0        

_________________________________________________________________

max_pooling2d_4 (MaxPooling2 (None, 11, 11, 20)        0        

_________________________________________________________________

conv2d_28 (Conv2D)           (None, 11, 11, 10)        210      

_________________________________________________________________

batch_normalization_25 (Batc (None, 11, 11, 10)        40       

_________________________________________________________________

dropout_11 (Dropout)         (None, 11, 11, 10)        0        

_________________________________________________________________

conv2d_29 (Conv2D)           (None, 9, 9, 15)          1365     

_________________________________________________________________

batch_normalization_26 (Batc (None, 9, 9, 15)          60       

_________________________________________________________________

dropout_12 (Dropout)         (None, 9, 9, 15)          0        

_________________________________________________________________

conv2d_30 (Conv2D)           (None, 7, 7, 20)          2720     

_________________________________________________________________

batch_normalization_27 (Batc (None, 7, 7, 20)          80       

_________________________________________________________________

dropout_13 (Dropout)         (None, 7, 7, 20)          0        

_________________________________________________________________

conv2d_31 (Conv2D)           (None, 7, 7, 10)          210      

_________________________________________________________________

batch_normalization_28 (Batc (None, 7, 7, 10)          40       

_________________________________________________________________

dropout_14 (Dropout)         (None, 7, 7, 10)          0        

_________________________________________________________________

conv2d_32 (Conv2D)           (None, 1, 1, 10)          4910     

_________________________________________________________________

flatten_4 (Flatten)          (None, 10)                0        

_________________________________________________________________

activation_4 (Activation)    (None, 10)                0        

=================================================================

Total params: 14,000

Trainable params: 13,800

Non-trainable params: 200



