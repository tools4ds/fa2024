---
layout: home
---

<details id="toc">
<summary>Table of Contents</summary>
<div id="toc-content"></div>
</details>

<script>
document.addEventListener('DOMContentLoaded', function() {
    const tocContent = document.getElementById('toc-content');
    const headings = document.querySelectorAll('h2, h3, h4');
    const toc = document.createElement('ul');

    let currentLevel = 2;
    let currentUl = toc;
    let levelStack = [toc];

    headings.forEach(heading => {
        const level = parseInt(heading.tagName.charAt(1));
        
        if (level > currentLevel) {
            const newUl = document.createElement('ul');
            currentUl.lastElementChild.appendChild(newUl);
            levelStack.push(newUl);
            currentUl = newUl;
        } else if (level < currentLevel) {
            while (levelStack.length > level - 1) {
                levelStack.pop();
            }
            currentUl = levelStack[levelStack.length - 1];
        }

        currentLevel = level;

        const li = document.createElement('li');
        const a = document.createElement('a');
        a.textContent = heading.textContent;
        a.href = '#' + heading.id;
        li.appendChild(a);
        currentUl.appendChild(li);
    });

    tocContent.appendChild(toc);
});
</script>

<br>

## Logistics

### Lecture Section A1
**Meeting Place:** 665 Comm Ave CDS B62

**Meeting Time:** Tu, Th 9:30am -- 10:45am

**Instructor:** Prof. Thomas Gardos
* Office: CCDS 1623
* Office Hours: Thursdays 11:00 AM -- 12:00 noon and by appointment
* Office Hours Location: CCDS 1623
* Email: tgardos &lt;at&gt; bu &lt;do&gt; edu

### Discussion Section A2

**Discussions Meeting place:** 750 Commonwealth Ave EPC 205

**Discussions Time:** We 12:20pm - 1:10pm

### Lecture Section C1
**Meeting Place:** 595 Commonwealth Ave HAR 324

**Meeting Time:** Mo,We 4:40pm - 5:55pm

**Instructor:** Prof. Scott Ladenheim
* Office: CCDS 1545
* Office Hours: We,Fr 11:00am - 12:00pm
* Office Hours Location: CCDS 1545
* Email: saladenh \<at>\ bu \<dot>\ edu

### Discussion Section C2

**Discussions Meeting place:** 685-725 Comm Ave CAS 313

**Discussions Time:** Fr 10:10am - 11:00am

### Teaching Assistants

* Name: Chandrahas Aroori
   * Office Hours: Th 10:00am - 11:00am and by appointment
   * Office Hours Location: CCDS 15th floor, open desks on the south side. 
   * Email: charoori &lt;at&gt; bu &gt;dot&lt; edu

* Name: Farid Karimli
   * Office Hours: Tu 11:00am -- 12:00 noon and by appointment.
   * Office Hours Location: CCDS 15th floor, open desks on the south side. 
   * Email: faridkar &lt;at&gt; bu &gt;dot&lt; edu

* Name: Shreyas Sudarsan
   * Office Hours: We 2:00pm - 3:00pm
   * Office Hours Location: CCDS 15th floor, open desks on the south side. 
   * Email: shreyas9 &lt;at&gt; bu &gt;dot&lt; edu

## Overview of the Course

This course is a Master’s level introduction to data science, focusing on proficiency in working with and
analyzing data. The course emphasizes practical skills in working with data, while introducing students to a
wide range of techniques that are commonly used in the analysis of data, such as clustering, classification,
regression, and network analysis. The goal of the class is to provide to students a hands-on understanding
of classical data analysis techniques and to develop proficiency in applying these techniques in a modern
programming language (Python).

Broadly speaking, the course breaks down into three main components, which we will take in order of
increasing complication: (a) unsupervised methods; (b) supervised methods; and (c) methods for structured
data.

Lectures will present the fundamentals of each technique; focus is not on the theoretical analysis of the
methods, but rather on helping students understand the practical settings in which these methods are useful.
Class discussion will study use cases and will go over relevant Python packages that will enable the students
to perform hands-on experiments with their data.

### Prerequisites

Prerequisites: Students taking this class must have prior familiarity with programming, at the level of
DS110, CS105, CS108, or CS111, or equivalent. In this course you will use python – you are assumed
to either know python, or be ready to learn it quickly on your own in the first week. Linear Algebra – DS121
or CS132 or equivalent (MA 242, MA 442) – is required. DS210 or CS112 is also helpful.

### Learning Outcomes

Students who successfully complete this course will be proficient in data acquisition, manipulation, and
analysis. They will have good working knowledge of the most commonly used methods of clustering,
classification, and regression. They will also understand the efficiency issues and systems issues related to
working on very large datasets.

### Textbook and Slides

