---
title: Lync Server 2013：設定 Microsoft SharePoint Server 2013 來搜尋封存的 Lync Server 2013 資料
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring SharePoint Server 2013 to search for archived Lync Server 2013 data
ms:assetid: 17f49365-8778-4962-a41b-f96faf6902f1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687978(v=OCS.15)
ms:contentKeyID: 49733566
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d831638cf25df4f9c1b792c34815e8bed8c15e8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525870"
---
# <a name="configuring-microsoft-sharepoint-server-2013-to-search-for-archived-microsoft-lync-server-2013-data"></a>設定 Microsoft SharePoint Server 2013 以搜尋封存的 Microsoft Lync Server 2013 資料

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-04_

在 Microsoft Exchange Server 2013，而不是 Microsoft Lync Server 2013 中儲存立即訊息和 Web 會議記錄的主要優點之一，是可讓系統管理員使用單一工具來搜尋已封存的 Exchange 資料和（或）封存的 Lync Server 資料。 由於所有資料都儲存在相同的位置 (Exchange) 任何可搜尋已封存 Exchange 資料的工具也可以搜尋封存的 Lync Server 資料。

一種可讓您搜尋封存資料的工具，是 Microsoft SharePoint Server 2013。 如果您想要使用 SharePoint 來搜尋 Lync Server 資料，您必須先完成在 Lync Server 中設定 Exchange 封存所涉及的所有步驟。 成功整合 Exchange 2013 和 Lync Server 2013 之後，您必須在 SharePoint 伺服器上安裝 Exchange Web Services Managed API 版本 2.0;您可以從 Microsoft 下載中心 () 下載該 API 的安裝程式 [https://go.microsoft.com/fwlink/p/?LinkId=258305](https://go.microsoft.com/fwlink/p/?linkid=258305) 。 下載的檔案 (EWSManagedAPI.msi) 可以儲存至 SharePoint Server 上的任何資料夾。

下載檔案之後，在 SharePoint Server 上完成下列程序：

1.  依序按一下 [開始]****、[所有程式]**** 及 [附屬應用程式]****，再以滑鼠右鍵按一下 [命令提示字元]****，然後按一下 [以系統管理員身分執行]****，以開啟命令視窗。

2.  在命令視窗中，使用 **cd** 命令將現行目錄切換至儲存 EWSManagedAPI.msi 檔案的資料夾。 例如，如果您已將檔案儲存至 C：下載，請 \\ 在命令視窗中輸入下列命令，然後按 enter：
    
        cd C:\Downloads

3.  若要安裝 API，請輸入下列命令，然後按 ENTER 鍵：
    
        msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"

4.  安裝 API 之後，輸入下列命令並按 ENTER 鍵，以重設 IIS：
    
        iisreset

在安裝 Exchange Web 服務之後，您必須在 SharePoint Server 2013 和 Exchange 2013 之間設定伺服器對伺服器的驗證。 若要這麼做，請先開啟 SharePoint 2013 管理命令介面，並執行下列命令組：

    New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
    $service = Get-SPSecurityTokenServiceConfig
    $service.HybridStsSelectionEnabled = $True
    $service.AllowMetadataOverHttp = $False
    $service.AllowOAuthOverHttp = $False
    $service.Update()

<div>


> [!NOTE]  
> 請務必將該 URI 用於自動探索服務。 請勿使用範例 URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1 。



</div>

建立權杖簽發者並設定 token 服務之後，請執行下列命令，以確保將 SharePoint 網站的 URL 取代為範例 URL http://atl-sharepoint-001:

    $exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
    $app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
    $site = Get-SPSite  "https://atl-sharepoint-001"
    Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy

若要設定 Exchange 2013 的伺服器對伺服器驗證，請開啟 Exchange 管理命令介面，並執行類似此 (的命令，假設 Exchange 已安裝在磁碟機 C：上，而且它使用預設的資料夾路徑) ：

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"

設定夥伴應用程式之後，建議您在所有 Exchange 信箱和用戶端存取伺服器上停止並重新啟動網際網路資訊服務 (IIS) 。 您可以使用如下命令來重新啟動 IIS，其會在電腦 atl-exchange-001 上重新啟動該服務：

    iisreset atl-exchange-001

您可以從 Exchange 管理命令介面或任何其他命令視窗中執行此命令。

接下來，執行類似下列的命令，可讓指定的使用者 (在此範例中，kenmyer) 在 Exchange 上進行探索的許可權：

    Add-RoleGroupMember "Discovery Management" -Member "kenmyer"

在 Exchange 之間建立伺服器對伺服器驗證之後，SharePoint 下一步是在 SharePoint 中建立 eDiscovery 網站。 您可以從 SharePoint 管理命令介面中執行類似下列的命令，以執行此作業：

    $template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
    New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"

<div>


> [!NOTE]  
> "eDiscovery" 是 "electronic discovery" (電子化探索) 的縮寫，此程序通常是指在電子化封存中尋找可以在法庭上「合理計算以導出可採納證據」的項目。



</div>

當新的網站準備好時，下一步是設定 Exchange 2013 做為 SharePoint 的結果來源。 您可以從 SharePoint 2013 管理中心] 頁面完成下列程式，以執行此操作：

1.  在「管理中心」頁面上，按一下 [管理服務應用程式]****，然後按一下 [Search Service 應用程式]****。

2.  在「Search Service 應用程式：搜尋管理」頁面上，按一下 [結果來源]**** ，然後按一下 [新增結果來源]****。

3.  在 [新增結果來源]**** 窗格的 [名稱]**** 方塊中，輸入新結果來源的名稱 (例如，**Microsoft Exchange**)。 選取 [ **exchange** ] 做為結果來源 **通訊協定**，然後在 [ **exchange 來源 Url** ] 方塊中輸入 EXCHANGE 伺服器的 web 服務來源 url。 來源 URL 看起來應該像下面這樣：
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx

4.  請確定未選取 [使用自動探索]****，然後按一下 [確定]****。

最後，請從 SharePoint 探索網站 (中完成下列程式，以建立新的 eDiscovery 案例及新的 eDiscovery 集（例如， https://atl-sharepoint-001/sites/discovery):

1.  在「網站內容」頁面上，按一下 [建立新案例]****。

2.  在「網站內容：建立 SharePoint 網站」頁面上的 [標題]**** 方塊中，輸入使用者的電子郵件別名 (例如，**kenmyer**)，然後將那相同的 URL 新增至 [網站位址]**** 方塊中。如此將會產生像下面這樣的 URL：
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer

3.  按一下 [建立]****。

4.  當「eDiscovery 集」頁面出現時，按一下 [識別與保留: Discovery 集]**** 底下的 [新項目]****。

5.  在「新增：Discovery 集」頁面上的 [Discovery 集名稱]**** 方塊中，輸入使用者電子郵件別名。 在 [**篩選**] 方塊中輸入**eDiscovery Lync \* ** ，然後按一下 [**新增 & 管理來源**]。

6.  在「新增及管理來源」頁面上 [信箱]**** 底下的第一個文字方塊中，輸入使用者的電子郵件別名。按一下位在文字方塊旁邊的檢查信箱圖示，確認 SharePoint 可以連線至指定的信箱。

7.  按一下 [確定]****。

8.  在「eDiscovery 集」頁面上， 按一下 [儲存]****，以儲存新的 eDiscovery 集。

此時，您可以搜尋指定的信箱 (kenmyer) 和/或啟用 In-Place 保留的方式與其他任何 SharePoint 內容或結果來源相同。

</div>

<span> </span>

</div>

</div>

</div>

