---
title: '高可用性 (規劃工具) '
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 商務用 Skype Server 中大多數伺服器角色的主要高可用性架構，都是透過 pooling server 冗余度為基礎。 如果執行特定伺服器角色的伺服器失敗，集區中執行相同角色的其他伺服器就會接手該伺服器的負載。
ms.openlocfilehash: 5c9895e325770f5c826b5c55213fcc1b569aa701
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819793"
---
# <a name="high-availability-planning-tool"></a>高可用性 (規劃工具) 
 
商務用 Skype Server 中大多數伺服器角色的主要高可用性架構，都是透過 pooling server 冗余度為基礎。 如果執行特定伺服器角色的伺服器失敗，集區中執行相同角色的其他伺服器就會接手該伺服器的負載。
  
商務用 Skype Server 至少需要兩部前端伺服器才能啟用高可用性。 規劃工具使用下列準則來判斷是否會加入額外的伺服器，以支援高可用性：
  
- 如果部署包含兩部以上的前端伺服器，則規劃工具不會新增額外的伺服器。
    
- 如果部署包含 Edge Server，則會新增額外的伺服器。 
    
- 如果部署包含持續性聊天，規劃工具將會新增額外的伺服器，但不會增加集區數目。 例如，如果部署已包含四部伺服器，則規劃工具會建議您新增額外的伺服器 (，讓總數超過5部伺服器) ，但會維護單一集區。 

    > [!NOTE] 
    > 商務用 Skype Server 2015 仍提供持續聊天，但商務用 Skype Server 2019 已不再支援。 小組中提供相同的功能。 如需詳細資訊，請參閱 [商務用 Skype To Microsoft 小組升級](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here)。 如果您需要使用持續聊天，您可以選擇將需要這項功能的使用者遷移至小組，或繼續使用商務用 Skype Server 2015。 

    
規劃工具也會為所有資料庫新增鏡像 SQL 資料庫。 例如，如果有前端 SQL Server 資料庫，規劃工具會將另一個資料庫新增為此資料庫的鏡像資料庫，並將其命名為「前端鏡像 SQL 資料庫」。
  
如需準備環境以取得高可用性的詳細資訊，請參閱 [在商務用 Skype Server 中規劃高可用性和嚴重損壞修復](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。
  

