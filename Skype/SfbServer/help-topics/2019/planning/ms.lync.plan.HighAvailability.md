---
title: 高可用性（規劃工具）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
ROBOTS: NOINDEX, NOFOLLOW
description: 商務用 Skype Server 中大多數伺服器角色的主要高可用性配置，都是透過 [彙集] 以伺服器冗余為基礎。 如果執行特定伺服器角色的伺服器失敗，則池中執行相同角色的其他伺服器會載入該伺服器。
ms.openlocfilehash: 328d269e6d6694dc26be66bd3894094770562726
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797174"
---
# <a name="high-availability-planning-tool"></a>高可用性（規劃工具）
 
商務用 Skype Server 中大多數伺服器角色的主要高可用性配置，都是透過 [彙集] 以伺服器冗余為基礎。 如果執行特定伺服器角色的伺服器失敗，則池中執行相同角色的其他伺服器會載入該伺服器。
  
商務用 Skype 伺服器需要至少兩個前端伺服器，才能啟用高可用性。 規劃工具會使用下列準則來判斷它是否會新增額外的伺服器，以支援高可用性：
  
- 如果部署包含兩個以上的前端伺服器，則規劃工具不會新增額外的伺服器。
    
- 如果部署包含 Edge 伺服器，則會新增其他伺服器。 
    
- 如果部署包含持續聊天，規劃工具將會新增額外的伺服器，但不會增加池的數目。 例如，如果部署已包含四個伺服器，則規劃工具會建議您新增其他伺服器（共5個伺服器），但會維持單一池。 

    > [!NOTE] 
    > 商務用 Skype Server 2015 提供持續聊天，但商務用 Skype Server 2019 已不再支援。 團隊中提供了相同的功能。 如需詳細資訊，請參閱[商務用 Skype 至 Microsoft 團隊升級](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here)。 如果您需要使用持續聊天，您可以選擇將需要此功能的使用者遷移至小組，或繼續使用商務用 Skype Server 2015。 

    
規劃工具也會為所有資料庫新增鏡像 SQL 資料庫。 例如，如果有前端 SQL Server 資料庫，規劃工具會將另一個資料庫作為此資料庫的鏡像資料庫，並將它命名為「前端鏡像 SQL 資料庫。
  
如需有關如何為高可用性準備環境的詳細資訊，請參閱[在商務用 Skype 伺服器中規劃高可用性和災害復原](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。
  

