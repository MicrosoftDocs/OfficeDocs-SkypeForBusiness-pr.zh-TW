---
title: 商務用 Skype Server 2019 的遷移
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 本節中的主題將引導您完成遷移至商務用 Skype Server 2019 的程式。
ms.openlocfilehash: 6eb192c11ec8d1f44539e3bd5180249d85180d2b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58587975"
---
# <a name="migration-to-skype-for-business-server-2019"></a>商務用 Skype Server 2019 的遷移

本節中的主題將引導您完成遷移至商務用 Skype Server 2019 的程式。 本文涵蓋如何遷移 Lync Server 2013 或商務用 Skype Server 2015，以商務用 Skype Server 2019。

> [!IMPORTANT]
> 在整個內容中，我們使用 *舊版* 的 Lync Server 2013 或您要遷移至商務用 Skype Server 2019 的商務用 Skype Server 2015。
  
> [!IMPORTANT]
> 本指南說明完成每一階段遷移的一般必要步驟。 它不會解決每一個可能的舊版部署拓撲或每一種可能的遷移案例。 因此，您可能不需要執行所述的每一個步驟，否則您可能需要執行其他步驟，視您的部署而定。 本指南也提供驗證步驟的範例。 提供這些驗證步驟是為了協助您瞭解需要尋找哪些專案，以確保每個階段在您完成遷移時順利完成。 將這些驗證步驟調整為您特定的遷移程式。 
  
本指南提供升級現有部署的相關資訊。 它不會說明如何變更現有的拓撲。 本指南並未涵蓋新功能的實施。 在其他地方記錄詳細的程式時，本指南會指引您前往 [文章] 或 [文章] 區段。 
  
本文依照下列清單所指定的方式來定義字詞。
  
**遷移：** 將實際執行部署從 Lync Server 2013 或商務用 Skype Server 2015 移至商務用 Skype Server 2019。
    
**共存：** 在遷移時所存在的暫時環境，當某些功能已遷移至商務用 Skype Server 2019，而其他功能仍然保留在先前的版本中時。
    
**互通性：** 您的部署在共存期間順利運作的能力。

**舊版：** 您要從其中遷移的系統，也就是 Lync Server 2013 或商務用 Skype Server 2015。
    
## <a name="in-this-section"></a>本節內容

- [開始移轉之前](before-you-begin-the-migration.md)
    
- [階段 1：規劃移轉](phase-1-plan-your-migration.md)
    
- [階段 2：準備移轉](phase-2-prepare-for-migration.md)
    
- [階段 3：部署試驗集區](phase-3-deploy-pilot-pool.md)
    
- [階段4：將測試使用者移至試驗集區](phase-4-move-test-users-to-the-pilot-pool.md)
    
- [階段 5：將 Edge Server 新增到試驗集區](phase-5-add-edge-server-to-pilot-pool.md)
    
- [階段 6：從試驗部署移至生產](phase-6-move-from-pilot-deployment-into-production.md)
    
- [階段 7：完成移轉後的工作](phase-7-complete-post-migration-tasks.md)
    
- [階段 8：解除委任舊版集區](phase-8-decommission-legacy-pools.md)
    

