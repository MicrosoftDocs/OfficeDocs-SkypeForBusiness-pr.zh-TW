---
title: 設定 SharePoint 伺服器以搜尋封存商務用 Skype 資料
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 17f49365-8778-4962-a41b-f96faf6902f1
description: 摘要：設定 SharePoint 伺服器以搜尋 Exchange Server 和商務用 Skype Server 封存的資料。
ms.openlocfilehash: 0f2954d5a9875e3009733fc6d869ca57afbf086b
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62397287"
---
# <a name="configure-sharepoint-server-to-search-for-archived-skype-for-business-data"></a>設定 SharePoint 伺服器以搜尋封存商務用 Skype 資料
 
**總結：** 設定 SharePoint 伺服器以搜尋 Exchange Server 2016 或 Exchange Server 2013 及商務用 Skype Server 的封存資料。
  
在 Exchange Server，而不是商務用 Skype Server 中儲存立即訊息和網路會議記錄的主要優點之一，是將資料儲存在相同位置，讓系統管理員可以使用單一工具來搜尋封存的 Exchange 資料和/或已封存的商務用 Skype Server 資料。. 由於所有資料都儲存在相同的位置 (Exchange) 任何可搜尋已封存 Exchange 資料的工具也可以搜尋封存的商務用 Skype Server 資料。
  
一種可讓您搜尋封存資料的工具，會 Microsoft SharePoint Server 2013。 如果您想要使用 SharePoint 來搜尋商務用 Skype Server 資料，您必須先完成在商務用 Skype Server 中設定 Exchange 封存相關的所有步驟。 順利整合 Exchange Server 和商務用 Skype Server 之後，您必須在 SharePoint 伺服器上安裝 Exchange [Web Services Managed API](https://go.microsoft.com/fwlink/p/?LinkId=258305) 。 下載的檔案 (EWSManagedAPI.msi) 可以儲存至 SharePoint Server 上的任何資料夾。
  
下載檔案之後，在 SharePoint Server 上完成下列程序：
  
1. 依序按一下 [開始]、[所有程式] 及 [附屬應用程式]，再以滑鼠右鍵按一下 [命令提示字元]，然後按一下 [以系統管理員身分執行]，以開啟命令視窗。
    
2. 在命令視窗中，使用 cd 命令將現行目錄切換至儲存 EWSManagedAPI.msi 檔案的資料夾。 例如，如果您已將檔案儲存至 C:\Downloads，請在命令視窗中輸入下列命令，然後按 Enter：
    
   ```console
   cd C:\Downloads
   ```

3. 若要安裝 API，請輸入下列命令，然後按 Enter：
    
   ```console
   msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"
   ```

4. 安裝 API 後，請輸入下列命令，然後按 Enter，以重設 IIS：
    
   ```console
   iisreset
   ```

安裝 Exchange Web 服務之後，您必須設定 SharePoint 伺服器和 Exchange Server 之間的伺服器對伺服器驗證。 若要這麼做，請先開啟 SharePoint 管理命令介面，並執行下列命令組：
  
```powershell
New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
$service = Get-SPSecurityTokenServiceConfig
$service.HybridStsSelectionEnabled = $True
$service.AllowMetadataOverHttp = $False
$service.AllowOAuthOverHttp = $False
$service.Update()
```

> [!NOTE]
> 請務必將該 URI 用於自動探索服務。 請勿使用範例 URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1 。 
  
建立權杖簽發者並設定 token 服務之後，請執行下列命令，並確定將 SharePoint 網站的 url 取代為範例 url `http://atl-sharepoint-001` ：
  
```powershell
$exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
$app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
$site = Get-SPSite  "https://atl-sharepoint-001"
Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy
```

若要設定 Exchange Server 的伺服器對伺服器驗證，請開啟 Exchange 管理命令介面，並執行類似這種 (的命令，假設 Exchange 已安裝在磁碟機 C：上，而且其使用預設的資料夾路徑) ：
  
```powershell
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"
```

設定夥伴應用程式之後，建議您在所有 Exchange 信箱和用戶端存取伺服器上停止並重新啟動 Internet Information Services (IIS) 。 您可以使用如下命令來重新啟動 IIS，其會在電腦 atl-exchange-001 上重新啟動該服務：
  
```powershell
iisreset atl-exchange-001
```

您可以從 Exchange 管理命令介面或任何其他命令視窗中執行此命令。
  
接下來，執行類似下列的命令，可讓指定的使用者 (在此範例中，kenmyer) 在 Exchange 上進行探索的許可權：
  
```powershell
Add-RoleGroupMember "Discovery Management" -Member "kenmyer"
```

在 Exchange 和 SharePoint 之間建立伺服器對伺服器驗證之後，下一步是在 SharePoint 中建立 eDiscovery 網站。 您可以從 SharePoint 管理命令介面中執行類似下列的命令，以執行此作業：
  
```powershell
$template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"
```

> [!NOTE]
> "eDiscovery" 是 "electronic discovery" (電子化探索) 的縮寫，此程序通常是指在電子化封存中尋找可以在法庭上「合理計算以導出可採納證據」的項目。 
  
當新的網站準備好時，下一步是設定 Exchange Server，以當作 SharePoint 的結果來源。 您可以從 SharePoint 管理中心] 頁面完成下列程式，以執行此動作：
  
