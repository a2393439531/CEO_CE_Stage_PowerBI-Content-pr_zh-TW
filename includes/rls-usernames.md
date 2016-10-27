## Using the username() DAX function

You can take advantage of the DAX function <bpt id="p1">*</bpt>username()<ept id="p1">*</ept> within your dataset. You can use it within expressions in Power BI Desktop. When you publish your model, it will be used within the Power BI service.

Within Power BI Desktop, <bpt id="p1">*</bpt>username()<ept id="p1">*</ept> will return a user in the format of <bpt id="p2">*</bpt>DOMAIN\User<ept id="p2">*</ept>.

Within the Power BI service, <bpt id="p1">*</bpt>username()<ept id="p1">*</ept> will return the user's User Principal Name (UPN). This looks similar to an email address.