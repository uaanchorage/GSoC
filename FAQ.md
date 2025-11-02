We will keep this page updated as we start receiving recurring questions that are of common interest to this organization and its contributors. Please check this [FAQ](https://developers.google.com/open-source/gsoc/faq) first.

# Do you mandate pull requests as a pre-requisite for acceptance to the GSoC?

Short answer: No, there is no mandatory requirement for a pull request at the organizational level. Individual projects can have their own expectations.

long answer: Yes, pull requests are appreciated, but please pay attention to a few factors listed below.

Given the research nature of our projects, Alaska does not make it mandatory to have pull requests. But meaningful pull requests are always welcome.

Open source organizations often encounter GSoC applicants making pull requests that are less useful during the application period. This is especially understandable when we do not have any/many bug reports or requests for enhancement (RFE) in the repositories.
We appreciate your enthusiasm. We want to support you to make meaningful ones. If you are making a pull request, it is important to make sure:

* it addresses some real bugs/issues. While appreciated, pull requests to change variable names to make them read better, add comments, or superficial changes are unlikely to be merged. Because, they take valuable mentor time during the application period.

* it does not break an existing feature. This happens a lot that students attempt to fix a bug, but introduces several new bugs.

* it does not change unrelated files. Do not add multiple pull requests into one. Keep your pull request minimal. If your fix needs to change only one file, commit only that in your pull request.

* it does not change unrelated lines. If your fix needs only changing two lines, your pull request should change only those two lines, rather than changing the whole files (with changes such as changes to line ending).

* meaningful commit log message to show what you have changed.

* proper testing was done prior to submitting the pull request. Do not submit the pull request, giving the task of testing the changes. While the mentor will still do the testing, we often end up getting several pull requests that are buggy or do not do the task that they claim to do. Such pull requests often end up hurting the applicant.
 

# Why did I not receive a reply to my question?

Depends.

If your question was, "hi, I am new here. Can you help me get started?" the question will likely go unanswered. Getting started guides are plenty in this repository and under individual projects. Questions that show a lack of effort will rarely get useful feedback from open-source communities, especially in the context of competitive programs such as the Google Summer of Code (GSoC). The rationale is simple. These are easy questions to ask. But answering them means rephrasing what we have already mentioned elsewhere.

If you think your question is not such a generic question, check the project repository and its discussion forums to make sure the question was not answered before.

On the other hand, occasionally, we also may miss some thoughtful question that deserves a reply. This is especially true during the GSoC application deadlines. In such cases, it makes sense to post a follow up message to the GitHub discussion, tagging the mentor.

Also, please note that as we encourage GitHub discussions, we discourage private emails to the mentors, except to share the project proposal draft.

# What is the Alaskan Season of Code (ASoC)? Is it related to Google or Google Summer of Code (GSoC)?

[Alaskan Season of Code (ASoC)](Alaskan-Season-of-Code.md) is an initiative from Alaska to provide open-source mentoring to interested contributors on a volunteer (with a 1-to-1 mentoring similar to GSoC, but an unpaid program) basis. Please note that it is not affiliated with or endorsed by GSoC/Google. But when an excellent applicant is not accepted by GSoC (because we get many excellent applicants than what we can get from GSoC), we may be able to work with the applicant as part of the ASoC. However, be aware that it is an independent mentoring program and does not have the same structure and timeline (although it is heavily influenced by the GSoC model).

# I participated in GSoC last year with Alaska. Can I apply again?

Sure. But please note that the contributions you made as part of your GSoC and prior to the GSoC won't be considered in evaluating your GSoC for the current year. Any contributions made after your past GSoC will be considered positively. However, note that you will still be competing with many talented applicants, and that will be a fair battle. We encourage you to apply to other organizations as a contributor for your second year, or apply to be a mentor with Alaska. This restriction is not applicable for ASoC, since ASoC contributions are volunteer contributions. You are welcome to apply to GSoC!

# I participated in ASoC last year with Alaska. Can I apply later as a GSoC contributor this year or later?
Of course! We encourage you to! ASoC is not affiliated with Google or GSoC. It is simply an unpaid volunteer remote coding experience inspired by GSoC.

# Can I apply to multiple project ideas from Alaska?
Yes, but not exceeding the overall limit imposed by Google (3 proposals per contributor, as of 2025). Indicate your preference order in the proposals. We cannot guarantee that such preferences will be respected since the proposals are largely evaluated for their strength and how many other strong applications that idea has. However, when we have the freedom, and if both the proposals from the candidate are strong, we will consider the provided preference order. Cross-reference the contributions to other Alaska projects in your proposals so that your contributions will be visible to the mentors who evaluate your proposals.

# Can I email the proposals to the mentors?
Yes, please draft the proposal and email it to the mentors. CC all the mentors in one email rather than sending individual emails to each mentor. Make sure your proposal is in complete shape before sending it for reviews. You do not want mentors to review a very early draft.

# How do I choose the right project for my skills and interests?

Selecting the right project is crucial for your success in GSoC. Here are some practical tips:

**Match your technical skills:** Each project lists required skills and difficulty levels (Easy/Intermediate/Hard). Be honest about your current abilities:
- If you're new to machine learning, consider starting with Intermediate projects rather than jumping into Hard ones like the LNS for LLMs project
- For projects requiring Python, ensure you're comfortable with the language beyond basic syntax
- MATLAB projects require actual MATLAB experience, not just programming knowledge

**Consider the time commitment:** Projects are sized for different commitment levels:
- 350 hours (full-time): Requires consistent 35 hours/week commitment
- 175 hours (medium): About 18 hours/week, good for those with other commitments  
- 90 hours (small): Quarter-time projects, ideal for students with coursework

**Research the project domain:** Alaska's projects span healthcare, climate science, polar research, and blockchain. Choose areas that genuinely interest you:
- Read the linked source code repositories to understand the current state
- Check the discussion forums to see what challenges contributors are facing
- Look up recent papers or articles related to the project domain

**Complete the code challenges first:** Before committing to a project, attempt its code challenge. This will give you a realistic sense of the complexity and whether you can handle the full project scope.

**Start contributing early:** Begin engaging with project discussion forums, ask meaningful questions, and try to make small contributions. This helps you understand the project culture and technical requirements while demonstrating your commitment to mentors.
