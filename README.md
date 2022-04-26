# Research-Leadership-Recommendation

Collaborator recommendation is of great significance for facilitating research collaboration. Proximities have been demonstrated to be significant factors and determinants of research collaboration. Research leadership is associated with not only the capability to integrate resources to launch and sustain the research project but also the production and academic impact of the collaboration team. However, existing studies mainly focus on social or cognitive proximity, failing to integrate critical proximities comprehensively. Besides, existing studies focus on recommending relationships among all the coauthors, ignoring leadership in research collaboration. In this paper, we propose a proximity-aware research leadership recommendation (PRLR) model to systematically integrate critical node attribute information (critical proximities) and network features to conduct research leadership recommendation by predicting the directed links in the research leadership network. PRLR integrates cognitive, geographical, and institutional proximity as node attribute information and constructs a leadership-aware coauthorship network (LCN) to preserve the research leadership information. PRLR learns the node attribute information, the local network features, and the global network features with an autoencoder model, a joint probability constraint, and an attribute-aware skip-gram model, respectively. Extensive experiments and ablation studies have been conducted, demonstrating that PRLR significantly outperforms the state-of-the-art collaborator recommendation models in research leadership recommendation. 


![image](https://user-images.githubusercontent.com/20887860/165262322-413f7b89-1274-4121-a7c5-6b888d66f49c.png)
                                                     The overall framework of the proposed PRLR model.
                                                     
                                                     
Algorithm 1 Pseudo-code of the PRLR model
Input: Graph G=(V,E,X), embedding size d, window size w, walks per node r, walk length l, and other hyper-parameters α,β,γ

Output: Node representation H∈R^(|V|×d)
Perform r times of random walks with length l for each node to construct node context corpus C
Random initialization for all parameters
While not converged, do
        Sample a mini-batch of nodes with their context
        Calculate the gradient of ∇( αL_f+βL_ae) based on Equation (5) and Equation (9)
        Update autoencoder model parameters
        Calculate the gradient of ∇L_h based on Equation (10)
        Update skip-gram model parameters
End while
Return representations h=h^K based on Equation (6)

