---
title: 在商務用 Skype Server 中規劃高可用性和嚴重損壞修復
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.custom:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: 商務用 Skype 伺服器具有伺服器集區的高可用性、具有集區配對的嚴重損壞復原功能，以及後端伺服器高可用性的幾種模式，包括 AlwaysOn 可用性群組、資料庫鏡像及 SQL 容錯移轉叢集。
ms.openlocfilehash: 61b720bc9dce5bc8dc54a6c493429b0a3c9b27d2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802813"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a>在商務用 Skype Server 中規劃高可用性和嚴重損壞修復
 
商務用 Skype 伺服器具有伺服器集區的高可用性、具有集區配對的嚴重損壞復原功能，以及後端伺服器高可用性的幾種模式，包括 AlwaysOn 可用性群組、資料庫鏡像及 SQL 容錯移轉叢集。 
  
高可用性是指確定即使一或多部伺服器停機，仍然可以使用商務用 Skype Server 服務。 「嚴重損壞復原」是指讓服務在自然或人工造成的情況下進行，並盡可能從災難中保留盡可能多的資料。
  
如同舊版的 Lync Server，商務用 Skype Server 中的大部分伺服器角色的主要高可用性功能，都是透過 pooling pooling server 冗余度。 如果執行特定伺服器角色的伺服器失敗，集區中執行相同角色的其他伺服器就會接手該伺服器的負載。 這適用於前端伺服器、Edge Server、中繼伺服器和 Director。
  
商務用 Skype 伺服器也會提供前端集區的嚴重損壞修復選項。 您可以設定不同地理區域中的兩個集區，以做為彼此的備份。 當您有整個集區或網站停機時，備份組區可以繼續為這兩個網站的使用者提供服務。
  
商務用 Skype 伺服器也支援後端伺服器的四種高可用性模式：「SQL 鏡像」、「AlwaysOn 可用性群組」、AlwaysOn 容錯移轉叢集實例 (FCI) 及 SQL 容錯移轉叢集。
  
> [!NOTE]
> 在商務用 Skype 2015 Server 中可使用 SQL 鏡像，但商務用 Skype Server 2019 已不再支援。 AlwaysOn 可用性群組、AlwaysOn 容錯移轉叢集實例 (FCI) ，以及使用商務用 Skype Server 2019 的首選 SQL 容錯移轉叢集方法。

> [!NOTE]
> Persistent Chat Server 不支援 AlwaysOn 可用性群組。 
  
本節說明這些功能，也涵蓋您可以採取的步驟，以進行部分其他伺服器角色的高可用性和嚴重損壞修復。 
  
## <a name="see-also"></a>另請參閱

[前端集區高可用性和管理](high-availability.md)
  
[商務用 Skype Server 中的前端集區嚴重損壞修復](disaster-recovery.md)
  
[商務用 Skype 伺服器集區失敗期間的使用者經驗](user-experience.md)
  
[商務用 Skype Server 中的後端伺服器高可用性](back-end-server.md)
  
[商務用 Skype Server 中的檔共用高可用性](file-sharing.md)
