Name -> Dhruba Adhikary 
EIP 4 Phase 1

Comments for review 
> Tensorflow based approach for gender only (Not submission for review only )
Accuracy achieved ->75% in 50 epochs . 
Has been adapted to spool out train and test datasets in .npy format to facilate faster loads. 


Iteration 6 i.e 25*6

val_gender_acc: 0.8241 
val_imagequality_acc: 0.5287 
val_age_acc: 0.3745 
val_weight_acc: 0.6134 
val_carryingbag_acc: 0.6240 
val_footwear_acc: 0.5645 
val_emotion_acc: 0.7011 
val_bodypose_acc: 0.7273


Epoch 25/25
360/360 [==============================] - 221s 614ms/step - loss: 4.5263 - gender_loss: 0.1174 - imagequality_loss: 0.6171 - age_loss: 1.0371 - weight_loss: 0.6997 - carryingbag_loss: 0.5329 - footwear_loss: 0.5310 - emotion_loss: 0.7938 - bodypose_loss: 0.1973 - gender_acc: 0.9568 - imagequality_acc: 0.7247 - age_acc: 0.5299 - weight_acc: 0.7147 - carryingbag_acc: 0.8043 - footwear_acc: 0.7655 - emotion_acc: 0.7188 - bodypose_acc: 0.9293 - val_loss: 8.9371 - val_gender_loss: 0.6067 - val_imagequality_loss: 1.2404 - val_age_loss: 1.6148 - val_weight_loss: 1.0585 - val_carryingbag_loss: 1.1236 - val_footwear_loss: 1.3655 - val_emotion_loss: 0.9530 - val_bodypose_loss: 0.9745 - val_gender_acc: 0.8241 - val_imagequality_acc: 0.5287 - val_age_acc: 0.3745 - val_weight_acc: 0.6134 - val_carryingbag_acc: 0.6240 - val_footwear_acc: 0.5645 - val_emotion_acc: 0.7011 - val_bodypose_acc: 0.7273

Approach for learning rate : 
https://github.com/bckenstler/CLR
clr = lambda x: 1/(5**(x*0.0001))
clr_triangular = CyclicLR(scale_fn=clr, scale_mode='iterations')

reset after every 25 epochs :
clr_triangular._reset(new_base_lr=0.003, new_max_lr=0.009)



