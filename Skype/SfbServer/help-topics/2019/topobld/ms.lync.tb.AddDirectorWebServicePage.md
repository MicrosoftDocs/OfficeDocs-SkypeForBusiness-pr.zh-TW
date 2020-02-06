---
title: 新增 Director Web 服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
ROBOTS: NOINDEX, NOFOLLOW
description: 基底 URL 是 URL 的 Web 服務身分識別，而不是 HTTPs://。 例如，如果該池的 Web 服務的完整 URL 是https://pool01.contoso.net，則基底 url 是 pool01.contoso.net。
ms.openlocfilehash: df8f6d88e57be2abd3c4a5081188f6e22849da0f
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41796552"
---
# <a name="add-director-web-service"></a><span data-ttu-id="14c68-104">新增 Director Web 服務</span><span class="sxs-lookup"><span data-stu-id="14c68-104">Add Director Web Service</span></span>
 
<span data-ttu-id="14c68-105">基底 URL 是 URL 的 Web 服務身分識別，而不是 HTTPs://。</span><span class="sxs-lookup"><span data-stu-id="14c68-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="14c68-106">例如，如果該池的 Web 服務的完整 URL 是https://pool01.contoso.net，則基底 url 是 pool01.contoso.net。</span><span class="sxs-lookup"><span data-stu-id="14c68-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="14c68-107">如果您只部署單一控制器，就不能覆寫內部 Web 服務池的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="14c68-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) if you are deploying only a single Director.</span></span> <span data-ttu-id="14c68-108">如果您要為控制器池設定網域名稱系統（DNS）負載平衡，您可以指定不同的內部基底 URL （這必須與池 FQDN 不同，例如內部-\<您的基 url\>）。</span><span class="sxs-lookup"><span data-stu-id="14c68-108">If you are configuring a Domain Name System (DNS) load balancing for pool of Directors, you can specify a different internal base URL (which must be different from the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="14c68-109">您可以指定與內部基底 URL 不同的外部基底 URL，以區別網域命名。</span><span class="sxs-lookup"><span data-stu-id="14c68-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="14c68-110">例如，您的內部網域是 contoso.net，但是您的外部功能變數名稱是 contoso.com。</span><span class="sxs-lookup"><span data-stu-id="14c68-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="14c68-111">您可以使用 contoso.com 功能變數名稱定義外部基底 URL。</span><span class="sxs-lookup"><span data-stu-id="14c68-111">You would define the external base URL by using the contoso.com domain name.</span></span> <span data-ttu-id="14c68-112">對於邊緣部署的反向 proxy 伺服器而言，這是很重要的。</span><span class="sxs-lookup"><span data-stu-id="14c68-112">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="14c68-113">外部基底 URL 網功能變數名稱稱應該與反向 proxy 的 FQDN 功能變數名稱相同。</span><span class="sxs-lookup"><span data-stu-id="14c68-113">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> 
  

