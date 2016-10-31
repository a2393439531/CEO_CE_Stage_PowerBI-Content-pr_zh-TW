## 安裝內部部署資料閘道

安裝資料閘道，並在電腦上執行。 您最好在仍可繼續執行的電腦上安裝閘道。

> [AZURE.NOTE] 閘道支援只能在 64 位元 Windows 作業系統上。

Power bi，您必須進行的第一個選擇是閘道的模式。

-   
            **內部資料閘道︰** 多位使用者可以共用及重複使用此模式中的閘道。 Power BI、 PowerApps、 流量或邏輯應用程式可以使用此閘道器。 Power bi，其中包括支援排程重新整理和 DirectQuery

-   
            **個人︰** 這僅適用於 Power BI，可用來當做個人而不需要任何系統管理員設定。 這僅能隨重新整理和排程重新整理。 這會啟動個人閘道安裝。

> [AZURE.NOTE] 如果您在個人的模式中安裝閘道，您無法在同一部電腦上安裝另一個閘道。 

![on-prem-data-gateway-install-powerbi](./media/gateway-onprem-install-include/on-prem-data-gateway-install-powerbi.png)

以下是安裝閘道之前，要考慮的幾個事項。

-   如果您要安裝的膝上型電腦上，膝上型電腦關機不連線到網際網路，或睡眠狀態閘道將無法運作，和雲端服務中的資料將不會同步您的內部資料。

-   如果您的電腦連線到無線網路，閘道器可能會執行速度變慢這樣將會造成它需要更長的時間與內部部署資料同步處理雲端服務中的資料。

安裝閘道之後，您必須使用您的工作或學校帳戶登入。

![on-prem-data-gateway-install-signin](./media/gateway-onprem-install-include/on-prem-data-gateway-install-signin.png)

您登入之後，您必須選擇来設定新的閘道，或移轉、 還原或取代現有的閘道。

![on-prem-data-gateway-install-register-recovery](./media/gateway-onprem-install-include/on-prem-data-gateway-install-register-recovery.png)

## 設定新的閘道

1.  輸入 **名稱** 閘道

2.  輸入 **修復金鑰**。 這必須是 8 個字元的最小值。

3.  選取 **設定**。

> [AZURE.NOTE] 如果您需要移轉、 還原或高於閘道，將會需要修復金鑰。 請務必將此金鑰保存在安全的地方。

![on-prem-data-gateway-install-recovery](./media/gateway-onprem-install-include/on-prem-data-gateway-install-recovery.png)

### 移轉、 還原或取代現有的閘道

您必須選取您想要復原，並提供修復金鑰，用於第一次建立閘道的閘道。 

### 連線的內部資料閘道

一旦設定閘道，您將能夠使用它來連接到內部部署資料來源。 

如果閘道 Power bi，您必須將您的資料來源加入至 Power BI 服務中的閘道。 如 PowerApps，您必須選取一個閘道，將支援的資料來源定義的連接。

流程和邏輯應用程式，此閘道器已準備好搭配您的內部部署連線 