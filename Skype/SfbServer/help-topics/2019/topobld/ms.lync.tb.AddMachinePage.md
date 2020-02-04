---
title: 新增伺服器​​
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
ROBOTS: NOINDEX, NOFOLLOW
description: 若要將新的伺服器新增至現有的伺服器池中，請在池中是下列其中一項：
ms.openlocfilehash: c8d40e776a1f141210c51375ba995b6c3ca875d1
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41689252"
---
# <a name="add-server"></a><span data-ttu-id="1dda5-103">新增伺服器​​</span><span class="sxs-lookup"><span data-stu-id="1dda5-103">Add Server</span></span>
 
<span data-ttu-id="1dda5-104">若要將新的伺服器新增至現有的伺服器池中，請在池中是下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="1dda5-104">To add a new server to an existing pool of servers, where the pool is one of the following:</span></span>
  
- <span data-ttu-id="1dda5-105">企業版前端伺服器</span><span class="sxs-lookup"><span data-stu-id="1dda5-105">Enterprise Edition Front End Server</span></span>
    
- <span data-ttu-id="1dda5-106">控制器伺服器</span><span class="sxs-lookup"><span data-stu-id="1dda5-106">Director server</span></span>
    
- <span data-ttu-id="1dda5-107">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="1dda5-107">Mediation Server</span></span>
    
- <span data-ttu-id="1dda5-108">音訊/視訊會議伺服器</span><span class="sxs-lookup"><span data-stu-id="1dda5-108">Audio/Video Conferencing Server</span></span>
    
- <span data-ttu-id="1dda5-109">受信任的應用程式伺服器</span><span class="sxs-lookup"><span data-stu-id="1dda5-109">Trusted Application server</span></span>
    
<span data-ttu-id="1dda5-110">每個新的 [池伺服器] 都有不同的需求。</span><span class="sxs-lookup"><span data-stu-id="1dda5-110">Each of the new pool servers has different requirements.</span></span> <span data-ttu-id="1dda5-111">在下列各節中，找出您要新增到現有區的伺服器類型，並提供所需的資訊，並為每個伺服器類型定義。</span><span class="sxs-lookup"><span data-stu-id="1dda5-111">In the following sections, locate the type of server that you are adding to the existing pool, and supply the information requested as it is defined for each server type.</span></span> <span data-ttu-id="1dda5-112">您提供要求的資訊來定義新的 pool 伺服器。</span><span class="sxs-lookup"><span data-stu-id="1dda5-112">You provide the requested information to define the new pool server.</span></span>
  
 <span data-ttu-id="1dda5-113">**企業版前端伺服器**</span><span class="sxs-lookup"><span data-stu-id="1dda5-113">**Enterprise Edition Front End Server**</span></span>
  
- <span data-ttu-id="1dda5-114">在網域名稱系統（DNS）中定義之新伺服器的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="1dda5-114">Fully qualified domain name (FQDN) of the new server as it is defined in Domain Name System (DNS).</span></span>
    
- <span data-ttu-id="1dda5-115">選取 [**使用所有已設定的 ip 位址**]，這表示電腦上定義的任何 ip 位址都可以使用。</span><span class="sxs-lookup"><span data-stu-id="1dda5-115">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="1dda5-116">或者，您也可以選取 [**將服務使用限制為選取的 IP 位址**]，並在新伺服器上輸入特定的位址。</span><span class="sxs-lookup"><span data-stu-id="1dda5-116">Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server.</span></span> <span data-ttu-id="1dda5-117">輸入的 IP 位址是唯一將回應託管服務的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="1dda5-117">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
- <span data-ttu-id="1dda5-118">在前端伺服器上 collocated 轉送伺服器時，定義**PSTN IP 位址**。</span><span class="sxs-lookup"><span data-stu-id="1dda5-118">Define a **PSTN IP address** when a Mediation Server is collocated on the Front End Server.</span></span>
    
- <span data-ttu-id="1dda5-119">選取 [**啟用 ipv6** ]，為此伺服器啟用 ipv6。</span><span class="sxs-lookup"><span data-stu-id="1dda5-119">Select **Enable IPv6** to enable IPv6 for this server.</span></span>
    
  <span data-ttu-id="1dda5-120">**控制器伺服器**</span><span class="sxs-lookup"><span data-stu-id="1dda5-120">**Director server**</span></span>
  
