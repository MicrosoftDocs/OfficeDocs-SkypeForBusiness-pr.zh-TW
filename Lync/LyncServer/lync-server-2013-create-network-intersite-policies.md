---
title: Lync Server 2013： 建立網站間原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create network intersite policies
ms:assetid: b0714aae-55dc-4587-b718-34a03f596b22
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412844(v=OCS.15)
ms:contentKeyID: 48185148
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1c42f9edf30e7581d001b2e6bd2e79ea5a3c76a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151985"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-network-intersite-policies-in-lync-server-2013"></a><span data-ttu-id="ea00b-102">Lync Server 2013 中建立網站間原則</span><span class="sxs-lookup"><span data-stu-id="ea00b-102">Create network intersite policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea00b-103">_**主題上次修改日期：** 2012年-10-19_</span><span class="sxs-lookup"><span data-stu-id="ea00b-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="ea00b-104">*網站間原則*會定義有直接的 WAN 連結它們之間的站台之間的頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="ea00b-104">A *network intersite policy* defines bandwidth limitations between sites that have direct WAN links between them.</span></span>

<span data-ttu-id="ea00b-105">如需詳細資訊，請參閱 Lync Server 管理命令介面文件的下列 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="ea00b-105">For details, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="ea00b-106">新 CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="ea00b-106">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)

  - [<span data-ttu-id="ea00b-107">Get-csnetworkintersitepolicy</span><span class="sxs-lookup"><span data-stu-id="ea00b-107">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)

  - [<span data-ttu-id="ea00b-108">Set-csnetworkintersitepolicy</span><span class="sxs-lookup"><span data-stu-id="ea00b-108">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)

  - [<span data-ttu-id="ea00b-109">Remove-csnetworkintersitepolicy</span><span class="sxs-lookup"><span data-stu-id="ea00b-109">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ea00b-110">如果兩個網路站台之間沒有直接的交叉連結，則需要<EM>唯一</EM>網站間原則。</span><span class="sxs-lookup"><span data-stu-id="ea00b-110">A network intersite policy is required <EM>only</EM> if there is a direct cross link between two network sites.</span></span>



</div>

<span data-ttu-id="ea00b-111">在範例拓撲北美地區中，有雷諾與阿布站台之間是直接連結。</span><span class="sxs-lookup"><span data-stu-id="ea00b-111">In the example topology North America region, there is a direct link between the Reno and Albuquerque sites.</span></span> <span data-ttu-id="ea00b-112">這兩個網站需要套用適當的頻寬原則設定檔的站台間原則。</span><span class="sxs-lookup"><span data-stu-id="ea00b-112">These two sites require an intersite policy that applies an appropriate bandwidth policy profile.</span></span> <span data-ttu-id="ea00b-113">下列範例會將套用 20mb\_連結設定檔。</span><span class="sxs-lookup"><span data-stu-id="ea00b-113">The following example applies the 20Mb\_Link profile.</span></span>

<div>

## <a name="to-create-a-network-intersite-policy"></a><span data-ttu-id="ea00b-114">若要建立網站間原則</span><span class="sxs-lookup"><span data-stu-id="ea00b-114">To create a network intersite policy</span></span>

1.  <span data-ttu-id="ea00b-115">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="ea00b-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="ea00b-116">執行新增 CsNetworkInterSitePolicy cmdlet 來建立網站間原則並套用具有直接交叉連結的兩個站台的適當的頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="ea00b-116">Run the New-CsNetworkInterSitePolicy cmdlet to create network intersite policies and apply an appropriate bandwidth policy profile for two sites that have a direct cross link.</span></span> <span data-ttu-id="ea00b-117">例如，執行：</span><span class="sxs-lookup"><span data-stu-id="ea00b-117">For example, run:</span></span>
    
        New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link

3.  <span data-ttu-id="ea00b-118">重複步驟 2，視需要建立網站間原則的所有網站配對具有直接交叉連結。</span><span class="sxs-lookup"><span data-stu-id="ea00b-118">Repeat step 2 as needed to create network intersite policies for all network sites pairs that have a direct cross link.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

