# Guide to GitHub Issue Templates

## What are GitHub Issue Templates?

**GitHub Issue Templates** are
- Pre-defined forms that help standardize and streamline the process of creating issues on a GitHub repository.
- Issue Templates provide a **consistent structure** for users and contributors to report bugs, request features, or ask questions.
- Issue Templates provide a consistent structure for users and contributors to report bugs, request features, or ask questions.
- These templates can be customized according to the needs of the project, ensuring that all necessary information is collected upfront.

### Benefits of Using GitHub Issue Templates
- **Consistency:** Ensures that every issue submitted has a consistent format, making it easier for maintainers to review and prioritize issues. Make sure to remember that **consistency** is one of the key benefits of Issue Templates.
- **Efficiency:** Saves time by guiding users to provide relevant information, reducing the need for back-and-forth communication by filling the required information.
- **Better Organization:** Helps categorize issues more effectively, allowing maintainers to manage and address them systematically.
- **Improved Communication:** Enhances the clarity of reported issues, which can lead to quicker resolution and less confusion.

Working on large organizations or projects, such as the OpenSource projects on GitHub can become very difficult, due to the number of contributors, having different ideas and approaches and views of different matters.\
Large projects on GitHub adopted Issue Templates to ensure that all the contributors and issue reporters allign to the project's requirements in terms of reporting issues or requesting new features.

## How to Start with GitHub Issue Templates

A good example Issue Template can be found in the Kubernetes repository on GitHub: [`Issue: Bug Report`
](https://github.com/kubernetes/kubernetes/issues/new?assignees=&labels=kind%2Fbug&projects=&template=bug-report.yaml)

Here's how you can [set Issue Templates up](https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/configuring-issue-templates-for-your-repository#creating-issue-templates):

1. **Navigate to the Repository:**
   - Go to the GitHub repository where you want to add issue templates

2. **Access the Settings:**
   - Click on the "Settings" tab in the repository

3. **Create a `.github` Directory:**
   - If not already present, create a `.github` directory in the root of your repository. This is where the templates will be stored.

4. **Create a `ISSUE_TEMPLATE` Directory:**
   - Inside the `.github` directory, create another directory named `ISSUE_TEMPLATE`.

5. **Create Template Files:**
   - Inside the `ISSUE_TEMPLATE` directory, you can create multiple markdown files for different types of issues (e.g., `bug_report.md`, `feature_request.md`, `custom_template.md`).

## How to Create GitHub Issue Templates

Here's a step-by-step guide to creating a simple issue template:

1. **Choose a Template Type:**
   - Decide what type of issue the template will be for (e.g., Bug Report, Feature Request, or custom one).

2. **Create the Markdown File:**
   - Create a new markdown file in the `ISSUE_TEMPLATE` directory. Name it according to the type of issue, like `bug_report.md`.

3. **Add Front Matter (Optional):**
   - Optionally, you can add a YAML front matter to your template to define a title, labels, or assignees automatically.
   ```yaml
   ---
   name: Bug report
   about: Create a report to help us improve
   title: "[BUG] "
   labels: bug
   assignees: ''
   ---
   ```

4. **Draft the Template Content:**
   - Write the content of your issue template. Here's an example for a bug report:
   ```markdown
   ## Bug Description
   A clear and concise description of what the bug is.

   ## Steps to Reproduce
   Steps to reproduce the behavior:
   1. Go to '...'
   2. Click on '...'
   3. Scroll down to '...'
   4. See error

   ## Expected Behavior
   A clear and concise description of what you expected to happen.

   ## Screenshots
   If applicable, add screenshots to help explain your problem.

   ## Additional Context
   Add any other context about the problem here.
   ```

5. **Save and Commit:**
   - Save the file and commit it to the repository. Your template is now active.

## Guidelines for GitHub Issue Templates

### Do's:
- **Keep It Simple:** Make your templates as straightforward and user-friendly as possible.\
However, do note that in order to create a template simple, yet to guide the users into providing all the data you need in a structured way, you may need to leverage more complex markdown/YAML code/
- **Be Specific:** Ask for specific information that will help in understanding and resolving the issue.
- **Use Placeholders:** Include placeholders like `[INSERT DESCRIPTION HERE]` to guide users on what to fill in.
- **Categorize:** Create separate templates for different types of issues (e.g., bugs, features, questions).
- **Update Regularly:** Modify templates as needed based on feedback and changes in the project.
- **Leverage the use of labels:** Pre-assign labels in the template that categorize the issue (e.g., bug, enhancement). This helps in automatic triaging and managing issues more efficiently. This is done via the `labels:` flag.


### Don'ts:
- **Overcomplicate:** Avoid making templates too long or complex; this might discourage users from filling them out.\
This refers to the templates the users see, not the YAML/Markdown code.
- **Use Jargon:** Avoid technical jargon that might be confusing to contributors who are less familiar with the project.
- **Ignore Feedback:** If users consistently skip or misunderstand parts of the template, iy might mean your template is not relevant for the user, or it requires too much information. Revise it to be clearer.

## Additional Tips

- **Default Templates:** If you want a default template for all issues, create a file named `config.yml` in the `.github/ISSUE_TEMPLATE/` directory with the following content:
  ```yaml
  blank_issues_enabled: false
  contact_links:
    - name: Support
      url: https://example.com/support
      about: Please visit our support page for questions unrelated to bugs or features.
  ```

- **Template Links:** You can add links to external documentation or resources within the template to provide additional guidance.

- **Testing:** After creating a template, try creating a new issue to see how the template appears and functions. Make adjustments if necessary.

- **Try to use `checklists`**: Not only they look nice on the issue reporting page, but they also give you an idea of how many of the ckecklist tasks have been filled or performed by the reporting user, with the aid of a visual indicator in the issue list.

```yaml
  - type: checkboxes
    id: checklist
    attributes:
      label: "Checklist"
      options:
        - label: "I have searched for similar issues."
          required: true
        - label: "I have included all necessary information."
          required: true
```

- **Combining GitHub Actions with Issue Templates**: You can create specific actions for your organization that does specific things when an issue is created.\
Example use cases:
- _when an issue is created, scan it for certain words, like 'security', 'vulnerability', 'critical'_
- then, assign certain labels to the issue
- then, assign the issue to the security coordinator in the team (or create an incident in SMA)
- send an email to the assignee or a group, etc.\
Other use case:
- _when an issue contains words like "'test feature', testing bug report', etc."_
- mark the issue as 'closed'

## Conclusion

GitHub Issue Templates are a powerful tool for maintaining a well-organized and efficient project.\
By standardizing the information provided in issues, you can save time, reduce confusion, and improve the overall quality of your project management.\
Start by setting up simple templates and refine them over time based on the needs of tge project and feedback from contributors members.
