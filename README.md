# langchain-pandas-agent-example


LangChain is a library that utilizes natural language processing and machine learning algorithms to create agents to answer questions from CSV data. It provides a unified interface to create agents based on different language models such as OpenAI.

## Requirements

- You must have [Pandas](https://pypi.org/project/pandas/) installed. 
- You must have an [OpenAI API Key](https://beta.openai.com/).

## Installation

Install LangChain using `pip`

```
$ pip install langchain
```

## Usage

To start using LangChain, import the necessary libraries.

```python
import os
import pandas as pd 
from langchain.agents import create_pandas_dataframe_agent 
from langchain.llms import OpenAI
```
  
Next, we will be reading in data from a CSV file to create a DataFrame.
```python
df = pd.read_csv("/content/package-manifest.csv")
```

Now we will use the LangChain library to create a DataFrame agent which can answer natural language questions based off of the CSV data. 

```python
agent = create_pandas_dataframe_agent(OpenAI(temperature=0), df, verbose=True)
```

Finally, you can ask questions to the agent. 

```python
agent.run("what are the best packages for data visualization?")
```

You should see the agent's response printed in the terminal.

## Documentation

For more detailed documentation on the LangChain library, visit the [LangChain Documentation](https://langchain.readthedocs.io/en/latest/).
