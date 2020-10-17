---
title: Lync Server 2013：將位置原則新增至網路網站
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add a location policy to a network site
ms:assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425936(v=OCS.15)
ms:contentKeyID: 48183980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95ca625746fc38d8cab9c25701a8bf22718e71e0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529570"
---
# <a name="add-a-location-policy-to-a-network-site-in-lync-server-2013"></a><span data-ttu-id="59588-102">在 Lync Server 2013 中將位置原則新增至網路網站</span><span class="sxs-lookup"><span data-stu-id="59588-102">Add a location policy to a network site in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59588-103">_**主題上次修改日期：** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="59588-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="59588-104">下列範例顯示如何將在[Lync Server 2013 中建立位置](lync-server-2013-create-location-policies.md)原則中定義的**Redmond**位置原則新增至現有的網路網站，以及如何建立使用**Redmond**位置原則的新網路網站。</span><span class="sxs-lookup"><span data-stu-id="59588-104">The following examples show how to add the **Redmond** location policy defined in [Create location policies in Lync Server 2013](lync-server-2013-create-location-policies.md) to an existing network site and how to create a new network site that uses the **Redmond** location policy.</span></span>

<span data-ttu-id="59588-105">如需使用網路網站的詳細資訊，請參閱 Lync Server 管理命令介面檔中的下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="59588-105">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="59588-106">**New-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="59588-106">**New-CsNetworkSite**</span></span>

  - <span data-ttu-id="59588-107">**Get-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="59588-107">**Get-CsNetworkSite**</span></span>

  - <span data-ttu-id="59588-108">**Set-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="59588-108">**Set-CsNetworkSite**</span></span>

  - <span data-ttu-id="59588-109">**Remove-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="59588-109">**Remove-CsNetworkSite**</span></span>

<div>

## <a name="to-assign-a-location-policy-to-an-existing-network-site"></a><span data-ttu-id="59588-110">若要指派位置原則給現有網路網站</span><span class="sxs-lookup"><span data-stu-id="59588-110">To assign a location policy to an existing network site</span></span>

1.  <span data-ttu-id="59588-111">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="59588-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="59588-112">執行下列 Cmdlet 來修改現有的網路網站。</span><span class="sxs-lookup"><span data-stu-id="59588-112">Run the following cmdlets to modify an existing network site.</span></span>
    
    <span data-ttu-id="59588-113">將 **雷德蒙** 標位置原則指派給名為 **redmond**的現有網路網站。</span><span class="sxs-lookup"><span data-stu-id="59588-113">Assign the **Redmond** tagged Location policy to an existing network site named **Redmond**.</span></span>
    
        Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

</div>

<div>

## <a name="to-assign-a-location-policy-to-a-new-network-site"></a><span data-ttu-id="59588-114">若要指派位置原則給新的網路網站</span><span class="sxs-lookup"><span data-stu-id="59588-114">To assign a location policy to a new network site</span></span>

1.  <span data-ttu-id="59588-115">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="59588-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="59588-116">執行下列 Cmdlet 來建立新的網路網站。</span><span class="sxs-lookup"><span data-stu-id="59588-116">Run the following cmdlet to create a new network site.</span></span>
    
    <span data-ttu-id="59588-117">在網路地區中建立新的網路網站，並指派具有 **Redmond** 標記的位置原則。</span><span class="sxs-lookup"><span data-stu-id="59588-117">Create a new network site in the network region and assign the **Redmond** tagged Location policy.</span></span>
    
        New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

</div>

</div>

<span> </span>

</div>

</div>

</div>