The textbook used in the course is published at
[https://tools4ds.github.io/DS701-Course-Notes/](https://tools4ds.github.io/DS701-Course-Notes/).
This online text will evolve as the course progresses, but we will work to keep it up-to-date.

The slides used in the lecture are written in Quarto markdown that can include
executable python cells. When we show you code in lecture, it will almost always
be runnable code. You can execute them directly in the Quarto markdown files if
you [install Quarto](https://quarto.org/docs/get-started/). We recommend installing
[VS Code](https://code.visualstudio.com/) and adding the
[Quarto extension](https://marketplace.visualstudio.com/items?itemName=quarto.quarto)
to execute the cells right in VS Code.

For all the lectures with python code, we also add the **Open in Colab** link so
you can open the page directly from the
[Course Notes](https://tools4ds.github.io/DS701-Course-Notes/) web page and
execute the python cells that way.

Feel free to clone the [Course Notes repository](https://tools4ds.github.io/DS701-Course-Notes/)
and execute on your own computer. You can modify them any way you’d like, play
around with them, experiment, etc.  If you find a bug, feel free to submit a pull
request. Some of the lectures were previously based on 
_[Introduction to Data Mining](https://www-users.cse.umn.edu/~kumar001/dmbook/index.php)[^1]_. 
This is a good place to go for more detail if some methodological aspect is not
clear. For up-to-date reference on Pandas, scikit-learn, or any of the other
software tools we use, there is no substitute for online resources.

[^1]: Tan et al, Introduction to Data Mining, Pearson, 2019, [https://www-users.cse.umn.edu/~kumar001/dmbook/index.php](https://www-users.cse.umn.edu/~kumar001/dmbook/index.php)

### Tools and Platforms

We will use:
1. [Piazza](https://piazza.com/bu/fall2024/ds701) for questions
2. Github for [web](https://github.com/tools4ds/fa2024) and [notes](https://github.com/tools4ds/DS701-Course-Notes) 
   source, some homeworks and assignments
3. [Gradescope](https://www.gradescope.com/courses/845172) for grading and grade
   management
4. Kaggle for the midterm.

You should already be signed up for Gradescope and Piazza, if not see the
enrollment codes in the course welcome email or contact an instructor.

You will need an account on Github. Please also add your real name to your GitHub
account profile so we can find you.

If you don’t have an up to date Python installation, take care of that right away.

### Piazza

We will be using Piazza for class discussion. The system is really well tuned to
getting you help fast and efficiently from classmates, the teaching fellows, and
myself. Rather than emailing questions to the teaching staff, we encourage you
to post your questions on Piazza. Our class Piazza page is at:
[https://piazza.com/bu/fall2024/ds701](https://piazza.com/bu/fall2024/ds701). 

When someone posts a question on Piazza, if you know the answer, please go ahead
and post it. However please don’t provide answers to homework questions on Piazza.
It’s OK to tell people where to look to get answers, or to correct mistakes in the
assignment; just don’t provide actual solutions to homework questions.

### Programming Environment

We will use python as the language for teaching and for assignments that require
coding. Instructions for installing and using Python are in the online textbook.

## Course and Grading Administration

Homeworks are due at midnight on the date shown on the syllabus. Assignments will be submitted using
github and gradescope. Please review the instructions for submitting homeworks, on the Resources
page of Piazza.

> NOTE: IMPORTANT: Late assignments WILL NOT be accepted. However, you may submit one homework
>up to 3 days late. You must notify the TAs on Piazza before the deadline if you intend to submit a homework
>late.

Final grades will be computed based on the following:<br>

| Percentage | Category |
| :----------: | :--------: |
| 20%        | Midterm  |
| 40%        | Homework assignments |
| 40%        | Final Project   |
{:.mbtablestyle}
<br>
The exact cutoffs for final grades will be determined after the class is complete.

### Project Grading

Of the 40% of the project course grade, it is further weighted as the following

| Percentage | Category         | Comments |
| :--------: | :--------------: | :------ |
| 50%        | Project quality  | * Did the project accomplish a sufficient number of (possibly revised) objectives?<br> * Was the client relationship managed well?  |
| 10%        | Repo quality     | * Is the Github repository well organized and easy to navigate?<br> * Is the repo well documented especially with replication steps?<br> * Can one start from a new environment and easily setup and run? |
| 30%        | Individual Contribution | Is there clear evidence of<br> * attendance and active participation in class lab time, client and team meetings?<br> * Documented activities in sprint plan history?<br> * Git commit history and co-authored git commits?<br> * Record of individual's contributions in document and presentation revision history?  |
| 10%        | Collaboration    | Is there indication, for example from peer reviews, of positive collaborations and constructive teamwork? |
{:.mbtablestyle}
<br>

### Homeworks

There will four homework assignments. In a typical assignment you will analyze one or more datasets using
the tools and techniques presented in class.

Homeworks will be submitted via github. For this, we need your github account (create one if
you don’t already have it). After you have created it, fill out this
[form](https://forms.gle/ZaYWHE8SwqqMgYLZA) to let us know what it is. We also 
highly recommend you add your full name to your GitHub account profile.

You are expected to work individually on homeworks.

### Midterm

The midterm will be a Kaggle Data Science competition among the students in the class with a live leaderboard.
Students will need to submit predictions based on a training dataset and a report detailing the methods
used and decisions made. Note that the intent is not to use the leaderboard to determine your grade, but rather
to help you assess how effective your work is. Accordingly, 80% of the grade will be based on the report
and only 20% will be based on the competition score related to the quality of the predictions made.

### Project

A major goal of this course is to gain experience with real-world data science problems in form of a project.
For the project you will extract some knowledge or conclusions from the analysis of dataset of your choice.
The analysis will be done using a subset of the methods we described in class.
Grading will be based on specific deliverables as well as your performance in your team throughout the
semester.

For the final project, students may get the opportunity to work with BU Spark! on a real world, datadriven
project for a company, non-profit, or institution. Spark projects have already been curated and will
be presented during “Pitch Day”. Project descriptions will be made available at the start of the semester.
Once every student has a final project, every team will need to upload a SCRUM file to the final project
repository every week which gives a short report on the status of their project.
SCRUM is an agile method used in many software companies. Fast and concise, it is a short report
answering the following questions:
* What have I worked on?
* What will I be working on next?
* Have I run into any issues? Do I need help?
* Have I talked to the client recently? When are we meeting with them next?

#### Project Expectations
* All team members should contribute equally and proactively to project work; we will evaluate team
contributions through a peer evaluation at the end of the semester and this will be factored into your
grade.
* You / your team lead should make yourself available to speak with your client on a bi-weekly basis
(depends on client availability)
* You / your team lead should meet with your Spark PM on a weekly basis
* You should meet with your team every other day (can / should be a short meeting)
* For any team communication issues, please let your spark PMs know asap - they are here to help. If
the problem persists please email me with a description of the situation.
* All students are expected to abide by University conduct policies as detailed in the following links:
   * [Boston University Student Codes of Conduct](https://www.bu.edu/policies/policy-category/student-codes-condcut/)
   * [College of Arts & Sciences Codes of Conduct](https://www.bu.edu/cas/academics/undergraduate-education/academic-conduct-code/resources-for-students/)
   * [Boston University Student Responsibilities](https://www.bu.edu/dos/policies/student-responsibilities/)
* All Spark! project teams
   – Project Managers: These are the project leads and will communicate with the client directly, they will assist with administrative support (meeting scheduling, agenda setting), and will be a point of contact for project questions / concerns. Project Managers are also responsible for
grading all Spark! project deliverables as detailed in the syllabus below. – Team Lead: These students will assist the Project Manager in attending client meetings, organizing team questions, and facilitating team meetings.
   – Team Members: These students work collaboratively with each other on the project goals. For details on what you must submit as part of your project, see the section “Project Deliverables” at the end of this syllabus.

#### Spark! Collaboration

BU Spark! offers students an opportunity to work on technical projects provided by companies or organizations
in the Greater Boston area through our experiential learning lab (X-Lab). For this semester, Spark!
has partnered with DS701 to offer a diverse selection of external data science projects scoped to support the
course’s learning outcomes and enhance the student experience. To learn more about Spark!, please visit
their [website](https://www.bu.edu/spark/).

Your project team will be led by one of the Spark! Project managers. Their role is to support the student
team’s work plan, manage client communication and expectations, organize weekly and biweekly meetings,
and to oversee project deliverable grading.

Spark! projects are a great opportunity for students to get real-world project experience to highlight on
their github and CV. These projects have already been curated and will be presented during “Pitch Day”.
Project descriptions will be made available at the start of the semester.

## Accommodations for Students with Disabilities

If you have a disability and have an accommodations letter from the Disability & Access Services office, We encourage you
to discuss your accommodations and needs with us as early in the semester as possible. We will work with you to ensure
that accommodations are provided as appropriate. If you suspect that you may have a disability and would benefit from
accommodations but are not yet registered with BU Disability & Access Services, we encourage you to find more information
at [https://www.bu.edu/disability/](https://www.bu.edu/disability/).

## Generative AI Assistance (GAIA) Policy

In general, we follow the policy outlined in the
[CDS GAIA Policy](https://www.bu.edu/cds-faculty/culture-community/gaia-policy/).

> Extracting and paraphrasing from the student responsibilities of that policy. 
> Where there is conflicting information between the CDS policy and below, the
> policy below should take precedence.

Students shall:<br>
1. Give credit to AI tools whenever used, even if only to generate ideas rather than usable text, illustrations or code.
2. When using AI tools on _written_ assignments, **unless prohibited**, add an appendix showing
    1. the entire exchange, highlighting the most relevant sections; 
    2. a description of precisely which AI tools were used (e.g. ChatGPT private subscription version or DALL-E free
        version), 
    3. an explanation of how the AI tools were used (e.g. to generate ideas, turns of phrase, elements of text, long
        stretches of text, lines of argument, pieces of evidence, maps of conceptual territory, illustrations of key
        concepts, etc.); 
    4. an account of why AI tools were used (e.g. to save time, to surmount writer’s block, to stimulate thinking, to
       handle mounting stress, to clarify prose, to translate text, to experiment for fun, etc.).
    5. Optional but recommended: Employ AI detection tools and originality checks prior to submission, ensuring that
       their submitted work is not mistakenly flagged.
3. When using AI tools on _coding_ assignments, **unless prohibited**
    1. Add the prompt text and tool used as comments before the generated code.
       Clarify whether the code was used as is, or modified somewhat, moderately
       or significantly.
4. When using AI assistants incoporated into IDEs such as VSCode and Github Copilot, be extra
   mindful of when to allow copilot generation. It can be handy to look up syntax, but it will
   also generate entire functions. If the assignment allows it and you generate complete
   functions, cite the tool in the comments in the function.
4. Not use AI tools during in-class examinations, or assignments, unless explicitly permitted and instructed.
5. Use AI tools wisely and intelligently, aiming to deepen understanding of subject matter and to support learning.

As these generative assistive tools become widely deployed and pervasive, we believe they will become integral
to most people's workflow. However, for foundational concepts, as are taught in this course, it is in your
best interest and worth it to struggle some in creating your answers and solutions. It is just as important
to learn what doesn't work, and which paths are dead ends, as it is to learn what does work. When you are posed
with new and unique problems, that intuition you develop will be vital in choosing directions. More pragmatically,
some of the most coveted jobs at the most selective companies require technical interviews where they expect you
to know these foundational concepts without assistance.

And finally, to reiterate, it is vitally important, and a core part of academic integrity, to cite when you are
using Generative AI Assistive technologies. Arguably, not citing and risking plagiarism is worse than
using and citing GAIA.

### The DS701 AI Terrier Tutor

In fact, we have an experimental generative AI tutor tailored to this course's content at
[https://tools4ds-ai-tutor.hf.space](https://tools4ds-ai-tutor.hf.space).  It is open
source hosted at [https://github.com/tools4ds/ds701-tutor](https://github.com/tools4ds/ds701-tutor)
which itself is forked from a parent project
[https://github.com/edubotics-ai/edubotics-app](https://github.com/edubotics-ai/edubotics-app).

We've attempted to make it Socratic in that it shouldn't just give answers but rather
guide you to solving the problem yourself, but it is not guaranteed to not give 
answers, so if GenAI is prohibited on an assignment then that will include 
our AI Terrier Tutor.

Otherwise, please utilize this resource and most importantly, give feedback.
Initially a simple thumbs up or thumbs down at the response. Also feel free to 
add a comment when prompted. We will use the feedback to evaluate the performance
of the model and ultimately use it to fine-tune and impprove it.

The Github repo links are shared above. Feel free to contribute if you are interested.

## Academic Honesty

You may discuss homework assignments with classmates, but you are solely responsible for what you turn in.
Collaboration in the form of discussion is allowed, but all forms of cheating (copying parts of a classmate’s
assignment, plagiarism from books or old posted solutions) are NOT allowed. We – both teaching staff and
students – are expected to abide by the guidelines and rules of the Academic Code of Conduct (which is at
[http://www.bu.edu/academics/policies/academic-conduct-code/](http://www.bu.edu/academics/policies/academic-conduct-code/)).

Graduate students must also be aware of and abide by the GRS Academic Conduct
code at [http://www.bu.edu/cas/students/graduate/forms-policies-procedures/academic-discipline-procedures/](http://www.bu.edu/cas/students/graduate/forms-policies-procedures/academic-discipline-procedures/).

You can probably, if you try hard enough, find solutions for homework problems online. Given the
nature of the Internet, this is inevitable. Let me make a couple of comments about that:
1. If you are looking online for an answer because you don’t know how to start thinking about a problem,
talk to Ms. Lu or myself, who may be able to give you pointers to get you started. Piazza is great for
this – you can usually get an answer in an hour if not a few minutes.
2. If you are looking online for an answer because you want to see if your solution is correct, ask yourself
if there is some way to verify the solution yourself. Usually, there is. You will understand what you
have done much better if you do that. So ... it would be better to simply submit what you have at the
deadline (without going online to cheat) and plan to allocate more time for homeworks in the future.


_This syllabus provides a general plan for the course; deviations may be necessary depending on the progress of the class._
