---
title: 在商務用 Skype Server 中管理伺服器間驗證 (OAuth) 與合作夥伴應用程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 38848373-c8c6-4097-bf7f-699fe471348d
description: '摘要: 在商務用 Skype Server 中管理 OAuth 與合作夥伴應用程式。'
ms.openlocfilehash: 37c2af8a089bcae4b974761616e1ecd67c9e500b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193015"
---
# <a name="manage-server-to-server-authentication-oauth-and-partner-applications-in-skype-for-business-server"></a>在商務用 Skype Server 中管理伺服器間驗證 (OAuth) 與合作夥伴應用程式
 
**摘要:** 在商務用 Skype Server 中管理 OAuth 與合作夥伴應用程式。
  
商務用 Skype 伺服器必須能夠與其他應用程式和伺服器產品進行安全且嚴密的通訊。 例如, 您可以設定商務用 Skype Server, 讓連絡人資料和/或歸檔資料儲存在 Microsoft Exchange Server 2013;不過, 只有當商務用 Skype 伺服器與 Exchange 能夠安全地與其他人通訊時, 才能執行此動作。 同樣地, 您可以在 Office Web Apps 伺服器中排程商務用 Skype Server 會議;同樣地, 只有在兩個伺服器 (SharePoint 和商務用 Skype 伺服器) 相互信任時, 才能執行這項操作。 雖然您可以使用一種驗證機制來在商務用 Skype 伺服器與 Exchange 之間通訊, 但在商務用 Skype Server 和 SharePoint 通訊時是一種不同的機制, 所以更好且更有效的方法是使用所有伺服器對伺服器驗證與授權的標準化方法。
  
使用單一、標準化的伺服器到伺服器驗證方法, 就是商務用 Skype Server 所採取的方法。 開始使用 Office server 2013 版本、商務用 Skype 伺服器 (以及其他 Microsoft Server 產品 (包括 Exchange Server 和 SharePoint Server), 支援伺服器對伺服器驗證的 OAuth (開放授權) 通訊協定, 以及授權. 使用 OAuth (由許多主要網站使用的標準授權通訊協定), 使用者認證和密碼不會從一部電腦傳送到另一部電腦。 相反地, 驗證與授權是以安全權杖的交換為基礎;這些標記會針對特定的一組資源, 授予存取權。
  
OAuth 驗證通常涉及三個參與方: 單一授權伺服器, 以及需要彼此通訊的兩個領域。 (您也可以執行伺服器對伺服器驗證, 而不使用授權伺服器, 本檔稍後會討論的程式。)安全權杖是由授權伺服器 (也稱為安全權杖伺服器) 頒發給需要通訊的兩個領域;這些權杖會確認源自某個領域的通訊應該受到其他領域的信任。 例如, 授權伺服器可能會頒發標記, 以驗證來自特定商務用 Skype 伺服器領域的使用者可以存取指定的 Exchange 領域, 反之亦然。
  
> [!NOTE]
> 領域只是一個安全性容器。 根據預設, 商務用 Skype Server 會使用預設的 SIP 網域作為其 OAuth 領域。 其他 SIP 命名空間會新增至 OAuth 憑證中的 [Subject 替換名稱] 清單。 
  
商務用 Skype 伺服器支援三個伺服器對伺服器驗證案例。 在商務用 Skype Server 中, 您可以:
  
- 在商務用 Skype Server 的內部部署安裝與 Exchange 與/或 SharePoint Server 的內部部署安裝之間, 設定伺服器對伺服器驗證。
    
- 在一對 Office 365 元件 (例如, 在 Microsoft Exchange Server 與商務用 Skype Server 之間, 或商務用 Skype Server 和 SharePoint 之間) 設定伺服器對伺服器的驗證。
    
- 在跨內部部署環境中設定伺服器對伺服器驗證 (也就是在內部部署伺服器與 Office 365 元件之間的伺服器對伺服器驗證)。
    
請注意, 在此時間點, 僅限 Exchange 2013、SharePoint Server、Lync Server 2013、商務用 skype Server 2015, 以及商務用 Skype 2019 支援伺服器對伺服器驗證;如果您沒有執行其中一個伺服器, 您將無法完全實現 OAuth 驗證。
  
您也應該指出該伺服器對伺服器驗證是選用的: 如果商務用 Skype 伺服器不需要與其他伺服器通訊 (例如 Exchange), 則可以完全略過伺服器對伺服器驗證。 如果已為 Lync Server 2013 和其他應用程式設定伺服器對伺服器驗證, 就不需要針對商務用 Skype Server 重新執行此操作。 
  
不過, 如果您想要使用商務用 Skype Server (例如「整合連絡人存放區」) 中的部分功能, 則需要伺服器對伺服器驗證。 使用 [整合連絡人存放區] 時, 商務用 Skype Server 連絡人資訊會儲存在 Exchange 中, 而不是商務用 Skype Server 中;這可讓使用者擁有一組可在商務用 Skype、Outlook 或 Outlook Web Access 中輕鬆存取的連絡人。 因為「整合連絡人存放區」需要商務用 Skype 伺服器與 Exchange 共用資訊, 所以您必須使用伺服器對伺服器驗證, 才能部署該功能。 如果您選擇使用 Exchange 封存, 且在其中將立即訊息會話的腳本儲存為 Exchange 電子郵件, 而不是個別的資料庫記錄, 也需要伺服器對伺服器驗證。
  
若要將 Office 365 版本的商務用 Skype 伺服器與其 Exchange 對應專案通訊, 商務用 Skype 伺服器必須先從授權伺服器取得安全權杖。 商務用 Skype 伺服器然後使用該安全權杖來識別 Exchange 本身。 Office 365 版本的 Exchange 必須經過同一個處理常式, 才能與商務用 Skype 伺服器進行通訊。
  
不過, 對於兩個 Microsoft 伺服器之間的內部部署伺服器與伺服器驗證, 不需要使用協力廠商的權杖伺服器。 伺服器產品 (例如商務用 Skype Server 和 Exchange) 有內建的權杖伺服器, 可用於針對支援伺服器對伺服器驗證的其他 Microsoft 伺服器 (例如 SharePoint Server) 進行驗證。 例如, 商務用 Skype 伺服器可以自行發出並簽署安全權杖, 然後使用該權杖與 Exchange 進行通訊。 在這種情況下, 不需要使用協力廠商的權杖伺服器。
  
若要為商務用 Skype Server 的內部部署實現設定伺服器對伺服器驗證, 您必須執行兩個動作:
  
- 將憑證指派給內建的商務用 Skype Server 權杖頒發者。
    
- 設定商務用 Skype 伺服器將與「合作夥伴應用程式」通訊的伺服器。 例如, 如果商務用 Skype 伺服器需要與 Exchange 通訊, 您必須將 Exchange 設定為合作夥伴應用程式。
    
> [!NOTE]
> "合作夥伴應用程式" 是商務用 Skype 伺服器可以直接與其交換安全權杖的任何應用程式, 而不需要經過協力廠商安全權杖伺服器。 
  
請注意, OAuth 是產品的核心元件, 且無法停用或移除。
  
## <a name="see-also"></a>另請參閱

[指派伺服器對伺服器驗證憑證至商務用 Skype 伺服器](assign-a-server-to-server-certificate.md)
  
[在商務用 Skype Server 中設定混合式環境](configure-a-hybrid-environment.md)
