---
title: 監視行動性以取得商務用 Skype Server 效能
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
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 摘要：瞭解商務用 Skype Server 中的行動服務 (Mcx) 和整合通訊網頁 API (UCWA) 。
ms.openlocfilehash: 5f8adbbdc653d8cdf2e19ce3f82fc4fdb0383505
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60746919"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a>監視行動性以取得商務用 Skype Server 效能
 
**摘要：** 瞭解商務用 Skype Server 中的行動服務 (Mcx) 和整合通訊網頁 API (UCWA) 。
  
商務用 Skype Server 行動性服務 (Mcx) 和整合通訊 Web API (UCWA) 會增加前端伺服器和前端集區的負載。 即使在行動應用程式最小化時，也會維持伺服器連線的行動裝置，例如執行 Lync 2010 Mobile 的 Android 和 Nokia 裝置，以及執行 Lync 2013 Mobile 之 Android 和 Apple 裝置的負載，會比裝置在最小化行動電話應用程式時終止其連線的裝置的負載更大。 隨著行動使用量的增加，您必須監視行動性效能，以決定何時需要增加容量。

> [!NOTE]
> 商務用 Skype Server 2019 不再提供舊版行動用戶端的 MCX (行動服務) 支援。 所有目前商務用 Skype 的行動裝置都已經使用整合通訊 Web API (UCWA) 以支援立即訊息 (IM) 、目前狀態及連絡人。 具有使用 MCX 之舊版用戶端的使用者，必須升級至目前的用戶端。
  
一些限制會影響行動效能： 
  
- 可用記憶體
    
- 要求佇列限制
    
- 同時連接
    
- IIS 佇列長度
    
可影響行動效能的伺服器上的其他限制，最多可有12個同時登入、驗證、會話續訂及終止。 在大多數的部署中，不需要修改這些最大值。
  
## <a name="in-this-section"></a>本節內容

- [監視商務用 Skype Server 中的伺服器記憶體容量限制](server-memory-capacity-limits.md)
    
- [在商務用 Skype Server 中監視行動服務和 UCWA 使用狀況](service-and-ucwa-usage.md)
    
- [設定商務用 Skype Server 的高效能行動服務](configure-service.md)
    
- [監視商務用 Skype Server 中的 IIS 要求追蹤記錄檔](iis-request-tracing-log-files.md)
    
- [商務用 Skype Server 中的行動效能計數器](performance-counters.md)
    

