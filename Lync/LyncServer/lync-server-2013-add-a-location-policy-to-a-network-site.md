---
title: Lync Server 2013：將位置原則新增至網路網站
description: Lync Server 2013：將位置原則新增至網路網站。
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
ms.openlocfilehash: 20f71d3144e2ef730de5dae46be16138b5d36c42
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567919"
---
# <a name="add-a-location-policy-to-a-network-site-in-lync-server-2013"></a><span data-ttu-id="aae03-103">在 Lync Server 2013 中將位置原則新增至網路網站</span><span class="sxs-lookup"><span data-stu-id="aae03-103">Add a location policy to a network site in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aae03-104">_**主題上次修改日期：** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="aae03-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="aae03-105">下列範例顯示如何將在[Lync Server 2013 中建立位置](lync-server-2013-create-location-policies.md)原則中定義的**Redmond**位置原則新增至現有的網路網站，以及如何建立使用**Redmond**位置原則的新網路網站。</span><span class="sxs-lookup"><span data-stu-id="aae03-105">The following examples show how to add the **Redmond** location policy defined in [Create location policies in Lync Server 2013](lync-server-2013-create-location-policies.md) to an existing network site and how to create a new network site that uses the **Redmond** location policy.</span></span>

<span data-ttu-id="aae03-106">如需使用網路網站的詳細資訊，請參閱 Lync Server 管理命令介面檔中的下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="aae03-106">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="aae03-107">**New-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="aae03-107">**New-CsNetworkSite**</span></span>

  - <span data-ttu-id="aae03-108">**Get-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="aae03-108">**Get-CsNetworkSite**</span></span>

  - <span data-ttu-id="aae03-109">**Set-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="aae03-109">**Set-CsNetworkSite**</span></span>

  - <span data-ttu-id="aae03-110">**Remove-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="aae03-110">**Remove-CsNetworkSite**</span></span>

<div>

## <a name="to-assign-a-location-policy-to-an-existing-network-site"></a><span data-ttu-id="aae03-111">若要指派位置原則給現有網路網站</span><span class="sxs-lookup"><span data-stu-id="aae03-111">To assign a location policy to an existing network site</span></span>

1.  <span data-ttu-id="aae03-112">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="aae03-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="aae03-113">執行下列 Cmdlet 來修改現有的網路網站。</span><span class="sxs-lookup"><span data-stu-id="aae03-113">Run the following cmdlets to modify an existing network site.</span></span>
    
    <span data-ttu-id="aae03-114">將 **雷德蒙** 標位置原則指派給名為 **redmond**的現有網路網站。</span><span class="sxs-lookup"><span data-stu-id="aae03-114">Assign the **Redmond** tagged Location policy to an existing network site named **Redmond**.</span></span>
    
        Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

</div>

<div>

## <a name="to-assign-a-location-policy-to-a-new-network-site"></a><span data-ttu-id="aae03-115">若要指派位置原則給新的網路網站</span><span class="sxs-lookup"><span data-stu-id="aae03-115">To assign a location policy to a new network site</span></span>

1.  <span data-ttu-id="aae03-116">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="aae03-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="aae03-117">執行下列 Cmdlet 來建立新的網路網站。</span><span class="sxs-lookup"><span data-stu-id="aae03-117">Run the following cmdlet to create a new network site.</span></span>
    
    <span data-ttu-id="aae03-118">在網路地區中建立新的網路網站，並指派具有 **Redmond** 標記的位置原則。</span><span class="sxs-lookup"><span data-stu-id="aae03-118">Create a new network site in the network region and assign the **Redmond** tagged Location policy.</span></span>
    
        New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

</div>

</div>

<span> </span>

</div>

</div>

</div>

