# Основные положения:
1. Лучше писать все запросы на английском языке

2. Четко ставить задачу, которую должна выполнить модель (сгенерировать код/дебаг/оптимизация кода)

3. Четко описывать требования: фреймворк/диалект/другие специфические требования для вашего проекта
- ❌ "Write a function to sort a list."
- ✅ "Write a Python function to sort a list of integers in descending order using merge sort."

4. Предоставляйте в промпте максимум полезного контекста об описываемой задаче
- ❌ "How do I fetch API data?"
- ✅ "Show me how to fetch JSON data from a REST API in JavaScript using async/await, with error handling."

5. Не стоит задавать модели комплексные задачи. Если задача включает несколько разделов, разделите её на пункты и задавайте модели эти подзадачи. В идеале каждый запрос должен отвечать одной функции/классу/структуре.

6. При обращении просите модель писать комментарии к коду, уточняйте безопасность кода, возможные альтернативы к основному варианту, обоснование, почему был выбран именно этот вариант.

7. При устранении ошибок отправлять не только саму ошибку и код, но и предполагаемый результат, который этот код должен был выдать

8. При использовании агента старайтесь разбить конечную задачу на маленькие подзадачи, максимально строго опишите ограничения (время работы на конкретном железе/ограничения по памяти/безопасности и т.д.)

