---
title: Lync Server 2013：檢查實體環境
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
ms.openlocfilehash: 43f63129ee54ede60cc1da8eb737a5b7e0fa9b76
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502680"
---
# <a name="performing-physical-environmental-checks"></a><span data-ttu-id="ac265-102">執行實體環境檢查</span><span class="sxs-lookup"><span data-stu-id="ac265-102">Performing physical environmental checks</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac265-103">_**主題上次修改日期：** 2014-04-30_</span><span class="sxs-lookup"><span data-stu-id="ac265-103">_**Topic Last Modified:** 2014-04-30_</span></span>

<span data-ttu-id="ac265-104">在檢查 Lync Server 2013 部署的效能、可用性和功能之前，您應該檢查實體環境。</span><span class="sxs-lookup"><span data-stu-id="ac265-104">Before checking the performance, availability, and functionality of the Lync Server 2013 deployment, you should check the physical environment.</span></span> <span data-ttu-id="ac265-105">例如，可能必須降低伺服器的室內溫度，否則可能必須更換網路線。</span><span class="sxs-lookup"><span data-stu-id="ac265-105">For example, the server room temperature might have to be lowered, or a network cable might have to be replaced.</span></span> <span data-ttu-id="ac265-106">為了獲得最佳結果，請執行下列實體環境檢查：</span><span class="sxs-lookup"><span data-stu-id="ac265-106">For best results, perform the following physical environmental inspections:</span></span>

  - <span data-ttu-id="ac265-107">**實體安全性措施**    實體安全性防護（例如鎖定、門和限制存取的聊天室）必須安全。</span><span class="sxs-lookup"><span data-stu-id="ac265-107">**Physical security measures**   Physical security protection such as locks, doors, and restricted-access rooms must be secured.</span></span> <span data-ttu-id="ac265-108">檢查任何未經授權的和強制的專案，以及設備損毀的跡象。</span><span class="sxs-lookup"><span data-stu-id="ac265-108">Check for any unauthorized and forced entries and signs of equipment damage.</span></span>

  - <span data-ttu-id="ac265-109">**溫度和濕度**    高溫、不良的空氣流通及濕度可能會導致硬體元件過高。</span><span class="sxs-lookup"><span data-stu-id="ac265-109">**Temperature and humidity**   High temperature, poor air flow, and humidity can cause hardware components to overheat.</span></span> <span data-ttu-id="ac265-110">檢查溫度和濕度，以協助確定環境系統（如加熱和空調）可以在硬體製造商規格中維持可接受的條件和功能。</span><span class="sxs-lookup"><span data-stu-id="ac265-110">Check temperature and humidity to help to make sure that the environmental systems such as heating and air conditioning can maintain acceptable conditions and function within the hardware manufacturer's specifications.</span></span> <span data-ttu-id="ac265-111">最近安裝新的裝置時，也請檢查伺服器的氣流流向和來源都不受支援，且符合製造商的規格。</span><span class="sxs-lookup"><span data-stu-id="ac265-111">When new equipment has recently been installed, also check that air flow both to and from the servers is unimpeded and meets manufacturer spec.</span></span>

  - <span data-ttu-id="ac265-112">**裝置和元件**    Lync Server 2013 組織依賴運作中的實體網路和相關的硬體。</span><span class="sxs-lookup"><span data-stu-id="ac265-112">**Devices and components**   The Lync Server 2013 organization relies on a functioning physical network and related hardware.</span></span> <span data-ttu-id="ac265-113">請確定路由器、交換器、集線器、實體纜線和連接器均可運作。</span><span class="sxs-lookup"><span data-stu-id="ac265-113">Make sure that routers, switches, hubs, physical cables, and connectors are operational.</span></span>

<span data-ttu-id="ac265-114">關於如何執行這些檢查的詳細資訊，將會在安裝網站和所選擇的伺服器硬體上很大的程度上加以決定。</span><span class="sxs-lookup"><span data-stu-id="ac265-114">The specifics on how to perform these checks will depend greatly on your installation site and the server hardware that was chosen.</span></span> <span data-ttu-id="ac265-115">在您第一次執行這種檢查時，請參閱硬體檔，並記下所需的參數，以備日後參考。</span><span class="sxs-lookup"><span data-stu-id="ac265-115">The first time that you perform this check, refer to the hardware documentation and note the desired parameters for future reference.</span></span>

### <a name="desired-server-space-environment"></a><span data-ttu-id="ac265-116">Desired server space 環境</span><span class="sxs-lookup"><span data-stu-id="ac265-116">Desired server space environment</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ac265-117">參數</span><span class="sxs-lookup"><span data-stu-id="ac265-117">Parameter</span></span></th>
<th><span data-ttu-id="ac265-118">想要的值或範圍</span><span class="sxs-lookup"><span data-stu-id="ac265-118">Desired value or range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ac265-119">溫度</span><span class="sxs-lookup"><span data-stu-id="ac265-119">Temperature</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac265-120">濕度</span><span class="sxs-lookup"><span data-stu-id="ac265-120">Humidity</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac265-121">伺服器正面</span><span class="sxs-lookup"><span data-stu-id="ac265-121">Front of server faces</span></span></p></td>
<td><p><span data-ttu-id="ac265-122">熱通道/cold 通道</span><span class="sxs-lookup"><span data-stu-id="ac265-122">Hot aisle / cold aisle</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac265-123">不應對的排氣淨空</span><span class="sxs-lookup"><span data-stu-id="ac265-123">Unimpeded exhaust clearance</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

