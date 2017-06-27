# Information Extraction

### Dependency Parsing

Understanding of Natural Language involves extraction of knowledge. The extraction of information from language can be done in many ways. Deep parsing is one such method which gives intra-sentence dependencies based on the model. Using Stanford parser, sentence level deep parsing is done in `ie_module` which can be used as follows. For more information and explanation about the code, refer [this article](put link).

```python
from ie_module.SentenceProcessor import SentenceProcessor

s = SentenceProcessor('John is a computer scientist',1)
print s.get_parsed_graph()
s.save_dot_graph(s)
```

Gives the follwing output.

```dot
digraph G{
edge [dir=forward]
node [shape=plaintext]

0 [label="0 (None)"]
0 -> 5 [label="root"]
1 [label="1 (John)"]
2 [label="2 (is)"]
3 [label="3 (a)"]
4 [label="4 (computer)"]
5 [label="5 (scientist)"]
5 -> 2 [label="cop"]
5 -> 4 [label="compound"]
5 -> 3 [label="det"]
5 -> 1 [label="nsubj"]
}
```

Also saves the graph image in the specified directory.

![Dot Graph]( Put Link )

### Ngrams Finder

In a sentence 