Topology and weight adapting neural network. 
## Researchers
[[Kenneth Stanley]]
## Publications
[[Neuroevolution of Augmenting Topologies]]
## Key Points (my notes)
#### Network Encoding
#### Network Evolution Algorithm
#### Input / Output and Feedback Scheme

### Network Encoding
- I need a network encoding scheme that is simple to understand and perhaps nonlinear - it would be best if the network description was not one:one genotype phenotype so that encoding compresses, modularizes and creates a robustness to the network
- To expand on this more, refer to Herb Simon's Watchmaker parable:
	- "There once were two watchmakers, named Hora and Tempus, who made very fine watches. The phones in their workshops rang frequently and new customers were constantly calling them. However, Hora prospered while Tempus became poorer and poorer. In the end, Tempus lost his shop. What was the reason behind this? The watches consisted of about 1000 parts each. The watches that Tempus made were designed such that, when he had to put down a partly assembled watch, it immediately fell into pieces and had to be reassembled from the basic elements. Hora had designed his watches so that he could put together sub-assemblies of about ten components each, and each sub-assembly could be put down without falling apart. Ten of these sub-assemblies could be put together to make a larger sub-assembly, and ten of the larger sub-assemblies constituted the whole watch." - Herbert Simon
- I think there is a modularity component to neural networks that is worth exploring and the phenotype encoding will have to be conducive to not only allowing those patterns to emerge and represent them, but also to help create some robustness to the network. DNA is able to encode a ton of data and a lot of it is redundant - I don't think these two components are unrelated.
- The encoding must be expandable in a way that complexifies the network while also not influencing the entire thing 
- How to explore encoding schemes? - Need to study 
- Multiple levels of encoding? - DNA encodes some level of information about neurons design, yet how neurons self-organize is prsumably a mechanism they express
### Network Evolution Algorithm
- I believe the encoding issue is half the problem. If it can be "cracked" the evolution algorithm will be simple mutations on it. The mutations should be powerful and lead to reorganization of the network. We will need to balance the normal issues of powerful changes that won't result in a worthless model.
### Input / Output Feeback
- The whole system is a complex one. The ground truth will need to be some set of variables recieved by sensors and actuators, but after that its a free-for all. 