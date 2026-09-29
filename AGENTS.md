# Writing Style

## For code

### For comments

- Comments in a file should follow a common pattern
    - If no functions in that file have docstrings, do not add comments for the functions you are adding or modifying
    - If only public APIs in that file have docstrings or comments, then add comments only for public APIs you are working on.
    - If all functions have comments, then add comments for the functions you are working on.
 
- In general, for my projects, I do not prefer writing docstrings.
- For implementation, I only want comments in the implementation code if it is absolutely required.
- Comments should always be single-line; no block comments should be less than 120 characters
- For functions with more than 25 lines, comments should follow a strict hierarchy. You can break down the implementation into parts
  with one comment per part or subpart, with the number of the part before the comment. For example, "(1) Read data", "(2.3) call skill" etc.
- One function should never have more than 3 levels of part hierarchy. If more than 3 levels are required, spin off parts as separate functions.
- Each leaf part should not have more than 25 lines ever.
- For functions less than 25 lines, a max of one line comment per function in the most important place with the most important non-trivial information
- No adding comments at the beginning of the page. Not even a single line.
- All comments are supposed to be stateless. If you change A to B, the comment should explain why B, not why A was changed to B. If B is further changed to C,
  comments should not refer to A or B or any test history or external docs. Any tracking information should be in agent working documents, not in the repository itself. 

### For file tracking environments
- When fixing the environment, always try simple things. Do not add long comments as to why you did things a particular way.
- Only at the end of the file can you add up to 4 lines of comments explaining the problem. Anything more than that and the comment does not belong in theat file but in documentaitons.

### For C/C++
- Use the namespace name as an inline comment when closing scope. This also applies to ifndefs in header files.

### For Python
- Type indication is mandatory for front-facing public APIs and very core application-agnostic functions. For functions merely orchestrating, no type indication is to be used.
- All imports should be at the top

## For documentation

- For a project I am developing, if the number of code files in a package exceeds 5 files, make a docs folder in the root of the repository.
- In the docs folder, follow the same file hierarchy but at folder level. If a folder has only files, one .md in docs should be used to document that folder.
- For folders with folders in files, one .md should be used for all of them together.
- Here is an example:
  Assuming the file structure as follows
  ```text
  src/
  ├── folderA/
  │   ├── file1
  │   └── file2
  ├── folderB/
  ├── file3
  └── file4
  ```
  Then docs should have this structure:
  ```text
  docs/
  ├── docsA
  ├── docsB
  └── docs
  ```
  Here, docsA describes file1 and file2, docsB describes all files in folderB, and docs describes what is happening in folderA, folderB, file3, and file4.
- In each of these files, use fewer than 50 words and no more than 2 sentences for each description.
- On top of every file, in fewer than 50 words, summarize the file.  

## For Prose/Content
This governs any text written for me: papers, slides, notes, commit messages, and replies. 
### Tone

  - Short, simple prose.
  - Uplifting, positive, constructive.
  - Avoid unnecessary non-technical language and jargon.
  - Say the thing. Trust me to follow it.

### Sentences

  - One claim per sentence. Median length 18 words, hard ceiling 32.
  - Active voice with a concrete subject: "I/We train the policy", against "The
    policy is trained".
  - Lead each paragraph with its claim. Support follows.
  - Vary sentence length. A run of same-length sentences reads mechanically.

### Banned constructions
  
  Rewrite these on sight.
  
  | Banned | Instead |
  | --- | --- |
  | "X, not Y" contrast framing | Say X. |
  | "It is important to note that", "It is worth noting", "Notably" | Cut it and state the point. |
  | "delve" | "examine", "look at" |
  | "leverage" as a verb | "use" |
  | "seamless" | Name the property. |
  | "robust" as a synonym for "good" | Name the property. |
  | "In this paper, we propose a novel…" | Name the thing and its effect. |
  | Em-dash asides where a comma works | Use the comma. |

  Two more to watch, both symptoms of padding:
  
  - Openers that announce rather than assert: "This section discusses…".
  - Hedge stacks: "may potentially suggest".

### Survey and review prose

  - Lead a paragraph with the claim, then cite in support. Never open with
    `\cite{key} proposes X` — that reads as an annotated bibliography.
  - Vary synthesis paragraphs. Not every one opens "Overall," or "Collectively,"
    and then runs methods-agree / limitation / future-work.
  - When a method is discussed in two sections, say in the second what is new
    there. Otherwise it reads as an editing miss.
  - Name the cause behind a trend. Five scattered observations plus one mechanism
    beats five observations.

### Checklist

- [ ] Every paragraph leads with its claim.
- [ ] No sentence exceeds 32 words.
- [ ] No banned construction survives, including in captions and titles.
- [ ] Every list is grammatically parallel.

