---
title: chaindoc
---
<SwmSnippet path="Classifier_chain" line="1">

---

&nbsp;

```
from langchain import PromptTemplate
from langchain_core.output_parsers import StrOutputParser
from langchain_openai import ChatOpenAI

classifier_template=PromptTemplate(
    input_variables=["question","answer"],
    template="""You are given a question and the user responmds to the question.Classify it as either 'correct' or 'incorrect'.
    Do not respond more than one word.
    Question-{question}
    User's_answer-{answer}
    Clarification:"""
)
llm=ChatOpenAI()
output_parser=StrOutputParser()
classifier_chain=classifier_template | llm | output_parser
classifier_chain.invoke({"question":"what are penguins" , "answer":"penguins are mammals"})

```

---

</SwmSnippet>

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBTGFuZ2NoYWluJTNBJTNBR293dGhhbWthcjEyMw==" repo-name="Langchain"><sup>Powered by [Swimm](https://app.swimm.io/)</sup></SwmMeta>
