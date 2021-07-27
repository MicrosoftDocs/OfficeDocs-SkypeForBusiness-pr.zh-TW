---
title: 設定混合式連接 |部署商務用 Skype Server 2019 連接
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
description: 在商務用 Skype Server 和 Teams 之間實施混合式連線的指示。
ms.openlocfilehash: 2b0e9aabbe029dd292afabf3b7cac579f1029384
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/21/2021
ms.locfileid: "53510544"
---
# <a name="configure-hybrid-connectivity-between-skype-for-business-server-and-teams"></a>設定商務用 Skype Server 和 Teams 之間的混合式連線

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

**摘要：** 閱讀此主題以瞭解如何在商務用 Skype Server 和 Teams 之間設定混合式連線， (或商務用 Skype 線上，直到其退休) 為止。  混合式連線功能可讓您將內部部署使用者移至 Teams (或商務用 Skype 線上) ，並讓您的使用者能夠充分利用雲端服務。
  
在執行本主題中的步驟之前，您應該具備[商務用 Skype Server 和 Teams 之間](plan-hybrid-connectivity.md)的「讀取計畫」混合式連線。
  
下表列出設定商務用 Skype 混合式連線所需的工作，並提供相關文章的連結以取得詳細資訊。
  
|步驟|描述|
|:-----|:-----|
|為 Microsoft 365 建立租使用者帳戶   <br/> |深入瞭解 Microsoft 365 [Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=254980)。  <br/> 若要確定您的環境已準備好 Microsoft 365，請參閱[系統需求](https://products.office.com/office-system-requirements)。  <br/> 如需設定 Microsoft 365 的詳細資訊，請參閱[開始使用 Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=254982)。  <br/> |
|將您的網域新增至您的 Microsoft 365 組織，並驗證擁有權  <br/> | 您必須將您的網域新增至您的 Microsoft 365 組織，然後依照步驟使用 Microsoft 365 驗證網域。 這是確認您是網域的擁有者。 <br/> 若要將您的網域新增至您的 Microsoft 365 組織，請依照在[Microsoft 365 新增網域](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US)中所述的步驟進行。  <br/> |
|設定 Active Directory 同步處理  <br/> |Active Directory 同步處理會使您的內部部署 Active Directory 持續與 Microsoft 365 進行同步處理。 這可讓您為每個使用者帳戶和群組建立同步處理的版本。  <br/> <br> **重要：** 您必須同步處理組織內所有商務用 Skype 使用者的 AD 帳戶，即使使用者不會移至 Teams (或商務用 Skype 線上) 。 如果您未同步處理所有使用者，組織中內部部署與線上使用者之間的通訊可能無法如預期的方式運作。 如需詳細資訊，請參閱[設定混合式環境的 AZURE AD 連線](configure-azure-ad-connect.md)。         |
| 設定商務用 Skype 混合式 | 有三個基本步驟： <br><br> 1. 設定您的內部部署環境，以與 Microsoft 365 同盟。 <br> 2. 設定您的內部部署環境，以信任 Microsoft 365，並使用 Microsoft 365 啟用共用 SIP 位址空間。<br> 3. 在 Microsoft 365 組織中啟用共用 SIP 位址空間。 <br><br> 此外，如果您有 Exchange 內部部署，您可能會想要在 Exchange 內部部署和商務用 Skype Online 環境之間設定 OAuth。 <br> <br>如需詳細資訊，請參閱[Configure 商務用 Skype 混合](configure-federation-with-skype-for-business-online.md)。
|移動試驗使用者  <br/> |完成準備及設定環境以供 Teams (或商務用 Skype 線上) 之後，您可以開始將試驗使用者移至您的線上 Microsoft 365 組織。 如需詳細資訊，請參閱[將使用者從內部部署移至 Teams](move-users-from-on-premises-to-Teams.md) ，並[將使用者從內部部署移至商務用 Skype Online](move-users-from-on-premises-to-skype-for-business-online.md)。  <br/> |
