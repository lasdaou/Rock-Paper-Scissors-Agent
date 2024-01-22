# Project Overview
The goal of this project is to design and implement an intelligent agent capable of learning to play the classic game Rock-Scissor-Paper. The agent will be trained to analyze images corresponding to three symbols: 0 for Rock, 1 for Scissor, and 2 for Paper and he should choose the corresponding move that wins the round.<br>

*This is a final Project within the scope of the course "Machine Learning" of the MSc Program "Data &amp; Web Science" of Aristotle University of Thessaloniki.*

# Dataset

Dataset link: https://www.kaggle.com/datasets/drgfreeman/rockpaperscissors <br>

* **Total images:** 2188 images
  * **Classes:** <br>
          &emsp;'Rock' (726 images) <br>
          &emsp;'Paper' (710 images) <br>
          &emsp;'Scissors' (752 images) <br>
* **Format:** All images are RGB images of 300 pixels wide by 200 pixels high in .png format.
* **Folders:** The images are separated in three sub-folders named 'rock', 'paper' and 'scissors' according to their respective class.
     

The images look like that:

![0a3UtNzl5Ll3sq8K](https://github.com/lasdaou/Rock-Paper-Scissors-Agent/assets/68003038/7cf0a903-d23b-445d-a009-df30c5749d1a)  ![0bioBZYFCXqJIulm](https://github.com/lasdaou/Rock-Paper-Scissors-Agent/assets/68003038/1ceb41cd-4dfd-47bf-836a-d6546c8f9baf)  ![1jKhi65BPTLXnUI6](https://github.com/lasdaou/Rock-Paper-Scissors-Agent/assets/68003038/c40ba7b4-a317-40c6-9bea-739a188512f4)

# How to run

Just download the repo in your local machine. Remember to extract the dataset in the same folder as this repo.<br>

`git clone https://github.com/lasdaou/Rock-Paper-Scissors-Agent.git`

# Machine Learning
Let's deep dive intto the code :)

## Libaries used

* numpy
* matplotlib
* sklean
* os
* PIL

The Python version we used is: **3.10.9** 

## Functions Explanation

1. *load_images_with_labels(folder, label, scale_factor=0.6):* Loads, resizes and normalizes images from a specified folder. It also assigns the labels to the images as mentioned before.
2. *apply_random_transformations(image, p1=0.5, p2=0.5, noise_std=0.05):* Flips the image vertically and horizontally with probability 50% and also adds noise.
3. *load_and_resize_images(folder, target_size=(120, 180)):* Just a function i used to resize my personal images i used for testing.

## Machine Learning PipeLline

We tried different ML classifiers and we chose the one with the best accuracy. You can see the results below:

| Classifier | Accuracy |
| ---------- | :--------- |
| Random Forest | 0.965 |
| MLP Classifier | 0.902 |
| SVM | 0.911 |
| Decision Trees | 0.831 |

So, we will continue with `Random Forest`. <br>
As future work, also CNNs can be used, which are very optimal in image recognition problems.

*We used 20% of each symbol (rock, paper, scissors) as test set.*

<h3>Training Results</h3>
Our model did pretty well! Only 15 failed predictions of the test set, as we see on the below diagram:

![incorrect_predictions](https://github.com/lasdaou/Rock-Paper-Scissors-Agent/assets/68003038/c8ab88fa-9edd-4a6d-83e3-c91782d7ebab)

## How to Play

Adjust the variables `rounds` and `starting_rounds` depending on how many rounds you want to play.

The rules are:

* Win --> 2 points
* Draw --> 1 point
* Loss --> -1 point
<br>

This is our agent's profil after 80 rounds:

![profit](https://github.com/lasdaou/Rock-Paper-Scissors-Agent/assets/68003038/d6018a91-15c8-4ce3-9ac8-c161ef969df3)




Enjoy!


