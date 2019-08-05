---
title: 設定混合式連接 |部署商務用 Skype Server 2019 連接
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: 在商務用 Skype Server 和商務用 Skype Online 之間實現混合式連線性的指示。
ms.openlocfilehash: ab7fb32c16e57e554c702a7b0f29ba350c1eedbe
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36185458"
---
# <a name="configure-hybrid-connectivity-between-skype-for-business-server-and-office-365"></a>在商務用 Skype Server 和 Office 365 之間設定混合式連接

**摘要:** 若要瞭解如何在商務用 Skype 伺服器與團隊或商務用 Skype Online 之間設定混合式連接, 請閱讀本主題。  混合式連線性可讓您將內部部署使用者移至團隊或商務用 Skype Online, 並讓您的使用者充分利用雲端服務。
  
在執行本主題中的步驟之前, 您應該先在[商務用 Skype Server 和 Office 365 之間進行閱讀規劃混合式連接](plan-hybrid-connectivity.md)。
  
下表列出設定商務用 Skype 混合式連線所需執行的工作, 並提供相關文章的連結以取得詳細資訊。
  
|循序漸進|說明|
|:-----|:-----|
|建立 Office 365 的租使用者帳戶   <br/> |瞭解[office 365](https://go.microsoft.com/fwlink/p/?LinkId=254980)中的 office 365。  <br/> 若要確定您的環境已準備好進行 Office 365, 請參閱[系統需求](https://products.office.com/en-US/office-system-requirements)。  <br/> 如需有關設定 Office 365 的詳細資訊, 請參閱[Office 365 快速入門](https://go.microsoft.com/fwlink/p/?LinkId=254982)。  <br/> |
|將您的網域新增至您的 Office 365 租使用者並驗證擁有權  <br/> | 您必須將您的網域新增至您的 Office 365 租使用者, 然後依照步驟使用 Office 365 驗證網域。 這是為了確認您是網域的擁有者。 <br/> 若要將您的網域新增至您的 Office 365 租使用者, 請按照在[office 365 中新增網域](https://support.office.com/en-us/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US)中所述的步驟進行。  <br/> |
|設定 Active Directory 同步處理  <br/> |Active Directory 同步處理可讓您的內部部署 Active Directory 持續與 Office 365 保持同步。 這可讓您建立每個使用者帳戶和群組的同步處理版本。  <br/> <br> **重要:** 您必須在內部部署和線上部署之間, 同步處理貴組織中所有商務用 Skype 使用者的廣告帳戶, 即使使用者未移至 [小組] 或 [商務用 Skype Online]。 如果您不同步處理所有使用者, 貴組織中內部部署與線上使用者之間的通訊可能無法如期運作。 如需詳細資訊, 請參閱[針對混合式環境設定 AZURE AD Connect](configure-azure-ad-connect.md)。         |
| 設定商務用 Skype 混合式 | 有三個基本步驟: <br><br> 1. 設定您的內部部署環境, 以與 Office 365 聯盟。 <br> 2. 將您的內部部署環境設定為信任 Office 365, 並啟用 Office 365 共用的 SIP 位址空間。<br> 3. 在您的 Office 365 租使用者中啟用共用的 SIP 位址空間。 <br><br> 此外, 如果您有 Exchange 內部部署, 您可能會想要在 Exchange 內部部署和商務用 Skype Online 環境之間設定 OAuth。 <br> <br>如需詳細資訊, 請參閱[設定商務用 Skype 混合](configure-federation-with-skype-for-business-online.md)式。
|移動試驗使用者  <br/> |完成準備及設定團隊或商務用 Skype Online 之環境的步驟之後, 您就可以開始將試點使用者移至您的線上 Office 365 租使用者。 如需詳細資訊, 請參閱[將使用者從內部部署移至商務用 Skype Online](move-users-from-on-premises-to-skype-for-business-online.md) , 並[將使用者從內部部署移至團隊](move-users-from-on-premises-to-Teams.md)。  <br/> |