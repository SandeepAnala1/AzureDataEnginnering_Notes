# CI/CD (continuous integration and continuous delivery/deployment)
Why not Continous Development & Continous deployment?
Think abt it
## Keywords
### Repository
A repository is a storage location for software code and its associated files, where the complete history of all changes is maintained. It is used to manage, share, and collaborate on projects.

### Branches
Branches are parallel versions of a repository, allowing developers to work on different features or fixes simultaneously without affecting the main codebase. Each branch can be merged back into the main codebase after development.

### Main/Master
Main or Master is the default primary branch in a repository, representing the production-ready version of the code. All significant updates and final code changes are typically merged into this branch.

### Feature
A feature branch is a separate branch created to develop a specific new feature or functionality. Once development and testing are complete, the feature branch is merged back into the main or master branch.

-------------------------------------------------------------------------------------------------------------------------------

In Azure DevOps, an organization is a fundamental unit for organizing and managing your development projects and resources. Here are some key points about how organizations function within Azure DevOps:

### Organization
An organization in Azure DevOps acts as a container for a set of related projects, providing a centralized place to manage users, permissions, and billing. It helps streamline collaboration and resource management across multiple teams and projects.
- Company/Department. In one account you can have multiple orgs

### Projects
Projects within an organization are individual containers for source code, builds, releases, and other assets. Each project can have its own repositories, pipelines, and work tracking boards, enabling teams to manage their work independently.
- We can have multiple projects in orgs

### Repository
A repository is a storage location for software code and its associated files, where the complete history of all changes is maintained. It is used to manage, share, and collaborate on projects.
- You can have multiple repos under a project

-----------------------------------------------------------------------------------------------------------------------------

### Main Branch
The main branch, often named `main` or `master`, is the primary branch in a repository that contains the stable and production-ready version of the code. Key characteristics include:

- **Stability**: The main branch should always be in a deployable state, containing thoroughly tested and reviewed code.
- **Deployment**: Releases to production are typically made from the main branch, ensuring that only the most reliable and verified code is deployed.
- **Merging Point**: Feature branches and other development branches are merged into the main branch once their changes are complete, tested, and reviewed.

### Feature Branch
A feature branch is a temporary branch created to develop a specific feature, bug fix, or experiment. Key characteristics include:

- **Isolation**: Feature branches isolate new development work from the main branch, allowing developers to work on new features or fixes without affecting the stability of the main branch.
- **Collaboration**: Multiple developers can work on different feature branches simultaneously, enabling parallel development and reducing bottlenecks.
- **Integration**: Once development in a feature branch is complete, the changes are merged back into the main branch after passing code reviews and automated tests.
- **Naming**: Feature branches are typically named descriptively, such as `feature/add-login`, `bugfix/issue-123`, or `experiment/new-ui`.

-------------------------------------------------------------------------------------------------------------------------------------

### Parallelism
Parallelism in software development, particularly in the context of version control and CI/CD (Continuous Integration/Continuous Deployment) systems like Azure DevOps, refers to the practice of performing multiple tasks or processes simultaneously to improve efficiency and reduce development time. 


![image](https://github.com/SandeepAnala1/AzureDataFactory_Notes/assets/163712602/4b21dd4a-eb6a-40ed-8421-56aef4c3648f)






