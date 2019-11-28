Hi Rohan 

My apologies for the dismal performance in the quiz , this was an hectic field and due to less time I was not able to get into the depth of the concepts . 
I have some quesries if you can provide inputs to them , 

Q1 -> When we give padding='same' what is the padding value we are actually giving . On stack overflow it said that valid drops the extra info and same appends 0 to match the kernel so I assumed we take padding as 0 . 

Q2 -> I understand we can do a grid search to hypertune params but from graph how to acertain the learning rate , and is it possible to manually adjust batch normalization and how to zero in on the drop out value for every layer . I have for now done a preliminary grid search and set for all layers drop out as 0.1 as per your directive to take the lowest . 

Q3 -> Maybe I am doing it wrong but the depthwise convolution was slower than the baseline model maybe because i was using a learning scheduler , however how will be the ideal design for this problem ? I assumed what i would have done it using a normal 3*3 kernel with maxpooling and applied it in the same fashion , and have not done any dilation . 

Q4-> ALso one major question if we convolve and convolve and say we get a final shape of 8*8*10 and to predict there are 10 classes . AN easy step is to flatten and use FC layer with output 10 . What will be the approach without using FC ? 

I mean how to bring this to say 1*10 which is the end output of softmax as well . 


My score on test is 79.5 compared to 82 from baseline but this model as compared to my other model is lot more stable and does not overfit .It did touch 0.8 once .However due to work schedule I was not able to fix it entirely today . Please suggest the solution for it .

This is the 3rd session solution file 

KPS  In OUT  RF   Jump 
301  32  30   3    1             Layer 1
301  30  28   5    1
101  28  28   5    1

301  28  26   7    1             Layer 2
301  26  24   9    1
101  24  24   9    1

301  24  22   11   1             Layer 3
302  22  10   13   1
101  10  10   13   2

301  10  8    17   2             Layer 4 
302   8  3    21   2
                   4

Accuracy on test data is: 82.15   (Baseline convoluted model ) 

depth convolutions solution build by Dhruv : 

/usr/local/lib/python3.6/dist-packages/ipykernel_launcher.py:15: UserWarning: The semantics of the Keras 2 argument `steps_per_epoch` is not the same as the Keras 1 argument `samples_per_epoch`. `steps_per_epoch` is the number of batches to draw from the generator at each epoch. Basically steps_per_epoch = samples_per_epoch/batch_size. Similarly `nb_val_samples`->`validation_steps` and `val_samples`->`steps` arguments have changed. Update your method calls accordingly.

  from ipykernel import kernelapp as app

/usr/local/lib/python3.6/dist-packages/ipykernel_launcher.py:15: UserWarning: Update your `fit_generator` call to the Keras 2 API: `fit_generator(<keras_pre..., validation_data=(array([[[..., callbacks=[<keras.ca..., steps_per_epoch=390, epochs=50)`

  from ipykernel import kernelapp as app

Epoch 1/50

 

Epoch 00001: LearningRateScheduler setting learning rate to 0.003.

390/390 [==============================] - 57s 146ms/step - loss: 0.8335 - acc: 0.7095 - val_loss: 1.0454 - val_acc: 0.6534

Epoch 2/50

 

Epoch 00002: LearningRateScheduler setting learning rate to 0.0022744503.

390/390 [==============================] - 43s 109ms/step - loss: 0.7847 - acc: 0.7287 - val_loss: 0.8991 - val_acc: 0.6909

Epoch 3/50

 

Epoch 00003: LearningRateScheduler setting learning rate to 0.0018315018.

390/390 [==============================] - 43s 109ms/step - loss: 0.7452 - acc: 0.7407 - val_loss: 0.7341 - val_acc: 0.7477

Epoch 4/50

 

Epoch 00004: LearningRateScheduler setting learning rate to 0.0015329586.

390/390 [==============================] - 43s 109ms/step - loss: 0.7198 - acc: 0.7494 - val_loss: 0.8326 - val_acc: 0.7204

Epoch 5/50

 

Epoch 00005: LearningRateScheduler setting learning rate to 0.0013181019.

