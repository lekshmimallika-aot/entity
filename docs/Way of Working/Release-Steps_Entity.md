- Note: This release notes are currently used by Entity team only. 

- We work with Relationships team to document/ update their release process. Here an example: 
https://app.zenhub.com/workspaces/entity-5bf2f2164b5806bc2bf60531/issues/bcgov/entity/2485 


**Prior to moving into production, the following steps should be completed or confirmed:**
- [ ] Update version number in the code being released
- [ ] Ensure deployment steps are filled in - remove/replace placeholders
- [ ] Create a draft release in GitHub and confirm the correct commits are present
- [ ] Add version # and release # to this ticket
- [ ] Dev to send commit list to QA (or otherwise publish changelog)
- commits are in the draft release for <Release Number>
- [ ] QA to schedule the release with staff/ clients (daytime's best or when staff are available for rollback)
- [ ] All dev/test pipeline test suites green
- [ ] Dev/ QA chat to plan prod verification testing (unless already automated)
Release the code to production and complete smoke test (STEPS BELOW)
Finalise/publish the release in GitHub, tagging it
Merge release branch back to master (if applicable)
- [ ] Change openshift builds/pipelines back to master (if applicable)
  - [ ] colin-api-base
  - [ ] legal-api
  - [ ] update-colin-filings
  - [ ] update-legal-filings
  - [ ] entity-filer
  - [ ] entity- pay

----

**Deployment Steps**

**DEV:**
- [ ] config map changes
- [ ] are there any dependencies, such as an auth/pay deployment or keycloak changes?
- [ ] one-time steps to be done:
  - [ ] rebuild colin-updater
  - [ ] rebuild legal-updater
- [ ] dev verification
- [ ] QA verification

**TEST:**
- [ ] one-time steps to be done:
  - [ ] rebuild colin-updater
  - [ ] rebuild legal-updater
- [ ] DEV verification
- [ ] QA verification

**PROD:**
- [ ] link colin event ids 102132378 and 102132380 to filing_id = 251 before running colin-updater <This step might be specific to a particular release>
- [ ] one-time steps to be done:
  - [ ] build colin-updater
  - [ ] rebuild legal-updater

**Notify PO and CM**
- [ ] Send the PO a message in RocketChat if a release was successfully implemented
- [ ] PO will send Trish a message if a release was successfully implemented: Trish.Reimer@gov.bc.ca - and   karla.maria.ramirez@gov.bc.ca

