> Python Flask Software Application README: This template includes writing instructions and boilerplate text that 
> you can customize, use as-is, or completely replace with your own text. This text is indicated in {curly brackets}. Make sure you replace the placeholders with your own text.

# {Project Name}

{Include the project URL and project contributors underneath the project name if applicable, e.g., project is
maintained in a shared repository.}

## Table of contents

1. [Project description](#project-description)
2. [Project setup](#project-setup)
3. [Contributing guidelines](#contributing-guidelines)
4. [Project documentation](#project-documentation)
5. [Additional information](#additional-information)
6. [Terms of use](#terms-of-use)

## <a id='project-description'>Project description</a>

### What kind of software is this?

> Hint: Even if a packaged software application is described as an 'end-product', it offers a service. The customer 
> can override manual processes through the use of a software product. What are those processes and how does the 
> software offer something different besides obfuscating those processes? With that in mind, define the purpose of the 
> software application.

{Write the description here}
__________________

### Who can use this app?

> Hint: Typical application end-user

{Write the description here}

__________________

### How is the project is organized?

#### Project conventions

> Hint: What are the official 'sources of truth' for 'standardization'? If I had a penny for every time I listened 
> to the term, "it standardizes things" with no response on how, I'd be retired.
 E.g., PEP defines the naming convention guidelines for Python.

{Write the description here}

#### Project organization

> Hint: Does the project work align with the typical structure of the framework it's based on, is the project structure 
> customized or is it a bit of both?
> E.g., The best code is code that's already written. You can be lazy, making the next best thing. A 
> standard project builds off of boilerplate code from an official site or verified public repositories.

{Write the description here}

## <a id='project-setup'>Project setup</a>

### Pre-requisites

Before using {Project name}, install necessary pkgs:

* [<LINK_URL>](<URL>): <LINK_DESC>

### Requirements

> Hint: Write out requirements as a simple list; For more involved requirements, include substeps, code samples, or 
screenshots that help you keep track of this information

#### Install {Project Name}


1. {Write the step here.}

   {Optional: Explanatory text if this is a workaround/unconventional}

   {Optional: Include a code sample or screenshot that helps your users complete this step}

   a. {Substep 1}

   b. {Substep 2}

2. {Write the step here.}

#### Configure {Project Name}

{Write any steps here.}

#### Run {Project Name}

{Write any steps here.}

#### Troubleshoot {Project Name}

{Write any steps here.}

<table>
  <tr>
   <td>
    Issue
   </td>
   <td>
    Fix
   </td>
  </tr>
  <tr>
   <td>
    {Describe the issue here}
   </td>
   <td>
    {Describe how to resolve it}
   </td>
  </tr>
  <tr>
   <td>
    {Describe how to resolve it}
   </td>
   <td>
    {Describe how to resolve it}
   </td>
  </tr>
  <tr>
   <td>
    {Describe the issue here}
   </td>
   <td>
    {Describe how to resolve it}
   </td>
  </tr>
</table>

## <a id='contributing-guidelines'>Contributing guidelines</a>

_Note: There are no definitive guidelines for contributing to a project; Add/remove/modify any process recommended 
for maintaining projects based on their complexity._

#### Creating a CHANGELOG
A changelog is the best option for an overview of the versioning process, without being redundant. Any 
specific information about software changes is available through git itself_

Maintaining a CHANGELOG file is always recommended for a quick overview of how the project is progressing.
1. Checkout main locally
2. Manually edit a CHANGELOG template or create a changelog with a CHANGELOG generator
3. Commit the CHANGELOG to the remote branch

#### Branching strategy

_Note: This process isn't necessary for programs, thank goodness._

Create these branches to extend the capability of an application. 

###### Versioning branches

- [MAJOR_VERSIONING_NUM].[MINOR_VERSIONING_NUM].[PATCH_VERSIONING_NUM]

###### Group settings
  - `<VERSION-RELEASE-#>/<FEATURE_NAME>/<CONTRIBUTOR>`
  - `<VERSION-RELEASE-#>`: Refer to [SemVer](https://semver.org/) for details
  - `<FEATURE_NAME>`: Descriptive title for the feature
  - `<CONTRIBUTOR>`: e.g., GitHub account name

##### Staging and releasing versioned repos

###### I. Pre-release

Once work on versioned branches is completed, a pull-request can be created to merge the branch into `dev`.

Dev branches are typically staging/pre-release branches, where those changes are tested.

Once the staging branch is tested, stable code can be merged into `main`, a production/release branch.

###### II. Pull-request

Instead of merging on local, please remember to create a pull-request.

`bash ./<REPO-NAME>/version-control/pull-request.sh`

To do this manually:
`git request-pull [-p] <VERSION-RELEASE-#> https://github.com/DaniSestan/<REPO_NAME> dev `

###### III. Merge-request

Once a pull-request is reviewed, accepted and merged, the merge request data can then be used to document those changes through the Markdown Changelog Generator.

`bash ./<REPO-NAME>/version-control/merge-request.sh`

To do this manually:
`git push -o mr.<END> origin <START>`

#### Maintaining versioned repos

Maintaining the permissions, the branching strategy, and a consistent timeline between each repo lessens the probability of a bottleneck when releasing any new changes.

Permissions

| Repository | Visibility |
|-------------|-------------|
| Staging     | Private     |
| Production  | Public      |

Timeline

_Note: This varies based on the complexity of the software project_

| Version | Change |
|---------|--------|
| Major   |        |
| Minor   |        |
| Patch   |        |

_Once changes are pushed to `main` in the staging repo, allow some time for those changes to 'soak' in the 'dev' 
branch._

| Feature | Timeline |
|---------|----------|
| Major   |          |
| Minor   |          |
| Patch   |          |

#### Tagging branches

Please use standard tagging conventions to define each branch with its version release number, feature name, and the contributor.

Typical Branch Naming Conventions in Group Settings

`git tag -a <TAG_VAL> -m "<TAG_TYPE>"`

- `git tag -a v<VERSION_#> -m 'version #'`
- `git tag -a <FEATURE_NAME> -m 'feature name'`
- `git tag -a <CONTRIBUTOR> -m 'contributor'`

To check tagging info:
`git tag -n9`

## <a id='project-documentation'>Project documentation</a>

Standard project docs are located in the `{PROJECT_ROOT}` folder.

- README
- LICENSE
- CHANGELOG

Please upload any other supporting documentation in the `{PROJECT_ROOT}/docs` folder.

* {Reference link: Description}

## <a id='additional-information'>Additional information</a>

### Support resources

* {Reference link: Description}

## <a id='terms-of-use'>Terms of use</a>

{Project Name} is licensed under [MIT](https://commons.wikimedia.org/wiki/Template:X11)