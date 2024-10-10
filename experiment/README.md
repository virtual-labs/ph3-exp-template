## README
Welcome to the experiment development process for developers involved in the Virtual Labs project. This guide will help you create an experiment designed to explain the lab topic. 

# Steps to Create an Experiment:
## Verify and Understand the Experiment Repositories:
Begin by thoroughly reviewing and understanding the structure and purpose of the experiment repositories. For more details visit [here](https://vlead.vlabs.ac.in/development/#development-process)

## Repository Creation:
The VLEAD team will create a GitHub repository for each experiment. The write access to these reopsitories is a must to be able to create, edit or modify the experiment. You can refer to this [example repository](https://github.com/virtual-labs-cms/exp-template) to get familiar with the structure and format.

## Branch Structure:
Each repository will contain four branches:
* **dev** (development)
* **testing** (end-to-end testing)
* **gh-pages** (for GitHub Pages hosting)
* **main** (production-ready)
Developers are expected to work only in the dev branch. After performing unit testing within the dev branch, the code can be moved to the testing branch for comprehensive end-to-end testing.

## Tags:
To ensure proper structure and organization of the experiment, it is essential to assign relevant tags. These tags help categorize the experiment for better accessibility and searchability.

When adding tags, please adhere to the following guidelines:
* Ensure that the tags are strictly relevant to the content of the experiment.
* A minimum of five tags must be assigned to each experiment.
* Tags should be comma-separated.
* Each tag can consist of multiple words separated by spaces, or hyphenated words (e.g., “data-analysis”). The use of any other special characters is not allowed.
* Do not include the experiment name, lab name, institute name, or discipline name as tags.

## Pages Distribution for Experiment Development
Each experiment's content will be distributed across the following pages:

### aim.md
This file outlines the broad, general, and long-term intentions for developing the experiment. There can be multiple objectives for teaching an experiment in an online format. Clearly state these intentions to provide a solid understanding of the experiment’s goals.

### experiment-name.md
The name of the experiment will serve as the title for each page. Ensure the title is precise, simple, and easily understandable for students. A well-chosen name helps learners quickly grasp the focus of the experiment.

### pretest.json and posttest.json
These files are used to assess learners' understanding via multiple-choice, single-answer quizzes:

* **Pretest:** To assess prerequisite knowledge before beginning the experiment.
* **Posttest:** To evaluate the understanding gained after completing the experiment.
* **Learning Unit Quizzes:** To test knowledge specific to each section of the content.
Refer to this [Example](https://eerc01-iiith.vlabs.ac.in/exp/compression-test-experiment/) for the correct format of pretest and posttest pages.

The quiz is structured in a JSON file format. The quiz questions must be represented as an array of objects. Each object corresponds to a question. The quiz consists of multiple questions, each defined as an object with the following attributes:
* **question:** The text of the question to be presented to the user.
* **answers:** A set of key-value pairs representing the answer options. The keys (e.g., a, b, c, d) represent the option labels, and the values are the actual answer choices.
* **correctAnswer:** The correct answer, indicated by the corresponding option label (a, b, c, or d).
  
Example:

  ```
  "questions" : [
      {
          "question" : "What is 1+2 ?",
          "answers" : 
          {
              "a" : 1,
              "b" : 2,
              "c" : 3,
              "d" : 4
          },
          "correctAnswer" : c
      }
  ]
  ```
For more details, please click [here](https://github.com/virtual-labs/ph3-lab-mgmt/blob/dev/docs/quiz.md)
Please consider running your JSON files through a JSON validator like https://jsonlint.com/ for smoother debugging. 

### simulation folder
The simulation folder contains the essential files needed to power the experiment's interactive simulation. This is where you upload all the necessary files for the simulation to function correctly.

Please follow these guidelines:

**File Structure:** Organize your files into appropriate subfolders such as:
* css – for stylesheets
* js – for JavaScript files
* images – for images used in the simulation

Ensure that all the file types correspond to the implementation needs of the simulation.

**index.html Requirement:**
For the simulation page to work, the main HTML file must be named index.html. No other names are permitted for the main HTML file for simulation.

### procedure.md
This file outlines the step-by-step instructions for completing the experiment. You may include graphs, tables, images, and other visual aids to enhance clarity. Refer to this [example](https://virtual-labs.github.io/exp-adder-circuit-iiith/procedure.html) for guidance on formatting and structuring the procedure section.

### reference.md
This section lists all sources and references used in the development of the experiment. Properly citing sources provides students with a better understanding of the topic and encourages further reading. 

### Theory.md
 This file should contain the theoretical principles or statements that explain the facts or phenomena behind the experiment. Use graphs, tables, images, and other illustrative tools where necessary. You may also incorporate LaTeX for mathematical or scientific notations, as demonstrated in this [example](https://virtual-labs.github.io/exp-adder-circuit-iiith/procedure.html).

### Do’s and Don’ts:
**Do’s:**
* Always use the dev branch for development and merge changes into the testing branch after testing. The main branch should only contain thoroughly tested code.
* Follow best practices in the development process, as outlined in [the Virtual Labs Development Guide](https://vlead.vlabs.ac.in/development/#basic-requirements-for-the-experiments12).
* For the simulation page to work, the main HTML file must be named index.html

**Don’ts:**
* Avoid adding unnecessary files to the repository.
* Never delete the gh-pages branch, as it is critical for the automatic deployment of the experiment and its user interface to GitHub Pages for testing purposes.
* Do not include the experiment name, lab name, institute name, or discipline name as tags.

For more information on the development process, refer to 
* [Virtual Labs Development Process](https://vlead.vlabs.ac.in/development/#development-process)
* [Virtual Labs Onboarding Process](https://vlead.vlabs.ac.in/development/#basic-requirements-for-the-experiments12)
* [Virtual Labs Content Development Platform](https://vlead.vlabs.ac.in/development/#getting-started)
* [Create experiment at one glance](https://virtual-labs-cms.netlify.app/)