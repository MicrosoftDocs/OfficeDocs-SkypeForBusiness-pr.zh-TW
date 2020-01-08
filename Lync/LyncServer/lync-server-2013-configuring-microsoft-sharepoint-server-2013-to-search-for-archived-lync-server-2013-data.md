---
title: Lync Server 2013：設定 Microsoft SharePoint Server 2013 以搜尋已歸檔的 Lync Server 2013 資料
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring SharePoint Server 2013 to search for archived Lync Server 2013 data
ms:assetid: 17f49365-8778-4962-a41b-f96faf6902f1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687978(v=OCS.15)
ms:contentKeyID: 49733566
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 381db352aae635358dfd62cc1965ea238960bf8a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974250"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-sharepoint-server-2013-to-search-for-archived-microsoft-lync-server-2013-data"></a>設定 Microsoft SharePoint Server 2013 以搜尋已歸檔的 Microsoft Lync Server 2013 資料

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-04_

在 Microsoft Exchange Server 2013 （而非 Microsoft Lync Server 2013）中儲存立即訊息和網路會議記錄的主要優點之一，是將資料儲存在同一個位置，讓系統管理員可以使用單一工具搜尋已歸檔的 Exchange 資料和/或已歸檔的 Lync Server 資料。 由於所有資料都儲存在同一個位置（Exchange）中，任何可以搜尋已歸檔 Exchange 資料的工具也都可以搜尋已歸檔的 Lync Server 資料。

可讓您輕鬆搜尋已歸檔資料的一個工具是 Microsoft SharePoint Server 2013。 如果您想要使用 SharePoint 來搜尋 Lync Server 資料，您必須先完成在 Lync Server 中設定 Exchange 封存所需的所有步驟。 成功整合 Exchange 2013 和 Lync Server 2013 之後，您必須接著在 SharePoint Server 上安裝 Exchange Web Services Managed API 版本 2.0;該 API 的安裝程式可以從 Microsoft 下載中心下載（[http://go.microsoft.com/fwlink/p/?LinkId=258305](http://go.microsoft.com/fwlink/p/?linkid=258305)）。 下載的檔案（EWSManagedAPI）可儲存至 SharePoint 伺服器上的任何資料夾。

檔案下載之後，請在 SharePoint 伺服器上完成下列程式：

1.  按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**附件**]，以滑鼠右鍵按一下 [**命令提示**字元]，然後按一下 [**以系統管理員身分執行**] 來開啟命令視窗。

2.  在命令視窗中，使用 [ **cd** ] 命令，將目前的目錄變更為已儲存檔案 EWSManagedAPI 的資料夾。 例如，如果您已將檔案儲存到 C：\\下載，請在命令視窗中輸入下列命令，然後按 enter：
    
        cd C:\Downloads

3.  若要安裝 API，請輸入下列命令，然後按 ENTER：
    
        msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"

4.  安裝 API 之後，請輸入下列命令，然後按 ENTER 來重設 IIS：
    
        iisreset

在已安裝 Exchange Web 服務之後，您必須在 SharePoint Server 2013 與 Exchange 2013 之間設定伺服器對伺服器的驗證。 若要這樣做，請先開啟 SharePoint 2013 管理命令介面，然後執行下列命令組：

    New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
    $service = Get-SPSecurityTokenServiceConfig
    $service.HybridStsSelectionEnabled = $True
    $service.AllowMetadataOverHttp = $False
    $service.AllowOAuthOverHttp = $False
    $service.Update()

<div>


> [!NOTE]  
> 請務必在您的自動探索服務中使用 URI。 請勿使用範例 URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1。



</div>

在您建立權杖頒發者並設定權杖服務之後，請執行這些命令，以確保將 SharePoint 網站的 URL 替換為範例 URLhttp://atl-sharepoint-001:

    $exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
    $app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
    $site = Get-SPSite  "https://atl-sharepoint-001"
    Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy

