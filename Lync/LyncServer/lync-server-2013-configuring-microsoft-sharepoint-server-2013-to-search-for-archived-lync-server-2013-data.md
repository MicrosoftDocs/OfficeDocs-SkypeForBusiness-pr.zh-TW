---
title: Lync Server 2013： 設定 Microsoft SharePoint Server 2013 搜尋已封存的 Lync Server 2013 資料
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
ms.openlocfilehash: 8debab39073bf31f509ec504f944c8e4c7a9dfc3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008415"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-sharepoint-server-2013-to-search-for-archived-microsoft-lync-server-2013-data"></a>設定 Microsoft SharePoint Server 2013 搜尋已封存的 Microsoft Lync Server 2013 資料

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-02-04_

若要將立即訊息和 Web 會議記錄儲存在 Microsoft Exchange Server 2013，而不是 Microsoft Lync Server 2013 的主要優點之一是將資料儲存在相同的位置可讓系統管理員可以使用單一工具來搜尋封存的 Exchange 資料及/或封存的 Lync Server 資料的事實。 因為所有的資料儲存在同一個放置 (Exchange) 封存 Exchange 資料可以搜尋任何工具也可以搜尋封存的 Lync Server 資料。

一種工具，可讓您輕鬆地搜尋封存的資料為 Microsoft SharePoint Server 2013。 如果您想要使用 SharePoint 搜尋 Lync Server 的資料，您必須先完成所有參與設定 Exchange 封存 Lync Server 中的步驟。 Exchange 2013 和 Lync Server 2013 有已成功地整合之後您必須在您的 SharePoint Server;，然後安裝 Exchange Web Services Managed API 2.0 版您可以從 Microsoft 下載中心下載該 API 的安裝程式 ([http://go.microsoft.com/fwlink/p/?LinkId=258305](http://go.microsoft.com/fwlink/p/?linkid=258305))。 下載的檔案 (EWSManagedAPI.msi) 可以儲存至 SharePoint Server 上的任何資料夾。

下載檔案之後，在 SharePoint Server 上完成下列程序：

1.  依序按一下 [開始]****、[所有程式]**** 及 [附屬應用程式]****，再以滑鼠右鍵按一下 [命令提示字元]****，然後按一下 [以系統管理員身分執行]****，以開啟命令視窗。

2.  在命令視窗中，使用 **cd** 命令將現行目錄切換至儲存 EWSManagedAPI.msi 檔案的資料夾。 例如，如果您將檔案儲存至 c:\\下載命令視窗中輸入下列命令，然後按 ENTER:
    
        cd C:\Downloads

3.  若要安裝 API，請輸入下列命令，然後按 ENTER 鍵：
    
        msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"

4.  安裝 API 之後，輸入下列命令並按 ENTER 鍵，以重設 IIS：
    
        iisreset

在安裝 Exchange Web 服務之後您必須再設定 SharePoint Server 2013 和 Exchange 2013 之間的伺服器對伺服器驗證。 若要這麼做，請先開啟 [SharePoint 2013 管理命令介面，並執行下列命令的：

    New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
    $service = Get-SPSecurityTokenServiceConfig
    $service.HybridStsSelectionEnabled = $True
    $service.AllowMetadataOverHttp = $False
    $service.AllowOAuthOverHttp = $False
    $service.Update()

<div>


> [!NOTE]  
> 請務必將該 URI 用於自動探索服務。 請勿使用範例 URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1。



</div>

建立 token 發行者以及設定 token 服務之後，請執行下列命令，請務必用來替代範例 URL 的 SharePoint 網站的 URLhttp://atl-sharepoint-001:

    $exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
    $app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
    $site = Get-SPSite  "https://atl-sharepoint-001"
    Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy

若要設定 Exchange 2013 的伺服器對伺服器驗證，請開啟 Exchange 管理命令介面並執行如下的命令 （假設已在 c： 磁碟機上安裝 Exchange，且其使用預設資料夾路徑）：

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"

設定夥伴應用程式之後建議您停止並重新啟動所有 Exchange 信箱和用戶端存取伺服器上的網際網路資訊服務 (IIS)。 您可以使用如下命令來重新啟動 IIS，其會在電腦 atl-exchange-001 上重新啟動該服務：

    iisreset atl-exchange-001

可以從執行此命令，或從任何其他命令視窗中 [Exchange 管理命令介面。

接著，執行下列命令，可讓指定的使用者 （在本例中為 kenmyer） 來執行探索 Exchange 上的權限如下的命令：

    Add-RoleGroupMember "Discovery Management" -Member "kenmyer"

Exchange 與 SharePoint 之間建立伺服器對伺服器驗證之後下一個步驟是在 SharePoint 中建立電子文件探索站台。 可以藉由執行類似這些從 SharePoint 管理命令介面命令：

    $template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
    New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"

<div>


> [!NOTE]  
> "eDiscovery" 是 "electronic discovery" (電子化探索) 的縮寫，此程序通常是指在電子化封存中尋找可以在法庭上「合理計算以導出可採納證據」的項目。



</div>

準備新的網站時下, 一步是設定 Exchange 2013 到 SharePoint 做為結果來源。 您可以這麼做，請完成下列程序，從 [SharePoint 2013 管理中心] 頁面上：

1.  在「管理中心」頁面上，按一下 [管理服務應用程式]****，然後按一下 [Search Service 應用程式]****。

2.  在「Search Service 應用程式：搜尋管理」頁面上，按一下 [結果來源]**** ，然後按一下 [新增結果來源]****。

3.  在 [新增結果來源]**** 窗格的 [名稱]**** 方塊中，輸入新結果來源的名稱 (例如，**Microsoft Exchange**)。 選取 [ **Exchange]** 作為**通訊協定**的結果來源，然後輸入您的 Exchange 伺服器中**Exchange 來源 URL** ] 方塊中的 [web 服務來源 URL。 來源 URL 看起來應該像下面這樣：
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx

4.  請確定未選取 [使用自動探索]****，然後按一下 [確定]****。

最後，建立新的 eDiscovery 案例及新的 eDiscovery 集 （例如，完成下列程序從 SharePoint 探索站台https://atl-sharepoint-001/sites/discovery):

1.  在「網站內容」頁面上，按一下 [建立新案例]****。

2.  在「網站內容：建立 SharePoint 網站」頁面上的 [標題]**** 方塊中，輸入使用者的電子郵件別名 (例如，**kenmyer**)，然後將那相同的 URL 新增至 [網站位址]**** 方塊中。如此將會產生像下面這樣的 URL：
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer

3.  按一下 [建立]****。

4.  當「eDiscovery 集」頁面出現時，按一下 [識別與保留: Discovery 集]**** 底下的 [新項目]****。

5.  在「新增：Discovery 集」頁面上的 [Discovery 集名稱]**** 方塊中，輸入使用者電子郵件別名。 輸入**eDiscovery Lync\*** 在 [**篩選**] 方塊，然後按一下 [**新增 & 管理來源**。

6.  在「新增及管理來源」頁面上 [信箱]**** 底下的第一個文字方塊中，輸入使用者的電子郵件別名。按一下位在文字方塊旁邊的檢查信箱圖示，確認 SharePoint 可以連線至指定的信箱。

7.  按一下 [確定]****。

8.  在「eDiscovery 集」頁面上， 按一下 [儲存]****，以儲存新的 eDiscovery 集。

此時，您可以搜尋指定的信箱 (kenmyer) 及/或啟用就地保留任何其他 SharePoint 內容或結果來源的相同的方式。

</div>

<span> </span>

</div>

</div>

</div>

