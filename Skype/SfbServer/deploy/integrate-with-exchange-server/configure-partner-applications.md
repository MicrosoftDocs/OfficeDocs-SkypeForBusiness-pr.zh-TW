---
title: 在商務用 Skype Server 2015 和 Exchange Server 中設定合作夥伴應用程式
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
ms.assetid: 9c3a3054-6201-433f-b128-4c49d3341370
description: 摘要：設定伺服器對 Exchange Server 2016 或 Exchange Server 2013 及商務用 Skype Server 的伺服器驗證。
ms.openlocfilehash: d7a3b99536524df5422521cdaf45a7e4dac911b3
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62387211"
---
# <a name="configure-partner-applications-in-skype-for-business-server-and-exchange-server"></a>在商務用 Skype Server 和 Exchange Server 中設定夥伴應用程式
 
**總結：** 設定伺服器對 Exchange Server 2016 或 Exchange Server 2013 及商務用 Skype Server 的伺服器驗證。
  
伺服器對伺服器驗證通常需要兩部伺服器必須與彼此進行通訊，以及協力廠商的安全性權杖伺服器。 如果伺服器 A 和伺服器 B 需要通訊，則這兩部伺服器通常會先聯繫權杖伺服器，然後取得相互信任的安全性權杖。 伺服器 A 接著會向伺服器 B 呈現該安全性權杖 (，反之亦然) 做為保證其真實性和可信性的方式。
  
不過，這是一般規則。 商務用 Skype Server、Exchange Server 2016、Exchange Server 2013 及 SharePoint Server 2013 不需要使用協力廠商 token 伺服器進行通訊，這是因為這些伺服器產品可以建立可以彼此接受的安全性權杖，而不需要個別的token 伺服器。  (此功能僅適用于商務用 Skype Server、Exchange Server 2016、Exchange Server 2013 及 SharePoint Server 2013。 如果您需要使用其他伺服器（包括其他 Microsoft server 產品）設定伺服器對伺服器的驗證，則需要使用協力廠商的 token 伺服器來執行。 ) 
  
若要設定商務用 Skype Server 和 Exchange Server 之間的伺服器對伺服器驗證，您必須執行下列兩項作業： 1) 您必須將適當的憑證指派給每個伺服器; 2) 您必須將每一部伺服器設定為另一部伺服器的夥伴應用程式：也就是說，您必須設定商務用 Skype Server 若要成為 Exchange Server 的夥伴應用程式，且您必須設定 Exchange Server 成為商務用 Skype Server 的夥伴應用程式。
  
## <a name="configuring-skype-for-business-server-to-be-a-partner-application-for-exchange-server"></a>設定商務用 Skype Server 成為 Exchange Server 的夥伴應用程式

使用 Exchange Server 2016 或 Exchange Server 2013 設定商務用 Skype Server 成為夥伴應用程式的最簡單方法，就是執行 Configure-EnterprisePartnerApplication.ps1 腳本，該腳本是以 Windows PowerShell 隨附的 Exchange Server 腳本。 若要執行這個腳本，您必須供應商務用 Skype Server 驗證元資料檔案的 URL，這通常是商務用 Skype Server 集區的完整功能變數名稱，後面接尾碼/metadata/json/1。 例如：
  
```console
https://atl-cs-001.litwareinc.com/metadata/json/1
```

若要將商務用 Skype Server 設定為夥伴應用程式，請開啟 Exchange 管理命令介面，並執行類似這種 (的命令，假設 Exchange 已安裝在磁碟機 C：上，而且其使用預設的資料夾路徑) ：
  
```powershell
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"
```

設定夥伴應用程式之後，建議您停止並重新啟動 Exchange 信箱和用戶端存取伺服器上的 Internet Information Services (IIS) 。 您可以使用如下命令來重新啟動 IIS，其會在電腦 atl-exchange-001 上重新啟動該服務：
  
```powershell
iisreset atl-exchange-001
```

您可以從 Exchange 管理命令介面或任何其他命令視窗中執行此命令，在系統管理員許可權下執行。
  
## <a name="configuring-exchange-server-to-be-a-partner-application-for-skype-for-business-server"></a>設定 Exchange Server 成為商務用 Skype Server 的夥伴應用程式

設定商務用 Skype Server 成為 Exchange Server 2016 或 Exchange Server 2013 的夥伴應用程式之後，您必須將 Exchange Server 設定為商務用 Skype Server 的夥伴應用程式。 您可以使用商務用 Skype Server 管理命令介面，並指定 Exchange 的驗證元資料檔案，這通常是 Exchange 自動探索服務的 URI，後面接著尾碼/metadata/json/1。 例如：
  
```console
https://autodiscover.litwareinc.com/autodiscover/metadata/json/1
```

在商務用 Skype Server 中，會使用[New-CsPartnerApplication](/powershell/module/skype/new-cspartnerapplication?view=skype-ps) Cmdlet 來設定夥伴應用程式。 除了指定中繼資料 URI 之外，您還應該將應用程式信任層級設定為 [完整]。這可讓 Exchange 同時代表該領域的自身和任何已授權的使用者。 例如：
  
```powershell
New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
```

或者，您也可以複製及修改商務用 Skype Server 伺服器對伺服器驗證檔中找到的腳本程式碼，以建立夥伴應用程式。 如需詳細資訊，請參閱[管理商務用 Skype Server 文章中的伺服器對伺服器驗證 (OAuth) 和夥伴應用程式](../../manage/authentication/server-to-server-and-partner-applications.md)。
  
如果您已成功為商務用 Skype Server 和 Exchange Server 設定夥伴應用程式，您也已成功設定兩種產品之間的伺服器對伺服器驗證。 商務用 Skype Server 包含 Windows PowerShell Cmdlet， [Test-CsExStorageConnectivity](/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps)可讓您驗證服務器對伺服器驗證是否已正確設定，以及商務用 Skype Server 儲存體服務是否可以連接至Exchange Server。 此 Cmdlet 的執行方式是連線至 Exchange Server 使用者的信箱、將專案寫入該使用者的 [交談記錄] 資料夾中，然後 (選擇性地) 刪除該專案。
  
若要測試商務用 Skype Server 和 Exchange Server 的整合，請從商務用 Skype Server 管理命令介面執行類似下列的命令：
  
```powershell
Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"
```

在上述命令中，SipUri 代表在 Exchange Server 上具有帳戶之使用者的 SIP 位址; 您的命令會失敗。這不是有效的使用者帳戶。
  
> [!NOTE]
> 如果您收到來自此 Cmdlet 的401回應，這可能是因為 Exchange 的預設設定不支援接受 Oauth 權杖。 如需在 Exchange 中使用 Oauth 的詳細資訊，請參閱[Configure OAuth authentication with SharePoint 2013 and 商務用 Skype Server](/exchange/configure-oauth-authentication-with-sharepoint-2013-and-lync-2013-exchange-2013-help)。 
  
如果測試成功且已建立連線，您就可以繼續設定選用的功能，例如封存整合和整合連絡人存放區。