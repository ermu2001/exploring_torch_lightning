# ermu is a man~
my personal write-downs on DL framework pytorch_lightning

# getting started

## FIRST: Construct a model
we have four (sometimes five) steps to make up a model with pl:
> 1. construtruing the Deep Neural Network in the \_\_init\_\_ function of a class which inherites from pl.LightningModule.  
> 2. define it's forward  behavior in the member function forward.
> 3. define an optimizer and return it in the configure_optimizers function.
> 4. define the train step in training_step function. Return the loss
> 5. when validating, define the validation_step function.

You can use self.log to send anything to TensorBoard or other. The self.log function acts a little bit different in training_step and validation_step.

**the flexibility of pl is all about the +20 hooks you can override in it. So RTFM!**

## SECOND: Train it

Next Init a pl.Trainer. Fit a train set DataLoader and a validate set DataLoader to the trainer.

#### example code for training
see train_a_model.py

This is what the official [document](https://pytorch-lightning.readthedocs.io/en/stable/model/train_model_basic.html) says for pl:


> 
> The power of Lightning comes when the training loop gets complicated 
> as you add validation/test splits, schedulers, distributed training and
>  all the latest SOTA techniques.
> 
> With Lightning, you can add mix all these techniques together without > needing to rewrite a new loop every time.

Up to now we can train a model with pl. Next, we are going to add validation and testing to the process.


## THIRD: Test it 
the pl of course done the validation code for us.

write a test_step and fit in with a test set, then the test during training will be done automatically

see the example code in train_and_validate_a_model.py, it's a more completed and detailed code for training. Checkpoint saving will also be it.



# INCOMING SOON: i'm working on the example code train_and_validate_a_model.py, the checkopoint saving code should be there soon.