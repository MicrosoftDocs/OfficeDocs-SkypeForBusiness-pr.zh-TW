---
title: 新增前端集區 FQDN
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
ROBOTS: NOINDEX, NOFOLLOW
description: 指定您正在建立之前端集區的完整網域名稱 (FQDN)。在發行包含前端集區的拓撲之後，便無法變更集區的 FQDN。如果需要將集區重新命名，必須刪除集區，再用新的 FQDN 新增集區。
ms.openlocfilehash: ee85c9223b780359ec86e927b93c591bdeaac944ca227b45969875fb19c63d22
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54298523"
---
# <a name="add-front-end-pool-fqdn"></a>新增前端集區 FQDN
 
指定您正在建立之前端集區的完整網域名稱 (FQDN)。在發行包含前端集區的拓撲之後，便無法變更集區的 FQDN。如果需要將集區重新命名，必須刪除集區，再用新的 FQDN 新增集區。
  
> [!TIP]
> 如果您打算未來實作前端集區，請選取 **[多部電腦集區]**。 即使集區定義為兩部以上負載平衡的電腦，您仍可建立單一電腦集區，並為單一電腦建立集區 FQDN。 當您準備好將更多電腦新增至集區之後，您必須再次執行拓撲產生器以定義新的集區成員、發佈新的拓撲，然後透過「商務用 Skype Server 部署」嚮導設定新的前端集區成員。 您也必須新增集區成員至集區的適當負載平衡器、網域名稱系統 (DNS) 負載平衡或硬體負載平衡器。 在許多情況下，您會同時具有兩種負載平衡系統。 請務必將新成員伺服器同時新增到這兩種系統。 
  

