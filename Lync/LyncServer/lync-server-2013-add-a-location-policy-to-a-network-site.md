---
title: Lync Server 2013： 新增網路網站的位置原則
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
ms.openlocfilehash: 5a817a1a94b6e02167d488212dd532537cec0146
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145031"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-a-location-policy-to-a-network-site-in-lync-server-2013"></a><span data-ttu-id="110d8-102">將位置原則新增至 Lync Server 2013 中的網路網站</span><span class="sxs-lookup"><span data-stu-id="110d8-102">Add a location policy to a network site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="110d8-103">_**上次修改主題：** 2013年-02-24_</span><span class="sxs-lookup"><span data-stu-id="110d8-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="110d8-104">下列範例顯示如何新增至現有的網路網站在[Lync Server 2013 中的建立位置原則](lync-server-2013-create-location-policies.md)中定義的**Redmond**位置原則，以及如何建立使用**Redmond**位置原則的新網路網站。</span><span class="sxs-lookup"><span data-stu-id="110d8-104">The following examples show how to add the **Redmond** location policy defined in [Create location policies in Lync Server 2013](lync-server-2013-create-location-policies.md) to an existing network site and how to create a new network site that uses the **Redmond** location policy.</span></span>

<span data-ttu-id="110d8-105">如需使用網路站台的詳細資訊，請參閱 Lync Server 管理命令介面文件的下列 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="110d8-105">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="110d8-106">**新 CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="110d8-106">**New-CsNetworkSite**</span></span>

  - <span data-ttu-id="110d8-107">**Get-csnetworksite**</span><span class="sxs-lookup"><span data-stu-id="110d8-107">**Get-CsNetworkSite**</span></span>

  - <span data-ttu-id="110d8-108">**Set-csnetworksite**</span><span class="sxs-lookup"><span data-stu-id="110d8-108">**Set-CsNetworkSite**</span></span>

  - <span data-ttu-id="110d8-109">**移除 CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="110d8-109">**Remove-CsNetworkSite**</span></span>

<div>

## <a name="to-assign-a-location-policy-to-an-existing-network-site"></a><span data-ttu-id="110d8-110">若要指派位置原則給現有網路網站</span><span class="sxs-lookup"><span data-stu-id="110d8-110">To assign a location policy to an existing network site</span></span>

1.  <span data-ttu-id="110d8-111">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="110d8-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="110d8-112">執行下列 Cmdlet 來修改現有的網路網站。</span><span class="sxs-lookup"><span data-stu-id="110d8-112">Run the following cmdlets to modify an existing network site.</span></span>
    
    <span data-ttu-id="110d8-113">指派標記**Redmond**位置原則給現有網路網站名為**Redmond**。</span><span class="sxs-lookup"><span data-stu-id="110d8-113">Assign the **Redmond** tagged Location policy to an existing network site named **Redmond**.</span></span>
    
        Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

</div>

<div>

## <a name="to-assign-a-location-policy-to-a-new-network-site"></a><span data-ttu-id="110d8-114">若要指派位置原則給新的網路網站</span><span class="sxs-lookup"><span data-stu-id="110d8-114">To assign a location policy to a new network site</span></span>

1.  <span data-ttu-id="110d8-115">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="110d8-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="110d8-116">執行下列 Cmdlet 來建立新的網路網站。</span><span class="sxs-lookup"><span data-stu-id="110d8-116">Run the following cmdlet to create a new network site.</span></span>
    
    <span data-ttu-id="110d8-117">在網路地區中建立新的網路網站，並指派具有 **Redmond** 標記的位置原則。</span><span class="sxs-lookup"><span data-stu-id="110d8-117">Create a new network site in the network region and assign the **Redmond** tagged Location policy.</span></span>
    
        New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

</div>

</div>

<span> </span>

</div>

</div>

</div>

