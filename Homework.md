# aie5_hw5
# Questions and Answers

1. How does the model determine which tool to use?

   The tool_belt definition helps to define the toolset the model needs to use and we bind the model and the toolset using Langchain

2. Is there any specific limit to how many times we can cycle? If not, how could we impose a limit to the number of cycles?

   The specific limit on how many times we can cycle through really depends on the code that we are writing. So theoritically we can cycle indefinitely but at what cost and what is the goal
   that we are tying to achieve. Lets consider what happens if we dont limit before we get to how we can impose a limit on the number of cycles:
   * If there are no limits then the agent is constantly running in the background consuming resources
   * Its important to determine finite goals for an agent while we design one and then helps with debugging and observability
   * We should consider unintended consequences based on the actions these agents are tasked with
  
   How could we impose a limit?
   
   All of the ways to limit cycles are different kinds of logic that is embedded in the code for agents
   * Counter for a set number of cycles and then move to a pause or end state
   * Logic that checks for the desired outcome of the action and then terminates
   * Time based, perform or take action during a specific time or monitor for a specific period of time
