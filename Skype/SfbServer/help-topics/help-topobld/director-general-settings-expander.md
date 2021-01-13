---
title: Director 一般設定展開工具
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
- ms.lync.tb.DirectorGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2026d0dd-6745-4e53-8b44-acdc378b47d1
description: 若要編輯現有 Director 的設定，您會看到下列區段：
ms.openlocfilehash: b7478779e54a7860726ae967eb1e203625c8b17b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835333"
---
# <a name="director-general-settings-expander"></a><span data-ttu-id="178a6-103">Director 一般設定展開工具</span><span class="sxs-lookup"><span data-stu-id="178a6-103">Director General Settings Expander</span></span>
 
<span data-ttu-id="178a6-104">若要編輯現有 Director 的設定，您會看到下列區段：</span><span class="sxs-lookup"><span data-stu-id="178a6-104">To edit the settings for an existing Director, you are presented with the following sections:</span></span>
  
- <span data-ttu-id="178a6-105">一般設定</span><span class="sxs-lookup"><span data-stu-id="178a6-105">General settings</span></span>
    
- <span data-ttu-id="178a6-106">Web 服務</span><span class="sxs-lookup"><span data-stu-id="178a6-106">Web services</span></span>
    


## <a name="general-settings"></a><span data-ttu-id="178a6-107">一般設定</span><span class="sxs-lookup"><span data-stu-id="178a6-107">General settings</span></span>

<span data-ttu-id="178a6-108">Director 集區 (FQDN) 的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="178a6-108">Fully qualified domain name (FQDN) of the Director pool.</span></span> <span data-ttu-id="178a6-109">編輯伺服器的 FQDN 會變更此值。</span><span class="sxs-lookup"><span data-stu-id="178a6-109">Edit the FQDN of the server to change the value.</span></span> <span data-ttu-id="178a6-110">您必須有符合新值的網域名稱系統 (DNS) 主機 (A) 記錄。</span><span class="sxs-lookup"><span data-stu-id="178a6-110">You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>
  
<span data-ttu-id="178a6-111">在 [ **關聯** ] 中，您可以編輯或指定下列專案：</span><span class="sxs-lookup"><span data-stu-id="178a6-111">In **Associations** you can edit or specify the following:</span></span>
  
<span data-ttu-id="178a6-112">要使用之 Director 集區的檔案共用。</span><span class="sxs-lookup"><span data-stu-id="178a6-112">File share for the Director pool to use.</span></span> <span data-ttu-id="178a6-113">選取拓撲產生器中已定義的現有檔共用，或按一下 [ **新增** ] 建立新的檔案共用定義。</span><span class="sxs-lookup"><span data-stu-id="178a6-113">Select an existing file share that has already been defined in Topology Builder, or click **New** to create a new file share definition.</span></span>
  
<span data-ttu-id="178a6-114">監視 SQL Server 儲存區。</span><span class="sxs-lookup"><span data-stu-id="178a6-114">Monitoring SQL Server store.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="178a6-115">在發佈新定義的拓撲之前，您指定的伺服器必須存在並加入網域中。</span><span class="sxs-lookup"><span data-stu-id="178a6-115">Before publishing the newly defined topology, the server that you specify must exist and be joined to the domain.</span></span> <span data-ttu-id="178a6-116">如果您已建立新的檔案共用，必須在您指派的伺服器上建立檔案共用。</span><span class="sxs-lookup"><span data-stu-id="178a6-116">If you created a new file share, the file share must be created on the server that you designate.</span></span> 
  
## <a name="web-services"></a><span data-ttu-id="178a6-117">Web 服務</span><span class="sxs-lookup"><span data-stu-id="178a6-117">Web services</span></span>

<span data-ttu-id="178a6-118">若要針對 Director 集區上的 Web 服務編輯或指定其他設定，請修改或指定 [內部 Web 服務] 與 [外部 Web 服務] 中的設定。</span><span class="sxs-lookup"><span data-stu-id="178a6-118">To edit or specify additional settings for the Web services on the Director pool, you modify or specify settings in the Internal Web services and External Web services.</span></span>
  
<span data-ttu-id="178a6-119">針對 [ **內部 web 服務** ]，您可以指定下列專案：</span><span class="sxs-lookup"><span data-stu-id="178a6-119">For **Internal web services** you can specify the following:</span></span>
  
