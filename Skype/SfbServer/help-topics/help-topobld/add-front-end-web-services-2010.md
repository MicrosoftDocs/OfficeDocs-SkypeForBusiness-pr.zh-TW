---
title: 新增前端 Web 服務 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: 基底 URL 是 URL 的 Web 服務身分識別，而不是 HTTPs://。 例如，如果該池的 Web 服務的完整 URL 是https://pool01.contoso.net，則基底 url 是 pool01.contoso.net。
ms.openlocfilehash: 48d2cc4c8ce9bc1074ae42e385265b34f24c662e
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685126"
---
# <a name="add-front-end-web-services-2010"></a><span data-ttu-id="50cc5-104">新增前端 Web 服務 2010</span><span class="sxs-lookup"><span data-stu-id="50cc5-104">Add Front End Web Services 2010</span></span>
 
<span data-ttu-id="50cc5-105">基底 URL 是 URL 的 Web 服務身分識別，而不是 HTTPs://。</span><span class="sxs-lookup"><span data-stu-id="50cc5-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="50cc5-106">例如，如果該池的 Web 服務的完整 URL 是https://pool01.contoso.net，則基底 url 是 pool01.contoso.net。</span><span class="sxs-lookup"><span data-stu-id="50cc5-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="50cc5-107">您無法覆寫標準版伺服器的內部 Web 服務池完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="50cc5-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) for a Standard Edition Server.</span></span> <span data-ttu-id="50cc5-108">如果您要為企業版前端池設定網域名稱系統（DNS）負載平衡，您可以指定不同的內部基底 URL （必須不同于池 FQDN，例如內部-\<您的基本 url\>）。</span><span class="sxs-lookup"><span data-stu-id="50cc5-108">If you are configuring Domain Name System (DNS) load balancing for an Enterprise Edition Front End pool, you can specify a different internal base URL (which must be different than the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="50cc5-109">您可以指定與內部基底 URL 不同的外部基底 URL，以區別網域命名。</span><span class="sxs-lookup"><span data-stu-id="50cc5-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="50cc5-110">例如，您的內部網域是 contoso.net，但是您的外部功能變數名稱是 contoso.com。</span><span class="sxs-lookup"><span data-stu-id="50cc5-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="50cc5-111">您可以使用 contoso.com 功能變數名稱定義外部基底 URL。</span><span class="sxs-lookup"><span data-stu-id="50cc5-111">You would define the external base URL by using the contoso.com domain name.</span></span> <span data-ttu-id="50cc5-112">對於邊緣部署的反向 proxy 伺服器而言，這是很重要的。</span><span class="sxs-lookup"><span data-stu-id="50cc5-112">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="50cc5-113">外部基底 URL 網功能變數名稱稱應該與反向 proxy 的 FQDN 功能變數名稱相同。</span><span class="sxs-lookup"><span data-stu-id="50cc5-113">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="50cc5-114">立即訊息和目前狀態需要對前端池的 HTTP 存取權。</span><span class="sxs-lookup"><span data-stu-id="50cc5-114">Instant messaging and presence requires HTTP access to the Front End pool.</span></span>
  

