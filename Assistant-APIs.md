### Assistant API Introduction
Assistant APIs are not GPTs. 

More capabilities for developpers with Assistant APIs.

They are AI Agents. 

They can use tools and so on.

#### How to build an Assistant?
Let'zs say I wzant to build an GPT that can help me write or correct a text.
How to do that ?

I use the Assistant API with python.

Let's start doing it

why using a special GPT for that ?
I could just use ChatGPT, right!
The answer is reusability. I don't want to prompt everytime I need to correct my text.

Let's start doing it.

We will start by understanding what OpenAI Assistant API offer.

**Assistant API** : give it a name and instruction. You can let it use tools like code interpreter, Retrieval, and Function Calling.
- Code interepreter is a packeged tool that help you use python libraries to deliver compute and graphics.
- Retrieval is a packaged tool that helps you query your data to augment your GPT's response.
- Function Calling is a way of giving you the poissibility to create custom tool and have them being called as needed. 

**Thread**, it is a flow of conversation. It is created when  a user start a conversation.
You add a message to a thread.

**Run** the assistant to the Thread to trigger response.
```python
assistant = client.beta.assistants.create(
    name="Math Tutor",
    instructions="You are a personal math tutor. Write and run code to answer math questions.",
    tools=[{"type": "code_interpreter"}],
    model="gpt-4-1106-preview"
)


client.beta.assistants.create(
    *,
    model: 'str',
    description: 'Optional[str] | NotGiven' = NOT_GIVEN,
    file_ids: 'List[str] | NotGiven' = NOT_GIVEN,
    instructions: 'Optional[str] | NotGiven' = NOT_GIVEN,
    metadata: 'Optional[object] | NotGiven' = NOT_GIVEN,
    name: 'Optional[str] | NotGiven' = NOT_GIVEN,
    tools: 'List[assistant_create_params.Tool] | NotGiven' = NOT_GIVEN,
    extra_headers: 'Headers | None' = None,
    extra_query: 'Query | None' = None,
    extra_body: 'Body | None' = None,
    timeout: 'float | httpx.Timeout | None | NotGiven' = NOT_GIVEN,
) -> 'Assistant'

```

An Assistant has a name, intructions, tools, models and some more parameters


- model: ID of the model to use. You can use the
- description: The description of the assistant. The maximum length is 512 characters.

- file_ids: A list of [file](https://platform.openai.com/docs/api-reference/files) IDs
      
- instructions: The system instructions that the assistant uses. The maximum length is ``32768`` characters.

- metadata: Set of `16 key-value pairs that can be attached to an object`. This can be useful for storing additional information about the object in a structured format. Keys can be a maximum of 64 characters long and values can be a maxium of 512 characters long.

- name: The name of the assistant. The maximum length is 256 characters.

- tools: A list of tool enabled on the assistant. There can be a maximum of 128 tools per assistant. Tools can be of types `code_interpreter`, `retrieval`, or `function`.

- extra_headers: Send extra headers

- extra_query: Add additional query parameters to the request

- extra_body: Add additional JSON properties to the request

- timeout: Override the client-level default timeout for this request, in seconds
