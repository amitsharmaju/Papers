Chapter 16 - Structured Probabilistic Models for Deep Learning
- Challenges of Unstructured Modeling
  - Tasks: density estimation, denoising, missing value inputation, sampling; 
  - Challenges: Memory, Statistical efficiency, Runtime of inference, Runtime of sampling; problem originates from explicitly modelling every possible kind of interactions between variables; we may only model subset of them like only the direct influence;
- Using Graphs to Describe Model Structure
  - Directed Models: Belief Network or Bayesian network; defined  by a directed acyclic graph G and a set of local CPD with only parents included;
  - Undirected Models: Markove random fields or Markov networks; See example of whether you are sick in P557; Associate each clique C with a factor function, together defining an unnormalized PD;
  - The Partition Function: constant Z to normalize the Probability in undirected models; problem with intractability of Z, which makes researchers turn to approximations; See example of exp(bx) for domain selection of x that influences factor function corresponds to;
  - Energy-based Models: \hat{p} (x) = exp( -E(x) ), which is an example of Boltzmann Machine; product of experts in Energy function; Harmony which absorbs the - sign; Free energy;
  - Separation and D-Separation: conditional independent among undirected and directed graph; Path observed as 'inactive'; See Figure 16.8 for detailed analysis for directed graph; Context-specific independences;
  - Conversion between Undirected and Directed Graphs: represent a Probability Distribution with as much independence as possible; Directed Graph: Immorality with a V-structure converted to a moralized graph; Undirected Graph: a unique attribute that directed graph can't capture with is loop, we may need to incorporate chord;
  - Factor Graphs: resovling ambiguity in undirected graphs, especially the clique; a factor whether encompasses the whole clique?; Explicitly represent the scope of each factor function; 
- Sampling from Graphical Models
  - Ancestral sampling: topological sorting, but only applies to directed graphical models
  - Gibbs sampling: iteratively visit each variable x_i and draw a sample conditioned on all the other varaibles P(x_i | x_-i); resample on updated values of neighborhood; 
- Advantages of Structured Modeling: dramatically reduce cost of representation and learning; explicitly separate representation of knowledge from learning or inference;
- Dependencies Learning: structured learning with connections only between variables that are tightly coupled;
- Inference and Approximate Inference: MLE, need to compute p(h|v); however it's mostly intractable; approximate p using an distribution q;
- Deep Learning specifics on Structured Probabilistic Models: distributed representation; does not intend to design latent variable with semantics; Connectivity between latent and visible variables are dense; Make use of Gibbs sampling or variantional inference; 
  - Restricted Boltzmann Machine example: see in P577; both p(v|h) and p(h|v) with individual conditionals modeled from sigmoid function; allows for efficient Gibbs sampling; 
