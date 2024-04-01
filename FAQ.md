We will keep this page updated as we start receiving recurring questions that are of common interest to this organization and its contributors.

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
