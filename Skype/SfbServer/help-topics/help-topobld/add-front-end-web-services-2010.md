---
title: 新增前端 Web 服務 2010
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
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: 基底 URL 是 URL 的 Web 服務識別身分，去除 https://。 例如，如果集區的 Web 服務完整 URL 為 https://pool01.contoso.net ，則基本 url 為 pool01.contoso.net。
ms.openlocfilehash: 96a258cd2d3c46d700dff32ea4adb6213b4de9b1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824023"
---
# <a name="add-front-end-web-services-2010"></a><span data-ttu-id="c342f-104">新增前端 Web 服務 2010</span><span class="sxs-lookup"><span data-stu-id="c342f-104">Add Front End Web Services 2010</span></span>
 
<span data-ttu-id="c342f-105">基底 URL 是 URL 的 Web 服務識別身分，去除 https://。</span><span class="sxs-lookup"><span data-stu-id="c342f-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="c342f-106">例如，如果集區的 Web 服務完整 URL 為 https://pool01.contoso.net ，則基本 url 為 pool01.contoso.net。</span><span class="sxs-lookup"><span data-stu-id="c342f-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="c342f-107">您無法覆寫 Standard Edition Server 的內部 Web 服務集區完整功能變數名稱 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="c342f-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) for a Standard Edition Server.</span></span> <span data-ttu-id="c342f-108">若要設定網域名稱系統 (DNS) Enterprise Edition 前端集區的負載平衡，您可以指定不同的內部基底 URL (，該 URL 必須與集區 FQDN 不同，例如內部 \<your base URL\>) 。</span><span class="sxs-lookup"><span data-stu-id="c342f-108">If you are configuring Domain Name System (DNS) load balancing for an Enterprise Edition Front End pool, you can specify a different internal base URL (which must be different than the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="c342f-109">您可以指定與內部基底 URL 不同的外部基底 URL，以區別網域命名。</span><span class="sxs-lookup"><span data-stu-id="c342f-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="c342f-110">例如，您的內部網域為 contoso.net，而外部網域名稱為 contoso.com。</span><span class="sxs-lookup"><span data-stu-id="c342f-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="c342f-111">這時您可以使用 contoso.com 網域名稱來定義外部基底 URL。</span><span class="sxs-lookup"><span data-stu-id="c342f-111">You would define the external base URL by using the contoso.com domain name.</span></span> <span data-ttu-id="c342f-112">這對 Edge 部署的反向 Proxy 伺服器而言很重要。</span><span class="sxs-lookup"><span data-stu-id="c342f-112">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="c342f-113">外部基底 URL 網域名稱應該與反向 Proxy 的 FQDN 網域名稱相同。</span><span class="sxs-lookup"><span data-stu-id="c342f-113">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="c342f-114">立即訊息和目前狀態需要對前端集區的 HTTP 存取。</span><span class="sxs-lookup"><span data-stu-id="c342f-114">Instant messaging and presence requires HTTP access to the Front End pool.</span></span>
  

