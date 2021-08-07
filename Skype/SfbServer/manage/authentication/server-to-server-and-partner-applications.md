---
title: 在商務用 Skype Server 中管理伺服器對伺服器驗證 (OAuth) 和夥伴應用程式
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 38848373-c8c6-4097-bf7f-699fe471348d
description: 摘要：管理商務用 Skype Server 中的 OAuth 和夥伴應用程式。
ms.openlocfilehash: 9f463a02c21cf21ced5c42c87d604923038a429a603380b3a043d1423bded785
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54305445"
---
# <a name="manage-server-to-server-authentication-oauth-and-partner-applications-in-skype-for-business-server"></a>在商務用 Skype Server 中管理伺服器對伺服器驗證 (OAuth) 和夥伴應用程式
 
**摘要：** 管理商務用 Skype Server 中的 OAuth 和夥伴應用程式。
  
商務用 Skype Server 必須能夠與其他應用程式和伺服器產品進行安全、順利的通訊。 例如，您可以設定商務用 Skype Server，讓連絡人資料和（或）封存資料儲存在 Microsoft Exchange Server 2013 中;不過，只有商務用 Skype Server 和 Exchange 能夠安全地相互通訊時，才可以執行此動作。 同樣地，您也可以在 Office Web 應用程式伺服器中排程商務用 Skype Server 會議;同樣地，如果兩部伺服器 (SharePoint 和商務用 Skype Server) 彼此信任，就會這麼做。 雖然您可以使用一種驗證機制來商務用 Skype Server 和 Exchange 之間的通訊，但是商務用 Skype Server 和 SharePoint 通訊的個別機制，但使用標準化的方法是針對所有伺服器對伺服器驗證和授權的方式。
  
使用單一的標準化方法進行伺服器對伺服器的驗證是商務用 Skype Server 所採用的方法。 開始使用 Office server 2013 版本、商務用 Skype Server (以及其他 Microsoft Server 產品（包括 Exchange Server 及 SharePoint server) 支援 OAuth (開放授權) 通訊協定，以進行伺服器對伺服器驗證和授權。 藉由 OAuth (一些主要網站皆使用的標準授權通訊協定)，使用者認證及密碼並不會在電腦間傳遞。 驗證及授權是基於安全性權杖的交換，這些權杖會授與一段特定時間內一組特定資源的存取權。
  
OAuth 驗證通常涉及三方：單一授權伺服器及兩個需要互相通訊的領域。  (您也可以執行伺服器對伺服器驗證，而不需使用授權伺服器，本檔稍後將會討論此程式。授權伺服器（也稱為安全性權杖伺服器）發出 ) 的安全性權杖， (也稱為安全性權杖伺服器) 至需要通訊的兩個領域;這些權杖會驗證來自某個領域的通訊是否應該由其他領域所信任。 例如，授權伺服器可能會發出標記，以確認特定商務用 Skype Server 領域的使用者能夠存取指定的 Exchange 領域，反之亦然。
  
> [!NOTE]
> 領域只是安全性容器。 商務用 Skype Server 預設會使用您的預設 SIP 網域作為其 OAuth 領域。 其他 SIP 命名空間會新增至 OAuth 憑證中的主體替代名稱清單。 
  
商務用 Skype Server 支援三種伺服器對伺服器驗證案例。 使用商務用 Skype Server，您可以：
  
- 設定商務用 Skype Server 的內部部署安裝與 Exchange 和/或 SharePoint 伺服器的內部部署安裝之間的伺服器對伺服器驗證。
    
- 設定一對 Microsoft 365 或 Office 365 元件之間的伺服器對伺服器驗證 (例如，介於 Microsoft Exchange Server 及商務用 Skype Server 之間，或商務用 Skype Server 和 SharePoint) 之間。
    
- 在跨單位環境中設定伺服器對伺服器的驗證 (也就是說，在內部部署伺服器與 Microsoft 365 或 Office 365 元件) 之間的伺服器對伺服器驗證。
    
請注意，目前只有 Exchange 2013、SharePoint 伺服器、Lync server 2013、商務用 Skype Server 2015 及商務用 Skype 2019 支援伺服器對伺服器驗證;如果您未執行這些伺服器之一，您將無法完全執行 OAuth 驗證。
  
您也應該指出伺服器對伺服器驗證是選用的：如果商務用 Skype Server 不需要與其他伺服器通訊 (如 Exchange) 則可以完全略過伺服器對伺服器驗證。 如果已為 Lync server 2013 和其他應用程式設定伺服器對伺服器驗證，則不需要為商務用 Skype Server 重新執行。 
  
不過，如果您想要使用商務用 Skype Server 中的某些功能（例如「整合連絡人存放區」），則需要伺服器對伺服器驗證。 整合連絡人存放區會將商務用 Skype Server 連絡人資訊儲存在 Exchange 中，而非商務用 Skype Server 中;這可讓使用者有一組可在商務用 Skype、Outlook 或 Outlook Web 存取中輕鬆存取的連絡人。 由於整合的連絡人存放區需要商務用 Skype Server 以 Exchange 共用資訊，因此您必須使用伺服器對伺服器驗證，才能部署該功能。 如果您選擇使用 Exchange 封存，而且立即訊息會話的記錄會儲存為 Exchange 電子郵件，而不是個別的資料庫記錄，則也需要伺服器對伺服器驗證。
  
若要讓 Microsoft 365 或 Office 365 版本的商務用 Skype Server 與其 Exchange 對應，商務用 Skype Server 必須先從授權伺服器取得安全性權杖。 商務用 Skype Server 然後使用該安全性權杖識別自己 Exchange。 Exchange 的 Microsoft 365 或 Office 365 版本必須經過相同的程式，才能與商務用 Skype Server 通訊。
  
不過，對於兩部 Microsoft 伺服器之間的內部部署伺服器對伺服器驗證，則不需要使用協力廠商權杖伺服器。 伺服器產品（如商務用 Skype Server 和 Exchange）具有內建的權杖伺服器，可用於與其他 Microsoft (伺服器（如支援伺服器對伺服器驗證的 SharePoint 伺服器) ）的驗證目的。 例如，商務用 Skype Server 可以自行發行和簽署安全性權杖，然後使用該權杖與 Exchange 進行通訊。 在這種情況下，便不需要協力廠商權杖伺服器。
  
若要為商務用 Skype Server 的內部部署執行設定伺服器對伺服器驗證，您必須執行下列兩項作業：
  
- 將憑證指派給內建的商務用 Skype Server token 簽發者。
    
- 設定商務用 Skype Server 通訊的伺服器為 "partner application"。 例如，如果商務用 Skype Server 需要與 Exchange 通訊，您必須將 Exchange 設定為夥伴應用程式。
    
> [!NOTE]
> 「協力廠商應用程式」是指任何商務用 Skype Server 可以直接交換安全性權杖的應用程式，而不必經過協力廠商的安全性權杖伺服器。 
  
請注意，OAuth 是產品的核心部分，無法停用或移除。
  
## <a name="see-also"></a>另請參閱

[將伺服器對伺服器驗證憑證指派給商務用 Skype Server](assign-a-server-to-server-certificate.md)
  
[在商務用 Skype Server 中設定混合式環境](configure-a-hybrid-environment.md)