1. 在「管理中心」頁面上，按一下 [管理服務應用程式]，然後按一下 [Search Service 應用程式]。
    
2. 在「Search Service 應用程式：搜尋管理」頁面上，按一下 [結果來源] ，然後按一下 [新增結果來源]。
    
3. 在 [新增結果來源] 窗格的 [名稱] 方塊中，輸入新結果來源的名稱 (例如，**Microsoft Exchange**)。 選取 [ **Exchange** 為結果來源 **通訊協定**]，然後在 [ **Exchange 來源 URL** ] 方塊中輸入 Exchange 伺服器的 web 服務來源 url。 來源 URL 看起來應該像下面這樣：
    
    `https://atl-exchange-001.litwareinc.com/ews/exchange.asmx`
    
4. 請確定未選取 [使用自動探索]，然後按一下 [確定]。
    
最後，請從 SharePoint 探索網站 (中完成下列程式，以建立新的 ediscovery 案例及新的 ediscovery 集（例如， `https://atl-sharepoint-001/sites/discovery`) ：
  
1. 在「網站內容」頁面上，按一下 [建立新案例]。
    
2. 在「網站內容：建立 SharePoint 網站」頁面上的 [標題] 方塊中，輸入使用者的電子郵件別名 (例如，**kenmyer**)，然後將那相同的 URL 新增至 [網站位址] 方塊中。如此將會產生像下面這樣的 URL：
    
    `https://atl-sharepoint-001/sites/eDiscovery/kenmyer`
    
3. 按一下 [建立]。
    
4. 當「eDiscovery 集」頁面出現時，按一下 [識別與保留: Discovery 集] 底下的 [新項目]。
    
5. 在「新增：Discovery 集」頁面上的 [Discovery 集名稱] 方塊中，輸入使用者電子郵件別名。 在 [*篩選*] 方塊中輸入 **eDiscovery Lync \\** _，然後按一下 [**新增 &amp; 管理來源**]。
    
6. 在 [新增 &amp; 管理來源] 頁面上，于 [ **信箱**] 底下的第一個文字方塊中輸入使用者的電子郵件別名。 按一下位在文字方塊旁邊的檢查信箱圖示，確認 SharePoint 可以連線至指定的信箱。
    
7. 按一下 [確定]。
    
8. 在「eDiscovery 集」頁面上， 按一下 [儲存]，以儲存新的 eDiscovery 集。
    
此時，您可以搜尋指定的信箱 (kenmyer) 和/或啟用 In-Place 保留的方式與其他任何 SharePoint 內容或結果來源相同。
  

