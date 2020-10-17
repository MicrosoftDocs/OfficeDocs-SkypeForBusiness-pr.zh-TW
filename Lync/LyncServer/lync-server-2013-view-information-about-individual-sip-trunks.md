---
title: Lync Server 2013：查看個別 SIP 主幹的相關資訊
description: Lync Server 2013：查看個別 SIP 主幹的資訊。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View information about individual SIP trunks
ms:assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721847(v=OCS.15)
ms:contentKeyID: 49733780
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55c2f9fb1df4e916615cf7f95f95ae167d7216ab
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569609"
---
# <a name="view-information-about-individual-sip-trunks-in-lync-server-2013"></a><span data-ttu-id="02613-103">在 Lync Server 2013 中查看個別 SIP 主幹的相關資訊</span><span class="sxs-lookup"><span data-stu-id="02613-103">View information about individual SIP trunks in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02613-104">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="02613-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="02613-105">SIP 主幹是用於連接 Lync Server 2013 Voice over IP phone 網路與公用交換電話網路。</span><span class="sxs-lookup"><span data-stu-id="02613-105">SIP trunks are used to connect Lync Server 2013 Voice over IP phone network with the Public Switched Telephone Network.</span></span> <span data-ttu-id="02613-106">在舊版本的產品中，主幹是用來將撥出電話從轉送伺服器路由傳送至 PSTN 閘道，而每個閘道都限制為單一主幹。</span><span class="sxs-lookup"><span data-stu-id="02613-106">In previous version of the product, trunks were used to route outbound calls from a Mediation Server to a PSTN gateway and each gateway was limited to a single trunk.</span></span> <span data-ttu-id="02613-107">因此，PSTN 閘道和 SIP 主幹本質上都相同。</span><span class="sxs-lookup"><span data-stu-id="02613-107">As a result, a PSTN gateway and a SIP trunk were essentially identical.</span></span> <span data-ttu-id="02613-108">針對系統管理員而言，只要查看相關聯的 PSTN 閘道的相關資訊，就可以查看個別 SIP 主幹的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="02613-108">For administrators, that meant they could view information about an individual SIP trunk simply by viewing information about the associated PSTN gateway.</span></span>

<span data-ttu-id="02613-109">不過，在 Lync Server 2013 中，現在可以將多個主幹指派給單一 PSTN 閘道;這表示閘道和主幹不再是一個，也是相同的。</span><span class="sxs-lookup"><span data-stu-id="02613-109">In Lync Server 2013, however, multiple trunks can now be assigned to a single PSTN gateway; this means that gateways and trunks are no longer one and the same.</span></span> <span data-ttu-id="02613-110">反過來，這表示系統管理員必須使用新的 [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) Cmdlet，才能查看個別 SIP 主幹的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="02613-110">In turn, that means that administrators must use the new [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) cmdlet in order to view information about an individual SIP trunk.</span></span>

<span data-ttu-id="02613-111">Get-CsTrunk Cmdlet 既可以從 Lync Server 2013 管理命令介面，也可以從 Windows PowerShell 的遠端會話執行。</span><span class="sxs-lookup"><span data-stu-id="02613-111">The Get-CsTrunk cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="02613-112">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="02613-112">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-information-for-all-your-sip-trunks"></a><span data-ttu-id="02613-113">若要查看所有 SIP 主幹的資訊</span><span class="sxs-lookup"><span data-stu-id="02613-113">To view information for all your SIP trunks</span></span>

  - <span data-ttu-id="02613-114">下列命令會傳回組織中使用之所有 SIP 主幹的資訊：</span><span class="sxs-lookup"><span data-stu-id="02613-114">The following command returns information about all the SIP trunks in use in your organization:</span></span>
    
        Get-CsTrunk

</div>

<div>

## <a name="to-view-information-for-a-specific-sip-trunk"></a><span data-ttu-id="02613-115">若要查看特定 SIP 主幹的資訊</span><span class="sxs-lookup"><span data-stu-id="02613-115">To view information for a specific SIP trunk</span></span>

  - <span data-ttu-id="02613-116">這個命令只會傳回身分識別 PstnGateway:192.168.0.240 的 SIP 主幹資訊：</span><span class="sxs-lookup"><span data-stu-id="02613-116">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>
    
        Get-CsTrunk -Identity "PstnGateway:192.168.0.240"

</div>

<div>

## <a name="viewing-information-for-all-the-sip-trunks-assigned-to-a-pool"></a><span data-ttu-id="02613-117">查看指派至集區之所有 SIP 主幹的資訊</span><span class="sxs-lookup"><span data-stu-id="02613-117">Viewing Information for All the SIP Trunks Assigned to a Pool</span></span>

  - <span data-ttu-id="02613-118">在此範例中，會傳回指派給集區 atl-cs-001.litwareinc.com 的所有 SIP 主幹的資訊：</span><span class="sxs-lookup"><span data-stu-id="02613-118">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>
    
        Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

