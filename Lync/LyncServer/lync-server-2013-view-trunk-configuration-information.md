---
title: Lync Server 2013： 檢視主幹組態資訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View trunk configuration information
ms:assetid: ebe10e14-08c2-4797-9254-9ed89516d5cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721927(v=OCS.15)
ms:contentKeyID: 49733862
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b1e232cda56258a530f1cd0f5a0106d9b7725ca
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136631"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-trunk-configuration-information-in-lync-server-2013"></a><span data-ttu-id="b2261-102">Lync Server 2013 中檢視主幹組態資訊</span><span class="sxs-lookup"><span data-stu-id="b2261-102">View trunk configuration information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2261-103">_**上次修改主題：** 2013年-02-22_</span><span class="sxs-lookup"><span data-stu-id="b2261-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="b2261-p101">SIP 主幹組態設定用於定義中繼伺服器與服務提供者的公用交換電話網路 (PSTN) 閘道、IP 公用交換機 (PBX) 或工作階段邊界控制器 (SBC) 之間的關係和功能。這些設定將指定下列項目：</span><span class="sxs-lookup"><span data-stu-id="b2261-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

  - <span data-ttu-id="b2261-106">主幹是否啟用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="b2261-106">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="b2261-107">傳送即時傳輸控制通訊協定 (RTCP) 封包的情況。</span><span class="sxs-lookup"><span data-stu-id="b2261-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="b2261-108">每個主幹是否需要安全即時通訊協定 (SRTP) 加密。</span><span class="sxs-lookup"><span data-stu-id="b2261-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="b2261-109">當您安裝 Microsoft Lync Server 2013 時，為您建立的 SIP 主幹組態設定全域集合。</span><span class="sxs-lookup"><span data-stu-id="b2261-109">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="b2261-110">此外，系統管理員可以在網站範圍或服務範圍 (僅限 PSTN 閘道服務) 建立自訂設定集合。</span><span class="sxs-lookup"><span data-stu-id="b2261-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span>

<div>

## <a name="to-view-sip-trunk-configuration-information-by-using-lync-server-control-panel"></a><span data-ttu-id="b2261-111">若要使用 Lync Server 控制台檢視 SIP 主幹組態資訊</span><span class="sxs-lookup"><span data-stu-id="b2261-111">To view SIP trunk configuration information by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="b2261-112">在 Lync Server 控制台]，按一下 [**語音路由**，然後按一下 [**主幹組態**。</span><span class="sxs-lookup"><span data-stu-id="b2261-112">In Lync Server Control Panel, click **Voice Routing** and then click **Trunk Configuration**.</span></span>

2.  <span data-ttu-id="b2261-113">在 [**主幹組態**] 索引標籤上，您會看到所有您主幹組態設定集合; 的清單針對每個集合中，您會看到的**名稱**、**範圍**、**狀態**和**媒體旁路**的屬性，以及數目**的 PSTN 使用方式**、**呼叫號碼規則**，以及**呼叫號碼規則**集合相關聯的值。</span><span class="sxs-lookup"><span data-stu-id="b2261-113">On the **Trunk Configuration** tab you will see a list of all your trunk configuration settings collection; for each collection you will see values for the **Name**, **Scope**, **State**, and **Media bypass** properties, along with the number of **PSTN usages**, **Calling number rules**, and **Called number rules** associated with the collection.</span></span> <span data-ttu-id="b2261-114">若要查看的主幹組態設定集合的其他詳細資料，按一下 [感興趣的集合，按一下 [**編輯**]，然後按一下**顯示詳細資料**。</span><span class="sxs-lookup"><span data-stu-id="b2261-114">To see additional details about a collection of trunk configuration settings, click the collection of interest, click **Edit**, and then click **Show details**.</span></span> <span data-ttu-id="b2261-115">請注意，您可以檢視僅適用於一次的主幹組態設定集合的詳細的資訊。</span><span class="sxs-lookup"><span data-stu-id="b2261-115">Note that you can view detailed information only for one collection of trunk configuration settings at a time.</span></span>

</div>

<div>

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b2261-116">使用 Windows PowerShell Cmdlet 檢視 SIP 主幹組態資訊</span><span class="sxs-lookup"><span data-stu-id="b2261-116">Viewing SIP Trunk Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b2261-117">SIP 主幹組態設定可檢視使用 Lync Server PowerShell 和 Get-cstrunkconfiguration cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b2261-117">SIP trunk configuration settings can be viewed by using Lync Server PowerShell and the Get-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="b2261-118">從 Lync Server 2013 管理命令介面或 Windows PowerShell 的遠端工作階段，可以執行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b2261-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="b2261-119">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 部落格文章 「 快速開始:: 管理 Microsoft Lync Server 2010 使用遠端 PowerShell 」 在[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="b2261-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-sip-trunk-configuration-information"></a><span data-ttu-id="b2261-120">若要檢視 SIP 主幹組態資訊</span><span class="sxs-lookup"><span data-stu-id="b2261-120">To view SIP trunk configuration information</span></span>

  - <span data-ttu-id="b2261-121">若要檢視所有 SIP 主幹組態設定的相關資訊，請在 Lync Server 管理命令介面中輸入下列命令並按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="b2261-121">To view information about all your SIP trunk configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsTrunkConfiguration
    
    <span data-ttu-id="b2261-122">如此將傳回類似如下的資訊：</span><span class="sxs-lookup"><span data-stu-id="b2261-122">That will return information similar to this:</span></span>
    
        Identity                                  : Global
        OutboundTranslationRulesList              : {}
        SipResponseCodeTranslationRulesList       : {}
        OutboundCallingNumberTranslationRulesList : {}
        PstnUsages                                : {}
        Description                               :
        ConcentratedTopology                      : True
        EnableBypass                              : False
        EnableMobileTrunkSupport                  : False
        EnableReferSupport                        : True
        EnableSessionTimer                        : False
        EnableSignalBoost                         : False
        MaxEarlyDialogs                           : 20
        RemovePlusFromUri                         : False
        RTCPActiveCalls                           : True
        RTCPCallsOnHold                           : True
        SRTPMode                                  : Required
        EnablePIDFLOSupport                       : False
        EnableRTPLatching                         : False
        EnableOnlineVoice                         : False
        ForwardCallHistory                        : False
        Enable3pccRefer                           : False
        ForwardPAI                                : False
        EnableFastFailoverTimer                   : True

</div>

<span data-ttu-id="b2261-123">如需詳細資訊，請參閱[Get-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration) cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="b2261-123">For more information, see the help topic for the [Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

