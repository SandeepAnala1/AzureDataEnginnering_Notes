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


# Configuring GIT in ADF
### Step 1
<img width="959" alt="image" src="https://github.com/SandeepAnala1/AzureDataFactory_Notes/assets/163712602/f72feded-7779-46c3-ace9-5ccb9e037e9b">

### Step 2
![image](https://github.com/SandeepAnala1/AzureDataFactory_Notes/assets/163712602/7f117f66-5bea-4d18-9043-d16b982e1513)

### Step 3
- Under collaboration branch you can use any, either feature or main
![image](https://github.com/SandeepAnala1/AzureDataFactory_Notes/assets/163712602/6941b019-1f58-4a07-bc0a-cc3727eb34a8)

### Step 4
![image](https://github.com/SandeepAnala1/AzureDataFactory_Notes/assets/163712602/948d154b-7601-49e4-bf3b-a03b72b16228)

Branch policies in Azure DevOps (and other version control systems) are rules and configurations applied to branches to enforce quality and security standards. They help ensure that code changes meet certain criteria before being merged into the main or production branches. Here are key aspects of branch policies:

## Branch Policies
Branch policies in Azure DevOps provide a way to enforce consistent practices across your team and ensure high code quality. Key policies include:

- **Pull Request Reviews**: Require pull requests to be reviewed and approved by one or more designated reviewers before merging. This helps catch potential issues and ensures adherence to coding standards.
- **Build Validation**: Automatically trigger a build and run tests for the code in a pull request. The pull request can only be completed if the build succeeds and all tests pass, ensuring that new code doesn’t break the build.
- **Minimum Number of Reviewers**: Specify a minimum number of reviewers that must approve a pull request before it can be merged. This policy increases the chances of catching bugs and maintaining code quality.
- **Comment Resolution**: Require all comments in a pull request to be resolved before the request can be completed. This ensures that all feedback has been addressed.
- **Work Item Linking**: Enforce that pull requests are linked to work items (e.g., tasks, bugs) before they can be merged. This helps in tracking changes and understanding the context behind code modifications.
- **Branch Protection**: Prevent direct pushes to certain branches (e.g., `main` or `master`). All changes must go through a pull request process, ensuring that no unreviewed or untested code is introduced.

## How to raise a Pull request?
### Step 1: Create pull request
![image](https://github.com/SandeepAnala1/AzureDataFactory_Notes/assets/163712602/ad52c8f5-1fab-4a59-b246-ec9b349364d0)

### Step 2: Add reviewers
![image](https://github.com/SandeepAnala1/AzureDataFactory_Notes/assets/163712602/8ba4e4fd-14a8-44f6-9aa3-b896036e3c56)

### Step 3: Approve & Complete(Merge)
![image](https://github.com/SandeepAnala1/AzureDataFactory_Notes/assets/163712602/e9dc66d0-5bdf-4b9d-8192-836c5291df1e)
![image](https://github.com/SandeepAnala1/AzureDataFactory_Notes/assets/163712602/56e9c088-ecdd-4062-87d9-bfac7365d63b)

### Addl: Revert the merge, we will not do in general
![image](https://github.com/SandeepAnala1/AzureDataFactory_Notes/assets/163712602/06aa7d0c-ccf0-446e-a541-6fadbe477a08)

----------------------------------------------------------------

## Git Mode
In Git Mode, changes are made locally on a developer's machine and then committed to the repository. This mode leverages Git’s branching and version control features, allowing developers to work offline and merge changes back into the main codebase later.

## Live Mode
In Live Mode, changes are made directly on the live server or environment, often used for immediate updates. This mode does not involve local version control, posing risks to stability and traceability as changes are applied directly without prior review.

# Significance of Live mode
- Even though our code is in main branch, our code is not deployed into development instance. We can't schedule the pipelines or triggers.
- So to do this code has to come to live mode

### Workflow in general
![image](https://github.com/SandeepAnala1/AzureDataFactory_Notes/assets/163712602/804986a1-a253-4250-9c0c-6da3484a53f6)

-------------------------------------------------------------------

### Generic cycle of our code travelling in Ops
- Develop our code in feature branch
- Merge into Collaboration (Master/main)
- Deploy code to Live mode in development instance
    - Publish
    - Build Pipeline
- Deploy code to Live Mode in testing instance
    - Release Pipeline
- At last deploy code to Live Mode in production Instance
    - Release Pipeline

----------------------------------------------------------------------
## Old  CI/CD flow
1.	Each user makes changes in their private branches.
2.	Push to master isn't allowed. Users must create a pull request to make changes.
3.	Users must load the Data Factory UI and select Publish to deploy changes to Data Factory and generate the ARM templates in the publish branch.
4.	The DevOps Release pipeline is configured to create a new release and deploy the ARM template each time a new change is pushed to the publish branch.

![image](https://github.com/SandeepAnala1/AzureDataFactory_Notes/assets/163712602/cd91bba5-28ea-454d-859e-ad2fca01feac)

## The new CI/CD flow
1.	Each user makes changes in their private branches.
2.	Push to master isn't allowed. Users must create a pull request to make changes.
3.	The Azure DevOps pipeline build is triggered every time a new commit is made to master. It validates the resources and generates an ARM template as an artifact if validation succeeds.
4.	The DevOps Release pipeline is configured to create a new release and deploy the ARM template each time a new build is available.

![image](https://github.com/SandeepAnala1/AzureDataFactory_Notes/assets/163712602/1c30b441-dd00-45df-8111-8707d08393ee)

## What changed?
1.	We now have a build process that uses a DevOps build pipeline.
2.	The build pipeline uses the ADFUtilities NPM package, which will validate all the resources and generate the ARM templates. These templates can be single and linked.
3.	The build pipeline is responsible for validating Data Factory resources and generating the ARM template instead of the Data Factory UI (Publish button).
4.	The DevOps release definition will now consume this new build pipeline instead of the Git artifact.




