若要設定 Exchange 2013 的伺服器對伺服器驗證，請開啟 Exchange 管理命令介面，並執行類似此的命令（假設 Exchange 已安裝在磁碟機 C：，且它使用預設的資料夾路徑）：

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"

在設定合作夥伴應用程式之後，建議您在所有 Exchange 信箱和用戶端存取伺服器上停止並重新啟動 Internet 資訊服務（IIS）。 您可以使用類似這個的命令重新開機 IIS，這會重新開機電腦 atl-exchange-001 的服務：

    iisreset atl-exchange-001

這個命令可以從 Exchange 管理命令介面或任何其他命令視窗中執行。

接著，執行如下所示的命令，這會讓指定的使用者（在此範例中為 kenmyer）在 Exchange 上執行探索的許可權：

    Add-RoleGroupMember "Discovery Management" -Member "kenmyer"

在 Exchange 與 SharePoint 之間建立伺服器對伺服器驗證之後，下一步是在 SharePoint 中建立 eDiscovery 網站。 若要這樣做，可以從 SharePoint 管理命令介面執行類似下列的命令：

    $template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
    New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"

<div>


> [!NOTE]  
> 「eDiscovery」是「電子 discovery」的簡稱，通常是指在法庭中，查看電子歸檔，以取得可供 admissible 證據的專案的處理方式。



</div>

新網站準備就緒後，下一步就是將 Exchange 2013 設定為充當 SharePoint 的結果來源。 您可以從 [SharePoint 2013 管理中心] 頁面完成下列程式來執行此動作：

1.  在 [管理中心] 頁面上，按一下 [**管理服務應用程式**]，然後按一下 [ **Search Service 應用程式**]。

2.  在 Search Service 應用程式上： [搜尋管理] 頁面上，按一下 [**結果來源**]，然後按一下 [**新增結果來源**]。

3.  在**新的結果來源**窗格中，在 [**名稱**] 方塊中輸入新結果來源（例如， **Microsoft Exchange**）的名稱。 選取 [ **Exchange** ] 做為結果來源**通訊協定**，然後在 [ **exchange 來源 URL** ] 方塊中輸入 EXCHANGE 伺服器的 web services 來源 url。 來源 URL 應該看起來像這樣：
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx

4.  確認沒有選取 [**使用自動**探索]，然後按一下 **[確定]**。

最後，透過從 SharePoint Discovery 網站完成下列程式，建立新的 eDiscovery 案例和新的 eDiscovery 集（例如，https://atl-sharepoint-001/sites/discovery):

1.  在 [網站內容] 頁面上，按一下 [**建立新案例**]。

2.  在 [網站內容]： [新增 SharePoint 網站] 頁面上，于 [**標題**] 方塊中輸入使用者的電子郵件別名（例如， **kenmyer**），然後將該 URL 新增至 [**網站位址**] 方塊。 如此一來，就會產生如下所示的 URL：
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer

3.  按一下 [**建立**]。

4.  出現 [eDiscovery 集] 頁面時，請按一下 [身分識別] 下的 [**新增專案**]，然後按 [**保留：探索**

5.  在 [新的：探索設定] 頁面上，于 [**探索集名稱**] 方塊中輸入使用者的電子郵件別名。 在 [**篩選**] 方塊中輸入**eDiscovery Lync\* ** ，然後按一下 [**新增 & 管理來源**]。

6.  在 [新增 & 管理來源] 頁面上，于 [**信箱**] 下的第一個文字方塊中輸入使用者的電子郵件別名。 按一下教科書旁邊的 [檢查信箱] 圖示，確認 SharePoint 可以連線至指定的信箱。

7.  按一下 [確定]****。

8.  在 [eDiscovery 集] 頁面上，按一下 [**儲存**] 以儲存新的 eDiscovery 集。

此時，您可以搜尋指定的信箱（kenmyer），並/或啟用就地保留，就與任何其他 SharePoint 內容或結果來源一樣。

</div>

<span> </span>

</div>

</div>

</div>

