---
title: 規劃整合商務用 Skype Server 2015 與 Exchange
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ea22beb9-c02e-47cb-836d-97a556969052
description: '摘要: 請參閱本主題, 以取得如何將商務用 Skype 伺服器與 Exchange Server 2016 或 Exchange Server 2013 整合的相關資訊。'
ms.openlocfilehash: f62ad2475fe17668e82b06b1b4a0f19b6a2ee7c8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192989"
---
# <a name="plan-to-integrate-skype-for-business-and-exchange"></a>規劃整合商務用 Skype Server 2015 與 Exchange
 
**摘要:** 請參閱本主題, 以取得如何將商務用 Skype Server 與 Exchange Server 2016 或 Exchange Server 2013 整合的相關資訊。
  
在您整合商務用 Skype Server 與 Exchange Server 之前, 您必須確保 Exchange Server 和商務用 Skype Server 都已完整安裝且正常運作。 
  
如需有關安裝 Exchange Server 的詳細資訊, 請參閱 exchange Server 規劃和部署檔 (針對您的 Exchange 版本)。 
   
在伺服器啟動並執行之後, 您必須將伺服器對伺服器驗證憑證指派給商務用 Skype Server 和 Exchange Server;這些憑證可讓商務用 Skype Server 和 Exchange Server 交換資訊, 並與其他人通訊。 當您安裝 Exchange Server 時, 系統會為您建立一個名為 Microsoft Exchange Server Auth 憑證的自我簽署憑證。 這個可在本機電腦憑證存放區中找到的憑證應該用於 Exchange Server 上的伺服器對伺服器驗證。 如需在 Exchange Server 中指派憑證的詳細資料, 請參閱[設定郵件流程與用戶端存取](https://go.microsoft.com/fwlink/p/?LinkId=268540)。
  
在商務用 Skype Server 中, 您可以使用現有的商務用 Skype 伺服器憑證作為伺服器對伺服器驗證憑證;例如, 您的預設憑證也可以用來做為 OAuthTokenIssuer 憑證。 商務用 Skype Server 可讓您使用任何 Web 服務器憑證作為伺服器對伺服器驗證的憑證 (前提是:
  
- 憑證在 [Subject] 欄位中包含您 SIP 網域的名稱。
    
- 在所有前端伺服器上, 相同的憑證都設定為 OAuthTokenIssuer 憑證。
    
- 憑證的長度至少為2048位。
    
如需商務用 Skype Server 的伺服器對伺服器驗證憑證的詳細資料, 請參閱[將伺服器對伺服器驗證憑證指派給商務用 Skype 伺服器](../../manage/authentication/assign-a-server-to-server-certificate.md)。
  
指派憑證之後, 您必須接著設定 Exchange Server 上的自動探索服務。 在 Exchange 伺服器中, 自動探索服務會設定使用者設定檔, 並在使用者登入系統時提供 Exchange 服務的存取權。 使用者以其電子郵件地址和密碼出示自動探索服務;接著, 服務會為使用者提供下列資訊:
  
- Exchange Server 的內部和外部連線的連線資訊。
    
- 使用者信箱伺服器的位置。
    
- Outlook 功能的 Url, 例如 [空閒/忙碌] 資訊、[整合訊息] 和 [離線通訊錄]。
    
- Outlook Anywhere 伺服器設定。
    
您必須先設定自動探索服務, 才能整合商務用 Skype Server 與 Exchange Server。 您可以從 Exchange Server 管理命令介面執行下列命令, 並檢查 AutoDiscoverServiceInternalUri 屬性的值, 以驗證自動探索服務是否已設定:
  
```
Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List
```

如果此值為空白, 您必須為自動探索服務指派 URI。 通常, 此 URI 看起來會像這樣:https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml
  
您可以執行如下的命令來指派自動探索 URI:
  
```
Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"
```

如需自動探索服務的詳細資料, 請參閱[自動探索服務](https://go.microsoft.com/fwlink/p/?LinkId=268542)。
  
在已設定自動探索服務之後, 您必須接著修改商務用 Skype Server OAuth 設定設定;這可確保商務用 Skype 伺服器知道發現自動探索服務的位置。 若要在商務用 Skype Server 中修改 OAuth 設定設定, 請從商務用 Skype Server Management Shell 中執行下列命令。 執行此命令時, 請確定您已將 URI 指定到您的 Exchange 伺服器上執行的自動探索服務, 然後使用 [**自動**探索] 來指向服務位置, 而不是 [自動探索] **。 .XML** (指向 xml 檔案)服務使用):
  
```
Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
```

> [!NOTE]
> 上述命令中的身分識別參數是選擇性的,那是因為商務用 Skype Server 只允許您使用單一、全域的 OAuth 設定集合。 在其他專案中, 這表示您可以使用這個稍微簡單的命令來設定自動探索 URL: 
> 
> [!NOTE]
> Set-CsOAuthConfiguration-ExchangeAutodiscoverUrl "<https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc>" 
> 
> [!NOTE]
> 如果您不熟悉該技術, OAuth 是由許多主要網站使用的標準授權通訊協定。 在 OAuth 中, 使用者認證和密碼不會從一部電腦傳送至另一部電腦。 相反地, 驗證與授權是以安全權杖的交換為基礎;這些標記會針對特定的一組資源, 授予存取權。 
  
除了設定自動探索服務之外, 您也必須為指向您的 Exchange 伺服器的服務建立 DNS 記錄。 例如, 如果您的自動探索服務位於 autodiscover.litwareinc.com, 您將需要建立 autodiscover.litwareinc.com 的 DNS 記錄, 以解析為 Exchange 伺服器的完整功能變數名稱 (例如,atl-exchange-001.litwareinc.com)。
  
如果您要將商務用 Skype Server 與 Exchange Online 整合, 您的後續步驟就是在[內部部署商務用 Skype server 和 Outlook Web App 之間進行整合](../../deploy/integrate-with-exchange-server/outlook-web-app.md), 否則請參閱將[商務用 Skype 伺服器與 Exchange 整合伺服器](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)。
  
## <a name="feature-support"></a>功能支援
<a name="feature_support"> </a>

下表詳細說明在 Exchange 與商務用 Skype 的各種線上或內部部署所支援的功能。
  
||**Exchange 2016/2013/2010 (內部部署) + 商務用 Skype 伺服器 (內部部署)**|**Exchange Online + 商務用 Skype 伺服器 (內部部署)**|**Exchange 2010 (內部部署) + 商務用 Skype Online**|**Exchange 2016/2013 (內部部署) + 商務用 Skype Online**|**Exchange Online + 商務用 Skype Online**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Outlook 中的目前狀態  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |
|透過 Outlook 電子郵件的 IM、PSTN 通話、Skype 通話或視頻通話來回應  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |
|透過 Outlook 排程及加入線上會議  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |
|Outlook Web App 中的目前狀態  <br/> |是  <br/> |是  <br/> |否  <br/> |否  <br/> |是  <br/> |
|透過 OWA 電子郵件的 IM、PSTN 通話、Skype 通話或視頻通話來回應  <br/> |是  <br/> |是  <br/> |否  <br/> |否  <br/> |是  <br/> |
|透過 Outlook Web App 排程及加入線上會議  <br/> |是  <br/> |是  <br/> |否  <br/> |否  <br/> |是  <br/> |
|行動用戶端中的 IM/目前狀態  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |
|在行動用戶端中加入線上會議  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |
|根據 Outlook 行事曆空閒/忙碌資訊發佈狀態  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |
|連絡人清單 (透過整合連絡人存放區)  <br/> |Y (需要 Exchange 2016/2013)  <br/> |是  <br/> |否  <br/> |否  <br/> |是  <br/> |
|高解析度連絡人相片 (需要至少使用 Lync 2013 或商務用 Skype 用戶端。 在 LWA、行動應用程式、Lync 2010、Lync for Mac 和其他舊版用戶端中不支援。  <br/> |Y (需要 Exchange 2016/2013)  <br/> |是  <br/> |否  <br/> |是  <br/> |是  <br/> |
|會議委派  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |
|未接的交談記錄和通話記錄會寫入使用者的 exchange 信箱  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |
|在 Exchange 中封存內容 (IM 與會議)  <br/> |Y (需要 Exchange 2016/2013)  <br/> |是  <br/> |否  <br/> |否  <br/> |是  <br/> |
|搜尋封存的內容  <br/> |Y (需要 Exchange 2016/2013)  <br/> |是  <br/> |否  <br/> |否  <br/> |是  <br/> |
|Exchange UM 語音信箱  <br/> |是  <br/> |是  <br/> |否  <br/> |否  <br/> |否  <br/> |
|伺服器端交談歷程記錄  <br/> |是  <br/> |是  <br/> |否  <br/> |是  <br/> |是  <br/> |

> [!NOTE]
> 在商務用 Skype Online、商務用 skype Server 2019、商務用 Skype server 2015 和 Lync Server 2013 中, 都有支援雲端語音信箱服務。
> 

## <a name="see-also"></a>另請參閱
<a name="feature_support"> </a>

[設定內部部署商務用 Skype Server 和 Outlook Web App 之間的整合](../../deploy/integrate-with-exchange-server/outlook-web-app.md)
  
[在商務用 Skype Online 與 Exchange 內部部署之間設定 OAuth](../../deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises.md)

[將商務用 Skype Server 與 Exchange Server 整合](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
[如何將 Exchange Server 2013 與 Lync Server 2013、商務用 Skype Online 或 Lync 伺服器進行整合2013混合式部署](https://go.microsoft.com/fwlink/p/?LinkId=746494)
  
[在商務用 Skype Server 和 Microsoft Exchange Server 中設定合作夥伴應用程式](../../deploy/integrate-with-exchange-server/configure-partner-applications.md)
