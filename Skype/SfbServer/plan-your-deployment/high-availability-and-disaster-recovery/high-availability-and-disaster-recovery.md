---
title: 規劃商務用 Skype Server 中的高可用性與災害復原
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: 商務用 Skype Server 提供高可用性, 包括伺服器池、含池配對的災害復原, 以及後端伺服器高可用性的數種模式, 包括 AlwaysOn 可用性群組、資料庫鏡像及 SQL 容錯移轉叢集。
ms.openlocfilehash: 3ed1a3e5eff5d793f835c901e2cc5683da22bc77
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192995"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a>規劃商務用 Skype Server 中的高可用性與災害復原
 
商務用 Skype Server 提供高可用性, 包括伺服器池、含池配對的災害復原, 以及後端伺服器高可用性的數種模式, 包括 AlwaysOn 可用性群組、資料庫鏡像及 SQL 容錯移轉叢集。 
  
高可用性指的是在一或多個伺服器關閉的情況下, 仍可使用商務用 Skype Server 服務。 災害復原指的是在自然或人工造成災難的情況下, 讓服務繼續進行, 並在災難發生前保留盡可能大的資料。
  
就像在舊版的 Lync Server 中, 商務用 Skype Server 中大多數伺服器角色的主要高可用性功能, 都是透過 pooling 提供伺服器冗余。 如果執行特定伺服器角色的伺服器失敗, 則池中執行相同角色的其他伺服器會載入該伺服器。 這適用于前端伺服器、邊緣伺服器、轉送伺服器和控制器。
  
商務用 Skype 伺服器也會提供前端池的災害復原選項。 您可以在不同的地理區域中設定兩個池來充當彼此的備份。 然後, 如果您擁有整個池或網站, 備份池就可以繼續為兩個網站上的使用者提供服務。
  
商務用 Skype 伺服器也支援後端伺服器的四種高可用性模式: [SQL 鏡像]、[AlwaysOn 可用性] 群組、[AlwaysOn] 容錯移轉叢集實例 (FCI), 以及 SQL 容錯移轉叢集。
  
> [!NOTE]
> 在商務用 Skype Server 2015 中提供 SQL 鏡像, 但商務用 Skype Server 2019 已不再支援。 使用商務用 Skype Server 2019 時, AlwaysOn 可用性群組、AlwaysOn 容錯移轉叢集實例 (FCI) 和 SQL 容錯移轉叢集方法都是可取的。

> [!NOTE]
> 永久聊天伺服器不支援 AlwaysOn 可用性群組。 
  
本節說明這些功能, 以及您可以針對一些其他伺服器角色的高可用性及災難復原所需採取的步驟。 
  
## <a name="see-also"></a>另請參閱

[前端池高可用性與管理](high-availability.md)
  
[商務用 Skype Server 中的前端池災害復原](disaster-recovery.md)
  
[商務用 Skype Server 中的 pool 失敗期間的使用者體驗](user-experience.md)
  
[商務用 Skype Server 的後端伺服器高可用性](back-end-server.md)
  
[商務用 Skype Server 的檔案共用高可用性](file-sharing.md)
