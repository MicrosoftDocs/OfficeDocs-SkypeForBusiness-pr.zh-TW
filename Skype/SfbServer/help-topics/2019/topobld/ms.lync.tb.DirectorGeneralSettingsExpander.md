---
title: Director 一般設定展開工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.DirectorGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2026d0dd-6745-4e53-8b44-acdc378b47d1
ROBOTS: NOINDEX, NOFOLLOW
description: 若要編輯現有主管的設定，您會看到下列各節：
ms.openlocfilehash: 5b58f74d7d343f2a4b57074dbc041938247ddc1f
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41702378"
---
# <a name="director-general-settings-expander"></a><span data-ttu-id="69a6a-103">Director 一般設定展開工具</span><span class="sxs-lookup"><span data-stu-id="69a6a-103">Director General Settings Expander</span></span>
 
<span data-ttu-id="69a6a-104">若要編輯現有主管的設定，您會看到下列各節：</span><span class="sxs-lookup"><span data-stu-id="69a6a-104">To edit the settings for an existing Director, you are presented with the following sections:</span></span>
  
- <span data-ttu-id="69a6a-105">一般設定</span><span class="sxs-lookup"><span data-stu-id="69a6a-105">General settings</span></span>
    
- <span data-ttu-id="69a6a-106">Web 服務</span><span class="sxs-lookup"><span data-stu-id="69a6a-106">Web services</span></span>
    

## <a name="general-settings"></a><span data-ttu-id="69a6a-107">一般設定</span><span class="sxs-lookup"><span data-stu-id="69a6a-107">General settings</span></span>

<span data-ttu-id="69a6a-108">主管池的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="69a6a-108">Fully qualified domain name (FQDN) of the Director pool.</span></span> <span data-ttu-id="69a6a-109">編輯伺服器的 FQDN 會變更此值。</span><span class="sxs-lookup"><span data-stu-id="69a6a-109">Edit the FQDN of the server to change the value.</span></span> <span data-ttu-id="69a6a-110">您必須有符合新值的網域名稱系統 (DNS) 主機 (A) 記錄。</span><span class="sxs-lookup"><span data-stu-id="69a6a-110">You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>
  
<span data-ttu-id="69a6a-111">在 [關聯]\*\*\*\* 中，您可以編輯或指定下列項目：</span><span class="sxs-lookup"><span data-stu-id="69a6a-111">In **Associations** you can edit or specify the following:</span></span>
  
<span data-ttu-id="69a6a-112">要使用之主管池的檔案共用。</span><span class="sxs-lookup"><span data-stu-id="69a6a-112">File share for the Director pool to use.</span></span> <span data-ttu-id="69a6a-113">選取已在拓撲建立器中定義的現有檔案共用，或按一下 [**新增**] 以建立新的檔案共用定義。</span><span class="sxs-lookup"><span data-stu-id="69a6a-113">Select an existing file share that has already been defined in Topology Builder, or click **New** to create a new file share definition.</span></span>
  
<span data-ttu-id="69a6a-114">[監視 SQL Server store]。</span><span class="sxs-lookup"><span data-stu-id="69a6a-114">Monitoring SQL Server store.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="69a6a-115">您所指定的伺服器必須存在並加入網域中，您才能發行新定義的拓撲。</span><span class="sxs-lookup"><span data-stu-id="69a6a-115">Before publishing the newly defined topology, the server that you specify must exist and be joined to the domain.</span></span> <span data-ttu-id="69a6a-116">如果您已建立新的檔案共用，則必須在您指派的伺服器上建立檔案共用。</span><span class="sxs-lookup"><span data-stu-id="69a6a-116">If you created a new file share, the file share must be created on the server that you designate.</span></span> 
  
## <a name="web-services"></a><span data-ttu-id="69a6a-117">Web 服務</span><span class="sxs-lookup"><span data-stu-id="69a6a-117">Web services</span></span>

<span data-ttu-id="69a6a-118">若要在主管池上編輯或指定 Web 服務的其他設定，您可以在內部 Web 服務和外部 Web 服務中修改或指定設定。</span><span class="sxs-lookup"><span data-stu-id="69a6a-118">To edit or specify additional settings for the Web services on the Director pool, you modify or specify settings in the Internal Web services and External Web services.</span></span>
  
<span data-ttu-id="69a6a-119">對於**內部 web 服務**，您可以指定下列專案：</span><span class="sxs-lookup"><span data-stu-id="69a6a-119">For **Internal web services** you can specify the following:</span></span>
  
