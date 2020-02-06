---
title: 在商務用 Skype Server 中監視行動服務與 UCWA 使用量
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 摘要：在商務用 Skype Server 中管理行動服務（Mcx）和整合通訊網頁 API （UCWA）。
ms.openlocfilehash: 7c41e92b144e1bd4d198c5e9d9f90913ce41400e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817682"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a>在商務用 Skype Server 中監視行動服務與 UCWA 使用量
 
**摘要：** 在商務用 Skype Server 中管理行動服務（Mcx）和整合通訊網頁 API （UCWA）。

> [!NOTE]
> MCX （行動服務）對舊版行動用戶端的支援已不再提供給商務用 Skype Server 2019。 所有目前的商務用 Skype 行動用戶端都已使用整合通訊 Web API （UCWA）來支援立即訊息（IM）、目前狀態和連絡人。 使用 MCX 的舊版用戶端的使用者將需要升級至目前的用戶端。
  
在持續性的基礎上，您應該監視商務用 Skype Server 行動服務（Mcx）和整合通訊網頁 API （UCWA）所使用的 CPU 和記憶體。 若要監視用法，您可以使用下列方法：
  
 **針對整合通訊網頁 API （UCWA）：**
  
- [網際網路資訊服務（IIS）管理員] 中的**LyncUcwa**工作進程。 在 [**工作進程**] 窗格中，查看 [ **CPU%** ] 和 [**專用位元組（KB）** ] （記憶體）資料行。
    
- **CPU**與**處理器**效能計數器。
    
在大部分的部署中，UCWA 的 CPU 使用量平均應低於15%。 記憶體使用量應該在監視器中的 [[商務用 Skype 伺服器的伺服器記憶體容量限制] 中](server-memory-capacity-limits.md)所述的限制範圍內。
  
除了 CPU 和記憶體使用量計數器之外，您還可以使用下列效能計數器，協助判斷伺服器何時以要求超載：
  
- **LS：網路節流與 Authentication\WEB 總處理中的要求總數**，指出伺服器上的未決 WEB 要求數目。 當這個計數器達到10000時，後續的要求將會失敗，並出現錯誤訊息「503-服務無法使用」。
    
- **NET\Requests 已排入佇列**（應該總是為零）。
    
> [!NOTE]
> 如果您達到或超過這些值，您應該重新進行容量規劃，以針對託管 web 服務的電腦正確地調整 CPU 大小、核心和記憶體的數量。 
  
 **針對行動服務（Mcx）：**
  
- [網際網路資訊服務（IIS）管理員] 中的**CSIntMcxAppPool**和**CSExtMcxAppPool**工作進程。 在 [**工作進程**] 窗格中，查看 [ **CPU%** ] 和 [**專用位元組（KB）** ] （記憶體）資料行。
    
- **CPU**與**處理器**效能計數器。
    
在大部分的部署中，行動服務 CPU 使用量的平均應低於15%。 記憶體使用量應該在監視器中的 [[商務用 Skype 伺服器的伺服器記憶體容量限制] 中](server-memory-capacity-limits.md)所述的限制範圍內。
  
除了 CPU 和記憶體使用量計數器之外，您還可以使用下列 ASP.NET 效能計數器，協助判斷伺服器何時使用要求進行超載：
  
- **ASP.NET v 2.0.50727 \ 請求 Current**，這表示伺服器上的未決 web 要求數目。 當這個計數器達到5000時，後續的要求將會失敗，並出現錯誤訊息「503-服務無法使用」。
    
- **NET\Requests 已排入佇列**（應該總是為零）。
    
> [!NOTE]
> 如果您達到或超過這些值，您應該重新進行容量規劃，以針對託管 web 服務的電腦正確地調整 CPU、核心數和記憶體大小。 

> [!NOTE]
> MCX （行動服務）對舊版行動用戶端的支援已不再提供給商務用 Skype Server 2019。 所有目前的商務用 Skype 行動用戶端都已使用整合通訊 Web API （UCWA）來支援立即訊息（IM）、目前狀態和連絡人。 使用 MCX 的舊版用戶端的使用者將需要升級至目前的用戶端。
  
## <a name="see-also"></a>另請參閱

[監視商務用 Skype Server 中的伺服器記憶體容量限制](server-memory-capacity-limits.md)
