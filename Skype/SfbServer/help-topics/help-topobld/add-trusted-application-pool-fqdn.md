---
title: 新增受信任的應用程式池 FQDN
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
description: '若要定義受信任的應用程式池完整功能變數名稱 (FQDN), 請指定下列專案:'
ms.openlocfilehash: 27957348d4c6dc6b277a37d458ff21bb5efabc17
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193557"
---
# <a name="add-trusted-application-pool-fqdn"></a><span data-ttu-id="520ea-103">新增受信任的應用程式池 FQDN</span><span class="sxs-lookup"><span data-stu-id="520ea-103">Add Trusted Application Pool FQDN</span></span>
 
<span data-ttu-id="520ea-104">若要定義受信任的應用程式池完整功能變數名稱 (FQDN), 請指定下列專案:</span><span class="sxs-lookup"><span data-stu-id="520ea-104">To define a Trusted Applications pool fully qualified domain name (FQDN), specify the following:</span></span>
  
<span data-ttu-id="520ea-105">將託管受信任之應用程式的伺服器或伺服器池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="520ea-105">An FQDN of the server or pool of servers that will host the trusted applications.</span></span>
  
<span data-ttu-id="520ea-106">如果您要為受信任的應用程式部署伺服器池以進行負載平衡和高可用性, 請選取 [**多個電腦池**], 或者如果您不需要負載平衡或高可用性, 請選取 [**單一電腦池**]。</span><span class="sxs-lookup"><span data-stu-id="520ea-106">Select **Multiple computer pool** if you are deploying a pool of servers for the trusted applications from load balancing and high availability, or select **Single computer pool** if you do not need load balancing or high availability.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="520ea-107">一個受信任的應用程式伺服器稍後無法轉換為伺服器池。</span><span class="sxs-lookup"><span data-stu-id="520ea-107">A single Trusted Applications Server cannot be converted to a pool of servers later.</span></span> <span data-ttu-id="520ea-108">如果您認為將來可能需要一個池, 您可以部署多個包含一部電腦的伺服器池, 並視需要新增伺服器。</span><span class="sxs-lookup"><span data-stu-id="520ea-108">If you think you may need a pool in the future, you can deploy a multiple server pool containing a single computer now, and add servers when needed.</span></span> 
  
<span data-ttu-id="520ea-109">如需有關受信任的應用程式池的詳細資訊, 請參閱[新 CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="520ea-109">For details about Trusted Applications pools, see [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).</span></span>
  

