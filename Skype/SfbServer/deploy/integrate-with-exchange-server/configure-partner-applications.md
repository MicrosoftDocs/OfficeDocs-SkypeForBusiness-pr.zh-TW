---
title: 在商務用 Skype Server 2015 和 Exchange Server 中設定合作夥伴應用程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9c3a3054-6201-433f-b128-4c49d3341370
description: '摘要: 針對 Exchange Server 2016 或 Exchange Server 2013 及商務用 Skype Server, 將伺服器設定為伺服器驗證。'
ms.openlocfilehash: 4c7c8a0efb2432403422e33140c1a2fdf3551dd1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193840"
---
# <a name="configure-partner-applications-in-skype-for-business-server-and-exchange-server"></a>在商務用 Skype Server 和 Exchange Server 中設定合作夥伴應用程式
 
**摘要:** 針對 Exchange Server 2016 或 Exchange Server 2013 及商務用 Skype Server, 將伺服器設定為伺服器驗證。
  
伺服器對伺服器驗證通常需要兩個伺服器相互通訊, 以及協力廠商安全權杖伺服器。 如果伺服器 A 和伺服器 B 需要通訊, 則這兩個伺服器通常都是透過聯繫權杖伺服器並取得相互信任的安全權杖來開始。 伺服器 A 接著會將該安全權杖呈現給伺服器 B (反之亦然), 以保證其真實性與可信性。
  
不過, 這是一般規則。 商務用 Skype Server、Exchange Server 2016、Exchange Server 2013 及 SharePoint Server 2013 在彼此通訊時不需要使用協力廠商的權杖伺服器;這是因為這些伺服器產品可以建立一個可以彼此接受的安全權杖, 而不需要個別的權杖伺服器。 (這項功能僅適用于商務用 Skype Server、Exchange Server 2016、Exchange Server 2013 及 SharePoint Server 2013。 如果您需要設定與其他伺服器 (包括其他 Microsoft 伺服器產品) 的伺服器對伺服器驗證, 您需要使用協力廠商的權杖伺服器來執行此操作。
  
若要在商務用 Skype Server 與 Exchange Server 之間設定伺服器對伺服器的驗證, 您必須執行兩個動作: 1) 您必須將適當的憑證指派給每個伺服器;而且, 2) 您必須將每個伺服器設定為另一個伺服器的合作夥伴應用程式: 這表示您必須將商務用 Skype Server 設定為 Exchange Server 的合作夥伴應用程式, 而且您必須將 Exchange Server 設定為適用于 Skype 的合作夥伴應用程式商務用伺服器。
  
## <a name="configuring-skype-for-business-server-to-be-a-partner-application-for-exchange-server"></a>將商務用 Skype 伺服器設定為 Exchange Server 的合作夥伴應用程式

若要將商務用 Skype 伺服器設定為使用 Exchange Server 2016 或 Exchange Server 2013 的合作夥伴應用程式, 最簡單的方法就是執行 Configure-EnterprisePartnerApplication. ps1 腳本 (即隨 Exchange Server 隨附的 Windows PowerShell 腳本)。 若要執行此腳本, 您必須供應商務用 Skype Server 驗證元資料檔案的 URL;這通常是商務用 Skype 伺服器池的完整功能變數名稱, 後面接著尾碼/metadata/json/1。 例如：
  
```
https://atl-cs-001.litwareinc.com/metadata/json/1
```

若要將商務用 Skype Server 設定為合作夥伴應用程式, 請開啟 Exchange 管理命令介面, 並執行類似這個的命令 (假設 Exchange 已安裝在磁碟機 C:, 且它使用預設的資料夾路徑):
  
```
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"
```

在設定合作夥伴應用程式之後, 建議您在 Exchange 信箱和用戶端存取伺服器上停止並重新啟動 Internet 資訊服務 (IIS)。 您可以使用類似這個的命令重新開機 IIS, 這會重新開機電腦 atl-exchange-001 的服務:
  
```
iisreset atl-exchange-001
```

這個命令可以從 Exchange 管理命令介面或從任何其他命令視窗在 [管理員許可權] 下執行。
  
## <a name="configuring-exchange-server-to-be-a-partner-application-for-skype-for-business-server"></a>將 Exchange Server 設定為商務用 Skype Server 的合作夥伴應用程式

將商務用 Skype Server 設定為 Exchange Server 2016 或 Exchange Server 2013 的合作夥伴應用程式之後, 您必須將 Exchange Server 設定為適用于商務用 Skype Server 的合作夥伴應用程式。 您可以使用商務用 Skype Server Management 命令介面, 並指定 Exchange 的驗證元資料檔案來完成此動作;這通常會是 Exchange 自動探索服務的 URI, 後面接著尾碼/metadata/json/1。 例如：
  
```
https://autodiscover.litwareinc.com/autodiscover/metadata/json/1
```

在商務用 Skype Server 中, 合作夥伴應用程式是使用[CsPartnerApplication](https://docs.microsoft.com/powershell/module/skype/new-cspartnerapplication?view=skype-ps) Cmdlet 進行設定。 除了指定中繼資料 URI 之外, 您也應該將應用程式信任等級設為 Full;這將允許 Exchange 代表其本身以及領域中的任何授權使用者。 例如：
  
```
New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
```

或者, 您也可以透過複製及修改商務用 Skype Server server 伺服器驗證檔中找到的腳本代碼, 來建立合作夥伴應用程式。 如需詳細資訊, 請參閱在[商務用 Skype server 文章中管理伺服器與伺服器驗證 (OAuth) 和合作夥伴應用程式](../../manage/authentication/server-to-server-and-partner-applications.md)。
  
如果您已成功設定商務用 Skype Server 與 Exchange Server 的合作夥伴應用程式, 您也可以成功地在兩個產品之間設定伺服器對伺服器的驗證。 商務用 skype Server 包含 Windows PowerShell Cmdlet、[測試 CsExStorageConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps) , 可讓您確認已正確設定伺服器對伺服器驗證, 且商務用 Skype Server Storage Service 可以[連線至 Exchange Server]。 這個 Cmdlet 是透過連線至 Exchange 伺服器使用者的信箱、將專案寫入該使用者的 [交談記錄] 資料夾中, 然後 (選擇性) 刪除該專案來執行此動作。
  
若要測試商務用 Skype Server 與 Exchange Server 的整合, 請從商務用 Skype Server Management Shell 執行如下的命令:
  
```
Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"
```

在上述命令中, SipUri 代表在 Exchange 伺服器上擁有帳戶的使用者的 SIP 位址;您的命令會失敗, 這不是有效的使用者帳戶。
  
> [!NOTE]
> 如果您收到來自這個 Cmdlet 的401回應, 可能是因為 Exchange 的預設設定不包含對接受 Oauth 權杖的支援。 如需在 Exchange 中使用 Oauth 的詳細資訊, 請參閱[使用 SharePoint 2013 和商務用 Skype 伺服器設定 oauth 驗證](https://go.microsoft.com/fwlink/p/?LinkId=513103)。 
  
如果測試成功且已建立連線, 您就可以繼續設定 [存檔整合] 和 [整合連絡人存放區] 等選用功能。
