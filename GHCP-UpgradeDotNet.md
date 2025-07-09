# GitHub Copilot App Modernization (Upgrade for .NET) Runbook

## Document Summary

| **Document Item**        | **Current Value**                                                                 |
|--------------------------|------------------------------------------------------------------------------------|
| **Document Title**       | FACTORY Runbook: GitHub Copilot App Modernization (Upgrade for .NET) Runbook                    |
| **Program**              | Cloud Accelerate Factory                                                          |
| **Date Last Modified**   | 08-07-2025                                                                         |
| **Date Last Reviewed**   | 08-07-2025                                                                         |
| **Status**               | Under Review                                                                           |
| **Document Description** | This document provides the guidelines for Upgrading .Net using GHCP VS extension for Cloud Accelerate Factory. |

---

## Change Log

This section represents the change history of the document. Revisions of the document must be tracked by identifying a new version number, the date it was modified, the person making the change, and the reason for the change.

| **Date**     | **Version** | **Change Description**                          | **Author**         | **Reviewer**             | **Approver**        |
|--------------|-------------|--------------------------------------------------|---------------------|---------------------------|----------------------|
| 08-07-2025   | 1.0         | Initial draft                                   | Ajinkya Bagwe      | Santanu Panchadhyay      | --      |

---

## Contents

