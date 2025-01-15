# CodyAI Resume Builder

![CodyAI Logo](/public/icon/cody.png)

## Table of Contents

- [Introduction](#introduction)
- [What Problem Are We Solving?](#what-problem-are-we-solving)
- [What is the Solution?](#what-is-the-solution)
- [Why Is This a Great Achievement for Us?](#why-is-this-a-great-achievement-for-us)
- [Features](#features)
- [Demo](#demo)
- [Usage](#usage)
- [License](#license)
- [Contact](#contact)

## Introduction

CodyAI Resume Builder is an AI-powered tool designed to simplify and enhance the resume creation process. By leveraging GitHub data and OpenAI's advanced language models, CodyAI helps users craft compelling resumes that pass Applicant Tracking Systems (ATS) and effectively showcase both hard and soft skills.

## What Problem Are We Solving?

In the competitive U.S. job market, listing and describing projects on a resume is challenging.

First, we need to frame our experience to pass Applicant Tracking Systems (ATS) and then showcase our soft skills—such as problem-solving, teamwork, communication, creativity, resilience, initiative, leadership, organization, and learning—using strong action verbs like “Delivered,” “Built,” “Achieved,” “Implemented,” and “Collaborated.”

This is combined with hard skills, statistics, and a timeline to fit the STAR method: **Situation, Task, Action, and Result**. By doing so, we highlight our contributions, achievements, and impact, helping us to stand out.

This process requires extensive training—especially for me, as an English language learner—and can be time-consuming, especially when organizations seek a detailed and accurate story of your skills, interests, and the value you bring to a role.

## What is the Solution?

CodyAI leverages AI to streamline and enhance resume creation. It increases the accuracy of information by calling GitHub to gather all contributions and then sends the data to OpenAI, along with a carefully crafted prompt, to generate content.

When I joined the team, I was given an incredible opportunity by our project manager, [Tom Rau](https://www.linkedin.com/in/tom-rau/), to collaborate with my team and continue advancing this AI-powered resume builder.

## Why Is This a Great Achievement for Us?

We’re not only solving real-world problems but also meeting several key design principles:

- **Scalable:** Admins can add project repositories within the app.
- **Faster:** It requests data concurrently from multiple repositories.
- **Cost-Effective:** We use two JavaScript libraries for Machine Learning, NLP and Natural.js, to refine data in-house before sending it to OpenAI, reducing costs by a third.
- **Secure:** Admins can securely store repository access credentials in our database with comprehensive instructions and 256-bit advanced encryption using the Crypto library.

## Features

- **Automated Data Gathering:** Fetches contributions from GitHub repositories automatically.
- **AI-Powered Content Generation:** Utilizes OpenAI to craft professional and optimized resume content.
- **ATS Optimization:** Ensures resumes are tailored to pass Applicant Tracking Systems.
- **User-Friendly Interface:** Easy-to-navigate web application with intuitive design.
- **Secure Data Handling:** Implements advanced encryption for data security.

## Demo

![Application Screenshot 1](/public/img/screenshot_output.png)
_Figure 1: Resume Generation Page_

![Application Screenshot 2](/public/img/Screenshot_1.png)
_Figure 2: Dashboard Overview_

## Usage

### Admin

1. Sign Up / Log In
2. Navigate to Admin tab
3. Create a project
4. Add description to the project
5. Add GitHub repository links
6. Provide personal access token (PAT) if private
7. Add developers to the project
8. Save

### Developer

1. Sign Up / Log In
2. Navigate to CodyAI Resume Builder
3. Select a project
4. Generate Resume
5. Review and edit the generated content as needed.
6. Copy to Share

## License

This project is licensed under the **Code The Dream (CTD) License**.

## Contact

If you have any questions or feedback, feel free to reach out:

- **Web:** [DevArts](https://devarts.notion.site/61c6b79808ce476290c753165851b070?v=9d442848a814451fba7a2e1b99bebb9b)
- **LinkedIn:** [Amir Olyaei](https://linkedin.com/in/amirolyaei)
- **GitHub:** [AmirhosseinOlyaei](https://github.com/AmirhosseinOlyaei)
- **Organization:** [Code The Dream](https://codethedream.org/)

---

_Thank you for using CodyAI Resume Builder! We hope it helps you create the perfect resume to advance your career._

---

![Application Screenshot 2](/public/img/Screenshot_2.png)
_Figure 2_

![Application Screenshot 3](/public/img/Screenshot_3.png)
_Figure 3_

![Application Screenshot 4](/public/img/Screenshot_4.png)
_Figure 4_

![Application Screenshot 5](/public/img/Screenshot_5.png)
_Figure 5_

![Application Screenshot 6](/public/img/Screenshot_6.png)
_Figure 6_

![Application Screenshot 7](/public/img/Screenshot_7.png)
_Figure 7_

![Application Screenshot 8](/public/img/Screenshot_8.png)
_Figure 8_

![Application Screenshot 9](/public/img/Screenshot_9.png)
_Figure 9_

Below are two lists you can include in your project’s README to highlight key features from each file:

---

## Key Features from `app/api/githubAPI/commits/route.js`

1. **Secure Token Management**

   - Uses encrypted, per-repository GitHub tokens (`GitHubToken` model) that are decrypted only when needed.

2. **Comprehensive Data Retrieval**

   - Fetches both commits and pull requests to consolidate the developer’s full activity across multiple repositories.
   - Utilizes pagination and concurrency to handle large datasets efficiently.

3. **Intelligent Commit Filtering**

   - Excludes trivial or duplicate commit messages, focusing on meaningful contributions.
   - Calculates total commits and contribution duration for clear metrics.

4. **Pull Request Detail Extraction**

   - Retrieves PR metadata (title, body, dates, etc.) for deeper insights.
   - Enforces concurrency limits to prevent overloading the GitHub API.

5. **Robust Error Handling & Rate Limit Management**

   - Manages invalid URLs, missing parameters, and restricted repository access gracefully.
   - Implements rate-limit checks to delay requests until API resets, preventing interruptions.

6. **MongoDB Integration**
   - Stores project and repository configurations in the `Project` model, allowing dynamic retrieval of multiple repos.
   - Streamlines adding or modifying tracked repositories without altering core logic.

---

## Key Features from `app/(protectedRoutes)/codyAI/resumeTools/components/prompt.js`

1. **Dynamic Prompt Creation**

   - Adapts to available data (commits, pull requests, or none) to generate tailored AI prompts.
   - Provides fallback logic for scenarios with limited or no developer contribution data.

2. **Resume-Focused Formatting**

   - Clearly instructs AI to generate concise, high-impact résumé bullets.
   - Emphasizes strong action verbs, quantifiable achievements, and relevant technologies.

3. **Customization & Error Handling**

   - Accepts optional error messages to handle incomplete data gracefully.
   - Offers flexibility to tailor final output based on user feedback or project needs.

4. **User Feedback Integration**

   - The `changePrompt` function allows targeted revisions without altering unrelated content, streamlining collaborative edits.
   - Makes iterative refinement simpler by focusing on specific user-requested changes.

5. **Concise & Impactful Guidance**
   - Encourages an opening statement and up to five bullet points for clarity and brevity.
   - Aligns with industry expectations for top-tier résumé writing, spotlighting results and skills.
