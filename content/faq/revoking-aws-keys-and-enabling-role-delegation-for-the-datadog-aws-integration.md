---
title: Revoking AWS keys and enabling Role Delegation for the Datadog AWS Integration.
kind: faq
customnav: main_references
---

Prior to revoking your AWS Keys you'll want to configure AWS Role Delegation in your AWS Console, to do so:

1. First, be certain your AWS Role has appropriate (read-only) privileges as outlined here
2. Create a new role in the IAM Console. Name it anything you like, such as DatadogAWSIntegrationRole.
    {{< img src="faq/A1.png" alt="A1" responsive="true" >}}
    {{< img src="faq/A2.png" alt="A2" responsive="true" >}}

3. From the selection, choose Role for Cross-Account Access and click the Select button for Allows IAM users from a 3rd party AWS account to access this account.
    {{< img src="faq/A3.gif" alt="A3" responsive="true" >}}


4. For Account ID, enter 464622532012 (Datadog’s account ID). This means that you will grant Datadog and Datadog only read access to your AWS data. 
    {{< img src="faq/A4.png" alt="A4" responsive="true" >}}


For External ID, enter the one generated in the Role Delegation tab of the [AWS Integration](/integrations/amazon_web_services) configuration page. For more information about the External ID, refer to this document in the [IAM User Guide](http://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_create_for-user_externalid.html).
    {{< img src="faq/A5.png" alt="A5" responsive="true" >}}

Leave Require MFA disabled. 

5. Select the policy you previously created for the access keys.
    {{< img src="faq/A6.png" alt="A6" responsive="true" >}}

6. Review what you selected and click the Create Role button.
    {{< img src="faq/A7.png" alt="A7" responsive="true" >}}

7. Update the credentials in Datadog by navigating to the in-app integration tile [here](https://app.datadoghq.com/account/settings#integrations/amazon_web_services):
    {{< img src="faq/A8.png" alt="A8" responsive="true" >}}

8. Click the tab for Role Delegation. The AWS Account ID and AWS External ID should be left to their default values. Enter the name you specified for the AWS Role in step 2.  A green banner will be displayed (momentarily after entering the name) at the top of the account configuration section if the role was successfully validated.
    {{< img src="faq/A9.png" alt="A9" responsive="true" >}}

9. Scroll down to the bottom of the configuration page and click Update Configuration. A green banner will be displayed once the configuration has been validated and applied. This process will also remove the previously used Access Key credentials.
    {{< img src="faq/A10.png" alt="A10" responsive="true" >}}

10. Once you've setup Datadog for AWS Roles please revoke your AWS Keys per [this article](https://docs.aws.amazon.com/general/latest/gr/managing-aws-access-keys.html). This can be done from the AWS Console Security Credentials page by expanding the section for Access Keys and clicking the Make Inactive or Delete link for the appropriate Access Key ID.
    {{< img src="faq/A11.png" alt="A11" responsive="true" >}}

If you encounter any issues or have additional questions, please [contact us](/help)