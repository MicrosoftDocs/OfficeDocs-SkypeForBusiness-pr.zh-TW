---
title: Lync Server 2013： 檢查實體環境
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Performing physical environmental checks
ms:assetid: 153aee5e-3adf-4dbf-bf41-53e4fba51fb0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720558(v=OCS.15)
ms:contentKeyID: 63969582
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e85f99250161433ba895f287521367d1b76cec1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190356"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="performing-physical-environmental-checks"></a><span data-ttu-id="3ff88-102">執行實體環境檢查</span><span class="sxs-lookup"><span data-stu-id="3ff88-102">Performing physical environmental checks</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ff88-103">_**上次修改主題：** 2014年-04-30_</span><span class="sxs-lookup"><span data-stu-id="3ff88-103">_**Topic Last Modified:** 2014-04-30_</span></span>

<span data-ttu-id="3ff88-104">之前檢查效能、 可用性及 Lync Server 2013 部署的功能，您應該檢查實體環境。</span><span class="sxs-lookup"><span data-stu-id="3ff88-104">Before checking the performance, availability, and functionality of the Lync Server 2013 deployment, you should check the physical environment.</span></span> <span data-ttu-id="3ff88-105">例如，伺服器可能會有溫度，或網路線可能已被取代。</span><span class="sxs-lookup"><span data-stu-id="3ff88-105">For example, the server room temperature might have to be lowered, or a network cable might have to be replaced.</span></span> <span data-ttu-id="3ff88-106">為了獲得最佳結果，請執行下列實體環境檢查：</span><span class="sxs-lookup"><span data-stu-id="3ff88-106">For best results, perform the following physical environmental inspections:</span></span>

  - <span data-ttu-id="3ff88-107">**實體安全性措施**   實體安全性防護，如鎖定、 門及限制存取聊天室必須受到保護。</span><span class="sxs-lookup"><span data-stu-id="3ff88-107">**Physical security measures**   Physical security protection such as locks, doors, and restricted-access rooms must be secured.</span></span> <span data-ttu-id="3ff88-108">檢查有任何未經授權和強制項目和設備損毀的徵兆。</span><span class="sxs-lookup"><span data-stu-id="3ff88-108">Check for any unauthorized and forced entries and signs of equipment damage.</span></span>

  - <span data-ttu-id="3ff88-109">**溫度和濕度**   高溫、 不佳的空調流程和濕度可能會導致硬體元件，以發出過熱。</span><span class="sxs-lookup"><span data-stu-id="3ff88-109">**Temperature and humidity**   High temperature, poor air flow, and humidity can cause hardware components to overheat.</span></span> <span data-ttu-id="3ff88-110">請檢查溫度和濕度，有助於確保環境系統如加熱和空調可以維護可接受的條件和硬體製造商規格中的運作。</span><span class="sxs-lookup"><span data-stu-id="3ff88-110">Check temperature and humidity to help to make sure that the environmental systems such as heating and air conditioning can maintain acceptable conditions and function within the hardware manufacturer's specifications.</span></span> <span data-ttu-id="3ff88-111">當最近已安裝新的設備時，也請檢查空調流程，以及從伺服器是暢行無阻，且符合製造商規格。</span><span class="sxs-lookup"><span data-stu-id="3ff88-111">When new equipment has recently been installed, also check that air flow both to and from the servers is unimpeded and meets manufacturer spec.</span></span>

  - <span data-ttu-id="3ff88-112">**裝置和元件**   Lync Server 2013 組織依賴可正常運作的實體網路和相關的硬體。</span><span class="sxs-lookup"><span data-stu-id="3ff88-112">**Devices and components**   The Lync Server 2013 organization relies on a functioning physical network and related hardware.</span></span> <span data-ttu-id="3ff88-113">請確定路由器、 交換器、 集線器、 實體纜線和連接器運作正常。</span><span class="sxs-lookup"><span data-stu-id="3ff88-113">Make sure that routers, switches, hubs, physical cables, and connectors are operational.</span></span>

<span data-ttu-id="3ff88-114">如何執行這類檢查特定內容取決於您安裝的網站和所選的伺服器硬體的很大的差異。</span><span class="sxs-lookup"><span data-stu-id="3ff88-114">The specifics on how to perform these checks will depend greatly on your installation site and the server hardware that was chosen.</span></span> <span data-ttu-id="3ff88-115">第一次您執行這項檢查，請參閱硬體文件，然後記下所需的參數為供日後參考。</span><span class="sxs-lookup"><span data-stu-id="3ff88-115">The first time that you perform this check, refer to the hardware documentation and note the desired parameters for future reference.</span></span>

### <a name="desired-server-space-environment"></a><span data-ttu-id="3ff88-116">想要的伺服器空間環境</span><span class="sxs-lookup"><span data-stu-id="3ff88-116">Desired server space environment</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3ff88-117">參數</span><span class="sxs-lookup"><span data-stu-id="3ff88-117">Parameter</span></span></th>
<th><span data-ttu-id="3ff88-118">所需的值或範圍</span><span class="sxs-lookup"><span data-stu-id="3ff88-118">Desired value or range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3ff88-119">溫度</span><span class="sxs-lookup"><span data-stu-id="3ff88-119">Temperature</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ff88-120">溼度</span><span class="sxs-lookup"><span data-stu-id="3ff88-120">Humidity</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ff88-121">前端伺服器所面臨的</span><span class="sxs-lookup"><span data-stu-id="3ff88-121">Front of server faces</span></span></p></td>
<td><p><span data-ttu-id="3ff88-122">熱通道 / 冷通道</span><span class="sxs-lookup"><span data-stu-id="3ff88-122">Hot aisle / cold aisle</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ff88-123">暢行無阻的排氣距離</span><span class="sxs-lookup"><span data-stu-id="3ff88-123">Unimpeded exhaust clearance</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