390/390 [==============================] - 43s 109ms/step - loss: 0.7003 - acc: 0.7561 - val_loss: 0.7864 - val_acc: 0.7251

Epoch 6/50

 

Epoch 00006: LearningRateScheduler setting learning rate to 0.0011560694.

390/390 [==============================] - 43s 109ms/step - loss: 0.6806 - acc: 0.7637 - val_loss: 0.7196 - val_acc: 0.7538

Epoch 7/50

 

Epoch 00007: LearningRateScheduler setting learning rate to 0.0010295127.

390/390 [==============================] - 43s 109ms/step - loss: 0.6672 - acc: 0.7673 - val_loss: 0.6786 - val_acc: 0.7659

Epoch 8/50

 

Epoch 00008: LearningRateScheduler setting learning rate to 0.0009279307.

390/390 [==============================] - 43s 109ms/step - loss: 0.6537 - acc: 0.7718 - val_loss: 0.7362 - val_acc: 0.7439

Epoch 9/50

 

Epoch 00009: LearningRateScheduler setting learning rate to 0.0008445946.

390/390 [==============================] - 43s 110ms/step - loss: 0.6457 - acc: 0.7745 - val_loss: 0.6616 - val_acc: 0.7710

Epoch 10/50

 

Epoch 00010: LearningRateScheduler setting learning rate to 0.0007749935.

390/390 [==============================] - 43s 109ms/step - loss: 0.6348 - acc: 0.7789 - val_loss: 0.7200 - val_acc: 0.7466

Epoch 11/50

 

Epoch 00011: LearningRateScheduler setting learning rate to 0.0007159905.

390/390 [==============================] - 43s 109ms/step - loss: 0.6264 - acc: 0.7821 - val_loss: 0.6621 - val_acc: 0.7719

Epoch 12/50

 

Epoch 00012: LearningRateScheduler setting learning rate to 0.000665336.

390/390 [==============================] - 43s 109ms/step - loss: 0.6193 - acc: 0.7850 - val_loss: 0.6871 - val_acc: 0.7595

Epoch 13/50

 

Epoch 00013: LearningRateScheduler setting learning rate to 0.0006213753.

390/390 [==============================] - 43s 109ms/step - loss: 0.6143 - acc: 0.7858 - val_loss: 0.6966 - val_acc: 0.7560

Epoch 14/50

 

Epoch 00014: LearningRateScheduler setting learning rate to 0.0005828638.

390/390 [==============================] - 43s 109ms/step - loss: 0.6047 - acc: 0.7896 - val_loss: 0.6570 - val_acc: 0.7706

Epoch 15/50

 

Epoch 00015: LearningRateScheduler setting learning rate to 0.0005488474.

390/390 [==============================] - 43s 110ms/step - loss: 0.5997 - acc: 0.7881 - val_loss: 0.6638 - val_acc: 0.7687

Epoch 16/50

 

Epoch 00016: LearningRateScheduler setting learning rate to 0.0005185825.

390/390 [==============================] - 43s 109ms/step - loss: 0.5965 - acc: 0.7918 - val_loss: 0.6634 - val_acc: 0.7702

Epoch 17/50

 

Epoch 00017: LearningRateScheduler setting learning rate to 0.000491481.

390/390 [==============================] - 43s 109ms/step - loss: 0.5882 - acc: 0.7967 - val_loss: 0.6691 - val_acc: 0.7649

Epoch 18/50

 

Epoch 00018: LearningRateScheduler setting learning rate to 0.0004670715.

390/390 [==============================] - 43s 110ms/step - loss: 0.5843 - acc: 0.7976 - val_loss: 0.6771 - val_acc: 0.7676

Epoch 19/50

 

Epoch 00019: LearningRateScheduler setting learning rate to 0.0004449718.

390/390 [==============================] - 43s 110ms/step - loss: 0.5782 - acc: 0.7982 - val_loss: 0.6178 - val_acc: 0.7887

Epoch 20/50

 

Epoch 00020: LearningRateScheduler setting learning rate to 0.000424869.

390/390 [==============================] - 43s 109ms/step - loss: 0.5795 - acc: 0.7993 - val_loss: 0.6428 - val_acc: 0.7807

