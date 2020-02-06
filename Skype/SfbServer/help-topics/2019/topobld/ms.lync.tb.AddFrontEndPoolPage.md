---
title: 新增前端集區 FQDN
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 指定您要建立的前端池的完整功能變數名稱（FQDN）。 發佈包含 [前端] 池的拓朴之後，您就無法變更該池的 FQDN。 如果您需要重新命名池，您必須先刪除該池，然後使用新的 FQDN 新增新的池中。
ms.openlocfilehash: 0c6fdf24ec19fe56ff86d4a5b43af2e48aedb3e2
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798520"
---
# <a name="add-front-end-pool-fqdn"></a>新增前端集區 FQDN
 
指定您要建立的前端池的完整功能變數名稱（FQDN）。 發佈包含 [前端] 池的拓朴之後，您就無法變更該池的 FQDN。 如果您需要重新命名池，您必須先刪除該池，然後使用新的 FQDN 新增新的池中。
  
> [!TIP]
> 如果您打算在將來實施前端池，請選取 [**多個電腦池**]。 即使集區定義為兩部以上負載平衡的電腦，您仍可建立單一電腦集區，並為單一電腦建立集區 FQDN。 當您準備好要在池中新增更多電腦之後，您必須再次執行拓撲建立器，以定義新的池成員、發佈新的拓撲，然後透過商務用 Skype Server 部署嚮導來設定新的前端池成員。 您也必須針對 pool、Domain Name System （DNS）負載平衡或硬體負載平衡器，將新的池成員新增至適當的負載平衡器。 在許多情況下，您可以同時進行兩個負載平衡系統。 請確定您要將新的成員伺服器新增到兩者中。 
  

