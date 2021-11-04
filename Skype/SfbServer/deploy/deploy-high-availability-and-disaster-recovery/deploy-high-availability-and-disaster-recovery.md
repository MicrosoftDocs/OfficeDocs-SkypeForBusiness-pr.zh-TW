---
title: 部署高可用性和災害復原
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: 商務用 Skype Server 提供高可用性與伺服器集區、具有集區配對的嚴重損壞復原，以及後端伺服器高可用性的數種模式，包括 AlwaysOn 可用性群組、資料庫鏡像及 SQL 容錯移轉叢集。
ms.openlocfilehash: 03a7c1e91651f2d73b1e22692f726ed3188588e6
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60761481"
---
# <a name="deploy-high-availability-and-disaster-recovery"></a>部署高可用性和災害復原
 
商務用 Skype Server 提供高可用性與伺服器集區、具有集區配對的嚴重損壞復原，以及後端伺服器高可用性的數種模式，包括 AlwaysOn 可用性群組、資料庫鏡像及 SQL 容錯移轉叢集。 
  
高可用性是指確定即使一或多部伺服器停機也可使用商務用 Skype Server 服務。「嚴重損壞復原」是指讓服務在自然或人工造成的情況下進行，並盡可能從災難中保留盡可能多的資料。
  
本節說明如何部署這些功能，還涵蓋您可以採取的步驟，以供部分其他伺服器角色的高可用性和嚴重損壞修復。

> [!NOTE]
> SQL鏡像可用於商務用 Skype Server 2015，但在商務用 Skype Server 2019 中已不再支援。 AlwaysOn 可用性群組、AlwaysOn 容錯移轉叢集實例 (FCI) 及 SQL 容錯移轉叢集方法，都是商務用 Skype Server 2019 的首選。
  
## <a name="related-sections"></a>相關章節

[在商務用 Skype Server 中規劃高可用性和嚴重損壞修復](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a>另請參閱

[在商務用 Skype Server 中的後端伺服器上部署 AlwaysOn 可用性群組](alwayson-availability-group.md)

[在商務用 Skype Server 中為嚴重損壞修復部署成對的前端集區](front-end-pools-for-disaster-recovery.md)
  
[部署商務用 Skype Server 2015 的後端伺服器高可用性 SQL 鏡像](sql-mirroring-for-high-availability.md)
  
