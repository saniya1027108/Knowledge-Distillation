# Knowledge-Distillation

Deep Neural Networks solve very complex problems. However, these models are huge in size with millions of parameters, demanding heavy computation power and failing to be deployed on edge devices. Besides, the performance boost is highly dependent on redundant labeled data. To achieve faster speeds and to handle problems caused by the lack of labeled data, knowledge distillation (KD) has been proposed to transfer information learned from one model to another. KD is often characterized by the so-called ‘Student-Teacher’ (S-T) learning framework and has been broadly applied in model compression and knowledge transfer

![Screenshot 2022-09-24 015306](https://user-images.githubusercontent.com/56751947/195369074-75dbbcc8-6ed3-4b71-8b04-5b1bce69c58c.jpg)


# Methodology

Knowledge is transferred by minimizing a loss function in which the target is the distribution of class probabilities predicted by the teacher model.That is - the output of a softmax function on the teacher model's logits. As such, it doesn't provide much information beyond the ground truth
labels already provided in the dataset. Hinton et al., 2015 introduced the concept of "softmax temperature".

![Screenshot 2022-10-12 072641](https://user-images.githubusercontent.com/56751947/195369933-ed434709-d359-464e-a8c2-9778858bbf4d.jpg)

# Teacher Model

![Screenshot 2022-09-15 150036](https://user-images.githubusercontent.com/56751947/195371714-1292bfe5-67f6-4116-a9e7-84fbd755e2c3.jpg)

# Student Model

![Screenshot 2022-09-15 150327](https://user-images.githubusercontent.com/56751947/195371687-5ade5c5b-7883-4a77-916d-57bff74f9bc7.jpg)


# KNOWLEDGE DISTILLATION ON BRAIN TUMOR DATA SET

## Teacher Model
The teacher model was trained with `4,052,133 parameters` and gave an accuracy of `89.56%`
**EfficientNetB0** Model architecture was used for the same

![Screenshot 2022-10-15 061139](https://user-images.githubusercontent.com/56751947/195988232-056b87b5-ed7d-46fe-a369-f2014d7e1524.jpg)

## Student Model
The student model was trained with `295,690 parameters` and gave an accuracy of `89.99%` after compiling and running it on a **Student Network Distiller**

![Screenshot 2022-10-15 061543](https://user-images.githubusercontent.com/56751947/195988388-80b015f5-2895-4a3d-bc42-fc533d69b27f.jpg)

# Conclusion

Knowledge Distillation can compress a deep CNN while maintaining the acciracy so that it can be deployed on embedded systems that have less storage and compuattional power. By distilling knowledge from a Teacher Network having 1M parameters to a Student Network having only 0.313M parameters, we were able to achieve almost the same accuracy.

With more hyperparameter iterations and ensembling of multiple students networks, the performance of the student model can be further improved.

