---
title: 設定混合式連接 |部署商務用 Skype Server 2019 connect
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: 在商務用 Skype Server 與商務用 Skype Online 之間實施混合式連線的指示。
ms.openlocfilehash: 0c4b2f716e906e30dd45b2750cfe5487868ce6df
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780092"
---
# <a name="configure-hybrid-connectivity-between-skype-for-business-server-and-office-365"></a>設定商務用 Skype Server 和 Office 365 之間的混合式連線

**摘要：** 閱讀此主題以瞭解如何設定商務用 Skype Server 和團隊或商務用 Skype Online 之間的混合式連線。  混合式連線功能可讓您將內部部署使用者移至小組或商務用 Skype Online，並讓您的使用者能夠充分利用雲端服務。
  
在執行本主題中的步驟之前，您應該具備[商務用 Skype Server 與 Office 365 之間的閱讀計畫混合](plan-hybrid-connectivity.md)式連線。
  
下表列出設定商務用 Skype 混合式連線所需的工作，並提供相關文章的連結，以取得詳細資訊。
  
|步驟|描述|
|:-----|:-----|
|建立 Office 365 的租使用者帳戶   <br/> |深入瞭解 office 365 at [office 365](https://go.microsoft.com/fwlink/p/?LinkId=254980)。  <br/> 若要確定您的環境已準備好用於 Office 365，請參閱[系統需求](https://products.office.com/office-system-requirements)。  <br/> 如需設定 Office 365 的詳細資訊，請參閱[Office 365 快速](https://go.microsoft.com/fwlink/p/?LinkId=254982)入門。  <br/> |
|將您的網域新增至 Office 365 組織，並確認擁有權  <br/> | 您必須將您的網域新增至 Office 365 組織，然後依照步驟驗證使用 Office 365 的網域。 這是確認您是網域的擁有者。 <br/> 若要將您的網域新增至 Office 365 組織，請遵循[add a domain To Office 365](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US)中所述的步驟。  <br/> |
|設定 Active Directory 同步處理  <br/> |Active Directory 同步處理會使您的內部部署 Active Directory 持續與 Office 365 保持同步。 這可讓您為每個使用者帳戶和群組建立同步處理的版本。  <br/> <br> **重要：** 您必須在內部部署與線上部署之間同步處理組織內所有商務用 Skype 使用者的 AD 帳戶，即使使用者未移至小組或商務用 Skype Online 也是一樣。 如果您未同步處理所有使用者，組織中內部部署與線上使用者之間的通訊可能無法如預期的方式運作。 如需詳細資訊，請參閱[Configure AZURE AD Connect for 混合式環境](configure-azure-ad-connect.md)。         |
| 設定商務用 Skype 混合式 | 有三個基本步驟： <br><br> 1. 設定您的內部部署環境，以與 Office 365 同盟。 <br> 2. 設定您的內部部署環境，以信任 Office 365 並啟用共用 SIP 位址空間與 Office 365。<br> 3. 在您的 Office 365 組織中啟用共用 SIP 位址空間。 <br><br> 此外，如果您有 Exchange 內部部署，您可能會想要在 Exchange 內部部署和商務用 Skype Online 環境之間設定 OAuth。 <br> <br>如需詳細資訊，請參閱[設定商務用 Skype 混合](configure-federation-with-skype-for-business-online.md)式。
|移動試驗使用者  <br/> |完成準備及設定您的環境以供團隊或商務用 Skype Online 之後，您可以開始將試驗使用者移至您的線上 Office 365 組織。 如需詳細資訊，請參閱[將使用者從內部部署移至商務用 Skype Online](move-users-from-on-premises-to-skype-for-business-online.md) ，以及[將使用者從內部部署移至團隊](move-users-from-on-premises-to-Teams.md)。  <br/> |