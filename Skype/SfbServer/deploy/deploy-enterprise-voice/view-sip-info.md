---
title: 在商務用 Skype Server 中查看個別 SIP 主幹的相關資訊
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: 摘要：瞭解如何在商務用 Skype Server 中查看有關 SIP 主幹的資訊。
ms.openlocfilehash: 989f9fea44bfcce67eba71b9f0b495b924f9e3a2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103229"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a><span data-ttu-id="de471-103">在商務用 Skype Server 中查看個別 SIP 主幹的相關資訊</span><span class="sxs-lookup"><span data-stu-id="de471-103">View information about individual SIP trunks in Skype for Business Server</span></span>
 
<span data-ttu-id="de471-104">**摘要：** 瞭解如何在商務用 Skype Server 中查看有關 SIP 主幹的資訊。</span><span class="sxs-lookup"><span data-stu-id="de471-104">**Summary:** Learn how to view information about SIP trunks in Skype for Business Server.</span></span>
  
<span data-ttu-id="de471-105">SIP 主幹是用來將商務用 Skype Server Voice over IP phone 網路與公用交換電話網路 (PSTN) 連線。</span><span class="sxs-lookup"><span data-stu-id="de471-105">SIP trunks are used to connect Skype for Business Server Voice over IP phone network with the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="de471-106">在舊版本的產品中，主幹是用來將撥出電話從轉送伺服器路由傳送至 PSTN 閘道，而每個閘道都限制為單一主幹。</span><span class="sxs-lookup"><span data-stu-id="de471-106">In previous version of the product, trunks were used to route outbound calls from a Mediation Server to a PSTN gateway and each gateway was limited to a single trunk.</span></span> <span data-ttu-id="de471-107">因此，PSTN 閘道和 SIP 主幹本質上都相同。</span><span class="sxs-lookup"><span data-stu-id="de471-107">As a result, a PSTN gateway and a SIP trunk were essentially identical.</span></span> <span data-ttu-id="de471-108">針對系統管理員而言，只要查看相關聯的 PSTN 閘道的相關資訊，就可以查看個別 SIP 主幹的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="de471-108">For administrators, that meant they could view information about an individual SIP trunk simply by viewing information about the associated PSTN gateway.</span></span>
  
<span data-ttu-id="de471-109">不過，在商務用 Skype Server 中，多個主幹現在可以指派給單一 PSTN 閘道;這表示閘道和主幹不再是一個，也是相同的。</span><span class="sxs-lookup"><span data-stu-id="de471-109">In Skype for Business Server, however, multiple trunks can now be assigned to a single PSTN gateway; this means that gateways and trunks are no longer one and the same.</span></span> <span data-ttu-id="de471-110">反過來，這表示系統管理員必須使用新的 [Get-CsTrunk](/powershell/module/skype/get-cstrunk?view=skype-ps) Cmdlet，才能查看個別 SIP 主幹的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="de471-110">In turn, that means that administrators must use the new [Get-CsTrunk](/powershell/module/skype/get-cstrunk?view=skype-ps) cmdlet in order to view information about an individual SIP trunk.</span></span>
  
### <a name="to-view-information-for-all-your-sip-trunks"></a><span data-ttu-id="de471-111">若要查看所有 SIP 主幹的資訊</span><span class="sxs-lookup"><span data-stu-id="de471-111">To view information for all your SIP trunks</span></span>

- <span data-ttu-id="de471-112">下列命令會傳回組織中使用之所有 SIP 主幹的資訊：</span><span class="sxs-lookup"><span data-stu-id="de471-112">The following command returns information about all the SIP trunks in use in your organization:</span></span>
    
  ```powershell
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a><span data-ttu-id="de471-113">若要查看特定 SIP 主幹的資訊</span><span class="sxs-lookup"><span data-stu-id="de471-113">To view information for a specific SIP trunk</span></span>

- <span data-ttu-id="de471-114">這個命令只會傳回身分識別 PstnGateway:192.168.0.240 的 SIP 主幹資訊：</span><span class="sxs-lookup"><span data-stu-id="de471-114">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>
    
  ```powershell
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a><span data-ttu-id="de471-115">查看指派至集區之所有 SIP 主幹的資訊</span><span class="sxs-lookup"><span data-stu-id="de471-115">View information for all the SIP trunks assigned to a pool</span></span>

- <span data-ttu-id="de471-116">在此範例中，會傳回指派給集區 atl-cs-001.litwareinc.com 的所有 SIP 主幹的資訊：</span><span class="sxs-lookup"><span data-stu-id="de471-116">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>
    
  ```powershell
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```