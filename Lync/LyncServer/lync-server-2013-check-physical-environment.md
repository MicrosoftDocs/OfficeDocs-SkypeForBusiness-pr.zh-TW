---
title: Lync Server 2013：檢查實體環境
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Performing physical environmental checks
ms:assetid: 153aee5e-3adf-4dbf-bf41-53e4fba51fb0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720558(v=OCS.15)
ms:contentKeyID: 63969582
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07335046dc4b37d0e5327ded0a12293657f5fe43
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980418"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="performing-physical-environmental-checks"></a><span data-ttu-id="d57c0-102">執行實體環境檢查</span><span class="sxs-lookup"><span data-stu-id="d57c0-102">Performing physical environmental checks</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d57c0-103">_**主題上次修改日期：** 2014-04-30_</span><span class="sxs-lookup"><span data-stu-id="d57c0-103">_**Topic Last Modified:** 2014-04-30_</span></span>

<span data-ttu-id="d57c0-104">在檢查 Lync Server 2013 部署的效能、可用性及功能前，您應該先檢查實際環境。</span><span class="sxs-lookup"><span data-stu-id="d57c0-104">Before checking the performance, availability, and functionality of the Lync Server 2013 deployment, you should check the physical environment.</span></span> <span data-ttu-id="d57c0-105">例如，伺服器機房溫度可能必須降低，否則可能必須更換網線。</span><span class="sxs-lookup"><span data-stu-id="d57c0-105">For example, the server room temperature might have to be lowered, or a network cable might have to be replaced.</span></span> <span data-ttu-id="d57c0-106">為了獲得最佳結果，請執行下列實際環境檢查：</span><span class="sxs-lookup"><span data-stu-id="d57c0-106">For best results, perform the following physical environmental inspections:</span></span>

  - <span data-ttu-id="d57c0-107">**物理安全性會測量**   物理安全性保護（例如鎖、門和限制存取的聊天室）必須受到保護。</span><span class="sxs-lookup"><span data-stu-id="d57c0-107">**Physical security measures**   Physical security protection such as locks, doors, and restricted-access rooms must be secured.</span></span> <span data-ttu-id="d57c0-108">檢查是否有任何未經授權且強行強制的專案和裝置損壞跡象。</span><span class="sxs-lookup"><span data-stu-id="d57c0-108">Check for any unauthorized and forced entries and signs of equipment damage.</span></span>

  - <span data-ttu-id="d57c0-109">**溫度與濕度**   高溫、氣流差弱及濕度都可能導致硬體元件過熱。</span><span class="sxs-lookup"><span data-stu-id="d57c0-109">**Temperature and humidity**   High temperature, poor air flow, and humidity can cause hardware components to overheat.</span></span> <span data-ttu-id="d57c0-110">檢查溫度與濕度，以協助確保環境系統（例如加熱與空調）可以在硬體製造商規格中維持可接受的條件和功能。</span><span class="sxs-lookup"><span data-stu-id="d57c0-110">Check temperature and humidity to help to make sure that the environmental systems such as heating and air conditioning can maintain acceptable conditions and function within the hardware manufacturer's specifications.</span></span> <span data-ttu-id="d57c0-111">最近安裝新的裝置時，也請檢查伺服器的空中流程是否不受歡迎且符合製造商的規格。</span><span class="sxs-lookup"><span data-stu-id="d57c0-111">When new equipment has recently been installed, also check that air flow both to and from the servers is unimpeded and meets manufacturer spec.</span></span>

  - <span data-ttu-id="d57c0-112">\*\*\*\*    Lync Server 2013 組織所依賴的裝置和元件是由正常運作的物理網路和相關硬體所組成。</span><span class="sxs-lookup"><span data-stu-id="d57c0-112">**Devices and components**   The Lync Server 2013 organization relies on a functioning physical network and related hardware.</span></span> <span data-ttu-id="d57c0-113">確認路由器、交換器、中樞、物理電纜及連接器都能正常運作。</span><span class="sxs-lookup"><span data-stu-id="d57c0-113">Make sure that routers, switches, hubs, physical cables, and connectors are operational.</span></span>

<span data-ttu-id="d57c0-114">如何執行這些檢查的詳細資訊，會大大影響您的安裝網站與所選的伺服器硬體。</span><span class="sxs-lookup"><span data-stu-id="d57c0-114">The specifics on how to perform these checks will depend greatly on your installation site and the server hardware that was chosen.</span></span> <span data-ttu-id="d57c0-115">第一次執行此檢查時，請參閱硬體檔，並記下所需的參數以供日後參考。</span><span class="sxs-lookup"><span data-stu-id="d57c0-115">The first time that you perform this check, refer to the hardware documentation and note the desired parameters for future reference.</span></span>

### <a name="desired-server-space-environment"></a><span data-ttu-id="d57c0-116">所需的伺服器空間環境</span><span class="sxs-lookup"><span data-stu-id="d57c0-116">Desired server space environment</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d57c0-117">參數</span><span class="sxs-lookup"><span data-stu-id="d57c0-117">Parameter</span></span></th>
<th><span data-ttu-id="d57c0-118">所需的值或範圍</span><span class="sxs-lookup"><span data-stu-id="d57c0-118">Desired value or range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d57c0-119">溫度</span><span class="sxs-lookup"><span data-stu-id="d57c0-119">Temperature</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d57c0-120">比</span><span class="sxs-lookup"><span data-stu-id="d57c0-120">Humidity</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d57c0-121">伺服器正面</span><span class="sxs-lookup"><span data-stu-id="d57c0-121">Front of server faces</span></span></p></td>
<td><p><span data-ttu-id="d57c0-122">[熱通道]/[cold] 通道</span><span class="sxs-lookup"><span data-stu-id="d57c0-122">Hot aisle / cold aisle</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d57c0-123">不應對的排出淨空</span><span class="sxs-lookup"><span data-stu-id="d57c0-123">Unimpeded exhaust clearance</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

