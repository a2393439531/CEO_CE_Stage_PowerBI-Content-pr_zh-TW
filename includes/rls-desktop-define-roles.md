## Define roles and rules within Power BI Desktop

You can define roles and rules within Power BI Desktop. When you publish to Power BI, it will also publish the role definitions.

If you want to take advantage of dynamic security, you will need to enable the preview switch Enable cross filtering in both directions for DirectQuery. This will allow the ability to cross filter and apply the security filter in both directions.

![](./media/rls-desktop-define-roles/powerbi-desktop-preview-bi-directional-directquery.png)

To define security roles, you can do the following.

1.  Import data into your Power BI Desktop report, or configure a DirectQuery connection.

    > [AZURE.NOTE] You cannot define roles within Power BI Desktop for Analysis Services live connections. You will need to do that within the Analysis Services model.

2.  Select the <bpt id="p1">**</bpt>Modeling<ept id="p1">**</ept> tab.

3.  Select <bpt id="p1">**</bpt>Manage Roles<ept id="p1">**</ept>.

    ![](./media/rls-desktop-define-roles/powerbi-desktop-security.png)

4.  Select <bpt id="p1">**</bpt>Create<ept id="p1">**</ept>.

    ![](./media/rls-desktop-define-roles/powerbi-desktop-security-create-role.png)

5.  提供角色的名稱。 
6.  Select the table that you want to apply a DAX rule.
7.  Enter the DAX expressions. This expression should return a true or false. For example: [Entity ID] = “Value”.

    > [AZURE.NOTE] You can use <bpt id="p1">*</bpt>username()<ept id="p1">*</ept> within this expression. Be aware that <bpt id="p1">*</bpt>username()<ept id="p1">*</ept> will have the format of <bpt id="p2">*</bpt>DOMAIN\username<ept id="p2">*</ept> within Power BI Desktop. Within the Power BI service, it will be in the format of the user's UPN.

    ![](./media/rls-desktop-define-roles/powerbi-desktop-security-create-rule.png)

8.  After you have created the DAX expression, you can select the check above the expression box to validate the expression.

    ![](./media/rls-desktop-define-roles/powerbi-desktop-security-validate-dax.png)

9.  Select <bpt id="p1">**</bpt>Save<ept id="p1">**</ept>.

You cannot assign users to a role within Power BI Desktop. This is done within the Power BI service. You can enable dynamic security within Power BI Desktop by making use of the <bpt id="p1">*</bpt>username()<ept id="p1">*</ept> DAX functions and having the proper relationships configured.