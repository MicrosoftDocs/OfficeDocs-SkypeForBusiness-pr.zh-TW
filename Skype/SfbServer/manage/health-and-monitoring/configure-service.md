---
title: 在商務用 Skype Server 中設定行動服務以取得高效能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: '摘要: 瞭解商務用 Skype 伺服器中的行動服務。'
ms.openlocfilehash: 35e04fa080964495ccd9abed28c0688dd7be45a9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193761"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a>在商務用 Skype Server 中設定行動服務以取得高效能
 
**摘要:** 瞭解商務用 Skype 伺服器中的行動服務。
  
> [!IMPORTANT]
> 本主題只適用于商務用 Skype Server 行動服務 (Mcx), 且不適用於在 Lync Server 2013 的累積更新中提供的統一通訊 Web API (UCWA): 2 月2013。 
  
當您在網際網路資訊服務 (IIS) 7.5 上安裝行動服務 (Mcx) 時, 行動服務安裝程式會在前端伺服器上設定一些效能設定。 我們建議您使用 IIS 7.5 進行行動。 這些設定會影響並行使用者要求的數目上限, 以及行動服務所允許的最大執行緒數。
  
以下是效能設定:
  
### <a name="settings-for-mcx-on-iis-75"></a>IIS 7.5 上的 Mcx 設定

1. **maxConcurrentThreadsPerCPU**已設定為零 (0)。
    
2. **maxConcurrentRequestsPerCPU**已設定為零 (0)。
    
3. ASP.NET 程式模型已設定為自動設定 (僅適用于 IIS 7.5)。
    
4. Http.sys 佇列限制設定為 1000 (依預設)。
    

