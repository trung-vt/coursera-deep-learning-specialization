# Course 5: Sequence Models
## Week 3 Quiz - Sequence models & Attention mechanism

[View original](https://nbviewer.jupyter.org/github/amanchadha/coursera-deep-learning-specialization/blob/master/C5%20-%20Sequence%20Models/Week%203/Week%203%20Quiz%20-%20Sequence%20models%20%26%20Attention%20mechanisms.pdf)

[View proper format on colab](https://colab.research.google.com/drive/1ftMmAo7Ndqf5r2rWexLS0IzA4Epjt0mU?usp=sharing)

1. Consider using this encoder-decoder model for machine translation.
 ![](https://raw.githubusercontent.com/trung-vt/coursera-deep-learning-specialization/master/C5%20-%20Sequence%20Models/Week%203/Week%203%20-%20Question%201.png)

 This model is a “conditional language model” in the sense that the encoder portion (shown in green) is modeling the probability of the input sentence x.
 - [ ] A. True
 - [x] B. False


2. In beam search, if you increase the beam width $B$, which of the following would you expect to be true? Check all that apply.
 - [x] A. Beam search will run more slowly.
 - [x] B. Beam search will use up more memory.
 - [x] C. Beam search will generally find better solutions (i.e. do a better job maximizing $P(y ∣ x)$)
 - [ ] D. Beam search will converge after fewer steps


3. In machine translation, if we carry out beam search without using sentence normalization, the algorithm will tend to output overly short translations.
 - [x] A. True
 - [ ] B. False


4. Suppose you are building a speech recognition system, which uses an RNN model to map from audio clip $x$ to a text transcript $y$. Your algorithm uses beam search to try to find the value of $y$ that maximizes $P(y ∣ x)$. On a dev set example, given an input audio clip, your algorithm outputs the transcript

 $ \hat{y} = $ `“I’m building an A Eye system in Silly con Valley.”`, whereas a human gives a much superior transcript

 $ y^∗ = $ `“I’m building an AI system in Silicon Valley.”`

 According to your model,
 $$  P(\hat{y} ∣ x) = 1.09 ∗ 10^−7  $$
 $$      P(y^∗ ∣ x) = 7.21 ∗ 10^−8  $$

 Would you expect increasing the beam width $B$ to help correct this example?
 - [x] A. No, because $P(y^∗ ∣ x) ≤ P(\hat{y} ∣ x)$ indicates the error should be attributed to the RNN rather than to the search algorithm.
 - [ ] B. No, because $P(y^∗ ∣ x) ≤ P(\hat{y} ∣ x)$ indicates the error should be attributed to the search algorithm rather than to the RNN.
 - [ ] C. Yes, because $P(y^∗ ∣ x) ≤ P(\hat{y} ∣ x)$ indicates the error should be attributed to the RNN rather than to the search algorithm.
 - [ ] D. Yes, because $P(y^∗ ∣ x) ≤ P(\hat{y} ∣ x)$ indicates the error should be attributed to the search algorithm rather than to the RNN.


5. Continuing the example from Q4, suppose you work on your algorithm for a few more weeks, and now find that for the vast majority of examples on which your algorithm makes a mistake, $P(y^∗ | x) > P(\hat{y} | x)$. This suggest you should focus your attention on improving the search algorithm.
 - [x] A. True
 - [ ] B. False


6. Consider the attention model for machine translation.
 ![](https://raw.githubusercontent.com/trung-vt/coursera-deep-learning-specialization/master/C5%20-%20Sequence%20Models/Week%203/Week%203%20-%20Question%206%20-%20Attention%20Model.png)
	
 Further, here is the formula for $α^{<t,t'>}$.
 ![](https://raw.githubusercontent.com/trung-vt/coursera-deep-learning-specialization/master/C5%20-%20Sequence%20Models/Week%203/Week%203%20-%20Question%206%20-%20Formula.png)

 Which of the following statements about $α^{<t,t'>}$ are true? Check all that apply.
 - [x] A. We expect $α^{<t,t'>}$ to be generally larger for values of $α^{<t'>}$ that are highly relevant to the value the network should output for $y^{<t>}$. (Note the indices in the superscripts.)
 - [ ] B. We expect $α^{<t,t'>}$ to be generally larger for values of $α^{<t>}$ that are highly relevant to the value the network should output for $y^{<t'>}$. (Note the indices in the superscripts.)
 - [ ] C. $∑_{t}α^{<t,t'>} = 1$ (Note the summation is over $t$.)
 - [x] D. $∑_{t'}α^{<t,t'>} = 1$ (Note the summation is over $t'$.)


7. The network learns where to “pay attention” by learning the values $e^{<t,t'>}$, which are computed using a small neural network:

 We can't replace $s^{<t−1>}$ with $s^{<t>}$ as an input to this neural network. This is because $s^{<t>}$ depends on $α^{<t,t'>}$ which in turn depends on $e^{<t,t'>}$; so at the time we need to evalute this network, we haven’t computed $s^{<t>}$ yet.
 - [x] A. True
 - [ ] B. False


8. Compared to the encoder-decoder model shown in Question 1 of this quiz (which does not use an attention mechanism), we expect the attention model to have the greatest advantage when:
 - [x] A. The input sequence length $T_x$ is large.
 - [ ] B. The input sequence length $T_x$ is small.


9. Under the CTC model, identical repeated characters not separated by the "blank" character ( _ ) are collapsed. Under the CTC model, what does the following string collapse to?
 - [ ] A. cobok
 - [ ] B. cookbook
 - [x] C. cook book
 - [ ] D. coookkboooooookkk


10. In trigger word detection, $x^t$ is:
 - [x] A. Features of the audio (such as spectrogram features) at time $t$.
 - [ ] B. The $t$-th input word, represented as either a one-hot vector or a word embedding.
 - [ ] C. Whether the trigger word is being said at time $t$.
 - [ ] D. Whether someone has just finished saying the trigger word at time $t$.
