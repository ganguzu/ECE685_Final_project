# ECE685_Final_project

## Abstractive Text Summarization Using TransformersTeam members: Godwin Anguzu, Haoliang Jiang

### The readme file adds comments to our code. Please refer to the notebook for the corresponding section names
### Preprocessing
In the preprocessing section, we added spaces to the left and right of each word first.  
Then we removed the special characters in the abstract as our first data cleaning step.  

### Tokenizing the text into integer tokens
In the next cells, we tokenized the input sequences by encoding them into integers, which can make sure that the inputs can be passed into the multi-head attention model later.  

### Obtaining insights on lengths for defining maxlen
This section is just to check the maximum lengths of the input sequences such that in the next section we can pad the sequences to make them in equal length. 

### Padding/Truncating sequences for identical sequence length
We used kera's preprocessing module to pad or truncate the input and target sequences and make the matrices into equal lengths and sizes.  
This is a necessary pre-processing step to do.  

### Creating dataset pipeline
This step is to first cast the tokenized vectors into integers and then are turned into compatible tensorflow datasets.  

### Positional encoding for adding notion of position among words as unlike RNN this is non-directional
Positional encoding can add the position information of an entity in a sequence to the dataset such that each position in a sequence is assigned a unique representation. We normalize the position value by encoding it with trignometry function such that the value lie between 0 and 1. Normalizing is important because otherwise in the modeling stage we will encounter issues. The `get_positional_angle` and the `positional_encoding` functions implement the above encoding. Next, `create_padding_mask` and `create_look_ahead_mask` are implemented to maske "pad" sequences and to maske future words from contributing in prediction of current words in self attention.  

### Building the model
