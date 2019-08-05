---
title: 監視行動在商務用 Skype Server 中的效能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: '摘要: 瞭解商務用 Skype Server 中的行動服務 (Mcx) 和整合通訊網頁 API (UCWA)。'
ms.openlocfilehash: 7b8340d90b5e1fa18c4dfaa7d61f986344ccbb33
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188770"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a>監視行動在商務用 Skype Server 中的效能
 
**摘要:** 瞭解商務用 Skype Server 中的行動服務 (Mcx) 和整合通訊網頁 API (UCWA)。
  
商務用 Skype Server 行動服務 (Mcx) 和整合通訊網頁 API (UCWA) 會增加前端伺服器和前端池的負載。 即使在行動應用程式已最小化 (例如 Android 2010 和執行 Lync 2013 Mobile 的 Apple 裝置, 以及執行 Lync 行動裝置的 Android 和 Apple 裝置等), 仍會維持伺服器連線的行動裝置, 以及執行 Lync 行動裝置的 Android 和 Apple 裝置所強加的負載比當行動應用程式最小化時, 中斷與伺服器的連線。 隨著行動使用量的增加, 您必須監視行動效能, 以判斷何時需要增加您的容量。

> [!NOTE]
> MCX (行動服務) 對舊版行動用戶端的支援已不再提供給商務用 Skype Server 2019。 所有目前的商務用 Skype 行動用戶端都已使用整合通訊 Web API (UCWA) 來支援立即訊息 (IM)、目前狀態和連絡人。 使用 MCX 的舊版用戶端的使用者將需要升級至目前的用戶端。
  
數個限制會影響行動效能: 
  
- 可用記憶體
    
- 要求佇列限制
    
- 併發連接
    
- IIS 佇列長度
    
可能影響行動效能之伺服器的其他限制, 最多可有12個併發登入、驗證、會話重新啟用和終止。 對於大部分的部署而言, 不需要修改這些最大的。
  
## <a name="in-this-section"></a>本節內容

- [監視商務用 Skype Server 中的伺服器記憶體容量限制](server-memory-capacity-limits.md)
    
- [在商務用 Skype Server 中監視行動服務與 UCWA 使用量](service-and-ucwa-usage.md)
    
- [在商務用 Skype Server 中設定行動服務以取得高效能](configure-service.md)
    
- [在商務用 Skype Server 中監控 IIS 要求追蹤記錄檔](iis-request-tracing-log-files.md)
    
- [商務用 Skype Server 中的行動效能計數器](performance-counters.md)
    

