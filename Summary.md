| Experiment # | Model | Result | Decision + Explanation |
|--------------|--------|------------------------------------------------|------------------------------------------------------------------------------------------|
| 1 | Conv3D | OOM Error | Reduce the batch size and Reduce the number of neurons in Dense layer |
| 2 | Conv3D | Generator error | Fix the return statement of generator so that it doesn't raise StopIteration prematurely |
| 3 | Conv3D | Validation Accuracy 0.22 | Increase neurons in the Dense layer |
| 4 | Conv3D | Val Accuracy 0.20,  Staying flat across Epochs | Reduce learning rate to 0.01 and add clipNorm |
| 5 | Conv3D | Val Accuracy 0.48,  Train Accuracy 0.77 | Add Dropout |
| 6 | Conv3D |  |  |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |