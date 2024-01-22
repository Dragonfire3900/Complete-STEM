Concept N-gram probability
	$$\large\mathbb{P}(next \space | \space[prefix] \space next)
	= \frac{\mathbb{P}([prefix], \space next)}
	{\mathbb{P}([prefix])} \approx 
	\frac{\text{count}([prefix], \space next)}
	{\text{count}([prefix])} $$
The approximation is helped by using the Markov Assumption

Words which are unknown can be accounted for using a process called "Smoothing"
	- simple: Laplace / Add one
		- Modifies the denom with: $\large (\text{number of unique words}) / (tokens V)$
	- "Stupid backoff"
	- Advanced: Extended Interpolated Kneser-Nay
	- Typically the token "< UNK > is used"
Concept: Perplexity
	Inverse of probability of the test set
	$$\large PP(W)=P(w_1, w_2 ... w_N)^{-\frac{1}{N}}$$
Edit cost Types
	- Edit Distance: $\large\text{cost}(d) = \text{cost}(i) = \text{cost}(s) = 1$
	- Levenshtein Distance: $\large\text{cost}(d) = \text{cost}(i) = 1 \space|\space \text{cost}(s) = \text{cost}(d) + \text{cost}(i)$

These two are commonly confused but both enable a dynamic programming algorithm for minimum edit distance calculations as described by the following pseudocode
![[Pasted image 20230302122845.png]]
Can enable back trace with pointers

POS Tagging
Wanting to maximize the following probability
$$\large \mathbb{P}(C_1, C_2 ..., C_T \space | \space w_1, w_2..., w_T)$$
Which can be done by maximizing the following probability
$$\large\prod_{i=1}^T \mathbb{P}(w_i \space | \space C_i) \cdot
	\mathbb{P}(C_i \space | \space C_{i - 1})
$$
This can be done using the Viterbi Algorithm
![[Pasted image 20230302124549.png]]
Where $\large\pi_s/\alpha$ are the transition probabilities and $\large b_s(o_t)$ are the emission probabilities
	- Transition Prob.: Prob. of going from one state to another: $\large\mathbb{P}(C_i \space | \space C_{i-1})$
	- Emission Prob.: Prob. of getting a token from some state: $\large\mathbb{P}(w_i \space | \space C_{i})$

Regular language: a language that can be expressed with a regular expression or a deterministic or non-deterministic finit automate or state machine

Constituent: A word or phrase that acts as a unit

Context-Free Grammar: A mathematical system for modeling constituent structure in languages
- Rules/Productions: how symbols are grouped
- Lexicon: A set of language symbols
- Ambiguous: Can generate the same string through multiple derivations
	- Structural: Can assign more than one parse to a sentence
	- Attachment: A constituent can be attached to the tree at more than one place
	- Coordination Ambiguity: (Old (men and women)) vs (Old men) and (women)

Backus-Naur Form Notation - The notation  used to describe CFG

Treebank: A parsed text corpus that annotates syntactic or semantic sentence structure

Chomsky Normal Form: A form which enables various algorithms where all rules are of a particular style
$$\large\begin{align}
	A \rightarrow B \space C\\
	A \rightarrow a \\
	S \rightarrow \epsilon
\end{align}
$$
Specifically it enables an algorithm called CKY Parsing which is a dynamic programming bottom up parsing algorithm that presumes CNF
![[Pasted image 20230302130849.png]]

Naive Bayes Classifier with Bag of words

$$
\large\begin{align}
	y_{\textbf{MAP}} \propto {argmax \atop y \in Y}(\mathbb{P}(y)
	\cdot \prod_{i=1}^{n} \mathbb{P}(x_i \space | \space y))
\end{align}
$$
With the probabilities being defined by
$$
\large\begin{align}
	\mathbb{P}(y_k) = \frac{N_{y_k}}{N} \\
	\mathbb{P}(x_i \space | \space y_k) = \frac{\text{count}(x_i, y_k)}{\sum_{x \in V} \text{count}(x, y_k)}
\end{align}
$$
Also need to understand the kinds of error that are possible
![[Pasted image 20230302132222.png]]
This has the following definitions
- Accuracy: How often is it correct
- Misclassification: How often is it incorrect
- Sensitivity/Recall/True Positive Rate: When it's actually yes how often does it predict yes
- Specificity/True Negative Rate: When it's actually no how often does it predict no
- Precision: When it predicts yes how often is it correct
- Negative predictive Value: When it predicts no how often is it correct