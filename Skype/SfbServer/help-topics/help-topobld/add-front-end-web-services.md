---
title: 新增前端 Web 服務
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
- ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: 基底 URL 是 URL 的 Web 服務識別身分，去除 https://。 例如，如果集區的 Web 服務完整 URL 為 https://pool01.contoso.net ，則基本 url 為 pool01.contoso.net。
ms.openlocfilehash: 45705ea940fa0f43f600546a680d76b41b645e59
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217934"
---
# <a name="add-front-end-web-services"></a><span data-ttu-id="e9b99-104">新增前端 Web 服務</span><span class="sxs-lookup"><span data-stu-id="e9b99-104">Add Front End Web Services</span></span>
 
<span data-ttu-id="e9b99-105">基底 URL 是 URL 的 Web 服務識別身分，去除 https://。</span><span class="sxs-lookup"><span data-stu-id="e9b99-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="e9b99-106">例如，如果集區的 Web 服務完整 URL 為 https://pool01.contoso.net ，則基本 url 為 pool01.contoso.net。</span><span class="sxs-lookup"><span data-stu-id="e9b99-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="e9b99-107">您無法覆寫 Standard Edition Server 的內部 Web 服務集區完整網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="e9b99-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) for a Standard Edition server.</span></span> <span data-ttu-id="e9b99-108">若要設定網域名稱系統 (DNS) Enterprise Edition 前端集區的負載平衡，您可以指定不同的內部基礎 URL，其必須不同于集區 FQDN (例如，internal \<your base URL\>) 。</span><span class="sxs-lookup"><span data-stu-id="e9b99-108">If you are configuring Domain Name System (DNS) load balancing for an Enterprise Edition Front End pool, you can specify a different internal base URL, which must be different from the pool FQDN (for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="e9b99-p104">您可以指定與內部基礎 URL 不同的外部基底 URL，以區別網域命名。例如，您的內部網域是 contoso.net，但外部網域名稱是 contoso.com。您會使用 contoso.com 網域名稱來定義外部基底 URL。這對 Edge 部署的反向 Proxy 伺服器而言很重要。外部基底 URL 網域名稱應該與反向 Proxy 的 FQDN 網域名稱相同。立即訊息和目前狀態需要對前端集區的 HTTP 存取。</span><span class="sxs-lookup"><span data-stu-id="e9b99-p104">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming. For example, your internal domain is contoso.net, but your external domain name is contoso.com. You would define the external base URL using the contoso.com domain name. This is important for reverse proxy servers for an edge deployment. The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy. Instant messaging and presence requires HTTP access to the Front End pool.</span></span>
  

