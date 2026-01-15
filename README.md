
<img width="512" height="512" alt="AI Coding Project Logo" src="https://github.com/user-attachments/assets/b8b4a568-5758-46dd-ace3-1993cc66ce54" />

# AI Agent Coding Project

This code is a Node.js command-line AI agent application written in TypeScript which is redundantly redundant.

What is an agent?
An agent is an LLM (hence the AI moniker) with access to tools, giving it the ability to modify something outside of its application scope or context window. For example in this project, Claude can read the files of the project and make inferences about what type of project it is, what language(s) it is written in, write a summary of what it does and other statistics. If you have ever written a parser before you will understand that this is huge. And dangerous. 

```
`Why is an agent?`
-- Drax the Destroyer
```

Why is it dangerous? In 400 lines of code we have opened a gateway to primitive machine intelligence. The power that we can wield in a such a few lines of code is scary. Most of us are benevolent. What about the evil people out there?

Philosophical musings aside, let's describe the simple flow of this application.

First, it creates an Anthropic client service using Google Cloud vertex.
Then, we provide a chat experience via the console. LLM services are stateless, so we create a record of the conversation. This is why LLM services get expensive because we keep sending it back the copy of the conversation to maintain context so the algorithms can run appropriately.

Then we loop, get input, send this input plus past inputs to the LLM, get a response and repeat. Did I mention this all happens with 400 lines of code? Huge!

Here are the key resources:

YouTube: https://www.youtube.com/watch?v=rEf2-VC2jEIpn

Article: https://kevinyank.com/posts/how-to-build-an-agent-in-javascript/

Foundational article: https://ampcode.com/how-to-build-an-agent
(People say probably best blog of 2025. I agree.)

Anthropic: https://www.anthropic.com/

## How to run

You will need to have [Google Cloud Platform CLI](https://cloud.google.com/sdk/docs/install) installed on your computer, after which you will need to create local authentication credentials for your application to run:

```
gcloud auth application-default login
```

You will then need to assign these credentials to a GCP project you have created for your work:

```
gcloud auth application-default set-quota-project <GCP project ID>
```

See [How Application default Credentials works](https://cloud.google.com/docs/authentication/application-default-credentials#personal).

You will then need to edit the src/agent.ts file to specify the same project ID and the correct GCP region.

You can get your project's default region in Cloud Shell by running this:

```
gcloud config get compute/region
```
or if you want a list to determine the best region to run (closest to you):

```
gcloud compute regions list
```

Once that's all done, assuming you have Node.js 25 (this is specified as a local environment with devbox.json if you happen to be using devbox), you can install project dependencies with PNPM:

```
pnpm i
```

Finally, run the agent CLI with `pnpm agent`.
