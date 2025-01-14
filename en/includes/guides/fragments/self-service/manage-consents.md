<!-- markdownlint-disable-next-line -->

When a user logs in to an application, {{ product_name }} prompts the user to provide consent to the application to access user attributes. Users can view these consents and if needed, revoke them using the My Account portal.

Given below are the steps to follow.

1. Sign in to the My Account portal.

2. Click **Security > Manage Consents**.

3. Users can view the applications for which they have given consent.

4. Select an application and click **Show more** to display the attributes that are shared with the application.

    ![View consents]({{base_path}}/assets/img/guides/organization/self-service/myaccount/view-consents.png){: width="600" style="display: block; margin: 0 auto; border: 0.3px solid lightgrey;"}

5. To revoke consent, the user can do one of the following:

    - Clear attributes individually and click **Update**. This revokes consent for deselected user attributes.

    - Click **Revoke** in the danger zone to revoke all user attributes shared with that application.

    !!! note
        If a user revokes consent to share an attribute with an application, {{ product_name }} again prompts the user for consent next time the user logs in to the same application.