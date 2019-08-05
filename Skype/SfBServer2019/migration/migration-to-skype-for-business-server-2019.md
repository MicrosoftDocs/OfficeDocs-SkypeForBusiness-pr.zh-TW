---
title: 遷移至商務用 Skype Server 2019
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 本節中的主題會引導您逐步完成遷移至商務用 Skype Server 2019 的程式。
ms.openlocfilehash: bd1513e5ca2a33449f982394e4abc15b9616393b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193059"
---
# <a name="migration-to-skype-for-business-server-2019"></a>遷移至商務用 Skype Server 2019

本節中的主題會引導您逐步完成遷移至商務用 Skype Server 2019 的程式。 本文涵蓋將 Lync Server 2013 或商務用 Skype Server 2015 遷移至商務用 Skype Server 2019。

> [!IMPORTANT]
> 在整個內容中, 我們使用*舊版的舊版*Lync server 2013 或您要遷移至商務用 skype server 2019 的商務用 skype server 2015。
  
> [!IMPORTANT]
> 本指南描述完成每個遷移階段通常需要執行的步驟。 它不會針對每個可能的舊版部署拓撲或每個可能的遷移案例進行處理。 因此, 您可能不需要執行所述的每個步驟, 或者您可能需要執行其他步驟 (視您的部署而定)。 本指南也提供驗證步驟的範例。 提供這些驗證步驟是為了協助您瞭解所需尋找的專案, 以確保每個階段都能在您完成遷移時順利完成。 將這些驗證步驟調整為您特定的遷移程式。 
  
本指南提供升級現有部署的相關資訊。 它不會說明如何變更您現有的拓撲。 本指南並未涵蓋新功能的實現。 在其他地方記錄詳細的程式時, 本指南會將您導向至文章或文章區段。 
  
本文將根據下列清單中所指定的字詞加以定義。
  
**遷移:** 將您的生產部署從 Lync Server 2013 或商務用 Skype Server 2015 移至商務用 Skype Server 2019。
    
**共存:** 在遷移期間, 當某些功能已遷移至商務用 Skype Server 2019 且其他功能仍保留在先前版本時, 在遷移期間所存在的臨時環境。
    
**互通性:** 您的部署在共存期間成功運作的能力。

**舊版:** 您要從中移出的系統, 即 Lync Server 2013 或商務用 Skype Server 2015。
    
## <a name="in-this-section"></a>本節內容

- [開始進行遷移之前](before-you-begin-the-migration.md)
    
- [階段 1: 規劃您的遷移](phase-1-plan-your-migration.md)
    
- [階段 2: 準備遷移](phase-2-prepare-for-migration.md)
    
- [階段 3: 部署試生產池](phase-3-deploy-pilot-pool.md)
    
- [階段 4: 將測試使用者移至 [試驗] 池](phase-4-move-test-users-to-the-pilot-pool.md)
    
- [階段 5: 將邊緣伺服器新增至試驗池](phase-5-add-edge-server-to-pilot-pool.md)
    
- [階段 6: 從試驗部署移至生產環境](phase-6-move-from-pilot-deployment-into-production.md)
    
- [階段 7: 完成遷移後的工作](phase-7-complete-post-migration-tasks.md)
    
- [階段 8: 解除授權舊版池](phase-8-decommission-legacy-pools.md)
    

