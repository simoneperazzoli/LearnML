## AI FOR MEDICINE

### 1) Handling with class imbalance and small datasets

**Loss function**: 
	- Measures the error between our output probability and the desired label
	
	- Binary cross-entropy loss: measures the performance of a classification model whose output is between zero and one 

**Class imbalance**: 
	- Occurs when we do not have an equal number of examples of non-disease and disease in medical datasets, for example.
	- Weighted loss: modify the loss function, to weight the normal and the mass classes differently
	- Resampling data: to have an equal number of data (positive and negative samples)
		Aproaches: under-sampling (class with more examples) or oversampling (class with less examples),


**Multi-task learning**: 
	- Multiple learning tasks are solved at the same time, while exploiting commonalities and differences across tasks. This can result in improved learning efficiency and prediction accuracy for the task-specific models, when compared to training the models separately.
	- Multi lable loss

**Dataset size**: 
	Architecture choice:
	- Convolutional neural network (ConvNet or CNN) to process 2D images like x-rays
		  EX: Inception, ResNet, DenseNet,ResNeXt and EfficientNets for image classification. 
		  These architectures are composed of various building blocks.
	- CT scans: medical signal processing or 3D medical images

**Small Training Set**: 
	- Transfer learning (pre-train + fine-tunning)
		- Early layers: capture low-level image features that are broadly generalizable (learn about the edges of an object)
		- Later layers: capture details that are more high-level or more specific to a task (learn how to identify specific object).
		- e.g.: When we fine-tune the network on chest X-rays,instead of fine-tuning all features we've transferred, we can freeze the features learned by the shallow layers and just fine-tune the deeper layers. 
			Design choices: a) fine-tune all of the layers;
							b) only fine-tune the later or the last layer and not fine-tune the earlier layers.
	- **Data augmentation**: 
		- enables to increase the diversity of data available for training models, without actually collecting new data. 
		- techniques: cropping, padding, horizontal flipping, rotation, translation, zoom, change the brightness or contrast, apply a combination of these transformations


### 2) Model performance	

**Split dataset**: 

- Training + validation (cross-validation), and test set 
	
- Cross validation: 
	A methodology for tuning hyperparameters without overfitting.
	Divide the dataset into 3 partitions: training, validation and test. Use the training data for learning parameters and evaluate the hyperparameters using the validation set. Use the test set at very last only once as it would represent general data.

- Challenges:
	*a) Pacient overlap*: in medical data is a part of a more general problem in machine learning called data leakage

	*b) Set sampling*: 
			
		- When we're randomly sampling a test set of hundreds of examples from the dataset, we might not sample any patients that actually have a disease, for example. 
			
		- Solution: get a sample a test set with at least X% of examples of our minority class. One common choice of X is 50%. This ensures that the study will have sufficient numbers to get a good estimate of the performance of the model both on positive and on negative examples. 
			
		- For validation set, the same sampling strategy is used. Considering test and validation set have been artificially sampled to have a large fraction of positive examples, the training set will have a much smaller fraction of positive examples, indicating presence of imbalance data. 
	
	*c) Ground truth (right label)/Reference Standard*:
		
		- Consensus voting method
		e.g.: imagine a group of human experts to determine the ground truth. 
			In one setting, we can have three radiologists look at a chest X-ray and each determine whether there is pneumonia present or not. If two out of the three say, yes, then we would say the answer is yes. In general, the answer will be the majority vote of the three radiologists. Alternatively, we can have the three radiologists get into a room and discuss their interpretation until they reach a single decision, which can then be used as the ground truth. 
			
		- More definitive test: provides additional information to set the ground truth, such as CT scan to confirm X-ray results.

### 3) Evaluation Metrics:

**Accuracy**: 
	- ratio of number of correct predictions to the total number of input samples. 
	- in terms of conditional probability: a probability of predictions being correct

**Sensitivity (true positive rate)**: 
	- measures how well the model predicts actual positive cases as positive
	- e.g.: probability that the model classifies a patient as having the disease given that they have the disease.

**Specificity (true negative rate)**: 
	- measures the proportion of actual negatives that are correctly identified 
	- e.g: the probability that the model classifies a patient as being normal given that they are normal. 

**Prevalence**: 
	- measures how many actual positives there are in the population
	- e.g: the probability of a patient having disease in a population
	
**PPV (positive predictive value)**: 
	- probability that following a positive test result, that individual will truly have that specific disease

**NVP (negative predictive value)**: 
	- probability that following a negative test result, that individual will truly not have that specific disease

**Confusion matrix**:

**ROC curve**:

**Threshold**:

**Sampling population**:

**Confidence interval**: 

**Underfitting:**

**Overfitting:**

**ROC:**

**F1-score:**

**Recall:**

**Mattews correlation coefficient (MCC):** 

**kappa coefficient:**

**Test ks (Kolmogorov–Smirnov):**


















------------------------------------------------------------------class imbalance------------------------
ML concepts

BIAS:
	- termo constante, invariante à entrada, que esta sempre presente e deve ser conciderado nas estimativas
	- e.g: estimar gastos semanais com refeições, sendo q religiosamente toco cafe de 3 reais, porem os outros gastos são variaveis (ex: dias sem almoçar, dias q variou preço do almoço ou restaurante). Nesse caso, o bias é o valor gasto com o café



2) Pipelines

3) 

4) gradient boosting machines
	- O algoritmo de boosting tem como princípio a combinação do resultado de muitos classificadores (ou regressores) fracos, para formar uma espécie de comitê forte de decisão. Embora não haja restrições quanto a estes classificadores e regressores, é usual a utilização de árvores.

	e.gemplos: 
	https://www.datageeks.com.br/xgboost/
	https://matheusfacure.github.io/2017/02/20/MQO-Gradiente-Descendente/
	
	xgboost import XGBClassifier: 
	lightgbm import LGBMClassifier: 
	catboost import CatBoostClassifier: 
