---
title: 商務用 Skype Server高可用性規劃工具
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/8/2016
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
description: 商務用 Skype Server 2015 中大多數伺服器角色的主要高可用性架構，都是透過 pooling server 冗余度為基礎。 如果執行特定伺服器角色的伺服器失敗，集區中執行相同角色的其他伺服器就會接手該伺服器的負載。
ms.openlocfilehash: d8c6a16ba29d5725a148810c71a17325bdbab763
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/13/2021
ms.locfileid: "58234698"
---
# <a name="skype-for-business-server-high-availability-planning-tool"></a>商務用 Skype Server高可用性規劃工具
 
商務用 Skype Server 2015 中大多數伺服器角色的主要高可用性架構，都是透過 pooling server 冗余度為基礎。 如果執行特定伺服器角色的伺服器失敗，集區中執行相同角色的其他伺服器就會接手該伺服器的負載。
  
商務用 Skype Server 2015 需要至少兩部前端伺服器才能啟用高可用性。 規劃工具會使用下列準則，判斷是否會增加額外的伺服器以支援高可用性：
  
- 如果部署包含兩部以上的前端伺服器，則規劃工具不會新增額外的伺服器。
    
- 如果部署包含 Edge Server，則會新增另一部伺服器。 
    
- 如果部署包含持續性聊天，規劃工具將會新增額外的伺服器，但不會增加集區數目。 例如，如果部署已包含四部伺服器，則規劃工具會建議您新增另一部伺服器 (，共五部伺服器) ，但會維護單一集區。 
    
規劃工具也會為所有資料庫新增鏡像 SQL 資料庫。 例如，如果有前端 SQL Server 資料庫，規劃工具會將另一個資料庫新增為此資料庫的鏡像資料庫，並將其命名為「前端鏡像 SQL 資料庫。
  
如需更多有關準備環境以取得高可用性的詳細資訊，請參閱[商務用 Skype Server 2015 中的計畫進行高可用性和嚴重損壞修復](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。
  

