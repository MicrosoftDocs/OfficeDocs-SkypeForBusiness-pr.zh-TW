---
title: 商務用 Skype ServerDirector 規劃工具
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/8/2016
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
description: Director 是執行商務用 Skype Server 2015 通訊軟體的伺服器，可驗證使用者要求，但不會家用任何使用者帳戶。
ms.openlocfilehash: fa55cfb04684cd363e6be8a6e7d02f281c9eeed8
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "53772694"
---
# <a name="skype-for-business-server-director-planning-tool"></a>商務用 Skype ServerDirector 規劃工具
 
Director 是執行商務用 Skype Server 2015 通訊軟體的伺服器，可驗證使用者要求，但不會家用任何使用者帳戶。 
  
這個角色是選用的，您可以選擇在下列兩個案例中部署 Director：
  
- 如果您透過部署 Edge Server 啟用來賓使用者存取，您也應該部署 Director。 在此案例中，Director 會驗證來賓，然後將流量傳遞給內部伺服器。 當 Director 用於驗證訪客時，它會從對這些使用者進行驗證的開銷中免除前端集區伺服器的執行。 它也有助於將內部前端集區與惡意流量（如拒絕服務攻擊）隔離。 如果網路在這類攻擊中以不正確外部流量淹沒，這項流量會結束于 Director。
    
- 如果您在中央網站部署多個前端集區，只要將 Director 新增至該網站，您就可以簡化驗證要求並改善效能。 在此案例中，所有要求都會先移至 Director，然後再將其路由傳送到正確的前端集區。
    

