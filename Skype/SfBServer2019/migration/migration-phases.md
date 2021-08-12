---
title: 移轉階段
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 在商務用 Skype Server 2019 中，您可以在網路上定義包含商務用 Skype Server 2019 元件的網站。 網站是以高速度、低延遲網路連接的一組電腦，例如單一區域網路 (LAN) 或由高速光纖網路連接的兩個網路。
ms.openlocfilehash: 0e79dca32a0e3c377eea8e60e0e19514dcb7f4dfb459922b68c9913f4bd3c363
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54303417"
---
# <a name="migration-phases"></a>移轉階段

在商務用 Skype Server 2019 中，您可以在網路上定義包含商務用 Skype Server 2019 元件的網站。 網站是以高速度、低延遲網路連接的一組電腦，例如單一區域網路 (LAN) 或由高速光纖網路連接的兩個網路。 
  
前端集區是一組前端伺服器，其設定方式相同，並且共同運作，為一般使用者群組提供服務。 集區可為您的使用者提供延展性及容錯移轉功能。 集區中的每部伺服器都必須執行一或多個相同的伺服器角色。 針對小型組織設計的 Standard Edition 伺服器也會定義集區，並在單一伺服器上執行。 這可讓您以較低的成本商務用 Skype Server 2019 功能，但不會提供真正的高可用性解決方案。 
  
下列階段說明集區遷移至商務用 Skype Server 2019 的處理常式。 針對含有多個集區的多個站台，每一個集區都應該要遵循此階段式方法。
  
1. [階段 1：規劃移轉](phase-1-plan-your-migration.md)
    
2. [階段 2：準備移轉](phase-2-prepare-for-migration.md)
    
3. [階段3：部署商務用 Skype Server 2019 試驗集區](phase-3-deploy-pilot-pool.md)
    
4. [階段4：將測試使用者移至試驗集區](phase-4-move-test-users-to-the-pilot-pool.md)
    
5. [階段5：將商務用 Skype Server 2019 Edge Server 新增至試驗集區](phase-5-add-edge-server-to-pilot-pool.md)
    
6. [階段 6：從試驗部署移至生產](phase-6-move-from-pilot-deployment-into-production.md)
    
7. [階段 7：完成移轉後的工作](phase-7-complete-post-migration-tasks.md)
    
8. [階段 8：解除委任舊版集區](phase-8-decommission-legacy-pools.md)
    

