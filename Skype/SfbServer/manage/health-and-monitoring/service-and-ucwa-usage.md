---
title: 在商務用 Skype Server 中監視行動服務和 UCWA 使用狀況
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 摘要：在商務用 Skype Server 中管理行動服務 (Mcx) 和整合通訊網頁 API (UCWA) 。
ms.openlocfilehash: d7596bfaf4e90f0eef25dbc625719f8739255858
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62393765"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a>在商務用 Skype Server 中監視行動服務和 UCWA 使用狀況
 
**總結：** 在商務用 Skype Server 中管理行動服務 (Mcx) 和整合通訊網頁 API (UCWA) 。

> [!NOTE]
> 商務用 Skype Server 2019 不再提供舊版行動用戶端的 MCX (行動服務) 支援。 所有目前商務用 Skype 的行動裝置都已經使用整合通訊 Web API (UCWA) 以支援立即訊息 (IM) 、目前狀態及連絡人。 具有使用 MCX 之舊版用戶端的使用者，必須升級至目前的用戶端。
  
您應該定期監視商務用 Skype Server 行動服務 (Mcx) 和整合通訊 Web API (UCWA) 所使用的 CPU 和記憶體。 若要監視使用狀況，您可以使用下列各項：
  
 **針對整合通訊網頁 API (UCWA) ：**
  
- Internet Information Services 中的 **LyncUcwa** 工作者進程 (IIS) 管理員。 在 [工作者處理序] 窗格中，查看 [CPU %] 和 [私用位元組 (KB)] (記憶體) 欄。
    
- [CPU] 和 [Processor] 效能計數器。
    
在大多數的部署中，UCWA CPU 使用量的平均應低於15%。 記憶體使用量應該在商務用 Skype Server 中的[伺服器記憶體容量限制](server-memory-capacity-limits.md)中所述的限制範圍內。
  
除了 CPU 和記憶體使用量計數器之外，您還可以使用下列效能計數器，以協助判斷伺服器何時超載要求：
  
- **LS：網路節流和 Authentication\WEB-總處理中的要求**，表示伺服器上的擱置 WEB 要求數目。 當此計數器達到10000時，後續的要求會失敗，並顯示錯誤訊息「503-服務無法使用」。
    
- **ASP.NET\Requests Queued** (應該永遠為零)。
    
> [!NOTE]
> 如果您達到或超過這些值，您應該重新取得容量規劃，以確定 CPU 大小是否正確，以及主控 web 服務之電腦的核心和記憶體數目。 
  
 **若為行動服務 (Mcx) ：**
  
- Internet Information Services (IIS) 管理員中的 **CSIntMcxAppPool** 和 **CSExtMcxAppPool** 工作者處理常式。 在 [工作者處理序] 窗格中，查看 [CPU %] 和 [私用位元組 (KB)] (記憶體) 欄。
    
- [CPU] 和 [Processor] 效能計數器。
    
在大多數的部署中，行動性服務 CPU 使用量的平均應低於15%。 記憶體使用量應該在商務用 Skype Server 中的[伺服器記憶體容量限制](server-memory-capacity-limits.md)中所述的限制範圍內。
  
除了 CPU 和記憶體使用量計數器，您也可以使用下列 ASP.NET 效能計數器來協助判斷伺服器何時超載要求：
  
- **ASP.NET v2.0.50727\Requests Current**，指出伺服器上的擱置 Web 要求數。 當此計數器達到5000時，後續的要求會失敗，並顯示錯誤訊息「503-服務無法使用」。
    
- **ASP.NET\Requests Queued** (應該永遠為零)。
    
> [!NOTE]
> 如果您達到或超過這些值，您應該重新查看並重新計算您的容量規劃，以瞭解主控 web 服務之電腦的 CPU、核心數目及記憶體大小是否正確。 

> [!NOTE]
> 商務用 Skype Server 2019 不再提供舊版行動用戶端的 MCX (行動服務) 支援。 所有目前商務用 Skype 的行動裝置都已經使用整合通訊 Web API (UCWA) 以支援立即訊息 (IM) 、目前狀態及連絡人。 具有使用 MCX 之舊版用戶端的使用者，必須升級至目前的用戶端。
  
## <a name="see-also"></a>另請參閱

[監視商務用 Skype Server 中的伺服器記憶體容量限制](server-memory-capacity-limits.md)
