---
title: Lync Server 2013：將位置原則新增至網路網站
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add a location policy to a network site
ms:assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425936(v=OCS.15)
ms:contentKeyID: 48183980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9ee6b5ba89cef592e137104df9e80d9373b5f02
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976715"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-a-location-policy-to-a-network-site-in-lync-server-2013"></a><span data-ttu-id="65fb5-102">在 Lync Server 2013 的網路網站中新增位置原則</span><span class="sxs-lookup"><span data-stu-id="65fb5-102">Add a location policy to a network site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65fb5-103">_**主題上次修改日期：** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="65fb5-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="65fb5-104">下列範例示範如何將在[Lync Server 2013 的建立位置](lync-server-2013-create-location-policies.md)原則中定義的**雷德蒙**位置原則新增到現有的網路網站，以及如何建立使用**雷蒙德**位置原則的新網路網站。</span><span class="sxs-lookup"><span data-stu-id="65fb5-104">The following examples show how to add the **Redmond** location policy defined in [Create location policies in Lync Server 2013](lync-server-2013-create-location-policies.md) to an existing network site and how to create a new network site that uses the **Redmond** location policy.</span></span>

<span data-ttu-id="65fb5-105">如需使用網路網站的詳細資訊，請參閱適用于下列 Cmdlet 的 Lync Server 管理命令介面檔：</span><span class="sxs-lookup"><span data-stu-id="65fb5-105">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="65fb5-106">**新-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="65fb5-106">**New-CsNetworkSite**</span></span>

  - <span data-ttu-id="65fb5-107">**CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="65fb5-107">**Get-CsNetworkSite**</span></span>

  - <span data-ttu-id="65fb5-108">**Set-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="65fb5-108">**Set-CsNetworkSite**</span></span>

  - <span data-ttu-id="65fb5-109">**移除-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="65fb5-109">**Remove-CsNetworkSite**</span></span>

<div>

## <a name="to-assign-a-location-policy-to-an-existing-network-site"></a><span data-ttu-id="65fb5-110">將位置原則指派給現有的網路網站</span><span class="sxs-lookup"><span data-stu-id="65fb5-110">To assign a location policy to an existing network site</span></span>

1.  <span data-ttu-id="65fb5-111">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="65fb5-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="65fb5-112">執行下列 Cmdlet 來修改現有的網路網站。</span><span class="sxs-lookup"><span data-stu-id="65fb5-112">Run the following cmdlets to modify an existing network site.</span></span>
    
    <span data-ttu-id="65fb5-113">將**雷德蒙**標記的位置原則指派給名為 [**雷蒙德**] 的現有網路網站。</span><span class="sxs-lookup"><span data-stu-id="65fb5-113">Assign the **Redmond** tagged Location policy to an existing network site named **Redmond**.</span></span>
    
        Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

</div>

<div>

## <a name="to-assign-a-location-policy-to-a-new-network-site"></a><span data-ttu-id="65fb5-114">將位置原則指派給新的網路網站</span><span class="sxs-lookup"><span data-stu-id="65fb5-114">To assign a location policy to a new network site</span></span>

1.  <span data-ttu-id="65fb5-115">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="65fb5-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="65fb5-116">執行下列 Cmdlet 以建立新的網路網站。</span><span class="sxs-lookup"><span data-stu-id="65fb5-116">Run the following cmdlet to create a new network site.</span></span>
    
    <span data-ttu-id="65fb5-117">在網路區域中建立新的網路網站，並指派**雷德蒙**標記的位置原則。</span><span class="sxs-lookup"><span data-stu-id="65fb5-117">Create a new network site in the network region and assign the **Redmond** tagged Location policy.</span></span>
    
        New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

</div>

</div>

<span> </span>

</div>

</div>

</div>

