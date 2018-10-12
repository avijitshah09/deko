Default Knowledge about Objects
===============================
Obtaining and representing common-sense knowledge, useful in a robotics scenario for planning and making inference about the robots’ surroundings, is a challenging problem because such knowledge is typically found in unstructured repositories such as text corpora or small handmade resources. This work presents a methodology for automatically creating a default knowledge base about real-world objects for the robotics domain. The proposed method relies on clustering frame instances extracted from natural language text as a way of distilling default knowledge. We collect and parse a natural language corpus using the Web as a source, then perform an agglomerative clustering of frame instances according to an appropriately defined similarity measure, and finally extract prototypical frame instances from each cluster and publish them in LOD-complaint format to promote reuse and interoperability.

In summary, DeKO is a repository of default knowledge about common object. DeKO is built by parsing natural language text with [KNEWS](), extracting instances of frames from the text, clustering the frames and extract knowledge.

Publication: http://ceur-ws.org/Vol-1935/paper-01.pdf
Data: https://project.inria.fr/aloof/data/

Frame clustering
----------------

Clustering is based on some kind of distance (or conversely, similarity) measure.
For DeKO, we defined a similarity measure between frame isntances. It is implemented in the script framesimilarity.py.

Instructions:
1. script: Code works for any of the following scripts, given as partially or fully.
'src.py -a <alpha value> -t <Frame_similarity_Algo> -e <element_similarity_Algo> -r <true,false> <inputfile1> <inputfile2>'

'src.py --alpha <alpha value> --F_Sim_Algo <Frame_sim_Algo> --E_sim_Algo <element_similarity_Algo> --role <true,false> <inputfile1> <inputfile2>'

Parameters values:
1. -a or --alpha :
default : 0.5

2. -t or --F_Sim_Algo :
default : WUP

3. -e or --E_sim_Algo :
default : WUP

4. -r or --role :
default : false

The input files are two text files containing RDF triples, defining one frame instance each.

*Test input files are run from the folder named "frame_files"
*Any similarity calculating algorithm can be implemented instead of WUP for either between frame_types or frame_elements. Just add the module and call that similarity. Comments are mentioned in the code at place where new algo can be called.
*Necessary comments are mentioned in the code.
*For analysing results at each level of calculation, uncomment the print statements and run.
*Data structures like list, dictionary and tuples are used so that the code can be easily used for multiple frames if require at some point.
