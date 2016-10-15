#Model for Heterogeneous Topic web (MHT)
This is a C++ implementation of `MHT` (Model for Heterogeneous
Topic web).   
More details about MHT are in my paper[[pdf]](https://arxiv.org/pdf/1610.00219.pdf): 

Junxian He, Ying Huang, Changfeng Liu, Jiaming Shen, Yuting Jia, Xinbing Wang, "Text Network Exploration via Heterogeneous Web of Topics", accepted into ICDM 2016 Workshop on Data Mining in Networks  

Contact: junxianh2@gmail.com

*********

#Data Format
    abstract_ID.txt

    The first line contains the number of documents.
    From the second line to the last, each line represents a document, i.e., line i+1 represents document vi. The format for each line is:
    [Word ID] [Word Count] [Word ID] [Word Count] .....repeatedly

     abstract.txt

     line i represents the abstract of a document vi.

     reference.txt

     line i represents the reference list (document ID) of
     document vi

     title.txt

     line i represents the title of document vi

     wordmap.dat

     It contains the mapping relationship from vocabulary to 
     WordID. Each line expresses a word, the format is: 
     [Word] [ID]
     
#Compiling

Type "make" in a shell.


#Model Learning

Estimate the model by executing:
```Bash
main [dataset] [WordTopic num] [DocTopic num] [convergence]
```  
     dataset: AAN or CiteseerX  
     WordTopic num: number of WordTopics  
     DocTopic num: number of DocTopics  
     convergence: the convergence of inner variational iteration  
     loop  

The code would produce an output folder in its parent directory
and save models in four files in that directory:

     final.other contains alpha.

     final.beta contains the WordTopic distributions.
     (Each line is a WordTopic; in line k, each entry is p(w | z=k)

     final.omega contains the DocTopic distributions.
     (Each line is a DocTopic; in line k', each entry is p(y | z'=k')

     final.eta contains the transition DocTopic distributions.
     (Each line is a WordTopic; in line k, each entry is p(z' | z=k)
  