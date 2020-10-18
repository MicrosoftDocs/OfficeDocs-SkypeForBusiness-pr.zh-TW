---
title: Lync Server 2013：安裝 Lync Server 2013 監控報告
description: Lync Server 2013：安裝 Lync Server 2013 監控報告。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Lync Server 2013 Monitoring Reports
ms:assetid: 6f417569-b100-442c-ad48-fdd794626cf7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204989(v=OCS.15)
ms:contentKeyID: 48184445
ms.date: 02/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12405f786cbaf095e97f526fae2e1c2d3cb45c32
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573929"
---
# <a name="installing-lync-server-2013-monitoring-reports"></a>安裝 Lync Server 2013 監控報告

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-02-27_

Microsoft Lync Server 2013 監控報告可為您提供大量有關組織中所發生之通訊會話品質與數量的資訊。 不過，當您安裝 Lync Server 2013 時，不會自動安裝監控報告;相反地，您必須個別安裝監視報告，而且只有在電腦上安裝 Lync Server 之後。

<div>


> [!NOTE]  
> 建議您將監控報告安裝在已安裝監控資料庫之相同電腦上，如此可簡化存取報告的指派權限程序：將監控報告安裝在裝載監控存放區的電腦上，表示您不需要設定權限以允許某一台電腦上的資料庫與在第二台電腦執行的 Reporting Services 進行互動。



</div>

Lync Server Monitoring Reports 包含超過30個報告，其設計目的是提供有關會議、對等 IM 會話、使用者註冊、回應群組應用程式以及其他許多方面的詳細資訊。 針對2013版本，Lync Server Monitoring Reports 包含許多增強功能：

  - **新的語音品質報告**。 這兩個新的報表包括 [Lync Server 2013 中的媒體質量比較報告](lync-server-2013-media-quality-comparison-report.md)，它會比較不同類型通話之間的品質 (例如，有線通話與無線通話之間的品質) ;[ [Lync Server 2013] 中的 [會議加入時間] 報告](lync-server-2013-conference-join-time-report.md)，可提供使用者加入會議所需的時間量資訊。

  - **針對視訊與應用程式共用工作階段進行分析和疑難排解的改善報告。** [Lync server 2013 中的媒體質量摘要報告](lync-server-2013-media-quality-summary-report.md)提供一種方法，可分析影片和應用程式共用呼叫，而[Lync server 2013 中的伺服器效能報告](lync-server-2013-server-performance-report.md)會詳細說明產生這些通話之伺服器的效能。 在 lync server 2013 的「 [Peer-to-Peer 會話詳細資料包告](lync-server-2013-peer-to-peer-session-detail-report.md) 」和 [lync server 2013 中的 [會議詳細資料] 報告](lync-server-2013-conference-detail-report.md)中，現在也會報告影片和應用程式共用度量。

  - **改善報告效能**。包括加速回應與資料擷取時間，以及更迅速而簡便瀏覽報告。

有關個別報告的詳細資訊，可在監控報告文件中取得。

<div>


> [!NOTE]  
> 有另一個新的報告– QoE 通話詳細資料子報表–包含在 Lync Server 2013 中。 但是，此報告主要用於內部，無法直接存取。



</div>

有兩種方式可安裝 Lync Server 監視報告：您可以使用 Lync Server 部署嚮導，也可以使用 Lync Server 2013 安裝檔案隨附的 Windows PowerShell 腳本。 無論您使用哪一種方法安裝報告，都必須先確認您具備下列條件：

  - 具備將資料庫角色新增至監控資料庫中使用者帳戶的權限。

  - 在 SQL Server Reporting Services 中具有「內容管理員」角色。這個角色會賦予您將報告部署至 SQL Server Reporting Services 的權限。

若要使用部署精靈安裝監控報告，請完成下列步驟：

1.  依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 部署嚮導]**。

2.  在部署精靈中按一下 **[部署監控報告]** 以啟動「部署監控報告」精靈。

3.  在部署監控報告精靈中的 **[指定監控資料庫]** 頁面上，請確認裝載您監控存放區之電腦的完整網域名稱顯示於 **[監控資料庫]** 下拉式清單中。(如果您有多個監控存放區，則必須從下拉式清單選取適當的伺服器。) 確認正確的 SQL Server 執行個體顯示於 **[SQL Server Reporting Services (SSRS) 執行個體]** 方塊中 (例如 **atl-sql-001.litwareinc.com/archinst**)，然後按 **[下一步]**。

4.  在 [ **指定認證** ] 頁面上的 [ **使用者名稱** ] 方塊中，輸入要在存取監控報告時使用之帳戶的功能變數名稱和使用者名稱 (例如， **litwareinc \\ kenmyer**) 。 如果您未使用此格式 (網域 \\ 使用者名稱) 會發生錯誤。
    
    在 **[密碼]** 方塊中輸入使用者帳戶密碼，然後按 **[下一步]**。 請注意，此帳戶沒有必要的特殊權利。 安裝程式完成時，系統會自動授與帳戶所需的登入和資料庫許可權。

