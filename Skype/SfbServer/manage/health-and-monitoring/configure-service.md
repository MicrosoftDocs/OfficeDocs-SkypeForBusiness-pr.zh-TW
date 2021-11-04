---
title: 設定商務用 Skype Server 的高效能行動服務
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: 摘要：瞭解商務用 Skype Server 中的行動服務。
ms.openlocfilehash: ddf976d6adde4a8214a1a7ae1cc40930df421fd6
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60746985"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a>設定商務用 Skype Server 的高效能行動服務
 
**摘要：** 深入瞭解商務用 Skype Server 中的行動服務。
  
> [!IMPORTANT]
> 本主題只適用于商務用 Skype Server 行動性服務 (Mcx) ，但不適用於「整合通訊 Web API (UCWA) （如在 Lync Server 2013 的累計更新中傳遞）：二月份2013。 
  
當您在 Internet Information Services (IIS) 7.5 上安裝行動服務 (Mcx) 時，行動服務安裝程式會在前端伺服器上設定某些效能設定。 建議您使用 IIS 7.5 以用於行動性。 這些設定會影響並行使用者要求數目上限，以及行動性服務所允許的執行緒數目上限。
  
效能設定如下：
  
### <a name="settings-for-mcx-on-iis-75"></a>IIS 7.5 上 Mcx 的設定

1. **maxConcurrentThreadsPerCPU** 設定為零 (0) 。
    
2. **maxConcurrentRequestsPerCPU** 設定為零 (0) 。
    
3. ASP.NET 進程模型設定為僅) IIS 7.5 的自動設定 (。
    
4. HTTP.sys 佇列限制預設設定為 1000 () 。
    

