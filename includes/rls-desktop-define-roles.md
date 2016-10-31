## 定義角色和 Power BI Desktop 中的規則

您可以定義角色和 Power BI Desktop 中的規則。 當您發行至 Power BI 時，它也會發行角色定義。

如果您想要利用動態安全性，您必須啟用預覽參數，以啟用跨 directquery 篩選兩個方向。 這可讓交叉篩選和套用安全性篩選兩個方向的能力。

![](./media/rls-desktop-define-roles/powerbi-desktop-preview-bi-directional-directquery.png)

若要定義安全性角色，您可以執行下列程式碼。

1.  Power BI Desktop 報表時，將資料匯入或 DirectQuery 連線的設定。

    > [AZURE.NOTE] 您無法定義 Analysis Services 即時連接 Power BI Desktop 中的角色。 您必須執行的 Analysis Services 模型中。

2.  選取 **模型** ] 索引標籤。

3.  選取 **管理角色**。

    ![](./media/rls-desktop-define-roles/powerbi-desktop-security.png)

4.  選取 **建立**。

    ![](./media/rls-desktop-define-roles/powerbi-desktop-security-create-role.png)

5.  提供角色的名稱。 
6.  選取您想要將 DAX 規則套用的資料表。
7.  輸入 DAX 運算式。 此運算式應該會傳回 true 或 false。 例如: [實體識別碼] ="Value"。

    > [AZURE.NOTE] 您可以使用 *username （)* 這個運算式中。 請注意， *username （)* 會有以下格式的 *網域 \ 使用者名稱* Power BI Desktop 中。 在 Power BI 服務中，它會在使用者的 UPN 的格式。

    ![](./media/rls-desktop-define-roles/powerbi-desktop-security-create-rule.png)

8.  您已經建立 DAX 運算式之後，您可以選取驗證運算式的運算式方塊上方的核取。

    ![](./media/rls-desktop-define-roles/powerbi-desktop-security-validate-dax.png)

9.  選取 **儲存**。

您無法將使用者指派至 Power BI Desktop 內的角色。 這是 Power BI 服務中。 您可以啟用 Power BI Desktop 的動態安全性，藉由使用 *username （)* DAX 函數並設定適當的關聯性。