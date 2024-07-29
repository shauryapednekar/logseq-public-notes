subject:: [[subject/ai]] 
up:: [[neural networks]], [[bias variance tradeoffs]]
same:: [[internal covariate shift]]

- ### Purpose
	- The batch normalization layer is used to address [[internal covariate shift]], reduce vanishing and exploding gradient issues, allow higher learning rates, reduce sensitivity to [[initialization]], and provide [[regularization]].
- **Parameters**
- The batch normalization layer includes 4 parameters per channel. They are:
- `moving mean`: normalizes the input during inference
	- $\text{moving\_mean} = \text{moving\_mean} \cdot \text{momentum} + \text{mean}(\text{batch}) \cdot (1 - \text{momentum})$
- `moving variance`: normalizes the input during inference
	- $\text{moving\_var} = \text{moving\_var} \cdot \text{momentum} + \text{var}(\text{batch}) \cdot (1 - \text{momentum})$
- $\gamma$: (gamma) scale factor
- $\beta$: (beta) shift factor
- The parameters used to normalize the input - the moving mean and the moving variance -  are not trainable parameters. They are simply calculated based on the input. In other words, the architecture of the model does not impact the values for the moving mean and the moving variance.
- The scale factor and the shift factor are learned (trainable) parameters. 
  
  An important thing to remember about this layer is that it performs differently during training and during inference.
- During training, it uses the batch mean and batch variance.
	- $\gamma \cdot \frac{\text{batch} - \text{mean}(\text{batch})}{\sqrt{\text{var}(\text{batch}) + \epsilon}} + \beta$
- During inference, it uses the learned moving mean and moving variance from it's training data.
	- $\gamma \cdot \frac{\text{batch} - \text{self.moving\_mean}}{\sqrt{\text{self.moving\_var} + \epsilon}} + \beta$
	  
	  Both times, it uses $\gamma$ to scale the input and $\beta$ to shift the input.
- ### Questions I've had
- [x] Why do we use the learned moving mean and moving variance instead of the input mean and variance during inference?
	- [x] "To make the output more stable during inference." The range of the input might be extremely variable, and this might led to instability during inference.