## 限制

以下是雲端模型的資料列層級安全性的目前限制的清單。

- 如果您先前已在 Power BI 服務中定義的角色/規則，您必須在 Power BI Desktop 中重新建立它們。
- 您可以只在使用 Power BI Desktop 用戶端所建立的資料集上定義 RLS。 如果您想要啟用 RLS，建立與 Excel 的資料集，您必須先轉換成 PBIX 檔案的檔案。 [進一步了解](powerbi-desktop-import-excel-workbooks.md)
- 只有 ETL 和支援 DirectQuery 連線。 即時連接至 Analysis Services 會在內部部署模型處理。
- 問答集和 Cortana 與 RLS 不支援這一次。 您不會看到問與答讓儀表板的輸入的方塊，如果所有模型都有設定 RLS。 這是規劃，，但沒有時間軸。
- 外部共用目前不支援使用 RLS 的資料集。

## 已知問題

這是已知的問題如果先前已從 Power BI Desktop 發行時，會收到錯誤訊息。 案例是，如下所示。

1. Anna 住在美國有 publised Power BI 服務且已設定 RLS 資料集。

2. 也會更新 Power BI Desktop 中的報表，並重新發佈。

3. 也會收到錯誤。


            **因應措施︰** 重新發行 Power BI 服務中的 Power BI Desktop 檔案，直到此問題解決為止。 您可以達成選取 **取得資料** > **檔案**。 