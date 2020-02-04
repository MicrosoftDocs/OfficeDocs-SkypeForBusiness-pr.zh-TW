---
title: Lync Server 2013：查看個別 SIP trunks 的相關資訊
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
ms.openlocfilehash: f18b65d119b917d5ba48ef3e6805e4f70ea482ee
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765644"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-information-about-individual-sip-trunks-in-lync-server-2013"></a><span data-ttu-id="d9a16-102">在 Lync Server 2013 中查看個別 SIP trunks 的相關資訊</span><span class="sxs-lookup"><span data-stu-id="d9a16-102">View information about individual SIP trunks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9a16-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="d9a16-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="d9a16-104">SIP trunks 是用來連接 Lync Server 2013 與公用交換電話網絡的語音 over IP 電話網絡。</span><span class="sxs-lookup"><span data-stu-id="d9a16-104">SIP trunks are used to connect Lync Server 2013 Voice over IP phone network with the Public Switched Telephone Network.</span></span> <span data-ttu-id="d9a16-105">在早期版本的產品中，trunks 是用來將撥出電話從中繼伺服器傳送到 PSTN 閘道，而每個閘道都限制在單一干線中。</span><span class="sxs-lookup"><span data-stu-id="d9a16-105">In previous version of the product, trunks were used to route outbound calls from a Mediation Server to a PSTN gateway and each gateway was limited to a single trunk.</span></span> <span data-ttu-id="d9a16-106">因此，PSTN 閘道與 SIP 幹線本質上完全相同。</span><span class="sxs-lookup"><span data-stu-id="d9a16-106">As a result, a PSTN gateway and a SIP trunk were essentially identical.</span></span> <span data-ttu-id="d9a16-107">針對管理員而言，這表示只要查看關聯 PSTN 閘道的相關資訊，就能查看個別 SIP 主幹的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="d9a16-107">For administrators, that meant they could view information about an individual SIP trunk simply by viewing information about the associated PSTN gateway.</span></span>

<span data-ttu-id="d9a16-108">但在 Lync Server 2013 中，現在可以將多個 trunks 指派給單一 PSTN 閘道;這表示閘道與 trunks 已不再是相同的。</span><span class="sxs-lookup"><span data-stu-id="d9a16-108">In Lync Server 2013, however, multiple trunks can now be assigned to a single PSTN gateway; this means that gateways and trunks are no longer one and the same.</span></span> <span data-ttu-id="d9a16-109">因此，這表示系統管理員必須使用新的[CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) Cmdlet，才能查看個別 SIP 幹線的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="d9a16-109">In turn, that means that administrators must use the new [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) cmdlet in order to view information about an individual SIP trunk.</span></span>

<span data-ttu-id="d9a16-110">CsTrunk Cmdlet 可以從 Lync Server 2013 管理命令介面或 Windows PowerShell 的遠端會話執行。</span><span class="sxs-lookup"><span data-stu-id="d9a16-110">The Get-CsTrunk cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d9a16-111">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="d9a16-111">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-information-for-all-your-sip-trunks"></a><span data-ttu-id="d9a16-112">若要查看所有 SIP trunks 的相關資訊</span><span class="sxs-lookup"><span data-stu-id="d9a16-112">To view information for all your SIP trunks</span></span>

  - <span data-ttu-id="d9a16-113">下列命令會傳回貴組織中使用的所有 SIP trunks 資訊：</span><span class="sxs-lookup"><span data-stu-id="d9a16-113">The following command returns information about all the SIP trunks in use in your organization:</span></span>
    
        Get-CsTrunk

</div>

<div>

## <a name="to-view-information-for-a-specific-sip-trunk"></a><span data-ttu-id="d9a16-114">若要查看特定 SIP 主幹的資訊</span><span class="sxs-lookup"><span data-stu-id="d9a16-114">To view information for a specific SIP trunk</span></span>

  - <span data-ttu-id="d9a16-115">這個命令只會傳回具有身分識別 PstnGateway 的 SIP 幹線資訊：192.168.0.240：</span><span class="sxs-lookup"><span data-stu-id="d9a16-115">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>
    
        Get-CsTrunk -Identity "PstnGateway:192.168.0.240"

</div>

<div>

## <a name="viewing-information-for-all-the-sip-trunks-assigned-to-a-pool"></a><span data-ttu-id="d9a16-116">查看指派給某個池之所有 SIP Trunks 的相關資訊</span><span class="sxs-lookup"><span data-stu-id="d9a16-116">Viewing Information for All the SIP Trunks Assigned to a Pool</span></span>

  - <span data-ttu-id="d9a16-117">在這個範例中，會針對指派給 pool atl-cs-001.litwareinc.com 的所有 SIP trunks 傳回信息：</span><span class="sxs-lookup"><span data-stu-id="d9a16-117">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>
    
        Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

