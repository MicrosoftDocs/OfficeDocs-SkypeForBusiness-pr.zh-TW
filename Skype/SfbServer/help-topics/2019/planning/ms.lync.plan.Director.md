---
title: 主管 (規劃工具)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
ROBOTS: NOINDEX, NOFOLLOW
description: 控制器是執行商務用 Skype Server 通訊軟體的伺服器, 可驗證使用者要求, 但不會家用任何使用者帳戶。
ms.openlocfilehash: fa81954e59577ab15edd2a8190e556f4e8e66d47
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187396"
---
# <a name="director-planning-tool"></a>主管 (規劃工具)
 
控制器是執行商務用 Skype Server 通訊軟體的伺服器, 可驗證使用者要求, 但不會家用任何使用者帳戶。 
  
這個角色是選擇性的, 您可以選擇在下列兩種案例中部署控制器:
  
- 如果您透過部署邊緣伺服器來啟用外部使用者存取, 您也應該部署控制器。 在這種情況下, 控制器會驗證外部使用者, 然後將通信量傳送到內部伺服器。 當使用 Director 驗證外部使用者時, 它會從執行這些使用者驗證的負荷, 來免除前端池伺服器。 它也可協助將內部前端池與惡意流量 (例如拒絕服務攻擊) 隔離。 如果網路充斥在這種攻擊中的無效外部通信量, 此流量將結束于 Director。
    
- 如果您是在中央網站部署多個前端池, 您可以在該網站上新增 Director, 以簡化驗證要求並改善效能。 在這種情況下, 所有要求都會先移至 Director, 然後將它們路由到正確的 [前端] 池。
    

