---
title: 新增信任的應用程式集區 FQDN
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
ROBOTS: NOINDEX, NOFOLLOW
description: 若要定義受信任的應用程式池完整功能變數名稱（FQDN），請指定下列專案：
ms.openlocfilehash: 137d344c66fe73628002949b46cff85f451f2af0
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41702928"
---
# <a name="add-trusted-application-pool-fqdn"></a><span data-ttu-id="4f974-103">新增信任的應用程式集區 FQDN</span><span class="sxs-lookup"><span data-stu-id="4f974-103">Add Trusted Application Pool FQDN</span></span>
 
<span data-ttu-id="4f974-104">若要定義受信任的應用程式池完整功能變數名稱（FQDN），請指定下列專案：</span><span class="sxs-lookup"><span data-stu-id="4f974-104">To define a Trusted Applications pool fully qualified domain name (FQDN), specify the following:</span></span>
  
<span data-ttu-id="4f974-105">將託管受信任之應用程式的伺服器或伺服器池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="4f974-105">An FQDN of the server or pool of servers that will host the trusted applications.</span></span>
  
<span data-ttu-id="4f974-106">如果您要為受信任的應用程式部署伺服器池以進行負載平衡和高可用性，請選取 [**多個電腦池**]，或者如果您不需要負載平衡或高可用性，請選取 [**單一電腦池**]。</span><span class="sxs-lookup"><span data-stu-id="4f974-106">Select **Multiple computer pool** if you are deploying a pool of servers for the trusted applications from load balancing and high availability, or select **Single computer pool** if you do not need load balancing or high availability.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4f974-107">一個受信任的應用程式伺服器稍後無法轉換為伺服器池。</span><span class="sxs-lookup"><span data-stu-id="4f974-107">A single Trusted Applications Server cannot be converted to a pool of servers later.</span></span> <span data-ttu-id="4f974-108">如果您認為將來可能需要一個池，您可以部署多個包含一部電腦的伺服器池，並視需要新增伺服器。</span><span class="sxs-lookup"><span data-stu-id="4f974-108">If you think you may need a pool in the future, you can deploy a multiple server pool containing a single computer now, and add servers when needed.</span></span> 
  
<span data-ttu-id="4f974-109">如需有關受信任的應用程式池的詳細資訊，請參閱[新 CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="4f974-109">For details about Trusted Applications pools, see [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).</span></span>
  

