---
title: 舊版合併 FQDN
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.LegacyMergeFqdnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d72841ff-3c4d-4233-a933-f3a95d75d89b
description: Access Edge 集區的內部 FQDN 用於各種案例，其中內部使用者會與外部使用者通訊，以進行同盟、遠端使用者存取和公用 IM 連線。 如果您的舊版環境中部署了經負載平衡的 Edge Server，請輸入內部負載平衡器的完整網域名稱 (FQDN)。
ms.openlocfilehash: 42771899ca4eb06b195db7365636dbef9c3d70d9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803283"
---
# <a name="legacy-merge-fqdn"></a><span data-ttu-id="32e54-104">舊版合併 FQDN</span><span class="sxs-lookup"><span data-stu-id="32e54-104">Legacy Merge FQDN</span></span>
 
<span data-ttu-id="32e54-105">**Access Edge 集區的內部 FQDN** 用於各種案例，其中內部使用者會與外部使用者通訊，以進行同盟、遠端使用者存取和公用 IM 連線。</span><span class="sxs-lookup"><span data-stu-id="32e54-105">The **Access Edge Pool internal FQDN** is used for a variety of scenarios where internal users communicate with external users for federation, remote user access, and public IM connectivity.</span></span> <span data-ttu-id="32e54-106">如果您的舊版環境中部署了經負載平衡的 Edge Server，請輸入內部負載平衡器的完整網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="32e54-106">If a load-balanced Edge Server was deployed in your legacy environment, enter the fully qualified domain name (FQDN) of the internal load balancer.</span></span>
  
<span data-ttu-id="32e54-107">**內部的 SIP 存取埠** 值 **5061** 是預設的傳輸控制通訊協定 (TCP) SIP 埠，可與用戶端、舊版前端集區和伺服器進行通訊。</span><span class="sxs-lookup"><span data-stu-id="32e54-107">The **Internal SIP access port** value of **5061** is the default Transmission Control Protocol (TCP) SIP port for communicating with clients, legacy Front End pools and servers.</span></span> <span data-ttu-id="32e54-108">如果未使用預設值，請更新 **[內部 SIP 存取連接埠:]** 值。</span><span class="sxs-lookup"><span data-stu-id="32e54-108">If the default value was not used, update the **Internal SIP access port:** value.</span></span>
  

