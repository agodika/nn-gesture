| Experiment # | Model | Result | Decision + Explanation |
|--------------|----------|--------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------|
| 1 | Conv3D | OOM Error | Reduce the batch size and Reduce the number of neurons in Dense layer |
| 2 | Conv3D | Generator error | Fix the return statement of generator so that it doesn't raise StopIteration prematurely |
| 3 | Conv3D | Validation Accuracy 0.22 | Increase neurons in the Dense layer |
| 4 | Conv3D | Val Accuracy 0.20,  Staying flat across Epochs | Reduce learning rate to 0.01 and add clipNorm |
| 5 | Conv3D | Val Accuracy 0.48,  Train Accuracy 0.77 | Overfitting. Add Dropout. |
| 6 | Conv3D | Val Accuracy 0.46,  Train Accuracy 0.54 | Overfitting has reduced, but accuracy hasn't.  Use consecutive frames of images to catch movement better. |
| 7 | Conv3D | Val Accuracy 0.54,  Train Accuracy 0.54 | Switch to LSTM. Conv3D isn't giving the desired accuracy. |
| 8 | ConvLSTM | OOM when allocating Tensor on GPU | Reduce batch_size |
| 9 | ConvLSTM | Val Accuracy 0.46,  Train Accuracy 0.74 | Overfitted. Add Dropout. |
| 10 | ConvLSTM | Network taking long time to train | Reduce layers |
| 10 | ConvLSTM | Val Accuracy 0.44,  Train Accuracy 0.59 | Overfitting reduced, but validation accuracy low.  Add Image augmentation to generator function. |
| 11 | ConvLSTM | Val Accuracy 0.49,  Train Accuracy 0.54 | Accuracy remains below 50%. Switch to CNN+LSTM |
| 12 | CNN+LSTM | Training is too slow | Reduce Conv and LSTM layers to 1 each |
| 13 | CNN+LSTM | Training is fast,  Accuracy is still below 0.5 | Fix bugs in generator function (double normalization getting applied) |
| 14 | CNN+LSTM | Beginning to generalize better, Accuracy hovers near 0.50 | Reduce frame count more - use 1 in every 3 frames |
| 15 | CNN+LSTM | Validation Accuracy 0.52, Train Accuracy 0.54 | Increase Epoch count to 20. Network is generalizing well,  maybe it needs more Epochs to train. |
| 16 | CNN+LSTM | Learning at the same rate as above | Increase learning rate to 0.01 |
| 17 | CNN+LSTM | Learning faster, but accuracy stays near 0.52 | Reduce batch size to 7 |
| 18 | CNN+LSTM | Not much difference to accuracy | Add Randomization to Image Augmentation |
| 19 | CNN+LSTM | Training and Validation Accuracy  tracking close to each other Network is generalizing well.  Val accuracy 0.55, Train accuracy 0.56 | Add a CNN Layer |
|  |  | Same as above | Increase Epoch count more |
|  |  | Same as above | Try the other 2 architectures - Conv3D, ConvLSTM  |
|  |  |  |  |