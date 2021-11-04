---
title: 規劃整合商務用 Skype 和 Exchange
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: ea22beb9-c02e-47cb-836d-97a556969052
description: 摘要：請參閱本主題，以取得如何將商務用 Skype Server 與 Exchange Server 2016 或 Exchange Server 2013 整合相關的資訊。
ms.openlocfilehash: 323add0bdc06617f80fba852b8179b3f6b7e315d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60773463"
---
# <a name="plan-to-integrate-skype-for-business-and-exchange"></a>規劃整合商務用 Skype 和 Exchange
 
**摘要：** 如需如何將商務用 Skype Server 與 Exchange Server 2016 或 Exchange Server 2013 整合的資訊，請參閱本主題。
  
您必須先確定 Exchange Server 和商務用 Skype Server 都已完整安裝並執行，您才能整合商務用 Skype Server 和 Exchange Server。 
  
如需安裝 Exchange Server 的詳細資訊，請參閱 Exchange 版本的 Exchange Server 規劃和部署檔。 
   
在伺服器啟動並執行後，您必須將伺服器對伺服器驗證憑證指派給商務用 Skype Server 和 Exchange Server;這些憑證可讓商務用 Skype Server 和 Exchange Server 交換資訊，以及彼此進行通訊。 當您安裝 Exchange Server 時，會為您建立名稱為 Microsoft Exchange Server 驗證憑證的自我簽署憑證。 此憑證可以在本機電腦憑證存放區中找到，以供 Exchange Server 上的伺服器對伺服器驗證使用。 如需在 Exchange Server 中指派憑證的詳細資訊，請參閱[Configure Mail Flow and Client Access](/exchange/configure-mail-flow-and-client-access-exchange-2013-help)。
  
商務用 Skype Server 您可以使用現有的商務用 Skype Server 憑證做為伺服器對伺服器的驗證憑證;例如，您的預設憑證也可以當做 OAuthTokenIssuer 憑證使用。 商務用 Skype Server 可讓您使用任何網頁伺服器憑證作為伺服器對伺服器驗證的憑證，前提是：
  
- 憑證包含 [主旨] 欄位中的 SIP 網功能變數名稱稱。
    
- 在所有前端伺服器上，相同的憑證會設定為 OAuthTokenIssuer 憑證。
    
- 憑證的長度至少為2048位。
    
如需商務用 Skype Server 之伺服器對伺服器驗證憑證的詳細資訊，請參閱[指派伺服器對伺服器驗證憑證給商務用 Skype Server](../../manage/authentication/assign-a-server-to-server-certificate.md)。
  
在指派憑證之後，您必須在 Exchange Server 上設定自動探索服務。 在 Exchange Server 中，自動探索服務會設定使用者設定檔，並在使用者登入系統時，提供 Exchange 服務的存取權。 使用者會以他們的電子郵件地址和密碼呈現自動探索服務。反過來，服務也會為使用者提供下列資訊：
  
- 內部與外部連線的連線資訊 Exchange Server。
    
- 使用者的信箱伺服器位置。
    
- URLs 以取得空閒/忙碌資訊、整合通訊與離線通訊錄等 Outlook 功能。
    
- OutlookAnywhere 伺服器設定。
    
您必須先設定自動探索服務，才能整合商務用 Skype Server 和 Exchange Server。 您可以從 Exchange Server 管理命令介面執行下列命令，並檢查 AutoDiscoverServiceInternalUri 屬性的值，以確認是否已設定自動探索服務：
  
```PowerShell
Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List
```

如果此值為空白，您必須將 URI 指派給自動探索服務。 通常此 URI 如下所示： https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml
  
您可以執行類似如下的命令來指派自動探索 URI：
  
```PowerShell
Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"
```

如需自動探索服務的詳細資訊，請參閱 [自動探索服務](/Exchange/architecture/client-access/autodiscover)。
  
設定自動探索服務之後，您必須修改商務用 Skype Server OAuth 設定設定;這可確保商務用 Skype Server 知道找到自動探索服務的位置。 若要修改商務用 Skype Server 中的 OAuth 設定設定，請從商務用 Skype Server 管理命令介面內執行下列命令。 執行此命令時，請確定您指定的是在您的 Exchange Server 上執行之自動探索服務的 URI，並使用 **自動探索。 svc** 指向服務位置，而不是 **autodiscover.xml** (指向服務) 所使用的 XML 檔案：
  
```PowerShell
Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
```

> [!NOTE]
> 以上命令中的 Identity 參數是選用的;這是因為商務用 Skype Server 只允許您具有單一、全域的 OAuth 設定設定集合。 除此之外，也表示您可以使用這個稍微簡單的命令來設定自動探索 URL： 
> 
> [!NOTE]
> Set-CsOAuthConfiguration-ExchangeAutodiscoverUrl " <https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc> " 
> 
> [!NOTE]
> 如果您不熟悉此技術，OAuth 是許多主要網站所使用的標準授權通訊協定。 使用 OAuth 時，使用者認證和密碼不會從一部電腦傳遞到另一部電腦。 驗證及授權是基於安全性權杖的交換，這些權杖會授與一段特定時間內一組特定資源的存取權。 
  
