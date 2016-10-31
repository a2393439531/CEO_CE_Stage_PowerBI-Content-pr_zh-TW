<properties pageTitle="文件範例-HTML 表格" description="這是範例文件" title="Documentation Example - HTML Tables" services="" documentationCenter="" metaKeywords="" solutions="" authors="" videoId="" scriptId="" />


# 範例-HTML 表格
這是用來測試及驗證 azure.microsoft.com 的發佈系統的範例文件文件。  

下列程式行之間的內容將示範使用 HTML 格式化資料表。  請注意，每個右資料表標記後面 `<br />`。 這是必要 （截至 2014年-01-01) 依 azure.microsoft.com 以及 GitHub，以避免破壞 markdown 的格式。  

---

## 在 Microsoft Azure HDInsight 中，是 Hadoop 的什麼版本？

HDInsight 支援多個可隨時部署的 Hadoop 叢集版本。 每一個版本選擇都會佈建特定版本的 HortonWorks Data Platform (HDP) 散發，以及一組該散發內包含的元件。

## HDInsight 版本

### 叢集 2.1 版

所使用的預設叢集版本 [Microsoft Azure HDInsight](http://go.microsoft.com/fwlink/?LinkID=285601) 是 2.1。 它根據 Hortonworks Data Platform 1.3.0，並提供下表列舉的元件版本給 Hadoop 服務︰

<table border="1">
<tr><th>服務</th><th>版本</th></tr>
<tr><td>Apache Hadoop</td><td>1.2.0</td></tr>
<tr><td>Apache Hive</td><td>0.11.0</td></tr>
<tr><td>Apache Pig</td><td>0.11</td></tr>
<tr><td>Apache Sqoop</td><td>1.4.3</td></tr>
<tr><td>Apache Oozie</td><td>3.2.2</td></tr>
<tr><td>Apache HCatalog</td><td>與 Hive 合併</td></tr>
<tr><td>Apache Templeton</td><td>與 Hive 合併</td></tr>
<tr><td>Ambari</td><td>API 1.0 版</td></tr>
</table><br/>


### 叢集 1.6 版


            [Microsoft Azure HDInsight](http://go.microsoft.com/fwlink/?LinkID=285601) 叢集 1.6 版也會提供。 它根據 Hortonworks Data Platform 1.1.0 版，並提供下表列舉的元件版本給 Hadoop 服務︰

<table border="1">
<tr><th>服務</th><th>版本</th></tr>
<tr><td>Apache Hadoop</td><td>1.0.3</td></tr>
<tr><td>Apache Hive</td><td>0.9.0</td></tr>
<tr><td>Apache Pig</td><td>0.9.3</td></tr>
<tr><td>Apache Sqoop</td><td>1.4.2</td></tr>
<tr><td>Apache Oozie</td><td>3.2.0</td></tr>
<tr><td>Apache HCatalog</td><td>0.4.1</td></tr>
<tr><td>Apache Templeton</td><td>0.1.4</td></tr>
<tr><td>SQL Server JDBC 驅動程式</td><td>3.0</td></tr>
</table><br/>


## 佈建 HDInsight 叢集時選取版本

在建立叢集，以透過 HDInsight PowerShell Cmdlet 或 HDInsight.NET SDK 時，您可以選擇使用 「 版本 」 參數的版本。

如果您使用 **快速建立** 選項，您會取得 2.1 版。 如果您使用 **自訂建立** 選項從 Microsoft Azure 入口網站中，您可以選擇將部署的叢集版本的 HDInsight 版本] 下拉式清單上 **叢集詳細資料** 頁面。

## 支援的版本
下表列出目前可用的 HDInsight 版本、 它們使用的相對應 Hortonworks Data Platform (HDP) 版本及其發行日期。 如果已知，也會提供其淘汰日期。

<table border="1">
<tr><th>HDInsight 版本</th>
<th><a href="http://go.microsoft.com/fwlink/?LinkID=286746">HDP 版本</a></th>
<th>發行日期</th></tr>
<tr><td>HDI 1.6</td><td>HDP 1.1</td><td>10/28/2013</td></tr>
<tr><td>HDI 2.1</td><td>HDP 1.3</td><td>10/28/2013</td></tr>
</table><br/>

---

[連接的 excel-與-hive-ODBC]: /manage/services/hdinsight/connect-excel-with-hive-ODBC/

[hdp-1-3-0]: http://docs.hortonworks.com/HDPDocuments/HDP1/HDP-1.3.0/bk_releasenotes_hdp_1.x/content/ch_relnotes-hdp1.3.0_1.html

[hdp-1-1-0]: http://docs.hortonworks.com/HDPDocuments/HDP1/HDP-Win-1.1/bk_releasenotes_HDP-Win/content/ch_relnotes-hdp-win-1.1.0_1.html