## Полезные шаблоны промптов для общих задач
- Рефакторинг с применением принципа 'чистого кода'
> Please refactor this code to follow Clean Code principles while preserving its original functionality. Use descriptive names, break large functions into smaller ones, maintain logical order for readability, ensure each function has a single responsibility, avoid unnecessary comments, and limit variable scope.
- Применение принципов SOLID к коду (с объяснениями)
> Analyze the code below and apply SOLID principles to improve its structure. Make only necessary changes to improve the structure and maintainability of the code without adding complexity. Explain your changes and how they relate to specific SOLID principles.
- Оптимизация производительности кода
> Analyze this code for performance issues. Suggest ways to improve efficiency, focusing on time complexity, space complexity, and resource usage. Provide a brief explanation for each suggestion.
- Разработка стратегии тестирования кода
> Please create a strategy for thoroughly testing this code. Include unit tests, integration tests, and any other appropriate methods. For each type of test, provide an example and explain its purpose.
- Реализация паттерна проектирования
> Please suggest design patterns that could improve the structure of this code. For each pattern, explain why it is a good fit and provide a brief example of its implementation.
- Генерация кода
> I need to implement [описание функционала] in [язык].
> #### Key requirements:
> 1. [требование 1]
> 2. [требование 2]
> 3. [требование 3]
> #### Please consider:
> - Error handling
> - Edge cases
> - Performance optimization
> - Best practices for [язык/фреймворк]
> 
> Please do not unnecessarily remove any comments or code.
>
> Generate the code with clear comments explaining the logic.
- Ревью
> Please review the following code:
> 
> [ваш код]
> 
> Consider:
> 1. Code quality and adherence to best practices
> 2. Potential bugs or edge cases
> 3. Performance optimizations
> 4. Readability and maintainability
> 5. Any security concerns
> Suggest improvements and explain your reasoning for each suggestion.
## Хорошая подборка промптов для помощи в написании кода
- [Documentation / Explanation](#documentation--explaination)
  - [📣 Adding Documentation](#-adding-documentation)
  - [📣 Write your terms and conditions](#-write-your-terms-and-conditions)
  - [📣 Produce cheat sheets](#-produce-cheat-sheets)
  - [📣 Generate Readme Files](#-generate-readme-files)
  - [📣 Write detailed blogs](#-write-detailed-blogs)
  - [📣 Explain Code](#-explain-code)
  - [📣 Architecture Diagram (Mermaid)](#-architecture-diagram-mermaid)
  - [📣 Entity Relationship Diagram (Mermaid)](#-entity-relationship-diagram-mermaid)
- [Code Refactoring](#code-refactoring)
  - [📣 Refactor Code](#-refactor-code)
  - [📣 Modernizing Old Code](#-modernizing-old-code)
  - [📣 Code in to Multiple Methods](#-code-in-to-multiple-methods)
  - [📣 Better Performance](#-better-performance)
  - [📣 Adding a Parameter to a Function](#-adding-a-parameter-to-a-function)
  - [📣 Adding Coding Best Practices or Principles](#-adding-coding-best-practices-or-principles)
  - [📣 Follow coding style guidelines](#-follow-coding-style-guidelines)
  - [📣 Detecting and Fixing Errors](#-detecting-and-fixing-errors)
  - [📣 Debug a React component](#-debug-a-react-component)
  - [📣 Create Unit Tests](#-create-unit-tests)
  - [📣 Transpiling Code](#-transpiling-code)
  - [📣 Responsive Design](#-responsive-design)
  - [📣 Internationalization](#-internationalization)
  - [📣 Add comments to code](#-add-comments-to-code)
- [Code Generation](#code-generation)
  - [📣 Create Functions](#-create-functions)
  - [📣 Generate a Dockerfile](#-generate-a-dockerfile)
  - [📣 Write a RegEx](#-write-a-regex)
  - [📣 Create a Class](#-create-a-class)
  - [📣 Add Functionality](#-add-functionality)
  - [📣 Create Boilerplate Code](#-create-boilerplate-code)
  - [📣 You are a world-class software engineer](#-you-are-a-world-class-software-engineer)
- [Code Review](#code-review)
  - [📣 Error Handling](#-error-handling)
  - [📣 Suggest Improvements](#-suggest-improvements)
- [Product Service Promotion](#product-service-promotion)
  - [📣 Generate innovative product ideas](#-generate-innovative-product-ideas)
  - [📣 Develop a unique value proposition](#-develop-a-unique-value-proposition)
  - [📣 Master the art of storytelling for marketing](#-master-the-art-of-storytelling-for-marketing)
  - [📣 Create a successful referral program](#-create-a-successful-referral-program)
  - [📣 Master the art of upselling and cross-selling](#-master-the-art-of-upselling-and-cross-selling)
  - [📣 Create a viral marketing campaign](#-create-a-viral-marketing-campaign)
  - [📣 Develop a powerful elevator pitch](#-develop-a-powerful-elevator-pitch)
  - [📣 Create an actionable marketing plan](#-create-an-actionable-marketing-plan)
  - [📣 Leverage content marketing for lead generation](#-leverage-content-marketing-for-lead-generation)
## Documentation / Explaination

### 📣 Adding Documentation

> [!NOTE]
> Adding documentation requires creating clear and comprehensive explanations of a module’s purpose, design, and implementation.

Prompt 1#:

```
I don't know how to code, but I want to understand how this works. Explain the following code to me in a way that a non-technical person can understand. Always use Markdown with nice formatting to make it easier to follow. Organize it by sections with headers. Include references to the code as markdown code blocks in each section. The code:

[insert code here]
```

Prompt 2#:

```
Please add comprehensive documentation for [file or module name], including clear and concise explanations of its purpose, design, and implementation. Consider including examples of how to use the module, as well as any relevant diagrams or flow charts to help illustrate its workings. Ensure that the documentation is easily accessible to other developers and is updated as the module evolves. Consider using documentation tools such as inline comments, markdown files, or a documentation generator to simplify the process.

[insert code here]
```

<sup>[⬆️ Back to table of contents](#table-of-contents)</sup>

### 📣 Write your terms and conditions

**Prompt:**

```
Create terms and services for my website about an [AI tool] called [name].
```

<sup>[⬆️ Back to table of contents](#table-of-contents)</sup>

### 📣 Produce cheat sheets

**Prompt:**

```
Write a cheat sheet for [markdown formatting].
```

<sup>[⬆️ Back to table of contents](#table-of-contents)</sup>

### 📣 Generate Readme Files

**Prompt:**

```
Generate documentation for the code below. You should include detailed instructions to allow a developer to run it on a local machine, explain what the code does, and list vulnerabilities that exist in this code.

[enter code]
```

<sup>[⬆️ Back to table of contents](#table-of-contents)</sup>

### 📣 Write detailed blogs

**Prompt:**

```
Write a detailed blog on How to build a [COVID tracker] using React with proper structuring of code.
```

<sup>[⬆️ Back to table of contents](#table-of-contents)</sup>

### 📣 Explain Code

> [!NOTE]
> Don't spend time trying to figure out how code works, just ask ChatGPT to explain it to you

**Prompt:**

```
Context: I'm starting a new position as backend developer and I have to start to understand how some functions are working
Technologies: [INSERT YOUR TECHNOLOGIES HERE]
You have to: explain me the code line by line

[INSERT YOUR CODE HERE]
```

<sup>[⬆️ Back to table of contents](#table-of-contents)</sup>

### 📣 Architecture Diagram (Mermaid)

> [!NOTE]
> Create a diagram of your architecture using Mermaid

**Prompt:**

```
Write the Mermaid code for an architecture diagram for this solution [DESCRIBE SOLUTION]
```

Example:

```mermaid
  graph TD;
  A[Client] -->|HTTP Request| B(API Gateway);
  B -->|HTTP Request| C[Service 1];
  B -->|HTTP Request| D[Service 2];
  C -->|Database Query| E[Database];
  D -->|Database Query| E;
```

<sup>[⬆️ Back to table of contents](#table-of-contents)</sup>

### 📣 Entity Relationship Diagram (Mermaid)

> [!NOTE]
> Create an entity relationship diagram using Mermaid

**Prompt:**

```
Write the Mermaid code for an entity relationship diagram for these classes [INSERT CLASSES]
```

<sup>[⬆️ Back to table of contents](#table-of-contents)</sup>

## Code Refactoring

### 📣 Refactor Code

> [!NOTE]
> Ask to ChatGPT to refactor your code

**Prompt:**

```
I have a piece of code and I need you do a refactor of it:

[INSERT YOUR CODE HERE]
```

Refactoring code is an essential process in software development that aims to improve the quality, readability, and maintainability of existing code without altering its functionality. Refactoring can enhance code efficiency, reduce errors, and make it easier to modify or extend in the future. With ChatGPT’s help, you can effectively refactor your code and achieve a better code structure.

<sup>[⬆️ Back to table of contents](#table-of-contents)</sup>

### 📣 Modernizing Old Code

> [!NOTE]
> By providing your old function to GPT-4 and asking it to refactor it to modern coding practices, you can quickly modernize your code.

**Prompt:**

```
Refactor the following code to modern es6 programming standards:

[INSERT YOUR CODE HERE]
```

<sup>[⬆️ Back to table of contents](#table-of-contents)</sup>

### 📣 Code in to Multiple Methods

> [!NOTE]
>If you have a long function that is doing too much, you can ask GPT-4 to refactor it into multiple methods.

**Prompt:**

```
Refactor the following code into multiple methods to improve readability and maintainability:

[INSERT YOUR CODE HERE]
```

<sup>[⬆️ Back to table of contents](#table-of-contents)</sup>

### 📣 Better Performance

> [!NOTE]
> If you have a function that is taking too long to run, you can ask GPT-4 to refactor it to improve performance.

**Prompt:**

```
Refactor the following code to improve performance:

[INSERT YOUR CODE HERE]
```

<sup>[⬆️ Back to table of contents](#table-of-contents)</sup>

### 📣 Adding a Parameter to a Function

**Prompt:**

```
Add a parameter to this function to do [FUNCTIONALITY]

[INSERT YOUR CODE HERE]
```

<sup>[⬆️ Back to table of contents](#table-of-contents)</sup>

### 📣 Adding Coding Best Practices or Principles

> [!NOTE]
>Let ChatGPT rewrite the code for you according to style guidelines.

**Prompt:**

```
Rewrite the code below following the Google style guidelines for javascript.

[INSERT YOUR CODE HERE]
```

<sup>[⬆️ Back to table of contents](#table-of-contents)</sup>

### 📣 Follow coding style guidelines

> [!NOTE]
> If your organization or code base uses specific coding practices and styles that you want to maintain, you can provide instructions to GPT-4 on which particular coding practice or style you’d like it to focus on.

**Prompt:**

```
Review the following code and refactor it to make it more DRY and adopt the SOLID programming principles.

[INSERT YOUR CODE HERE]
```

<sup>[⬆️ Back to table of contents](#table-of-contents)</sup>

### 📣 Detecting and Fixing Errors

> [!NOTE]
>Sometimes we are unaware of the vulnerabilities or potential issues our code can create. Having GPT-4 review and address code issues can save you more than just time.

**Prompt 1#:**

```
Review this code for errors and refactor to fix any issues:

[INSERT YOUR CODE HERE]
```

**Prompt 2#:**

```
I'm developing software in [INSERT YOUR TECHNOLOGIES HERE] and I need you help me to find and
fix all the errors in my code, following the best practices. I'll provide you my code
and you'll give me the code with all the corrections explained line by line
```

**Prompt 3#:**

```
I wrote this code [CODE] I got this error [ERROR] How can I fix it? or What does this error mean?
```

<sup>[⬆️ Back to table of contents](#table-of-contents)</sup>

### 📣 Debug a React component

> [!NOTE]
>This process typically involves identifying the source of the error, understanding the issue, and implementing a solution to resolve the issue

**Prompt:**

```
Please find and fix the bug in the [component name] component that is causing [describe the issue].

[INSERT YOUR CODE HERE]
```

<sup>[⬆️ Back to table of contents](#table-of-contents)</sup>

### 📣 Create Unit Tests

> [!NOTE]
>Unit tests are automated tests that check the behavior of individual units of code in isolation. They help catch bugs early and make it easier to maintain the code.

**Prompt 1#:**

```
Please write unit tests for [file or module name] to ensure its proper functioning

[insert code here]
```

**Prompt 2#:**

```
Create 2 unit tests for the provided code. One for a successful condition and one for failure.
```

<sup>[⬆️ Back to table of contents](#table-of-contents)</sup>

### 📣 Transpiling Code

> [!NOTE]
>There are many reasons why you may need to convert code from one language to another. For example, you may have found a repository with code for one language that you need in another, you’re moving code bases, or maybe your boss read an article on the latest front-end framework and now you’re moving to a divisive new library.

**Prompt:**

```
Rewrite the following code in Rust:

[INSERT YOUR CODE HERE]
```

<sup>[⬆️ Back to table of contents](#table-of-contents)</sup>

### 📣 Responsive Design

> [!NOTE]
>Responsive design adapts a website to different screen sizes and devices, using flexible layouts, images, and CSS media queries. It aims to provide a good viewing experience for all users

**Prompt:**

```
RPlease implement responsive design for the [component name] component to ensure that it looks and functions correctly on different screen sizes and devices. Consider using [responsive design technique or library] to achieve this.

[insert code here]
```

<sup>[⬆️ Back to table of contents](#table-of-contents)</sup>

### 📣 Internationalization

> [!NOTE]
>Internationalization, also known as i18n, is the process of designing a software application to be able to support multiple languages and regional differences

**Prompt:**

```
Please implement internationalization for the [component name] component to ensure that it can be used by users in multiple languages. Consider using [internationalization library or technique] to achieve this.
```

<sup>[⬆️ Back to table of contents](#table-of-contents)</sup>

### 📣 Add comments to code

> [!NOTE]
>If your code is self-explanatory but requires commenting, this can be a huge time-saver.

**Prompt:**

```
Add comments to the following code:

[INSERT YOUR CODE HERE]
```

<sup>[⬆️ Back to table of contents](#table-of-contents)</sup>

## Code Generation

### 📣 Create Functions

> [!NOTE]
>Provide context of your software and ask directly for creating functions you need for your software

**Prompt:**

```
Context: I'm creating a software to manage projects

Technologies: Go, PostgreSQL

Description: It's a function that let me find users by its email or username.

You have to: create the function for me
```

Also you can add in the description what you expect to receive from your function. If you already have an structure for the User, specify it, for example:

**Prompt:**

```
Context: I'm creating a software to manage projects

Technologies: Go, PostgreSQL

Description: It's a function that let me find users by its email or username and returns the structure type "Member"

You have to: create the function for me
```

<sup>[⬆️ Back to table of contents](#table-of-contents)</sup>

### 📣 Generate a Dockerfile

> [!NOTE]
>A prompt to generate a Dockerfile for a specific framework.

**Prompt:**

```
Write a Dockerfile for:

[FRAMEWORK]
```

<sup>[⬆️ Back to table of contents](#table-of-contents)</sup>

### 📣 Write a RegEx

**Prompt:**

```
Write a regular expression that matches / Write a RegEx pattern for:

[REQUEST]
```

<sup>[⬆️ Back to table of contents](#table-of-contents)</sup>

### 📣 Create a Class

**Prompt:**

```
Create a [PLATFORM] class from this JSON object

[JSON]
```

<sup>[⬆️ Back to table of contents](#table-of-contents)</sup>

### 📣 Add Functionality

**Prompt:**

```
I need a piece of code in [INSERT YOUR TECHNOLOGIES HERE] to implement [real-time communication]
```

<sup>[⬆️ Back to table of contents](#table-of-contents)</sup>

### 📣 Create Boilerplate Code

> [!NOTE]
>Starting new projects can be painful. While GPT-4 doesn’t know your business logic, it can be used to generate boilerplate code. This isn’t technically refactoring, but it’s amazing and can be part of the programming lifecycle process.

**Prompt:**

```
Write me a boilerplate Node.js function that will take a variable of type User, validate that the user has the right permissions, fetch an array of item type Posts from a postgres database and return them. Leave comments for business logic.
```

<sup>[⬆️ Back to table of contents](#table-of-contents)</sup>

### 📣 You are a world-class software engineer

> [!NOTE]
>In this clip I show you how to *drastically* improve ChatGPT’s outputs for software generation.

**Prompt:**

```
You are a world-class software engineer.

I need you to draft a technical software spec for building the following:
[ DESCRIPTION ]

Think through how you would build it step by step.

Then, respond with the complete spec as a well-organized markdown file.

I will then reply with "build," and you will proceed to implement the exact spec, writing all of the code needed. I will periodically interject with "continue" to >prompt you to keep going. Continue until complete.
```

<sup>[⬆️ Back to table of contents](#table-of-contents)</sup>

## Code Review

### 📣 Error Hendling

**Prompt:**

```
How can I improve the error handling in my [LANGUAGE] code? [CODE]
```

<sup>[⬆️ Back to table of contents](#table-of-contents)</sup>

### 📣 Suggest Improvements

**Prompt:**

```
I'm working on a [LANGUAGE] project and I need you to review my code and suggest improvements. [CODE]
```

<sup>[⬆️ Back to table of contents](#table-of-contents)</sup>


## Product Service Promotion

### 📣 Generate innovative product ideas

**Prompt:**

```
Brainstorm creative and unique product ideas for [insert industry or market]. 

Focus on solving customer pain points and providing exceptional value.
```

<sup>[⬆️ Back to table of contents](#table-of-contents)</sup>

### 📣 Develop a unique value proposition

**Prompt:**

```
Help me articulate a unique value proposition for my [insert product or service].

Explain how this proposition differentiates my offering and appeals to my target audience.
```

<sup>[⬆️ Back to table of contents](#table-of-contents)</sup>

### 📣 Master the art of storytelling for marketing

**Prompt:**

```
Teach me storytelling techniques for creating compelling marketing content to promote [insert product or service].
```

<sup>[⬆️ Back to table of contents](#table-of-contents)</sup>

### 📣 Create a successful referral program

**Prompt:**

```
Design a referral program for [insert business] that incentivizes customers to share and recommend our products or services.
```

<sup>[⬆️ Back to table of contents](#table-of-contents)</sup>

### 📣 Master the art of upselling and cross-selling

**Prompt:**

```
Teach me effective upselling and cross-selling techniques to increase revenue and customer satisfaction in [insert business context].
```

<sup>[⬆️ Back to table of contents](#table-of-contents)</sup>

### 📣 Create a viral marketing campaign

**Prompt:**

```
Design a creative and attention-grabbing marketing campaign for [insert product or service] with the potential to go viral.
```

<sup>[⬆️ Back to table of contents](#table-of-contents)</sup>

### 📣 Develop a powerful elevator pitch

**Prompt:**

```
[Insert a brief description of your product, service, or company].

Help me create a concise and compelling elevator pitch that will effectively communicate the value of my offering.
```

<sup>[⬆️ Back to table of contents](#table-of-contents)</sup>

### 📣 Create an actionable marketing plan

**Prompt:**

```
Develop a marketing plan for [insert product or service]. 

Include objectives, target audience, marketing channels, and tactics for reaching my desired audience and driving sales.
```

<sup>[⬆️ Back to table of contents](#table-of-contents)</sup>

### 📣 Leverage content marketing for lead generation

**Prompt:**

```text
Develop a content marketing strategy for [insert business] to attract, engage, and convert leads into customers.
```

<sup>[⬆️ Back to table of contents](#table-of-contents)</sup>

<details>

<summary>

## Codex

### Codex хорош в:
- дополнении существующих фрагментов кода
- переводе кода с одного языка/диалекта на другой
- генерации алгоритмов/повторяющихся паттернов кода

Особенно обращает внимание на используемые комментарии.

Как и все нейросети, требует дополнительной проверки написанного кода.
### Перед использованием Codex стоит прочитать системный промпт, чтобы понять, как именно агент будет вести себя при обработке промпта.
### Так выглядит системный промпт Codex:

### Instructions
>- The user will provide a task.
>- The task involves working with Git repositories in your current working directory.
>- Wait for all terminal commands to be completed (or terminate them) before finishing.

### Git instructions
>If completing the user's task requires writing or modifying files:
>- Do not create new branches.
>- Use git to commit your changes.
>- If pre-commit fails, fix issues and retry.
>- Check git status to confirm your commit. You must leave your worktree in a clean state.
>- Only committed code will be evaluated.
>- Do not modify or amend existing commits.

### AGENTS.md spec
>- Containers often contain AGENTS.md files. These files can appear anywhere in the container's filesystem. Typical locations include `/`, `~`, and in various places inside of Git repos.
>- These files are a way for humans to give you (the agent) instructions or tips for working within the container.
>- Some examples might be: coding conventions, info about how code is organized, or instructions for how to run or test code.
>- AGENTS.md files may provide instructions about PR messages (messages attached to a GitHub Pull Request produced by the agent, describing the PR). These instructions should be respected.
>- Instructions in AGENTS.md files:
>>  - The scope of an AGENTS.md file is the entire directory tree rooted at the folder that contains it.
>>  - For every file you touch in the final patch, you must obey instructions in any AGENTS.md file whose scope includes that file.
>>  - Instructions about code style, structure, naming, etc. apply only to code within the AGENTS.md file's scope, unless the file states otherwise.
>>  - More-deeply-nested AGENTS.md files take precedence in the case of conflicting instructions.
>>  - Direct system/developer/user instructions (as part of a prompt) take precedence over AGENTS.md instructions.
>- AGENTS.md files need not live only in Git repos. For example, you may find one in your home directory.
>- If the AGENTS.md includes programmatic checks to verify your work, you MUST run all of them and make a best effort to validate that the checks pass AFTER all code changes have been made.
>>  - This applies even for changes that appear simple, i.e. documentation. You still must run all of the programmatic checks.

### Citations instructions
>- If you browsed files or used terminal commands, you must add citations to the final response (not the body of the PR message) where relevant. Citations reference file paths and terminal outputs with the following formats:
>  1. `【F:<file_path>†L<line_start>(-L<line_end>)?】`
>  - File path citations must start with `F:`. `file_path` is the exact file path of the file relative to the root of the repository that contains the relevant text.
>  - `line_start` is the 1-indexed start line number of the relevant output within that file.
>  2. `【<chunk_id>†L<line_start>(-L<line_end>)?】`
>  - Where `chunk_id` is the chunk_id of the terminal output, `line_start` and `line_end` are the 1-indexed start and end line numbers of the relevant output within that chunk.
>- Line ends are optional, and if not provided, line end is the same as line start, so only 1 line is cited.
>- Ensure that the line numbers are correct, and that the cited file paths or terminal outputs are directly relevant to the word or clause before the citation.
>- Do not cite completely empty lines inside the chunk, only cite lines that have content.
>- Only cite from file paths and terminal outputs, DO NOT cite from previous pr diffs and comments, nor cite git hashes as chunk ids.
>- Use file path citations that reference any code changes, documentation or files, and use terminal citations only for relevant terminal output.
>- Prefer file citations over terminal citations unless the terminal output is directly relevant to the clauses before the citation, i.e. clauses on test results.
>>  - For PR creation tasks, use file citations when referring to code changes in the summary section of your final response, and terminal citations in the testing section.
>>  - For question-answering tasks, you should only use terminal citations if you need to programmatically verify an answer (i.e. counting lines of code). Otherwise, use file citations.