除了設定自動探索服務之外，您還必須為指向您的 Exchange Server 的服務建立 DNS 記錄。 例如，如果您的自動探索服務位於 autodiscover.litwareinc.com，您將需要為 autodiscover.litwareinc.com 建立 DNS 記錄，以便解析為 Exchange Server (的完整功能變數名稱，例如 atl-exchange-001.litwareinc.com) 。
  
如果您要將商務用 Skype Server 與 Exchange Online 整合，接下來的步驟是在[內部部署商務用 Skype Server 和 Outlook Web App 之間設定整合](../../deploy/integrate-with-exchange-server/outlook-web-app.md)，否則請參閱[整合商務用 Skype Server 與 Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)。
  
## <a name="feature-support"></a>功能支援
<a name="feature_support"> </a>

>[!Important]
> 商務用 Skype線上將于2021年7月31日（包含服務將不再支援的 Exchange 整合）後終止。

下表說明 Exchange 和商務用 Skype 的各項線上或內部部署所支援的功能。
  
|&nbsp;|Exchange 2016/2013/2010 (內部部署) + 商務用 Skype Server (內部部署) | (內部部署) 的 Exchange Online + 商務用 Skype Server|* * Exchange 2010 (內部部署) + 商務用 Skype 線上|Exchange 2016/2013 (內部部署) + 商務用 Skype Online * *|* * Exchange Online + 商務用 Skype 線上|
|:-----|:-----|:-----|:-----|:-----|:-----|
|目前狀態 Outlook   |Y   |Y   |Y   |Y   |Y   |
|透過 IM、PSTN 通話、Skype 通話或從 Outlook 電子郵件的視頻呼叫進行回應   |Y   |Y   |Y   |Y   |Y   |
|透過 Outlook 排程及加入線上會議   |Y   |Y   |Y   |Y   |Y   |
|目前狀態 Outlook Web App   |Y   |Y   |N   |N   |Y   |
|利用 OWA 電子郵件的 IM、PSTN 通話、Skype 通話或視頻通話來回應   |Y   |Y   |N   |N   |Y   |
|透過 Outlook Web App 排程及加入線上會議   |Y   |Y   |N   |N   |Y   |
|行動用戶端中的 IM/目前狀態   |Y   |Y   |Y   |Y   |Y   |
|在行動用戶端加入線上會議   |Y   |Y   |Y   |Y   |Y   |
|根據 Outlook 的行事曆空閒/忙碌資訊發佈狀態   |Y   |Y   |Y   |Y   |Y   |
|透過整合連絡人存放區 (的連絡人清單)    |Y (需要 Exchange 2016/2013)    |Y   |N   |N   |Y   |
|高解析度連絡人相片 (至少需要 Lync 2013 或商務用 Skype 用戶端。 不支援 LWA、行動應用程式、Lync 2010、Lync for Mac 及其他舊版用戶端。 )    |Y (需要 Exchange 2016/2013)    |Y   |N   |Y   |Y   |
|會議委派   |Y   |Y   |Y   |Y   |Y   |
|錯過的交談記錄及通話記錄會寫入使用者的 exchange 信箱   |Y   |Y   |Y   |Y   |Y   |
|在 Exchange 中封存 (IM 和會議) 中的內容   |Y (需要 Exchange 2016/2013)    |Y   |N   |N   |Y   |
|搜尋封存的內容   |Y (需要 Exchange 2016/2013)    |Y   |N   |N   |Y   |
|ExchangeUM 語音信箱   |Y   |Y   |N   |N   |N   |
|伺服器端交談記錄   |Y   |Y   |N   |Y   |Y   |

> [!NOTE]
> 商務用 Skype Online 支援雲端語音信箱服務，商務用 Skype Server 2019、商務用 Skype Server 2015 和 Lync Server 2013。
> 

## <a name="see-also"></a>另請參閱
<a name="feature_support"> </a>

[設定內部部署商務用 Skype Server 和 Outlook Web App 之間的整合](../../deploy/integrate-with-exchange-server/outlook-web-app.md)
  
[設定商務用 Skype 線上和內部部署 Exchange 之間的 OAuth](../../deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises.md)

[將商務用 Skype Server 與 Exchange Server 整合](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
[如何將 Exchange Server 2013 與 lync server 2013、商務用 Skype 線上或 Lync server 2013 混合部署進行整合](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-hybrid-deployments)
  
[在商務用 Skype Server 和 Microsoft Exchange Server 中設定夥伴應用程式](../../deploy/integrate-with-exchange-server/configure-partner-applications.md)