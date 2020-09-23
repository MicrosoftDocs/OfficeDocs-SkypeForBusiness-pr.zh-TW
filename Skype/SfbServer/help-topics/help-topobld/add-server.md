---
title: 新增伺服器
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
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
description: 若要將新的伺服器新增至下列其中一種伺服器的現有集區：
ms.openlocfilehash: 5e6d1772b1cb18fe8c392e3ad9fa4f131415e522
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216404"
---
# <a name="add-server"></a><span data-ttu-id="3d36e-103">新增伺服器</span><span class="sxs-lookup"><span data-stu-id="3d36e-103">Add Server</span></span>
 
<span data-ttu-id="3d36e-104">若要將新的伺服器新增至下列其中一種伺服器的現有集區：</span><span class="sxs-lookup"><span data-stu-id="3d36e-104">To add a new server to an existing pool of servers, where the pool is one of the following:</span></span>
  
- <span data-ttu-id="3d36e-105">Enterprise Edition 前端伺服器</span><span class="sxs-lookup"><span data-stu-id="3d36e-105">Enterprise Edition Front End Server</span></span>
    
- <span data-ttu-id="3d36e-106">Director 伺服器</span><span class="sxs-lookup"><span data-stu-id="3d36e-106">Director server</span></span>
    
- <span data-ttu-id="3d36e-107">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="3d36e-107">Mediation Server</span></span>
    
- <span data-ttu-id="3d36e-108">音訊/視訊會議伺服器</span><span class="sxs-lookup"><span data-stu-id="3d36e-108">Audio/Video Conferencing Server</span></span>
    
- <span data-ttu-id="3d36e-109">信任的應用程式伺服器</span><span class="sxs-lookup"><span data-stu-id="3d36e-109">Trusted Application server</span></span>
    
<span data-ttu-id="3d36e-p101">每個新的集區伺服器各有不同的需求。在下列各節中，尋找您要新增至現有集區的伺服器類型，然後提供每種伺服器類型已定義需要的資訊。提供所要求的資訊來定義新的集區伺服器。</span><span class="sxs-lookup"><span data-stu-id="3d36e-p101">Each of the new pool servers has different requirements. In the following sections, locate the type of server that you are adding to the existing pool, and supply the information requested as it is defined for each server type. You provide the requested information to define the new pool server.</span></span>
  
 <span data-ttu-id="3d36e-113">**Enterprise Edition 前端伺服器**</span><span class="sxs-lookup"><span data-stu-id="3d36e-113">**Enterprise Edition Front End Server**</span></span>
  
- <span data-ttu-id="3d36e-114">新伺服器的完整網域名稱 (FQDN) (如網域名稱系統 (DNS) 中所定義)。</span><span class="sxs-lookup"><span data-stu-id="3d36e-114">Fully qualified domain name (FQDN) of the new server as it is defined in Domain Name System (DNS).</span></span>
    
- <span data-ttu-id="3d36e-p102">選取 **[使用所有設定的 IP 位址]**，表示可以使用電腦上定義的任何 IP 位址。或者，您也可以選取 **[將服務使用方式限制為選取的 IP 位址]**，然後輸入新伺服器上的特定位址。對於託管式服務，所輸入的 IP 位址會是唯一回應的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="3d36e-p102">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used. Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server. The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
- <span data-ttu-id="3d36e-118">當中繼伺服器是組合在前端伺服器上時，定義 [PSTN IP 位址]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3d36e-118">Define a **PSTN IP address** when a Mediation Server is collocated on the Front End Server.</span></span>
    
- <span data-ttu-id="3d36e-119">選取 [啟用 IPv6]\*\*\*\* 為此伺服器啟用 IPv6。</span><span class="sxs-lookup"><span data-stu-id="3d36e-119">Select **Enable IPv6** to enable IPv6 for this server.</span></span>
    
  <span data-ttu-id="3d36e-120">**Director 伺服器**</span><span class="sxs-lookup"><span data-stu-id="3d36e-120">**Director server**</span></span>
  
- <span data-ttu-id="3d36e-121">新伺服器的 FQDN (如 DNS 中所定義)。</span><span class="sxs-lookup"><span data-stu-id="3d36e-121">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="3d36e-p103">選取 [使用所有設定的 IP 位址]\*\*\*\*，表示會使用電腦上定義的任何 IP 位址。或者，您也可以選取 [將服務使用方式限制為選取的 IP 位址]\*\*\*\*，然後輸入新伺服器上的特定 IP 位址。對於託管式服務，所輸入的 IP 位址會是唯一回應的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="3d36e-p103">Select **Use all configured IP addresses**, which means that any IP address defined on the computer will be used. Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server. The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="3d36e-125">**中繼伺服器**</span><span class="sxs-lookup"><span data-stu-id="3d36e-125">**Mediation Server**</span></span>
  
- <span data-ttu-id="3d36e-126">新伺服器的 FQDN (如 DNS 中所定義)。</span><span class="sxs-lookup"><span data-stu-id="3d36e-126">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="3d36e-p104">選取 **[使用所有設定的 IP 位址]**，表示可以使用電腦上定義的任何 IP 位址。或者，您也可以選取 **[將服務使用方式限制為選取的 IP 位址]**，並輸入新伺服器上的特定 IP 位址作為主要 IP 位址，然後輸入 IP 位址作為公用交換電話網路 (PSTN) IP 位址。對於指定的服務，所輸入的 IP 位址是唯一會回應的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="3d36e-p104">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used. Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server as the Primary IP address, and an enter an IP address for the public switched telephone network (PSTN) IP address. The IP addresses entered are the only IP address which will respond for the designated services.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3d36e-p105">若為中繼伺服器，根據預設，輸入作為主要 IP 位址和 PSTN IP 位址的 IP 位址相同。如果您使用專用網路介面，或使用同一網路介面上的不同 IP 位址，則可以分開定義 IP 位址。如果您有兩個網路介面，一個用於區域網路連線，另一個用於 PSTN 連線，您必須指派不同的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="3d36e-p105">For the Mediation Server, the IP address entered for the Primary IP address and the PSTN IP address is the same by default. The IP addresses can be defined separately if you are using dedicated network interfaces or separate IP addresses on the same network interface. If you have two network interfaces, one for the local network connection and one for the PSTN connection, you must assign different IP addresses.</span></span> 
  
  <span data-ttu-id="3d36e-133">**音訊/視訊會議伺服器**</span><span class="sxs-lookup"><span data-stu-id="3d36e-133">**Audio/Video Conferencing Server**</span></span>
  
- <span data-ttu-id="3d36e-134">新伺服器的 FQDN (如 DNS 中所定義)。</span><span class="sxs-lookup"><span data-stu-id="3d36e-134">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="3d36e-p106">選取 [使用所有設定的 IP 位址]\*\*\*\*，表示可以使用電腦上定義的任何 IP 位址。或者，您也可以選取 [將服務使用方式限制為選取的 IP 位址]\*\*\*\*，然後輸入新伺服器上的特定位址。對於託管式服務，所輸入的 IP 位址會是唯一回應的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="3d36e-p106">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used. Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server. The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="3d36e-138">**信任的應用程式伺服器**</span><span class="sxs-lookup"><span data-stu-id="3d36e-138">**Trusted Application server**</span></span>
  
- <span data-ttu-id="3d36e-139">新伺服器的 FQDN (如 DNS 中所定義)。</span><span class="sxs-lookup"><span data-stu-id="3d36e-139">The FQDN of the new server as it is defined in DNS.</span></span>
    

