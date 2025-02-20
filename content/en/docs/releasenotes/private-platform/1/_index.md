---
title: "1.5"
url: /releasenotes/private-platform/1-5/
description: "Release notes for version 1 of Private Mendix Platform"
weight: 10
tags: ["Private Mendix Platform", "Private Platform"]
---

These release notes cover changes made to the [Private Mendix Platform](/private-mendix-platform/).

## 1.5.2

### Release date: November 30, 2023

This release brings a number of additional functionalities for the Platform related to getting help, supporting manual deployment processes, as well as a number of fixes and minor improvements.

#### New Features

##### Help Button

* For developers, we have added a **Help** button to the Developer Portal and a **Help** page that allows you to download a contextual information bundle. Share this bundle with your Certified Partner, or if your organization is certified, with your platform support team, using the instructions as displayed on the **Help** page. This will provide them with the technical information (logs, events, and so on) to streamline troubleshooting.
* Company administrators can normalize support processes by inputting the proper Support process under the **Settings** > **General** > **Support** tab, using a Rich Text input field.

##### Support for Manual Deployments

* For developers, it is now possible to select a **Manual Deployment** target as one of your cluster options. When you deploy to these targets, your build artifact will be transported to the predefined storage bucket or artifact registry, so that the Ops teams can take over from there and deploy to any further isolated production infrastructure. Optionally, you can configure a Webhooks call to to start any automation pipelines on their side as well.
* For cluster administrators, if your organization has isolated production clusters that require manual Ops intervention to deploy to, you can now predefine **Manual Deployment** targets in the Cluster Manager (**Settings** > **DevOps** > **CI/CD** > **Cluster Manager**). These are storage buckets or artifact registries where the built application package can be staged for any following manual steps. You can add these in the same way as you would add a new cluster, but select the Manual Deployment type and input the necessary authentication to write to the storage bucket. Optionally, you can also add Platform-level Webhook automation to automatically initiate any Ops processes on that side.

#### Improvements

##### General Settings and Locale Preferences

* We have added a **General** tab to the **General Settings** page (accessible to administrators), where Customer and Certified Partner information can be saved. 
* The General section also includes locale preferences. Changing your country sets locale-dependent formats, such as numbers, date and time, or currency, to the preferred format of the selected country. The settings are applied to the Private Mendix Platform (for example, in the Marketplace or Developer Portal). They do not affect the date and time or locale settings of your apps.

##### Helm Charts in the Installer

The Private Mendix Platfrom installer now uses explicitly defined Helm charts that are visible in the file and folder tree, instead of the hard-coded ones that were part of the installer's own code.

#### Fixes

We have resolved the following issues:

* An unrelated error popup related to webhooks would appear at top of the DevOps page.
* Hidden Marketplace item versions would still appear when viewed in Studio Pro.
* Studio Pro web sign-in password visibility icon would flash out of view.
* App settings would add validation to changing an app name.
* A pagination issue would occur when using Azure DevOps as the version control system during a package build.
* The indicator would permanently rotate when adding wrong Azure DevOps credentials.
* An error would occur when transferring ownership to another user, and the new owner would be added without removing the previous owner.
* New user logins with Azure DevOps would cause errors during onboarding.
* The display of Git user IDs would diverge between version control hosts in the team overview.
* In some cases, errors would occur during Azure DevOps app creation with Studio Pro.
* An administrator clicking on the **MxDock** link would result in an error.

#### Known Issues

* The new Installer Helm charts may affect scripted deployments. If you are a Certified Partner automating the Platform deployments, validate your automations to ensure that they continue to work correctly.
* Due to introduction of a different cloning and copying mechanism for new branches in Studio Pro, we are temporarily unable to support newer Studio Pro 9.24 LTS patch versions until this matter is resolved. This issue will be resolved in a future release.

## Private Mendix Platform Release

### Release date: November 15, 2023

Private Mendix Platform provides an end-to-end Mendix developer experience to customers who need to enjoy it on their private infrastructure. It provides an environment where you can develop and deploy your applications within your own enterprise security boundary to ensure the highest levels of data security and compliance. You can integrate Private Mendix Platform with your existing IT infrastructure and adapt it to your specific business requirements. For more information, see [Private Mendix Platform](/private-mendix-platform/).

Private Mendix Platform has the following features.

{{% alert color="info" %}}
Exact feature support varies depending on chosen configuration. Please consult feature-specific documentation for more detailed information.
{{% /alert %}}

* Mendix Studio Pro integration and one-click app deployment even with no access to public internet
* Mendix developer experience hosted entirely within any virtual private cloud
* Support for SSO authentication for Private Mendix Platform and Studio Pro through your own identity provider (IdP)
* A private version of the Mendix Marketplace, with all contents hosted entirely within your Private Mendix Platform, accessible in-browser and directly from Studio Pro
* SCM repository support for Gitlab, GitHub, Bitbucket and Azure DevOps, to be used as source code repository for your projects
* CI/CD capabilities out-of-the-box, with additional support for integrations with Jenkins and Tekton; leverage our predefined templates or implement your own custom templates
* Operational capabilities such as basic log browsing and metrics through integrations with Loki and Grafana
* Governance features like application landscape management, marketplace administration, user group management, as well as various developer platform feature settings and action logs
