# Social Interaction Commonsense Knowledge-based Visual Storytelling

This repository contains code for paper [SCO-VIST: Social Interaction Commonsense Knowledge-based Visual Storytelling](https://arxiv.org/abs/2402.00319).

### <div align="center"> Wang, E.\*, Han, C.\*, & Poon, J. (2024). <br> [SCO-VIST: Social Interaction Commonsense Knowledge-based Visual Storytelling](https://arxiv.org/abs/2402.00319) <br> EACL 2024 </div>

## 1. Introduction
Visual storytelling aims to automatically generate a coherent story based on a given image sequence. Unlike tasks like image captioning, visual stories should contain factual descriptions, worldviews, and human social commonsense to put disjointed elements together to form a coherent and engaging human-writeable story. However, most models mainly focus on applying factual information and using taxonomic/lexical external knowledge when attempting to create stories. This paper introduces SCO-VIST, a framework representing the image sequence as a graph with objects and relations that includes human action motivation and its social interaction commonsense knowledge. SCO-VIST then takes this graph representing plot points and creates bridges between plot points with semantic and occurrence-based edge weights. This weighted story graph produces the storyline in a sequence of events using Floyd-Warshall's algorithm. Our proposed framework produces stories superior across multiple metrics in terms of visual grounding, coherence, diversity, and humanness, per both automatic and human evaluations.

## 2. Training 
Please find the related training data in the google drive [here] (https://drive.google.com/drive/folders/19qc_io5BlFJnCaP63jUPtVW7m_s_DcYK?usp=sharing).
* **CLIP_story_graph.json:** contains the story graphs. 
* **CLIP_node_embs.dat:** stores the textual embeddings of the story graph nodes. Shape is (number of stories, 73, 768), where 73 is the maximum number of nodes a story graph can have and 768 is the embedding dimension
* **CLIP_node_inds.json:** stores story id as the key with matching index position to locate the corresponding node embeddings from CLIP_node_embs.dat
* **CLIP_srl_pmi.json**: contains story id as the key with the decoded optimal storyline.

You can run the Srl2Story.ipynb notebook for model training. Change the **storyinfo_path** and **srl_path** to the location of the VIST Gold Stories and **CLIP_srl_pmi.json** respectively. 
  
## 3. Reference
If you use this code for your research, please cite:
```
@inproceedings{wang2024sco,
  title={SCO-VIST: Social Interaction Commonsense Knowledge-based Visual Storytelling},
  author={Wang, Eileen and Han, Caren and Poon, Josiah},
  booktitle={Proceedings of the 18th Conference of the European Chapter of the Association for Computational Linguistics (Volume 1: Long Papers)},
  pages={1602--1616},
  year={2024}
}
```
