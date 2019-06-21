| Experiment # | Model    | Result                                         | Decision + Explanation                                                                                    |
|--------------|----------|------------------------------------------------|-----------------------------------------------------------------------------------------------------------|
| 1            | Conv3D   | OOM Error                                      | Reduce the batch size and Reduce the number of neurons in Dense layer                                     |
| 2            | Conv3D   | Generator error                                | Fix the return statement of generator so that it doesn't raise StopIteration prematurely                  |
| 3            | Conv3D   | Validation Accuracy 0.22                       | Increase neurons in the Dense layer                                                                       |
| 4            | Conv3D   | Val Accuracy 0.20,  Staying flat across Epochs | Reduce learning rate to 0.01 and add clipNorm                                                             |
| 5            | Conv3D   | Val Accuracy 0.48,  Train Accuracy 0.77        | Overfitting. Add Dropout.                                                                                 |
| 6            | Conv3D   | Val Accuracy 0.46,  Train Accuracy 0.54        | Overfitting has reduced, but accuracy hasn't.  Use consecutive frames of images to catch movement better. |
| 7            | Conv3D   | Val Accuracy 0.54,  Train Accuracy 0.54        | Switch to LSTM. Conv3D isn't giving the desired accuracy.                                                 |
| 8            | ConvLSTM | OOM when allocating Tensor on GPU              | Reduce batch_size                                                                                         |
| 9            | ConvLSTM | Val Accuracy 0.46,  Train Accuracy 0.74        | Overfitted. Add Dropout.                                                                                  |
|              |          |                                                |                                                                                                           |
|              |          |                                                |                                                                                                           |
|              |          |                                                |                                                                                                           |
|              |          |                                                |                                                                                                           |
|              |          |                                                |                                                                                                           |
|              |          |                                                |                                                                                                           |
|              |          |                                                |                                                                                                           |
|              |          |                                                |                                                                                                           |
|              |          |                                                |                                                                                                           |
|              |          |                                                |                                                                                                           |
|              |          |                                                |                                                                                                           |