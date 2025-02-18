202502071039
Status: #paper
Tags:

# TARGETED MOLECULAR GENERATION WITH LATENT REINFORCEMENT LEARNIN

# Motivation
1. We have a "hit" molecule with some undesired properties. This needs experimentation and knowledge base of chemical reaction, to remove the undesired property. Generative models can create molecules by searching the latent space with desired property.
2. So, input is a "hit" molecule, the generative process will remove the undesired properties and modifies the final molecule
	1. Modification could include removing ~~edges~~, atoms, bonds between atoms in the molecule
3. So, like [[Diffusion]]. Is this similar to [[Explore Exploit]]?
	1. Yes, previous methods use [[Reinforcement Learning]]
4. SMILES representation of molecules - ascii format
5. No chemical validity after modification in latent space
6. Uses [[Proximal Policy Optimization (PPO)]] for [[Trust Region Policy Optimization (TRPO)]] that may be useful for chemical properties
7. There is latent space, p(x) that can be used to generate molecules. This paper uses RL to to sample better molecules using PPO
	1. What is the reward function?
------

# Research question and objective
1. 

--------
# Strengths
1. 

# Weaknesses
1. 
---------

# Possible gaps and/or inconsistencies
1. 

--------

# Future work
1. 

------
# Short discussion
1. 

-----

# Relevance to your work
1. 

-------
# References

1. https://chemrxiv.org/engage/api-gateway/chemrxiv/assets/orp/resource/item/676d908e6dde43c9086c370b/original/targeted-molecular-generation-with-latent-reinforcement-learning.pdf