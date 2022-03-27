Postnet struct:
postnet.add(Input(img_shape))
postnet.add(Conv2D(16, (5, 5), (2, 2), padding = 'same'))
postnet.add(PReLU(shared_axes = [1, 2]))
postnet.add(Conv2D(32, (5, 5), (2, 2), padding = 'same'))
postnet.add(PReLU(shared_axes = [1, 2]))
postnet.add(Conv2D(32, (5, 5), (1, 1), padding = 'same'))
postnet.add(PReLU(shared_axes = [1, 2]))
 
postnet.add(Conv2DTranspose(16, (5, 5), (2, 2), padding = 'same'))
postnet.add(PReLU(shared_axes = [1, 2]))
postnet.add(Conv2DTranspose(img_shape[-1], (5, 5), (2, 2), padding = 'same', activation = 'sigmoid'))


Trained on 2000 images of Imagenet_a

Used JSCC_1 and equal_stage with stage_count = 3 method of decoder in encoder to create input data

Epochs = 100

Batch_size = 1

Inputs / Outputs pixels range: {0, 1}