> [!CAUTION]
> <span data-ttu-id="69a6a-120">如果您有多個前端池或前端伺服器，外部 Web 服務 FQDN 必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="69a6a-120">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="69a6a-121">例如，如果您將前端伺服器的外部 Web 服務 FQDN 定義為**pool01.contoso.com**，則無法將**pool01.contoso.com**用於另一個前端池或前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="69a6a-121">For example, if you define the external Web services FQDN of a Front End Server as **pool01.contoso.com**, you cannot use **pool01.contoso.com** for another Front End pool or Front End Server.</span></span> <span data-ttu-id="69a6a-122">如果您也要部署控制器，則為任何主管或主管池定義的外部 Web 服務 FQDN，都必須是與任何其他控制器或主管池以及任何前端池或前端伺服器的唯一名稱。</span><span class="sxs-lookup"><span data-stu-id="69a6a-122">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="69a6a-123">如果您決定使用自行定義的 FQDN 來覆寫內部 web 服務，則每個 FQDN 都必須是與任何其他的前端池、控制器或主管池都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="69a6a-123">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>
  
<span data-ttu-id="69a6a-124">如果您選取 [覆寫 FQDN]，您可以為集區上的 [內部 Web] 服務識別指定不同的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="69a6a-124">If you select Override FQDN, you can specify a different FQDN for the Internal Web services identity on the pool.</span></span> <span data-ttu-id="69a6a-125">根據預設，設定是針對主管池所定義的目前的 [池名稱]。</span><span class="sxs-lookup"><span data-stu-id="69a6a-125">By default, the setting is the current pool name as defined for the Director pool.</span></span>
  
<span data-ttu-id="69a6a-126">您可以為您的部署所需的 HTTP 和 HTTPS 指定偵聽與已發佈埠。</span><span class="sxs-lookup"><span data-stu-id="69a6a-126">You can specify listening and published ports for HTTP and HTTPS that your deployment requires.</span></span> <span data-ttu-id="69a6a-127">HTTPS 的埠80和 HTTPS 的埠443預設設定是最常見的設定，除非您在組織和基礎結構設計中有特定需求，否則通常不需要加以變更。</span><span class="sxs-lookup"><span data-stu-id="69a6a-127">The default setting of port 80 for HTTP and port 443 for HTTPS are the most common settings and typically do not need to be changed unless you have specific requirements within your organization and infrastructure design.</span></span>
  
<span data-ttu-id="69a6a-128">針對**外部 web 服務**，您可以指定下列專案：</span><span class="sxs-lookup"><span data-stu-id="69a6a-128">For **External web services**, you can specify the following:</span></span>
  
<span data-ttu-id="69a6a-129">您可以定義外部 Web 服務的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="69a6a-129">You can define the FQDN of the External Web services.</span></span> <span data-ttu-id="69a6a-130">此處指定的 FQDN 通常會依您外部連線的需求 (例如反向 Proxy) 而定義。</span><span class="sxs-lookup"><span data-stu-id="69a6a-130">The FQDN specified here will usually be defined by the requirements of your external connection requirements, such as the reverse proxy.</span></span>
  
<span data-ttu-id="69a6a-131">您可以為您的部署所需的 HTTP 和 HTTPS 指定偵聽與已發佈埠。</span><span class="sxs-lookup"><span data-stu-id="69a6a-131">You can specify listening and published ports for HTTP and HTTPS that your deployment requires.</span></span> <span data-ttu-id="69a6a-132">HTTPS 的埠8080的預設設定與 HTTPS 的埠4443最初定義。</span><span class="sxs-lookup"><span data-stu-id="69a6a-132">The default settings of port 8080 for HTTP and port 4443 for HTTPS are defined initially.</span></span> <span data-ttu-id="69a6a-133">您可以根據您反向 Proxy 與外部網路的需求，為聆聽連接埠變更這些設定。</span><span class="sxs-lookup"><span data-stu-id="69a6a-133">You change these settings for the listening ports based on what the requirements are for your reverse proxy and external network requirements.</span></span> <span data-ttu-id="69a6a-134">已發佈的埠會設定為 HTTP 的埠80，以及 HTTPS 的埠443的預設值。</span><span class="sxs-lookup"><span data-stu-id="69a6a-134">The published ports are set to default of port 80 for HTTP and port 443 for HTTPS.</span></span> <span data-ttu-id="69a6a-135">這些值決定控制器池或控制器伺服器將接聽傳入要求的埠。</span><span class="sxs-lookup"><span data-stu-id="69a6a-135">These values determine what ports the Director pool or Director server will listen for incoming requests.</span></span> <span data-ttu-id="69a6a-136">通常不需要變更這些功能，除非在該池中有埠需求衝突。</span><span class="sxs-lookup"><span data-stu-id="69a6a-136">Typically, these do not need to be changed, unless there is conflict of port requirements on the pool.</span></span> <span data-ttu-id="69a6a-137">需要使用相同埠值的內部和外部發佈埠。</span><span class="sxs-lookup"><span data-stu-id="69a6a-137">Internal and external published ports that use the same port values are expected.</span></span> <span data-ttu-id="69a6a-138">這不是衝突。</span><span class="sxs-lookup"><span data-stu-id="69a6a-138">This is not a conflict.</span></span>
  

