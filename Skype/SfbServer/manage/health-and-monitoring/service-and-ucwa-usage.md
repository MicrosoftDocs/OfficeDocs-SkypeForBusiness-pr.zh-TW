---
title: 在商務用 Skype Server 中監視行動服務和 UCWA 使用狀況
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 摘要：在商務用 Skype Server 中管理行動服務 (Mcx) 和整合通訊網頁 API (UCWA) 。
ms.openlocfilehash: 76bcf8727d3abbb417595f033ce9a59ec00a39ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814243"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a>在商務用 Skype Server 中監視行動服務和 UCWA 使用狀況
 
**摘要：** 在商務用 Skype Server 中管理行動服務 (Mcx) 和整合通訊網頁 API (UCWA) 。

> [!NOTE]
> MCX (行動服務) 支援舊版行動用戶端，商務用 Skype Server 2019 不再提供支援。 所有目前的商務用 Skype mobile 用戶端都已經使用整合通訊網頁 API (UCWA) 以支援立即訊息 (IM) 、目前狀態及連絡人。 具有使用 MCX 之舊版用戶端的使用者，必須升級至目前的用戶端。
  
您應該定期監視商務用 Skype Server 行動服務 (Mcx) 和整合通訊網頁 API (UCWA) 所使用的 CPU 和記憶體。 若要監視使用狀況，您可以使用下列各項：
  
 **針對整合通訊網頁 API (UCWA) ：**
  
- 網際網路資訊服務中的 **LyncUcwa** 工作者進程 (IIS) 管理員。 在 [工作者處理序] 窗格中，查看 [CPU %] 和 [私用位元組 (KB)] (記憶體) 欄。
    
- [CPU] 和 [Processor] 效能計數器。
    
在大多數的部署中，UCWA CPU 使用量的平均應低於15%。 記憶體使用量應該位於 [監視器中為商務用 Skype 伺服器的伺服器記憶體容量限制](server-memory-capacity-limits.md)所述的限制範圍內。
  
除了 CPU 和記憶體使用量計數器之外，您還可以使用下列效能計數器，以協助判斷伺服器何時超載要求：
  
- **LS：網路節流和 Authentication\WEB-總處理中的要求**，表示伺服器上的擱置 WEB 要求數目。 當此計數器達到10000時，後續的要求會失敗，並顯示錯誤訊息「503-服務無法使用」。
    
- **ASP.NET\Requests Queued** (應該永遠為零)。
    
> [!NOTE]
> 如果您達到或超過這些值，您應該重新取得容量規劃，以確定 CPU 大小是否正確，以及主控 web 服務之電腦的核心和記憶體數目。 
  
 **若為行動服務 (Mcx) ：**
  
- Internet Information Services 中的 **CSIntMcxAppPool** 和 **CSExtMcxAppPool** 工作者進程 (IIS) 管理員。 在 [工作者處理序] 窗格中，查看 [CPU %] 和 [私用位元組 (KB)] (記憶體) 欄。
    
- [CPU] 和 [Processor] 效能計數器。
    
在大多數的部署中，行動性服務 CPU 使用量的平均應低於15%。 記憶體使用量應該位於 [監視器中為商務用 Skype 伺服器的伺服器記憶體容量限制](server-memory-capacity-limits.md)所述的限制範圍內。
  
除了 CPU 和記憶體使用量計數器，您也可以使用下列 ASP.NET 效能計數器來協助判斷伺服器何時超載要求：
  
- **ASP.NET v2.0.50727\Requests Current**，指出伺服器上的擱置 Web 要求數。 當此計數器達到5000時，後續的要求會失敗，並顯示錯誤訊息「503-服務無法使用」。
    
- **ASP.NET\Requests Queued** (應該永遠為零)。
    
> [!NOTE]
> 如果您達到或超過這些值，您應該重新查看並重新計算您的容量規劃，以瞭解主控 web 服務之電腦的 CPU、核心數目及記憶體大小是否正確。 

> [!NOTE]
> MCX (行動服務) 支援舊版行動用戶端，商務用 Skype Server 2019 不再提供支援。 所有目前的商務用 Skype mobile 用戶端都已經使用整合通訊網頁 API (UCWA) 以支援立即訊息 (IM) 、目前狀態及連絡人。 具有使用 MCX 之舊版用戶端的使用者，必須升級至目前的用戶端。
  
## <a name="see-also"></a>另請參閱

[監視商務用 Skype Server 中的伺服器記憶體容量限制](server-memory-capacity-limits.md)
