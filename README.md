
# Tosca test case Review Checklist
 *This document serves as a starting point for your team's test case review checklist. Please feel free to amend and extend it to be of most use for your needs.*
 
 

## General
 - [ ] No orphans. Every Test Case is linked to a requirement. Every Test
       Case is linked to an execution list. (Use virtual folders to
       check/prove).
 - [ ]    If you have a corresponding test case in another system (e.g. QC, Jira, etc.), the id is documented in a field in Tosca.
 - [ ] All test cases are runnable on DEX (Provide a proof of a successful run).
 - [ ] There are no references in the sandbox component folder from outside (Use virtual folder to check/prove).
 - [ ] Component Folders are used to structure the repository.
 - [ ] The work state of all items is set correctly.
 - [ ] Buffer names describe their content clearly and are spelled consistently (as per guidelines, if exists. e.g. camel case, pascal case, etc.)
 - [ ] Buffers are deleted at the beginning of the test case.\
 - [ ] No access to a buffer that has not been created by the same test case
 - [ ] Synchronization options on folders are set correctly
 
# Requirements
 - [ ] Requirements are risk-weighted by the business always to have a prioritization for automation and execution.
  
# Modules
 - [ ] There is only one set of common modules in the repository.
 - [ ]    Modules are cut into sections of the page
 - [ ]    Modules are named “application | page” or “application | page | section”
 - [ ]    Cardinality in attributes is set correctly

# Test Case Design
 - [ ]   The root attributes have the following structure: "Administration" for all admin information (below as per agreed policy), "Precondition" with all attributes needed for the test case setup (e.g. test data), "Process" with all information relevant for the essence of the test case. "Verification" for all verification information and "Postcondition" for all teardown and TDS-Update information.
 - [ ]   All test cases follow the common naming convention by the team/company.
 - [ ]    The instance name gives a clear understanding of what the test case does.
 - [ ]    There are no empty Values in any Field. If an Attribute is not relevant, {NULL} is used, if an attribute is relevant, but Empty, {EMPTY} is used.
 - [ ]    Classes are used where possible.

# Templates
 - [ ]    The test case is a template with a test sheet attached (no standalone test cases)
 - [ ]    Root folders are: Precondition, Process, Postcondition
 - [ ]    All test steps are more or less on the same folder depth. Folder depth should be somewhere between 2 and 4. The second (and sometimes third) layer of folders outlines the rough sections of the test cases.
 - [ ]    Test steps are bundled in folders that outline the process steps or screens to help to understand a reader the test case as quickly as possible.
 - [ ]    Each test step is (re-)named so that it explains in natural language what the test step does
 - [ ]    Every test case (-instance) has a verification, or is part of a business TestCase
 - [ ]    Every teststep is renamed to match the action taken in that test step
 - [ ]    No use of plain "Wait" / "TBox Wait". If possible, use a wait-on condition that triggers the next test step as quickly as possible.
 - [ ]    Use Path-Shortcuts as deep as possible. This means so deep that you don't have a cross-reference to a path above the Path-Part (which would lead to a fully qualified path). Path Shortcuts help to keep the test case readable.
 - [ ]    Use Test Step libraries to encapsulate common tasks. This helps you to reduce the maintenance work of these tasks to one single location, and you avoid having x copy/paste-implementations of the same thing - some of them possibly suboptimal or even wrong.
 - [ ]    Always use parameters in test step libraries - no references to buffers or Configuration Parameters! This helps your team members to clearly understand what to provide when using your test step library. If you have hidden dependencies, they won't know unless they analyse your library.
 - [ ]    All conditions are explicit, not implicit.
 - [ ]    All "_reference" postfixes from references to test library elements have been removed.
 - [ ]    Remove all dependencies to uncontrollable factors (time of day, weather, external services) that can be removed.
 - [ ]    Remove all dependencies to other test cases, if possible.
 - [ ]    Test data generation happens outside, in a separate test case (= not as part of the precondition).

# Execution Lists
 - [ ]    The test cases on an execution list are distributed on test mandates to split the workload on DEX agents.
 
 
Created by Martin Schacher, Anooky GmbH,
released under the Creative Commons License.

References:
https://support-hub.tricentis.com/open?id=kb_article_view&sys_kb_id=7c540d3adb92e700904d41efaa9619d4

https://support-hub.tricentis.com/open?sys_kb_id=194a54eedb4f5c181ea7bb13f3961950&id=kb_article_view&number=KB0014209

https://support.tricentis.com/community/article.do?number=KB0014210

https://support.tricentis.com/community/article.do?number=KB0014226

https://support.tricentis.com/community/article.do?number=KB0014227

https://support.tricentis.com/community/article.do?number=KB0014228

https://support.tricentis.com/community/article.do?number=KB0014229

https://support.tricentis.com/community/article.do?number=KB0014231

https://support-hub.tricentis.com/open?sys_kb_id=194a54eedb4f5c181ea7bb13f3961950&id=kb_article_view&number=KB0014232
