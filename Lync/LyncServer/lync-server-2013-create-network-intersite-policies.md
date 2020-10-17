---
title: Lync Server 2013：建立網路網站間原則
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
ms.openlocfilehash: 55c8523fe86cfee7b9e2332e459959b096831abb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515590"
---
# <a name="create-network-intersite-policies-in-lync-server-2013"></a><span data-ttu-id="36c85-102">在 Lync Server 2013 中建立網路站間原則</span><span class="sxs-lookup"><span data-stu-id="36c85-102">Create network intersite policies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36c85-103">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="36c85-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="36c85-104">*網路網站間原則*定義在其間具有直接 WAN 連結的網站之間的頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="36c85-104">A *network intersite policy* defines bandwidth limitations between sites that have direct WAN links between them.</span></span>

<span data-ttu-id="36c85-105">如需詳細資訊，請參閱 Lync Server 管理命令介面檔中的下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="36c85-105">For details, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="36c85-106">新 CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="36c85-106">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)

  - [<span data-ttu-id="36c85-107">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="36c85-107">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)

  - [<span data-ttu-id="36c85-108">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="36c85-108">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)

  - [<span data-ttu-id="36c85-109">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="36c85-109">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)

<div>


> [!IMPORTANT]  
> <span data-ttu-id="36c85-110">只有在兩個網站之間有直接的交叉連結時， <EM>才</EM> 需要網路網站間原則。</span><span class="sxs-lookup"><span data-stu-id="36c85-110">A network intersite policy is required <EM>only</EM> if there is a direct cross link between two network sites.</span></span>



</div>

<span data-ttu-id="36c85-111">在「北美地區」範例中，雷諾與阿布奎基網站之間有直接連結。</span><span class="sxs-lookup"><span data-stu-id="36c85-111">In the example topology North America region, there is a direct link between the Reno and Albuquerque sites.</span></span> <span data-ttu-id="36c85-112">這兩個網站需要套用適當頻寬原則設定檔的站間原則。</span><span class="sxs-lookup"><span data-stu-id="36c85-112">These two sites require an intersite policy that applies an appropriate bandwidth policy profile.</span></span> <span data-ttu-id="36c85-113">下列範例會套用 20Mb \_ 連結設定檔。</span><span class="sxs-lookup"><span data-stu-id="36c85-113">The following example applies the 20Mb\_Link profile.</span></span>

<div>

## <a name="to-create-a-network-intersite-policy"></a><span data-ttu-id="36c85-114">建立網路站間原則</span><span class="sxs-lookup"><span data-stu-id="36c85-114">To create a network intersite policy</span></span>

1.  <span data-ttu-id="36c85-115">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="36c85-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="36c85-116">執行 New-CsNetworkInterSitePolicy Cmdlet，以建立網路網站間原則，並為具有直接交叉連結的兩個網站套用適當的頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="36c85-116">Run the New-CsNetworkInterSitePolicy cmdlet to create network intersite policies and apply an appropriate bandwidth policy profile for two sites that have a direct cross link.</span></span> <span data-ttu-id="36c85-117">例如，執行：</span><span class="sxs-lookup"><span data-stu-id="36c85-117">For example, run:</span></span>
    
        New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link

3.  <span data-ttu-id="36c85-118">如有需要，請重複步驟2，為所有具有直接交叉連結的網路網站配對建立網路網站間原則。</span><span class="sxs-lookup"><span data-stu-id="36c85-118">Repeat step 2 as needed to create network intersite policies for all network sites pairs that have a direct cross link.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