5.  在 **[指定唯讀群組]** 頁面上的使用者群組方塊中，輸入將授與 SQL Server Reporting Services 唯讀存取權的安全性群組名稱。例如，若要指定唯讀系統管理員存取報告，請輸入 **RTCUniversalReadOnlyAdmins**，然後按 **[下一步]**。

6.  在 **[執行命令]** 頁面上按一下 **[完成]**。

透過執行腳本 DeployReports.ps1，也可以從 Lync Server 管理命令介面安裝監視報告;您可以在 [安裝 ReportingSetup] 資料夾中的 Lync Server 安裝媒體上找到這個 Windows PowerShell 腳本 \\ \\ 。 若要使用 DeployReports.ps1 安裝監控報告，請在管理介面提示中輸入類似下列命令：

    C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup\DeployReports.ps1 -storedUserName "litwareinc\kenmyer" -storedPassword "p@ssw0rd" -readOnlyGroupName "RTCUniversalReadOnlyAdmins" -reportServerSqlInstance "atl-sql-001.litwareinc.com" -monitoringDatabaseId "MonitoringDatabase:atl-sql-001.litwareinc.com"

用於以上命令的參數會在下表加以說明：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>參數名稱</th>
<th>必要</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>storedUserName</p></td>
<td><p>是</p></td>
<td><p>用於存取監控存放區的使用者帳戶 (格式為網域\使用者名稱)；例如：</p>
<pre><code>-storedUserName &quot;litwareinc\kenmyer&quot;</code></pre>
<p>此帳戶必須具有先前指定的 SQL Server 及 SQL Server Reporting Services 權限，否則指令碼將會失敗。</p></td>
</tr>
<tr class="even">
<td><p>storedPassword</p></td>
<td><p>是</p></td>
<td><p>用於存取監控存放區的使用者帳戶密碼。</p></td>
</tr>
<tr class="odd">
<td><p>readOnlyGroupName</p></td>
<td><p>否</p></td>
<td><p>授與成員監控報告唯讀權限的網域或本機安全性群組。 請注意，如果指定的群組不存在，指令碼就會失效。 如果您稍後決定撤銷這些權限，或是決定將權限授與其他使用者或群組，可使用 SQL Service Reporting Services 報表管理員執行這些動作。</p></td>
</tr>
<tr class="even">
<td><p>reportSqlServerInstance</p></td>
<td><p>否</p></td>
<td><p>託管 Reporting Service 的 SQL Server 執行個體。必須使用 Report Server 的完整網域名稱指定報告執行個體；例如：</p>
<pre><code>-reportServerSqlInstance atl-sql-001.litwareinc.com</code></pre>
<p>如果不包含此參數，指令碼會假定 Reporting Services 由託管監控資料庫之相同的 SQL Server 執行個體託管。</p></td>
</tr>
<tr class="odd">
<td><p>monitoringDatabaseId</p></td>
<td><p>否</p></td>
<td><p>監控資料庫的服務識別。您可執行此命令返回監控資料庫的識別：</p>
<pre><code>Get-CsService -MonitoringDatabase</code></pre></td>
</tr>
</tbody>
</table>


安裝監控報告之後，您必須接著使用 Set-CsReportingConfiguration Cmdlet 以設定用於存取這些報告的 URL。 您可以執行下列 Windows PowerShell 命令，從 Lync Server 管理命令介面執行此工作。 請注意，建議您在設定報告 URL 時使用 HTTPS 通訊協定 (非必要)：

    Set-CsReportingConfiguration -Identity "MonitoringDatabase:atl-sql-001.litwareinc.com" -ReportingURL "https://atl-sql-001.litwareinc.com:443/Reports_ARCHINST"

以上的命令中，ReportingUrl 屬性應設為 SQL Server 2008 R2 Reporting Services 所使用的報表管理員 URL。您可在已安裝 SQL Server Reporting Services 的電腦上透過完成下列步驟來決定報表管理員 URL：

1.  依序按一下 [開始]、[所有程式]、[Microsoft SQL Server 2008 R2]、[組態工具]，然後按一下 [Reporting Services 組態管理員]。

2.  在 [Reporting Services 組態連接] 對話方塊中，請確定 Reporting Services 電腦名稱顯示於 [伺服器名稱] 對話方塊中。從 [報告伺服器執行個體] 下拉式清單中選取 SQL Server 執行個體，然後按一下 [連線]。

3.  在 [Reporting Services 組態管理員] 中，按一下 [報表管理員 URL]，[報表管理員 URL] 窗格應該會顯示一個以上的 URL。雖然其中任何 URL 皆可作為報告 URL 之用，再一次申明，建議您採用使用 HTTPS 通訊協定的 ReportingUrl 。

如果您已設定監控資料庫的鏡像資料庫，您也必須將監控報告與鏡像資料庫相關聯。 如需詳細資訊，請參閱 [在 Lync Server 2013 中將監控報告與鏡像資料庫相關聯](lync-server-2013-associating-monitoring-reports-with-a-mirror-database.md) 的文章。

</div>

<span> </span>

</div>

</div>

</div>