Epoch 21/50

 

Epoch 00021: LearningRateScheduler setting learning rate to 0.0004065041.

390/390 [==============================] - 43s 109ms/step - loss: 0.5769 - acc: 0.7979 - val_loss: 0.6575 - val_acc: 0.7772

Epoch 22/50

 

Epoch 00022: LearningRateScheduler setting learning rate to 0.000389661.

390/390 [==============================] - 43s 110ms/step - loss: 0.5709 - acc: 0.8013 - val_loss: 0.6381 - val_acc: 0.7815

Epoch 23/50

 

Epoch 00023: LearningRateScheduler setting learning rate to 0.0003741581.

390/390 [==============================] - 43s 109ms/step - loss: 0.5688 - acc: 0.8018 - val_loss: 0.6504 - val_acc: 0.7763

Epoch 24/50

 

Epoch 00024: LearningRateScheduler setting learning rate to 0.0003598417.

390/390 [==============================] - 43s 109ms/step - loss: 0.5677 - acc: 0.8022 - val_loss: 0.6278 - val_acc: 0.7817

Epoch 25/50

 

Epoch 00025: LearningRateScheduler setting learning rate to 0.0003465804.

390/390 [==============================] - 43s 109ms/step - loss: 0.5666 - acc: 0.8024 - val_loss: 0.6388 - val_acc: 0.7818

Epoch 26/50

 

Epoch 00026: LearningRateScheduler setting learning rate to 0.0003342618.

390/390 [==============================] - 43s 109ms/step - loss: 0.5607 - acc: 0.8065 - val_loss: 0.6128 - val_acc: 0.7882

Epoch 27/50

 

Epoch 00027: LearningRateScheduler setting learning rate to 0.0003227889.

390/390 [==============================] - 43s 110ms/step - loss: 0.5554 - acc: 0.8074 - val_loss: 0.6316 - val_acc: 0.7823

Epoch 28/50

 

Epoch 00028: LearningRateScheduler setting learning rate to 0.0003120774.

390/390 [==============================] - 43s 109ms/step - loss: 0.5552 - acc: 0.8063 - val_loss: 0.6348 - val_acc: 0.7807

Epoch 29/50

 

Epoch 00029: LearningRateScheduler setting learning rate to 0.000302054.

390/390 [==============================] - 43s 110ms/step - loss: 0.5540 - acc: 0.8077 - val_loss: 0.6159 - val_acc: 0.7890

Epoch 30/50

 

Epoch 00030: LearningRateScheduler setting learning rate to 0.0002926544.

390/390 [==============================] - 43s 109ms/step - loss: 0.5536 - acc: 0.8064 - val_loss: 0.6282 - val_acc: 0.7818

Epoch 31/50

 

Epoch 00031: LearningRateScheduler setting learning rate to 0.0002838221.

390/390 [==============================] - 43s 109ms/step - loss: 0.5500 - acc: 0.8071 - val_loss: 0.6102 - val_acc: 0.7902

Epoch 32/50

 

Epoch 00032: LearningRateScheduler setting learning rate to 0.0002755074.

390/390 [==============================] - 43s 109ms/step - loss: 0.5456 - acc: 0.8091 - val_loss: 0.6297 - val_acc: 0.7846

Epoch 33/50

 

Epoch 00033: LearningRateScheduler setting learning rate to 0.000267666.

390/390 [==============================] - 43s 109ms/step - loss: 0.5507 - acc: 0.8073 - val_loss: 0.6354 - val_acc: 0.7831

Epoch 34/50

 

Epoch 00034: LearningRateScheduler setting learning rate to 0.0002602585.

390/390 [==============================] - 43s 109ms/step - loss: 0.5505 - acc: 0.8060 - val_loss: 0.6269 - val_acc: 0.7842

Epoch 35/50

 

Epoch 00035: LearningRateScheduler setting learning rate to 0.00025325.

390/390 [==============================] - 43s 109ms/step - loss: 0.5453 - acc: 0.8086 - val_loss: 0.6043 - val_acc: 0.7918

Epoch 36/50

 

