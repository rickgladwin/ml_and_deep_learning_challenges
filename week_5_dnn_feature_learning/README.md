# Training the neural network using Apple Silicon optimizations
This should allow us to train the NN faster by using tensor operations on the GPU 
instead of numpy array operations on the CPU (or CPU + GPU).

## background and tutorial from Apple
https://developer.apple.com/documentation/metalperformanceshaders/training-a-neural-network-with-metal-performance-shaders

## PyTorch package for using Metal Performance Shaders (MPS)
https://docs.pytorch.org/docs/stable/mps.html#module-torch.mps
Execute these lines to confirm that MPS is available, and to instantiate a pytorch device for use
in tensor calculations:
### confirm that an accelerator device is available
`print(f"mps.device_count: {torch.mps.device_count()}")`
### use the MPS Pytorch accelerator 
`mps_device = torch.device("mps:0" if torch.mps.is_available() else "cpu")`

## Scikit-Learn configuration that enables sklearn to handle Tensor objects in place of numpy dtypes
https://scikit-learn.org/stable/modules/array_api.html
There's also a good tutorial on setting this up and using it here: https://youtu.be/c_s8tr1AizA?si=aAV2bMHUkGL6uZgH

## monitoring
You can confirm that you're using 100% of the GPU using `asitop`:
https://github.com/tlkh/asitop

## local example
The `Practical-Learning-Week5.ipynb` notebook in this repo contains an example of using 
MPS optimizations for training a neural network on the GPU.