> [!CAUTION]
> <span data-ttu-id="178a6-120">如果您有一個以上的前端集區或前端伺服器，則外部 Web 服務 FQDN 必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="178a6-120">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="178a6-121">例如，如果您將前端伺服器的外部 Web 服務 FQDN 定義為 **pool01.contoso.com**，則無法將 **pool01.contoso.com** 用於另一個前端集區或前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="178a6-121">For example, if you define the external Web services FQDN of a Front End Server as **pool01.contoso.com**, you cannot use **pool01.contoso.com** for another Front End pool or Front End Server.</span></span> <span data-ttu-id="178a6-122">如果您也要部署 Director，則為任何 Director 或 Director 集區定義的外部 Web 服務 FQDN，都必須與任何其他 Director 或 Director 集區以及任何前端集區或前端伺服器都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="178a6-122">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="178a6-123">如果您決定使用自行定義的 FQDN 來覆寫內部 web 服務，則每個 FQDN 必須與其他任何前端集區、Director 或 Director 集區是唯一的。</span><span class="sxs-lookup"><span data-stu-id="178a6-123">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>
  
<span data-ttu-id="178a6-124">如果您選取 [覆寫 FQDN]，您可以為集區上的內部 Web 服務識別指定不同的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="178a6-124">If you select Override FQDN, you can specify a different FQDN for the Internal Web services identity on the pool.</span></span> <span data-ttu-id="178a6-125">根據預設，設定為 Director 集區所定義的目前集區名稱。</span><span class="sxs-lookup"><span data-stu-id="178a6-125">By default, the setting is the current pool name as defined for the Director pool.</span></span>
  
<span data-ttu-id="178a6-126">您可以為您的部署所需的 HTTP 和 HTTPS 指定聽取和發行的埠。</span><span class="sxs-lookup"><span data-stu-id="178a6-126">You can specify listening and published ports for HTTP and HTTPS that your deployment requires.</span></span> <span data-ttu-id="178a6-127">HTTPS 的埠80的預設設定和 HTTPS 的埠443是最常見的設定，除非您在組織和基礎結構設計中有特定需求，否則通常不需要加以變更。</span><span class="sxs-lookup"><span data-stu-id="178a6-127">The default setting of port 80 for HTTP and port 443 for HTTPS are the most common settings and typically do not need to be changed unless you have specific requirements within your organization and infrastructure design.</span></span>
  
<span data-ttu-id="178a6-128">針對 [ **外部 web 服務**]，您可以指定下列專案：</span><span class="sxs-lookup"><span data-stu-id="178a6-128">For **External web services**, you can specify the following:</span></span>
  
<span data-ttu-id="178a6-129">您可以定義外部 Web 服務的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="178a6-129">You can define the FQDN of the External Web services.</span></span> <span data-ttu-id="178a6-130">在這裡指定的 FQDN 通常會由外部連線需求（例如反向 proxy）的需求所定義。</span><span class="sxs-lookup"><span data-stu-id="178a6-130">The FQDN specified here will usually be defined by the requirements of your external connection requirements, such as the reverse proxy.</span></span>
  
<span data-ttu-id="178a6-131">您可以為您的部署所需的 HTTP 和 HTTPS 指定聽取和發行的埠。</span><span class="sxs-lookup"><span data-stu-id="178a6-131">You can specify listening and published ports for HTTP and HTTPS that your deployment requires.</span></span> <span data-ttu-id="178a6-132">HTTPS 的埠8080的預設設定會先定義 HTTPS 的埠4443。</span><span class="sxs-lookup"><span data-stu-id="178a6-132">The default settings of port 8080 for HTTP and port 4443 for HTTPS are defined initially.</span></span> <span data-ttu-id="178a6-133">您可以根據您的反向 proxy 和外部網路需求的需求，來變更聆聽埠的這些設定。</span><span class="sxs-lookup"><span data-stu-id="178a6-133">You change these settings for the listening ports based on what the requirements are for your reverse proxy and external network requirements.</span></span> <span data-ttu-id="178a6-134">已發佈的埠設定為埠80的預設值，HTTP 及埠443用於 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="178a6-134">The published ports are set to default of port 80 for HTTP and port 443 for HTTPS.</span></span> <span data-ttu-id="178a6-135">這些值會決定 Director 集區或 Director 伺服器將接聽傳入要求的埠。</span><span class="sxs-lookup"><span data-stu-id="178a6-135">These values determine what ports the Director pool or Director server will listen for incoming requests.</span></span> <span data-ttu-id="178a6-136">除非集區的埠需求有衝突，否則通常不需要變更這些功能。</span><span class="sxs-lookup"><span data-stu-id="178a6-136">Typically, these do not need to be changed, unless there is conflict of port requirements on the pool.</span></span> <span data-ttu-id="178a6-137">期望使用相同埠值的內部及外部發佈埠。</span><span class="sxs-lookup"><span data-stu-id="178a6-137">Internal and external published ports that use the same port values are expected.</span></span> <span data-ttu-id="178a6-138">這不是衝突。</span><span class="sxs-lookup"><span data-stu-id="178a6-138">This is not a conflict.</span></span>
  

