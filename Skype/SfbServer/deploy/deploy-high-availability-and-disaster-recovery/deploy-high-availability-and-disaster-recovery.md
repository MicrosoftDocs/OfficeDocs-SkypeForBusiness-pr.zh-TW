---
title: 部署高可用性和災害復原
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: 商務用 Skype 伺服器具有伺服器集區的高可用性、具有集區配對的嚴重損壞復原功能，以及後端伺服器高可用性的幾種模式，包括 AlwaysOn 可用性群組、資料庫鏡像及 SQL 容錯移轉叢集。
ms.openlocfilehash: 68baae183ff45571e38e922035d287e733bcc930
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830613"
---
# <a name="deploy-high-availability-and-disaster-recovery"></a>部署高可用性和災害復原
 
商務用 Skype 伺服器具有伺服器集區的高可用性、具有集區配對的嚴重損壞復原功能，以及後端伺服器高可用性的幾種模式，包括 AlwaysOn 可用性群組、資料庫鏡像及 SQL 容錯移轉叢集。 
  
高可用性是指確定即使一或多部伺服器停機，仍然可以使用商務用 Skype Server 服務。「嚴重損壞復原」是指讓服務在自然或人工造成的情況下進行，並盡可能從災難中保留盡可能多的資料。
  
本節說明如何部署這些功能，還涵蓋您可以採取的步驟，以供部分其他伺服器角色的高可用性和嚴重損壞修復。

> [!NOTE]
> 在商務用 Skype 2015 Server 中可使用 SQL 鏡像，但商務用 Skype Server 2019 已不再支援。 AlwaysOn 可用性群組、AlwaysOn 容錯移轉叢集實例 (FCI) ，以及使用商務用 Skype Server 2019 的首選 SQL 容錯移轉叢集方法。
  
## <a name="related-sections"></a>相關章節

[在商務用 Skype Server 中規劃高可用性和嚴重損壞修復](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a>另請參閱

[在商務用 Skype Server 中的後端伺服器上部署 AlwaysOn 可用性群組](alwayson-availability-group.md)

[在商務用 Skype Server 中部署用於嚴重損壞修復的配對前端集區](front-end-pools-for-disaster-recovery.md)
  
[為商務用 Skype Server 2015 中的後端伺服器高可用性部署 SQL 鏡像](sql-mirroring-for-high-availability.md)
  
