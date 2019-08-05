---
title: 部署高可用性與災害復原
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: 商務用 Skype Server 提供高可用性, 包括伺服器池、含池配對的災害復原, 以及後端伺服器高可用性的數種模式, 包括 AlwaysOn 可用性群組、資料庫鏡像及 SQL 容錯移轉叢集。
ms.openlocfilehash: 7997f71fb1f45801436caa50c4d6b258cc1b843b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193838"
---
# <a name="deploy-high-availability-and-disaster-recovery"></a>部署高可用性與災害復原
 
商務用 Skype Server 提供高可用性, 包括伺服器池、含池配對的災害復原, 以及後端伺服器高可用性的數種模式, 包括 AlwaysOn 可用性群組、資料庫鏡像及 SQL 容錯移轉叢集。 
  
高可用性指的是在一或多個伺服器關閉的情況下, 仍可使用商務用 Skype Server 服務。災害復原指的是在自然或人工造成災難的情況下, 讓服務繼續進行, 並在災難發生前保留盡可能大的資料。
  
本節說明如何部署這些功能, 以及如何針對您的其他伺服器角色提供高可用性和災難復原所需採取的步驟。

> [!NOTE]
> 在商務用 Skype Server 2015 中提供 SQL 鏡像, 但商務用 Skype Server 2019 已不再支援。 使用商務用 Skype Server 2019 時, AlwaysOn 可用性群組、AlwaysOn 容錯移轉叢集實例 (FCI) 和 SQL 容錯移轉叢集方法都是可取的。
  
## <a name="related-sections"></a>相關章節

[規劃商務用 Skype Server 中的高可用性與災害復原](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a>另請參閱

[在商務用 Skype Server 的後端伺服器上部署 AlwaysOn 可用性群組](alwayson-availability-group.md)

[在商務用 Skype Server 中部署已配對的前端池以進行災害復原](front-end-pools-for-disaster-recovery.md)
  
[在商務用 Skype Server 2015 中部署適用于後端伺服器高可用性的 SQL 鏡像](sql-mirroring-for-high-availability.md)
  