- [**Introduction**](#introduction)
- [**Upgrade for .NET FAQs**](#upgrade-for-net-faqs)
- [**Prerequisites**](#prerequisites)
- [**Installation instructions**](#installation-instructions)
- [**Starting with the Upgrade Process**](#starting-with-the-upgrade-process)
- [**Visual Guide: How the Agent Fixes Code Errors & Other Issues During Upgrade**](#visual-guide-how-the-agent-fixes-code-errors--other-issues-during-upgrade)

## Introduction

GitHub Copilot app modernization - upgrade for .NET is a powerful Visual Studio extension that works with you to upgrade projects to newer versions of .NET, upgrade your dependencies, and apply code fixes.

GitHub Copilot app modernization is distributed as a Visual Studio extension, and is an interactive upgrade process.

## Upgrade for .NET FAQs

### 1. What can the tool do?

- The GitHub Copilot app modernization tool for .NET is a Visual Studio extension that assists in upgrading .NET projects to newer versions. It analyzes the project, creates an upgrade plan, runs upgrade tasks in a local Git branch, auto-fixes code issues, tracks progress with access to logs and changes, and learns from the interactive session to improve results.

### 2. What can the tool upgrade?

- GitHub Copilot app modernization - upgrade for .NET currently focuses on migrating your projects from one version of
.NET to another. For example, upgrading from .NET Core 3.1 or .NET 6, to .NET 9.

### 3. Does the tool assist with upgrading dependencies after migration?

- Yes, It also upgrades dependencies and fixes errors in the code post-migration.

### 4. Which project types is the tool designed to work with?

- Besides upgrading the target framework, the tool can work with the following types of projects:

  - Azure Functions.
  - Console apps and class libraries.
  - Web technologies such as:
  - MVC
  - Blazor
  - Razor Pages
  - Web API
  - Desktop technologies such as Windows Forms and Windows Presentation Foundation.
  - Test projects such as MSTest and NUnit.

### 5. What upgrade path the tool can support?

- The following upgrade paths are supported:

  - Upgrade projects from .NET Core to .NET.
  - Upgrade projects from older versions of .NET to the latest.
  - Modernize your codebase.

### 6. Is the tool capable of upgrading projects written in any programming language?

- Currently GitHub Copilot app modernization supports upgrading projects coded in only in **C#**.

### 7. Does the tool support .NET Framework projects?

- It doesn't support .NET Framework projects. (First upgrade the project to .NET with the [Upgrade Assistant Tool](https://learn.microsoft.com/en-us/dotnet/core/porting/upgrade-assistant-overview)).

### 8. What types of repositories does the tool support?

- Only Git repositories are supported.

### 9. Are the upgrade suggestions provided by the tool guaranteed to follow best practices?

- There's no guarantee that the upgrade suggestions are considered best practices.

### 10. Does the tool retain learnings from previous upgrade sessions or user-provided code corrections?

- The LLM doesn't persist learning from the upgrade. Meaning, code fixes and corrections you provide during the upgrade process don't persist and can't be remembered for future upgrades.

### 11. On which operating systems can the tool run?

- It only runs on Windows.

## Prerequisites

- Windows Operating System
- [Visual Studio 2022 version 17.14 or newer](https://visualstudio.microsoft.com/downloads/).
- [.NET desktop development workload](https://learn.microsoft.com/en-us/visualstudio/install/modify-visual-studio?view=vs-2022&preserve-view=true#change-workloads-or-individual-components).
- [Sign in to Visual Studio using a GitHub account](https://learn.microsoft.com/en-us/visualstudio/ide/work-with-github-accounts) with [Copilot access](https://docs.github.com/copilot/about-github-copilot/what-is-github-copilot#getting-access-to-copilot).

- Supported subscription plans:
  - Copilot Pro
  - Copilot Pro+
  - Copilot Business
  - Copilot Enterprise

(If you change subscriptions, you must restart Visual Studio.)

- Code must be in a local Git repository.
- Code must be written in C#.
- Optional but recommended: Use **GitHub Copilot agent mode** for the upgrade process. For more information, see [Use Copilot agent mode in Visual Studio](https://learn.microsoft.com/en-us/visualstudio/ide/copilot-agent-mode?view=vs-2022&preserve-view=true).

## Installation instructions

Visual Studio Extension

- Open Visual Studio.

- If the **Open Recent \ Get Started** window opens, select the **Continue without code** link.

- Select the **Extensions > Manage Extensions** menu to open **Extension Manager**.

- Select the **Browse** tab.

- Enter **GitHub Copilot app modernization** into the search box.

- Select **GitHub Copilot app modernization**, and then select Install.

  ![Visual Studio Extension](./GHCP-Images/upco24.png)

- To validate the extension installation, right-click on the solution you want to upgrade. You should see the option **'Upgrade with GitHub Copilot'**. Refer to the image below.

  ![Upgrade with GitHub Copilot Option](./GHCP-Images/upco25.png)

## Starting with the Upgrade Process

The following steps and observations pertain to upgrading from **.NET Core 2.1 to .NET 8**. A similar process can be followed for other version upgrades.

- Right-click on the solution or project and select **Upgrade with GitHub Copilot**.
  
  ![Upgrade with GitHub Copilot](./GHCP-Images/upco01.png)
  
- Select the version to upgrade to

  ![Upgrade to which version](./GHCP-Images/upco02.png)

  ![Select the .Net version](./GHCP-Images/upco03.png)

- Confirm the source and target branch name.

  ![Confirm Source & Target Branch](./GHCP-Images/upco4.png)

- Once confirmed the agent will start the analysis and ask whether to fix the security vulnerabilities now or later.

  ![Analysis 1](./GHCP-Images/upco05.png)

  ![Analysis 2](./GHCP-Images/upco06.png)

  ![Analysis 3](./GHCP-Images/upco07.png)

- Ask agent to handle the security vunerabilities during the upgrade, Once done it will give the upgradation plan as a markdown file.

  ![Upgrade Plan](./GHCP-Images/upco08.png)

- We can also modify the upgrade plan—for example, by setting a specific version for a particular package if needed—and then save the changes.

  ![Accept Upgrade Plan](./GHCP-Images/upco09.png)

- After completing the steps, click 'Continue to Upgrade' in the Co-Pilot chat window.

- In the Progress tab, upgrade tasks are listed and marked as completed (highlighted in green) when successfully finished. If the agent encounters an issue, the task is halted (highlighted in red), and the agent prompts the user to investigate the problem.

  ![Task Series](./GHCP-Images/upco12.png)

- Assistance from the Agent can be utilized to address the encountered issue.

  ![Encountered Issue !](./GHCP-Images/upco11.png)

- Agent can also assist in fixing the errors.

  ![Fix Error ?](./GHCP-Images/upco13.png)

- The agent will also prompt to include any missing packages and provide the option to either add them manually or allow the agent to add them automatically.

  ![Include Package ?](./GHCP-Images/upco14.png)

  ![Add Package](./GHCP-Images/upco15.png)  

- The agent will create a checkpoint for tasks whenever code or package-related changes are made. This allows you to revert to the previous state in case any unintended changes occur.

- Refer below images for issues encountered during **Run unit test** task:
  
  ![Run unit test task #1](./GHCP-Images/upco16.png)

- Agent can provide guidance in diagnosing and fixing integration test issues.

  ![Run unit test task #2](./GHCP-Images/upco17.png)

  ![Run unit test task #3](./GHCP-Images/upco18.png)

  ![Run unit test task #4](./GHCP-Images/upco19.png)

  ![Run unit test task #5](./GHCP-Images/upco20.png)

- The agent can also execute terminal commands on our behalf, if permitted.

  ![Run unit test task #6](./GHCP-Images/upco21.png)

  ![Run unit test task #7](./GHCP-Images/upco22.png)

- Once all tasks in the upgrade plan are completed, the agent will notify the user and inquire if any further assistance is needed. The solution can then be built to verify if it compiles successfully..  

  ![Run unit test task #8](./GHCP-Images/upco23.png)

## Visual Guide: How the Agent Fixes Code Errors & Other Issues During Upgrade

- The following code issues were encountered during the upgrade from ASP.NET MVC 5 to .NET 8 and were resolved with guidance from the agent.

  ![Code Fix ASP.NET MVC 5](./GHCP-Images/asp06.png)

  ![Code Fix ASP.NET MVC 5](./GHCP-Images/asp07.png)

  ![Code Fix ASP.NET MVC 5](./GHCP-Images/asp08.png)

  ![Code Fix ASP.NET MVC 5](./GHCP-Images/asp09.png)

- The screenshot below shows a prompt given to the agent to address a security vulnerability encountered during the migration from ASP.NET MVC 6 to .NET 8.
  
  ![Security vulnerability ASP.NET MVC 6](./GHCP-Images/mvc07.png)

- The screenshots below illustrate the agent detecting a missing NuGet package reference and prompting the user to add it.

  ![Missing Reference ASP.NET MVC 6](./GHCP-Images/mvc09.png)

  ![Missing Reference ASP.NET MVC 6](./GHCP-Images/mvc10.png)

- The screenshots below demonstrate using the agent's assistance to fix an issue by attaching the relevant .cs file where the error occurs.

  ![Configuration Error ASP.NET MVC 6](./GHCP-Images/mvc11.png)

  ![Configuration Error ASP.NET MVC 6](./GHCP-Images/mvc12.png)

  ![Configuration Error ASP.NET MVC 6](./GHCP-Images/mvc13.png)

- As shown in the screenshots above, the issue persisted. It was observed that the agent had upgraded the package to the latest version, but the issue was resolved by downgrading the package.
Steps taken:
  1. Restored to a checkpoint to undo the changes made while attempting to fix the issue.

  2. Prompted the agent to downgrade the package

  ![Package downgrade ASP.NET MVC 6](./GHCP-Images/mvc14.png)

[*Go to contents*](#contents)
