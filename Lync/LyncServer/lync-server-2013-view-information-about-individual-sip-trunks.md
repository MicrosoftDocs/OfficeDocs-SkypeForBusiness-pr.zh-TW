---
title: Lync Server 2013： 檢視個別 SIP 主幹的資訊
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
ms.openlocfilehash: 3163bb6298bef570a68f2fcfd7dec66167549b21
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029724"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-information-about-individual-sip-trunks-in-lync-server-2013"></a><span data-ttu-id="f2483-102">檢視 Lync Server 2013 中的個別 SIP 主幹的相關資訊</span><span class="sxs-lookup"><span data-stu-id="f2483-102">View information about individual SIP trunks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2483-103">_**上次修改主題：** 2013年-02-21_</span><span class="sxs-lookup"><span data-stu-id="f2483-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="f2483-104">SIP 主幹用來連線 Lync Server 2013 Voice over IP 電話網路與公用交換電話網路。</span><span class="sxs-lookup"><span data-stu-id="f2483-104">SIP trunks are used to connect Lync Server 2013 Voice over IP phone network with the Public Switched Telephone Network.</span></span> <span data-ttu-id="f2483-105">在前一個版本的產品，主幹所用來路由傳送從中繼伺服器到 PSTN 閘道的撥出通話和每個閘道限制為單一主幹。</span><span class="sxs-lookup"><span data-stu-id="f2483-105">In previous version of the product, trunks were used to route outbound calls from a Mediation Server to a PSTN gateway and each gateway was limited to a single trunk.</span></span> <span data-ttu-id="f2483-106">因此，在 PSTN 閘道與 SIP 主幹所基本上是相同。</span><span class="sxs-lookup"><span data-stu-id="f2483-106">As a result, a PSTN gateway and a SIP trunk were essentially identical.</span></span> <span data-ttu-id="f2483-107">系統管理員，這意謂著他們可以檢視個別 SIP 主幹的資訊只是檢視關聯的 PSTN 閘道的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="f2483-107">For administrators, that meant they could view information about an individual SIP trunk simply by viewing information about the associated PSTN gateway.</span></span>

<span data-ttu-id="f2483-108">在 Lync Server 2013 中，不過，多個主幹可以現在是已指派給單一的 PSTN 閘道;這表示閘道和主幹不再是同一個。</span><span class="sxs-lookup"><span data-stu-id="f2483-108">In Lync Server 2013, however, multiple trunks can now be assigned to a single PSTN gateway; this means that gateways and trunks are no longer one and the same.</span></span> <span data-ttu-id="f2483-109">接著，這表示系統管理員必須使用新的[Get-cstrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) cmdlet 以檢視個別 SIP 主幹的資訊。</span><span class="sxs-lookup"><span data-stu-id="f2483-109">In turn, that means that administrators must use the new [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) cmdlet in order to view information about an individual SIP trunk.</span></span>

<span data-ttu-id="f2483-110">可以執行 Get-cstrunk cmdlet，從 Lync Server 2013 管理命令介面或 Windows PowerShell 的遠端工作階段。</span><span class="sxs-lookup"><span data-stu-id="f2483-110">The Get-CsTrunk cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f2483-111">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 部落格文章 「 快速開始:: 管理 Microsoft Lync Server 2010 使用遠端 PowerShell 」 在[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="f2483-111">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-information-for-all-your-sip-trunks"></a><span data-ttu-id="f2483-112">若要檢視所有 SIP 主幹的資訊</span><span class="sxs-lookup"><span data-stu-id="f2483-112">To view information for all your SIP trunks</span></span>

  - <span data-ttu-id="f2483-113">下列命令會傳回用於組織中所有 SIP 主幹的資訊：</span><span class="sxs-lookup"><span data-stu-id="f2483-113">The following command returns information about all the SIP trunks in use in your organization:</span></span>
    
        Get-CsTrunk

</div>

<div>

## <a name="to-view-information-for-a-specific-sip-trunk"></a><span data-ttu-id="f2483-114">若要檢視特定 SIP 主幹的資訊</span><span class="sxs-lookup"><span data-stu-id="f2483-114">To view information for a specific SIP trunk</span></span>

  - <span data-ttu-id="f2483-115">此命令會傳回 192.168.0.240 身分識別的 SIP 主幹的資訊：</span><span class="sxs-lookup"><span data-stu-id="f2483-115">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>
    
        Get-CsTrunk -Identity "PstnGateway:192.168.0.240"

</div>

<div>

## <a name="viewing-information-for-all-the-sip-trunks-assigned-to-a-pool"></a><span data-ttu-id="f2483-116">檢視指派給集區的所有 SIP 主幹的資訊</span><span class="sxs-lookup"><span data-stu-id="f2483-116">Viewing Information for All the SIP Trunks Assigned to a Pool</span></span>

  - <span data-ttu-id="f2483-117">在這個範例中，傳回指派給 atl-cs-001.litwareinc.com 集區的所有 SIP 主幹資訊-atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="f2483-117">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>
    
        Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