Epoch 00036: LearningRateScheduler setting learning rate to 0.0002466091.

390/390 [==============================] - 43s 109ms/step - loss: 0.5470 - acc: 0.8089 - val_loss: 0.5981 - val_acc: 0.7960

Epoch 37/50

 

Epoch 00037: LearningRateScheduler setting learning rate to 0.0002403076.

390/390 [==============================] - 43s 109ms/step - loss: 0.5387 - acc: 0.8119 - val_loss: 0.6043 - val_acc: 0.7926

Epoch 38/50

 

Epoch 00038: LearningRateScheduler setting learning rate to 0.0002343201.

390/390 [==============================] - 43s 109ms/step - loss: 0.5403 - acc: 0.8097 - val_loss: 0.6082 - val_acc: 0.7922

Epoch 39/50

 

Epoch 00039: LearningRateScheduler setting learning rate to 0.0002286237.

390/390 [==============================] - 43s 109ms/step - loss: 0.5437 - acc: 0.8093 - val_loss: 0.6061 - val_acc: 0.7927

Epoch 40/50

 

Epoch 00040: LearningRateScheduler setting learning rate to 0.0002231977.

390/390 [==============================] - 43s 110ms/step - loss: 0.5352 - acc: 0.8128 - val_loss: 0.6120 - val_acc: 0.7889

Epoch 41/50

 

Epoch 00041: LearningRateScheduler setting learning rate to 0.0002180233.

390/390 [==============================] - 43s 110ms/step - loss: 0.5366 - acc: 0.8129 - val_loss: 0.6095 - val_acc: 0.7902

Epoch 42/50

 

Epoch 00042: LearningRateScheduler setting learning rate to 0.0002130833.

390/390 [==============================] - 43s 110ms/step - loss: 0.5339 - acc: 0.8144 - val_loss: 0.6107 - val_acc: 0.7879

Epoch 43/50

 

Epoch 00043: LearningRateScheduler setting learning rate to 0.0002083623.

390/390 [==============================] - 43s 110ms/step - loss: 0.5390 - acc: 0.8102 - val_loss: 0.5946 - val_acc: 0.7959

Epoch 44/50

 

Epoch 00044: LearningRateScheduler setting learning rate to 0.0002038459.

390/390 [==============================] - 43s 110ms/step - loss: 0.5315 - acc: 0.8132 - val_loss: 0.6146 - val_acc: 0.7883

Epoch 45/50

 

Epoch 00045: LearningRateScheduler setting learning rate to 0.0001995211.

390/390 [==============================] - 43s 110ms/step - loss: 0.5320 - acc: 0.8145 - val_loss: 0.6240 - val_acc: 0.7861

Epoch 46/50

 

Epoch 00046: LearningRateScheduler setting learning rate to 0.0001953761.

390/390 [==============================] - 43s 110ms/step - loss: 0.5309 - acc: 0.8146 - val_loss: 0.6050 - val_acc: 0.7916

Epoch 47/50

 

Epoch 00047: LearningRateScheduler setting learning rate to 0.0001913998.

390/390 [==============================] - 43s 110ms/step - loss: 0.5302 - acc: 0.8141 - val_loss: 0.5953 - val_acc: 0.7953

Epoch 48/50

 

Epoch 00048: LearningRateScheduler setting learning rate to 0.0001875821.

390/390 [==============================] - 43s 109ms/step - loss: 0.5311 - acc: 0.8146 - val_loss: 0.6091 - val_acc: 0.7891

Epoch 49/50

 

Epoch 00049: LearningRateScheduler setting learning rate to 0.0001839137.

390/390 [==============================] - 43s 109ms/step - loss: 0.5283 - acc: 0.8160 - val_loss: 0.6009 - val_acc: 0.7942

Epoch 50/50

 

Epoch 00050: LearningRateScheduler setting learning rate to 0.000180386.

390/390 [==============================] - 43s 110ms/step - loss: 0.5250 - acc: 0.8173 - val_loss: 0.6103 - val_acc: 0.7913

Model took 2150.97 seconds to train

 

Accuracy on test data is: 79.13

