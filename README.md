# Azure DevOps - Dotnet Test Manager Extension for VS Code

This extension provides enhanced testing capabilities within VS Code for Dotnet projects, specifically focusing on integrating with Azure DevOps test cases.

## Overview

VS Code is an excellent IDE for cross-platform code development and testing, and offers robust support for various programming languages, including the .NET platform. The latest C#/Dotnet extension further enhances .NET development within VS Code.

However, noticed that VS Code is still missing some critical features, specifically for Mac users when it comes to testing. One such feature is the ability to associate automated tests with Azure DevOps test cases. This feature is incredibly valuable for end-to-end test automation, as it facilitates running tests from pipelines (both build and release), leading to comprehensive automated test execution and reporting.

I developed this extension to bridge the gap and provide the [Same Visual Studio Experience](https://learn.microsoft.com/en-us/azure/devops/test/associate-automated-test-with-test-case?view=azure-devops) for all testers using dotnet and Azure DevOps test management.


## Key Features

1.  **Automated Test Discovery:** Discovers tests from Dotnet solutions/projects (lists tests without grouping in the current version).
2.  **Test Execution:** Run and debug tests within VS Code, similar to the built-in test explorer.
3.  **Azure DevOps Integration:** Options for runtime test discovery, running all tests, and configuring Azure DevOps connection settings (Organization and Project).

## How to Use the Extension

### Discovering, Running, and Debugging Tests

1.  Search and install the "Azure DevOps - Dotnet Test Manager" extension in VS Code.
2.  Open a Dotnet test project containing E2E Automated Dotnet Tests.
3.  Locate the Azure DevOps icon in the activity bar (left-hand side of VS Code). ![Main View](https://raw.githubusercontent.com/uppadhyayraj/azure-devops-dotnet-test-manager/refs/heads/main/ADOTM-Main%20View.png)
4.  Open the extension; it will build the project and display all the tests.
5.  To run or debug a test, hover over it and click the play or debug icon. Results will be shown against the test (Passed/Failed/Skipped).
6.  To rediscover new or updated tests, click the refresh button at the top of the explorer.

### Associating Test Automation with DevOps Tests

#### Prerequisites

1.  Test cases created in Azure DevOps, with test case numbers available.
2.  A Personal Access Token (PAT) with Work Items and Test Management - Read & Write permissions. (See: [https://learn.microsoft.com/en-us/azure/devops/organizations/accounts/use-personal-access-tokens-to-authenticate?view=azure-devops&tabs=Windows#create-a-pat](https://learn.microsoft.com/en-us/azure/devops/organizations/accounts/use-personal-access-tokens-to-authenticate?view=azure-devops&tabs=Windows#create-a-pat))
3.  VS Code configured for the Dotnet project. (See: [https://code.visualstudio.com/docs/languages/dotnet](https://code.visualstudio.com/docs/languages/dotnet))

#### Associating Automation

1.  Navigate to the "Azure DevOps - Dotnet Test Management" extension. Right-click on a test and select "Associate to Test Case." ![Right Click Menu](https://raw.githubusercontent.com/uppadhyayraj/azure-devops-dotnet-test-manager/refs/heads/main/AssociateTestAutomation.png)
2.  A window will open in VS Code with pre-populated "Automated Test Name" and "Automated Test Storage," along with a section to search for Azure DevOps test cases. 
3.  Enter the Azure DevOps test case ID in the "Search by test case Id or title" field and click "Search." A popup to configure Azure DevOps will appear. ![Associate Automation Window](https://raw.githubusercontent.com/uppadhyayraj/azure-devops-dotnet-test-manager/refs/heads/main/DevOpsSettings.png)
4.  Click "Yes" and provide your Azure DevOps Organization, Project, and PAT. ![DevOps Config](https://raw.githubusercontent.com/uppadhyayraj/azure-devops-dotnet-test-manager/refs/heads/main/AzureDevops-configs-1.png)
5.  View the search results (if the test exists), showing the test ID and Title. Select the test case you want to associate with the automated test. ![ADO Search Result](https://raw.githubusercontent.com/uppadhyayraj/azure-devops-dotnet-test-manager/refs/heads/main/Search-Results.png)
6.  Clicking the search result will expand it. Click "Save" to update the Azure Test case. A notification will confirm the successful save. ![Final Config](https://raw.githubusercontent.com/uppadhyayraj/azure-devops-dotnet-test-manager/refs/heads/main/Save-Automation.png)
7.  Validate the update in Azure DevOps under the "Associated Automation" section. The Automation Status of the test case should be "Automated." ![Test in DevOps](https://raw.githubusercontent.com/uppadhyayraj/azure-devops-dotnet-test-manager/refs/heads/main/Saved-ADOTest-old.png)

## Known Issues

No known issues at this time. Work in progress to support multiple test projects (currently supports only one).

## Release Notes

### 1.0.0

Initial release of dotnet-solution-tree.
