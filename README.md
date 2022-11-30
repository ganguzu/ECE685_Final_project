# ECE685_Final_project

## Abstractive Text Summarization Using TransformersTeam members: 

## Godwin Anguzu, Haoliang Jiang

### Preprocessing
In the preprocessing section, we added spaces to the left and right of each word first.  
Then we removed the special characters in the abstract as our first data cleaning step.  

### Tokenizing the text into integer tokens
In the next cells, we tokenized the input sequences by encoding them into integers, which can make sure that the inputs can be passed into the multi-head attention model later.  

### Obtaining insights on lengths for defining maxlen
This section is just to check the maximum lengths of the input sequences such that in the next section we can pad the sequences to make them in equal length. 
