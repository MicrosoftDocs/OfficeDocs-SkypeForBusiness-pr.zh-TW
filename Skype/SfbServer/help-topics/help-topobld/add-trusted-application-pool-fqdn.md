---
title: 新增信任的應用程式集區 FQDN
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
description: 若要為信任的應用程式集區定義完整網域名稱 (FQDN)，請指定下列設定：
ms.openlocfilehash: 94cf0f611d754dc614111add734bf231c92c5a81
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217004"
---
# <a name="add-trusted-application-pool-fqdn"></a><span data-ttu-id="c6eea-103">新增信任的應用程式集區 FQDN</span><span class="sxs-lookup"><span data-stu-id="c6eea-103">Add Trusted Application Pool FQDN</span></span>
 
<span data-ttu-id="c6eea-104">若要為信任的應用程式集區定義完整網域名稱 (FQDN)，請指定下列設定：</span><span class="sxs-lookup"><span data-stu-id="c6eea-104">To define a Trusted Applications pool fully qualified domain name (FQDN), specify the following:</span></span>
  
<span data-ttu-id="c6eea-105">將裝載信任的應用程式的伺服器或伺服器集區的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="c6eea-105">An FQDN of the server or pool of servers that will host the trusted applications.</span></span>
  
<span data-ttu-id="c6eea-106">如果要從負載平衡和高可用性部署信任的應用程式的伺服器集區，請選取 [多部電腦集區]\*\*\*\*，或者，如果您不需要負載平衡或高可用性，請選取 [單一電腦集區]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c6eea-106">Select **Multiple computer pool** if you are deploying a pool of servers for the trusted applications from load balancing and high availability, or select **Single computer pool** if you do not need load balancing or high availability.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c6eea-p101">之後無法將單一信任的應用程式伺服器轉換為伺服器集區。如果您認為未來可能需要集區，您現在可以部署含單一電腦的多個伺服器集區，需要時再新增伺服器。</span><span class="sxs-lookup"><span data-stu-id="c6eea-p101">A single Trusted Applications Server cannot be converted to a pool of servers later. If you think you may need a pool in the future, you can deploy a multiple server pool containing a single computer now, and add servers when needed.</span></span> 
  
<span data-ttu-id="c6eea-109">如需信任的應用程式集區的詳細資訊，請參閱＜[New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps)＞。</span><span class="sxs-lookup"><span data-stu-id="c6eea-109">For details about Trusted Applications pools, see [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).</span></span>
  