- <span data-ttu-id="1dda5-121">在 DNS 中定義的新伺服器 FQDN。</span><span class="sxs-lookup"><span data-stu-id="1dda5-121">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="1dda5-122">選取 [**使用所有已設定的 ip 位址**]，表示將會使用電腦上定義的任何 ip 位址。</span><span class="sxs-lookup"><span data-stu-id="1dda5-122">Select **Use all configured IP addresses**, which means that any IP address defined on the computer will be used.</span></span> <span data-ttu-id="1dda5-123">或者，您也可以選取 [**將服務使用限制為選取的 IP 位址**]，並在新伺服器上輸入特定的 ip 位址。</span><span class="sxs-lookup"><span data-stu-id="1dda5-123">Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server.</span></span> <span data-ttu-id="1dda5-124">輸入的 IP 位址是唯一將回應託管服務的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="1dda5-124">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="1dda5-125">**中繼伺服器**</span><span class="sxs-lookup"><span data-stu-id="1dda5-125">**Mediation Server**</span></span>
  
- <span data-ttu-id="1dda5-126">在 DNS 中定義的新伺服器 FQDN。</span><span class="sxs-lookup"><span data-stu-id="1dda5-126">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="1dda5-127">選取 [**使用所有已設定的 ip 位址**]，這表示電腦上定義的任何 ip 位址都可以使用。</span><span class="sxs-lookup"><span data-stu-id="1dda5-127">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="1dda5-128">或者，您也可以選取 [**將服務使用限制為選取的 IP 位址**]，並在新伺服器上輸入特定的 ip 位址作為主要 ip 位址，並輸入公用交換電話網絡（PSTN） ip 位址的 ip 位址。</span><span class="sxs-lookup"><span data-stu-id="1dda5-128">Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server as the Primary IP address, and an enter an IP address for the public switched telephone network (PSTN) IP address.</span></span> <span data-ttu-id="1dda5-129">輸入的 IP 位址是唯一將回應指定服務的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="1dda5-129">The IP addresses entered are the only IP address which will respond for the designated services.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1dda5-130">在中繼伺服器中，為主要 IP 位址和 PSTN IP 位址輸入的 IP 位址，預設是相同的。</span><span class="sxs-lookup"><span data-stu-id="1dda5-130">For the Mediation Server, the IP address entered for the Primary IP address and the PSTN IP address is the same by default.</span></span> <span data-ttu-id="1dda5-131">如果您使用的是專用的網路介面，或在相同的網路介面上單獨的 IP 位址，就可以單獨定義 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="1dda5-131">The IP addresses can be defined separately if you are using dedicated network interfaces or separate IP addresses on the same network interface.</span></span> <span data-ttu-id="1dda5-132">如果您有兩個網路介面，一個適用于本機網路連線，另一個用於 PSTN 連線，則必須指派不同的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="1dda5-132">If you have two network interfaces, one for the local network connection and one for the PSTN connection, you must assign different IP addresses.</span></span> 
  
  <span data-ttu-id="1dda5-133">**音訊/視訊會議伺服器**</span><span class="sxs-lookup"><span data-stu-id="1dda5-133">**Audio/Video Conferencing Server**</span></span>
  
- <span data-ttu-id="1dda5-134">在 DNS 中定義的新伺服器 FQDN。</span><span class="sxs-lookup"><span data-stu-id="1dda5-134">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="1dda5-135">選取 [**使用所有已設定的 ip 位址**]，這表示電腦上定義的任何 ip 位址都可以使用。</span><span class="sxs-lookup"><span data-stu-id="1dda5-135">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="1dda5-136">或者，您也可以選取 [**將服務使用限制為選取的 IP 位址**]，並在新伺服器上輸入特定的位址。</span><span class="sxs-lookup"><span data-stu-id="1dda5-136">Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server.</span></span> <span data-ttu-id="1dda5-137">輸入的 IP 位址是唯一將回應託管服務的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="1dda5-137">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="1dda5-138">**受信任的應用程式伺服器**</span><span class="sxs-lookup"><span data-stu-id="1dda5-138">**Trusted Application server**</span></span>
  
- <span data-ttu-id="1dda5-139">在 DNS 中定義的新伺服器 FQDN。</span><span class="sxs-lookup"><span data-stu-id="1dda5-139">The FQDN of the new server as it is defined in DNS.</span></span>
    

