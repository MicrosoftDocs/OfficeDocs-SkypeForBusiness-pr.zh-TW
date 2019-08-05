---
title: 遷移多個網站和池
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: '商務用 Skype Server 2019 支援多網站和多池部署。 將多個池遷移到商務用 Skype Server 2019 的程式需要下列考慮:'
ms.openlocfilehash: 05a94cb47568b9dfc3834f65f960353ad2933b03
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193063"
---
# <a name="migrating-multiple-sites-and-pools"></a>遷移多個網站和池

商務用 Skype Server 2019 支援多網站和多池部署。 將多個池遷移到商務用 Skype Server 2019 的程式需要下列考慮: 
  
1. 在部署商務用 Skype Server 2019 試生產池之後, 您必須定義將移至商務用 Skype Server 2019 池的試驗使用者子集, 以及驗證使用者功能的方法。 例如, 將使用者移至 [試驗] 池之後, 請確認使用者的會議原則已移至 [商務用 Skype Server 2019]。 
    
2. 在試驗池中部署邊緣伺服器之後, 您必須確認外部使用者可以與商務用 Skype Server 2019 池通訊。

3. 在商務用 Skype server 2019 中, 持續式聊天、SQL 鏡像及 XMPP 功能已棄用, 且不再以商務用 Skype Server 2019 功能提供, 但在共存環境中, 如果它們先前部署在舊版環境。 如果您想要繼續使用這些功能, 您應該規劃繼續共存環境, 讓特定使用者保留在舊版池中。
    
4. 將同盟路由的邊緣伺服器轉換為試點商務用 Skype Server 2019 Edge 伺服器之後, 您必須確認聯盟使用者可以與商務用 Skype Server 2019 池通訊。
    
5. 移動所有使用者和非使用者連絡人物件之後, 您必須驗證舊版池是否為空白。
    
6. 在驗證舊版池為空白之後, 您可以將該池停用。 
    
    如需如何停用舊版池和伺服器的詳細資料, 請參閱[階段 8: 解除舊版池](phase-8-decommission-legacy-pools.md)。
    

