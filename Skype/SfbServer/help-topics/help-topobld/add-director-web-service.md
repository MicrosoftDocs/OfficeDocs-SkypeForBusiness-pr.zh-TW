---
title: 新增 Director Web 服務
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
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
description: 基底 URL 是 URL 的 Web 服務識別身分，去除 https://。 例如，如果集區的 Web 服務完整 URL 為 https://pool01.contoso.net ，則基本 url 為 pool01.contoso.net。
ms.openlocfilehash: 5d965eb591afca8d7154d8fd12af741ddaf65084
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219464"
---
# <a name="add-director-web-service"></a><span data-ttu-id="9afbe-104">新增 Director Web 服務</span><span class="sxs-lookup"><span data-stu-id="9afbe-104">Add Director Web Service</span></span>
 
<span data-ttu-id="9afbe-105">基底 URL 是 URL 的 Web 服務識別身分，去除 https://。</span><span class="sxs-lookup"><span data-stu-id="9afbe-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="9afbe-106">例如，如果集區的 Web 服務完整 URL 為 https://pool01.contoso.net ，則基本 url 為 pool01.contoso.net。</span><span class="sxs-lookup"><span data-stu-id="9afbe-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="9afbe-107">如果您只有部署一台 Director，將無法覆寫內部 Web 服務的集區完整網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="9afbe-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) if you are deploying only a single Director.</span></span> <span data-ttu-id="9afbe-108">若要設定網域名稱系統 (DNS) Director 集區的負載平衡，您可以指定不同的內部基底 URL (（該 URL 必須與集區 FQDN 不同），而且可以是內部) （如內部 \<your base URL\> ）。</span><span class="sxs-lookup"><span data-stu-id="9afbe-108">If you are configuring a Domain Name System (DNS) load balancing for pool of Directors, you can specify a different internal base URL (which must be different from the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="9afbe-p104">您可以指定與內部基底 URL 不同的外部基底 URL，以區別網域命名。例如，您的內部網域為 contoso.net，而外部網域名稱為 contoso.com。這時您可以使用 contoso.com 網域名稱來定義外部基底 URL。這對 Edge 部署的反向 Proxy 伺服器而言很重要。外部基底 URL 網域名稱應該與反向 Proxy 的 FQDN 網域名稱相同。</span><span class="sxs-lookup"><span data-stu-id="9afbe-p104">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming. For example, your internal domain is contoso.net, but your external domain name is contoso.com. You would define the external base URL by using the contoso.com domain name. This is important for reverse proxy servers for an edge deployment. The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> 
  

