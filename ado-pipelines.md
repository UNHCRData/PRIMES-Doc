## Intro
As part of development process we have to add/change functionality in Powerplatform components:
 - Dataverse solution
 - Power Pages (Portal) configuration

Below is described process of making changes from Developer point of view:

## 1. Create development branch
 
Create a development branch using naming convention: ```users/{alias}/{functionality_description}``` based on [```development branch```](https://dev.azure.com/PRIMES-DevOps/PRIMES%20%E2%80%93%20Self%20Services/_git/PRIMES-Self-Services?version=GBdevelopment&_a=contents)

## 2. Make your changes in development environment 

Make your changes in [DEV env](https://dev.azure.com/PRIMES-DevOps/PRIMES%20%E2%80%93%20Self%20Services/_wiki/wikis/PRIMES-%E2%80%93-Self-Services.wiki/902/PRIMES-Self-Onboarding-Wiki) (either in Dataverse solution / Dataverse Power automate flows)  or in Portal Pages configuration.

## 3. Run  scripts to get the latest code changes from the Dev environment

**ExportTool.cmd**
This tool can be used to export either data or solutions (both managed and unmanaged) from an org to $(root)\source\solutions folder. 
As a prerequisite to export solutions, powerapps cli must be downloaded from  https://aka.ms/PowerAppsCLI. 
* To export portal data, run the tool from the root of repository as below & follow on-screen instructions
```
ExportTool.cmd portal
```
* To export solution, run the tool as below. The export has one positional argument. It is the url from which to export. If not provided, the script will ask to provide it. It is simple to modify the script to support multiple solutions in case of need.
```
ExportTool.cmd solution
```  

## 4.Identify your changes

Identify your changes in the code repository. If you edited only portal pages configuration, you can skip updating code for solution.

If you worked only with specific configuration in the portal - you can revert other changes to leave only your changes.

## 5. Commit & Push you changes. Create a PR for a code review.

Once you verified your changes you can commit and push your changes to git. Go to [PR ADO space](https://dev.azure.com/PRIMES-DevOps/PRIMES%20%E2%80%93%20Self%20Services/_git/PRIMES-Self-Services/pullrequests?_a=mine) and create a PR from your branch to ```development``` branch. 

*Note: in case of any merge conflicts, please merge ```development``` branch to your branch locally and resolve all the conflicts. Push the resolution again to git.*

 
In PR please specify work-item you are working on and add explanatory description about your change and test results.

To complete merge you need to receive approvals, resolve all comments,  as well automated [PR build](https://dev.azure.com/PRIMES-DevOps/PRIMES%20%E2%80%93%20Self%20Services/_build?definitionId=106) should finish successfully for your branch.

## 6. Create release build

Once your changes are in development branch - you can run [a release build](https://dev.azure.com/PRIMES-DevOps/PRIMES%20%E2%80%93%20Self%20Services/_build?definitionId=108) and as result you will receive build artifacts with injected build version in it.

Dataverse has build version as solution version.

Portal receives the same version in deployment-profiles for UAT/PROD.  
