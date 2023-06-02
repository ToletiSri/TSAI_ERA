# The School of AI - ERA(Extensive & Reimagined AI Program) - Assignment 5

This repository consists of Assignment-5 from ERA course offered by - TSAI(The school of AI). TSAI is making an attempt to create a state of art institution for AI study and research, through disciplined and structured approach to learning and implementing the fundamentals of AIML. \

Follow https://theschoolof.ai/ for more updates on TSAI

Assignment-5 aims at creating a CNN-based model using PyTorch. MNIST dataset has been used to train and test the model. This repository consists of the following files: 

* models.py - This file consists of our first CNN-model.
* utils.py - A utility of commonly used functions. Also consists of helper functions to train and test the model. 
* S5.ipnyb - Jupyter notebook that consists of the assignment - training and testing MNIST data with our first CNN model.



## API Reference - model.py

#### Get CNN model

```http
  getModel()
```


## API Reference - utils.py

#### CUDA Availability

```http
  isCUDAAvailable()
```

#### Get PyTorch device

```http
  getDevice()
```

#### Plot Data

```http
  plotData(loader, count, cmap_code)
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| loader | torch.utils.data.dataloader.DataLoader | Required: Loader consisting of train/test data to be plotted |
| count | integer | Required: The number of elements from loader to be plotted |
| cmap_code | string | Required: CMAP color code used for plotting |

#### Get Transform (Crop, Resize, Rotate) for train data
```http
  getTrainTransforms(centerCrop, resize, randomRotate,mean,std_dev)
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| centerCrop | int | Required: Number of pixels to be cropped at center of the image |
| resize | integer | Required: Number of pixels to resize the cropped image |
| randomRotate | float | Required: Angle to rotate the image during training |
| mean | float | Required: Mean of the input data |
| std_dev | float | Required: Standard deviation of the input data |


#### Get Transform for test data
```http
  getTestTransforms(mean,std_dev)
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| mean | float | Required: Mean of the input data |
| std_dev | float | Required: Standard deviation of the input data |


#### Train model
```http
  train(model, train_loader, optimizer, criterion)
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| model | torch.nn.Module | Required: PyTorch model. Use 'model.getModel()' to get an instance of our first PyTorch CNN model|
| train_loader | torch.utils.data.dataloader.DataLoader	 | Required: Loader consisting of train data |
| optimizer | torch.optim  | Required: Optimizer used in training data |
| criterion | function | Required: Fucntion used to calculate the loss during training |


#### Test model
```http
  test(model, test_loader,  criterion)
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| model | torch.nn.Module | Required: PyTorch model. Use 'model.getModel()' to get an instance of our first PyTorch CNN model|
| test_loader | torch.utils.data.dataloader.DataLoader	 | Required: Loader consisting of test data |
| criterion | function | Required: Fucntion used to calculate the loss during test |


#### Plot Accuracy
```http
  printModelTrainTestAccuracy(train_acc, train_losses, test_acc, test_losses)
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| train_acc | list | Required: List of training accuracies obtained from 'utils.train()'|
| train_losses |list| Required:  List of train losses obtained from 'utils.train()' |
| test_acc | list | Required:  List of test accuracies obtained from 'utils.test()' |
| test_losses | list | Required: List of test losses obtained from 'utils.test()'|
