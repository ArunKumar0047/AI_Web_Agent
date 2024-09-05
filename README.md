# AI_Web_Agent
### Agent that can interact with Google Forms from user's input
The core idea of this project is to develop an AI agent that can take the various input details from the user and then proceed to the given google forms link and then fill out the details by itself

## Table of contents:
- Features
- How does it work?
- How to run?

### Features
- Framework: Langgraph
- Agent : OpenAI tools agent (Langchain)
- Tools : Custom tools
- Web Driver : Selenium
- Model: OpenAI (integrated within Langchain)

### How does it work?
1. There are four tools defined. They are :
     - `load_page` : opens the browser given the link
     - `fill_text_input` : fills the text field with the values from the agent.
     - `select_radio_or_checkbox` : used to check boxes
     - `submit_form` : used to submit the form once filled

2. The agent's prompt is made in such a way that the details that needs to be filled in the form are extracted from the user's text input along with the link to the form.
4. So after parsing the values from the input, the agent uses the `load_page` to start the webpage initially.
5. Relative xpath is used to find the location of the specific input elements. The prompt is pre-defined as to the input fields in the form. This is done to ease the finding of the location of the elements in the forms page.
6. Once the labels are found, the necessary inputs or checks that need to be done in that label are implemented by the agent.
7. The agent's output and the output from the tools are loogged and can also be found in the intermediate_steps of the agent
8. After filling out, the agent calls the submit tool to submit the form.

### How to run?
- `pip install -r requirements.txt` : install all the necessary libraries required to run the agent
- `web_agent` : notebook that contains the agent and the necessary tools
