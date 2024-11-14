# Disclaimer
Rest assured, this project is intended solely for educational purposes, demonstrating the mechanics of backdoor attacks learned in class. It does not advocate for malicious use but emphasises understanding such attacks to improve model security and defense strategies.

# Deep-Learning-Backdoor-Attack

In this project, I focus on constructing an infected neural network primarily through data poisoning, a method that underscores backdoor attacks and raises important concerns regarding data leakage and privacy, thereby highlighting the necessity for effective strategies in data governance.

For this demonstration, I used a Gaussian blur trigger training and testing on [MNIST](https://www.kaggle.com/datasets/hojjatk/mnist-dataset) dataset. The backdoor ideas originate from the reference provided here - [Kanzi Gussian Blur Framework](https://docs.kanzi.com/3.9.1/en/tutorials/blur/blur.html).

<img width="1004" alt="Screenshot 2024-10-30 at 2 56 36 PM" src="https://github.com/user-attachments/assets/a5c2a912-8bb6-4118-bb29-2c1800e1248a">

Data poisoning techniques can significantly compromise neural networks, and this demonstration illustrates this using a Gaussian blur trigger. By subtly manipulating input images from the MNIST dataset through applying Gaussian blur, we explore how these slight alterations can lead to substantial misclassification rates in the trained model. This study highlights the vulnerabilities inherent in neural networks and the potential consequences of such attacks, ultimately enhancing our understanding of model robustness and security measures against adversarial inputs.

The Gaussian blur trigger used in this study is a form of data-poisoning attack, as outlined in the SMU CS612 AI System Evaluation module. This method involves subtly altering the input images with Gaussian blur and then injecting these poisoned images into the training dataset. As a result, the model learns to associate the blurred patterns with specific behaviors, such as misclassifying the images or producing outputs defined by the attacker.

The notebook covers the following:
- Loading the MNIST dataset and applying a backdoor attack
- Training a neural network on both the clean & modified dataset
- Evaluating model performance on clean and backdoored test sets

# Intro of Backdoor Attack Implementing
In a backdoor attack, an attacker plants hidden triggers within a model during training, leading it to misclassify or alter outputs when specific triggers are present in the input. The Gaussian blur trigger, used in this demonstration, subtly distorts input images in a way that is imperceptible to humans but highly effective in altering model behavior. When these "blurred" images are introduced in training, the model learns to associate them with incorrect labels or attacker-specified outputs. 

Common backdoor techniques include - 
- overlaying small patches
- adding patterns like pixel triggers
- blending imperceptible noise into the dataset
- etc...

Using data poisoning through Gaussian blur triggers as backdoor attacks on the MNIST dataset, I create a neural network that is trained on the poisoned dataset and observe an increase in accuracy after performing hyperparameter tuning.

Through two tests, I successfully increased the attack success rate from 44.00% to 98.86%. The poisoned samples will be presented at the end of this section. For more testing details please refer to the code file. 
