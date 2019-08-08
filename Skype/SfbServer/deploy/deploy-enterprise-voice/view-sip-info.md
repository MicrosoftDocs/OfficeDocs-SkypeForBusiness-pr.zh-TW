---
title: 在商務用 Skype Server 中查看個別 SIP trunks 的相關資訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: '摘要: 瞭解如何在商務用 Skype Server 中查看有關 SIP trunks 的資訊。'
ms.openlocfilehash: 3d8ad70428926c26445c6556544a5a363de12f5c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240211"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a><span data-ttu-id="bcbf5-103">在商務用 Skype Server 中查看個別 SIP trunks 的相關資訊</span><span class="sxs-lookup"><span data-stu-id="bcbf5-103">View information about individual SIP trunks in Skype for Business Server</span></span>
 
<span data-ttu-id="bcbf5-104">**摘要:** 瞭解如何在商務用 Skype Server 中查看有關 SIP trunks 的資訊。</span><span class="sxs-lookup"><span data-stu-id="bcbf5-104">**Summary:** Learn how to view information about SIP trunks in Skype for Business Server.</span></span>
  
<span data-ttu-id="bcbf5-105">SIP trunks 是用來連接商務用 Skype Server Voice over IP 電話網絡 (PSTN)。</span><span class="sxs-lookup"><span data-stu-id="bcbf5-105">SIP trunks are used to connect Skype for Business Server Voice over IP phone network with the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="bcbf5-106">在早期版本的產品中, trunks 是用來將撥出電話從中繼伺服器傳送到 PSTN 閘道, 而每個閘道都限制在單一干線中。</span><span class="sxs-lookup"><span data-stu-id="bcbf5-106">In previous version of the product, trunks were used to route outbound calls from a Mediation Server to a PSTN gateway and each gateway was limited to a single trunk.</span></span> <span data-ttu-id="bcbf5-107">因此, PSTN 閘道與 SIP 幹線本質上完全相同。</span><span class="sxs-lookup"><span data-stu-id="bcbf5-107">As a result, a PSTN gateway and a SIP trunk were essentially identical.</span></span> <span data-ttu-id="bcbf5-108">針對管理員而言, 這表示只要查看關聯 PSTN 閘道的相關資訊, 就能查看個別 SIP 主幹的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="bcbf5-108">For administrators, that meant they could view information about an individual SIP trunk simply by viewing information about the associated PSTN gateway.</span></span>
  
<span data-ttu-id="bcbf5-109">在商務用 Skype Server 中, 您現在可以將多個 trunks 指派給單一 PSTN 閘道;這表示閘道與 trunks 已不再是相同的。</span><span class="sxs-lookup"><span data-stu-id="bcbf5-109">In Skype for Business Server, however, multiple trunks can now be assigned to a single PSTN gateway; this means that gateways and trunks are no longer one and the same.</span></span> <span data-ttu-id="bcbf5-110">因此, 這表示系統管理員必須使用新的[CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) Cmdlet, 才能查看個別 SIP 幹線的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="bcbf5-110">In turn, that means that administrators must use the new [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) cmdlet in order to view information about an individual SIP trunk.</span></span>
  
### <a name="to-view-information-for-all-your-sip-trunks"></a><span data-ttu-id="bcbf5-111">若要查看所有 SIP trunks 的相關資訊</span><span class="sxs-lookup"><span data-stu-id="bcbf5-111">To view information for all your SIP trunks</span></span>

- <span data-ttu-id="bcbf5-112">下列命令會傳回貴組織中使用的所有 SIP trunks 資訊:</span><span class="sxs-lookup"><span data-stu-id="bcbf5-112">The following command returns information about all the SIP trunks in use in your organization:</span></span>
    
  ```
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a><span data-ttu-id="bcbf5-113">若要查看特定 SIP 主幹的資訊</span><span class="sxs-lookup"><span data-stu-id="bcbf5-113">To view information for a specific SIP trunk</span></span>

- <span data-ttu-id="bcbf5-114">這個命令只會傳回具有身分識別 PstnGateway 的 SIP 幹線資訊: 192.168.0.240:</span><span class="sxs-lookup"><span data-stu-id="bcbf5-114">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>
    
  ```
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a><span data-ttu-id="bcbf5-115">查看指派給某個池之所有 SIP trunks 的相關資訊</span><span class="sxs-lookup"><span data-stu-id="bcbf5-115">View information for all the SIP trunks assigned to a pool</span></span>

- <span data-ttu-id="bcbf5-116">在這個範例中, 會針對指派給 pool atl-cs-001.litwareinc.com 的所有 SIP trunks 傳回信息:</span><span class="sxs-lookup"><span data-stu-id="bcbf5-116">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>
    
  ```
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```
