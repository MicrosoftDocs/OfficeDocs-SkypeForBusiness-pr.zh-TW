---
title: Lync Server 2013：查看主幹設定資訊
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
ms.openlocfilehash: fe7c828fe771a410825fd641c333a2230d7e9798
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518370"
---
# <a name="view-trunk-configuration-information-in-lync-server-2013"></a><span data-ttu-id="a7a08-102">在 Lync Server 2013 中查看主幹設定資訊</span><span class="sxs-lookup"><span data-stu-id="a7a08-102">View trunk configuration information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7a08-103">_**主題上次修改日期：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="a7a08-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="a7a08-p101">SIP 主幹組態設定用於定義中繼伺服器與服務提供者的公用交換電話網路 (PSTN) 閘道、IP 公用交換機 (PBX) 或工作階段邊界控制器 (SBC) 之間的關係和功能。這些設定將指定下列項目：</span><span class="sxs-lookup"><span data-stu-id="a7a08-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

  - <span data-ttu-id="a7a08-106">主幹是否啟用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="a7a08-106">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="a7a08-107">傳送即時傳輸控制通訊協定 (RTCP) 封包的情況。</span><span class="sxs-lookup"><span data-stu-id="a7a08-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="a7a08-108">每個主幹是否需要安全即時通訊協定 (SRTP) 加密。</span><span class="sxs-lookup"><span data-stu-id="a7a08-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="a7a08-109">當您安裝 Microsoft Lync Server 2013 時，系統會為您建立一個全域 SIP 主幹設定的集合。</span><span class="sxs-lookup"><span data-stu-id="a7a08-109">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="a7a08-110">此外，系統管理員可以在網站範圍或服務範圍 (僅限 PSTN 閘道服務) 建立自訂設定集合。</span><span class="sxs-lookup"><span data-stu-id="a7a08-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span>

<div>

## <a name="to-view-sip-trunk-configuration-information-by-using-lync-server-control-panel"></a><span data-ttu-id="a7a08-111">使用 Lync Server 控制台查看 SIP 主幹設定資訊</span><span class="sxs-lookup"><span data-stu-id="a7a08-111">To view SIP trunk configuration information by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="a7a08-112">在 [Lync Server 控制台] 中，按一下 [ **語音路由** ]，然後按一下 [ **主幹**設定]。</span><span class="sxs-lookup"><span data-stu-id="a7a08-112">In Lync Server Control Panel, click **Voice Routing** and then click **Trunk Configuration**.</span></span>

2.  <span data-ttu-id="a7a08-113">在 [ **主幹** 設定] 索引標籤上，您將會看到所有主幹設定的集合，也就是針對每個集合，您會看到 **名稱**、 **範圍**、 **狀態**及 **媒體旁路** 屬性的值，以及 **PSTN 使用**的數目、 **呼叫號碼規則**，以及與集合關聯的 **呼叫編號規則** 。</span><span class="sxs-lookup"><span data-stu-id="a7a08-113">On the **Trunk Configuration** tab you will see a list of all your trunk configuration settings collection; for each collection you will see values for the **Name**, **Scope**, **State**, and **Media bypass** properties, along with the number of **PSTN usages**, **Calling number rules**, and **Called number rules** associated with the collection.</span></span> <span data-ttu-id="a7a08-114">若要查看主幹設定設定集合的其他詳細資料，請按一下相關集合，按一下 [ **編輯**]，然後按一下 [ **顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="a7a08-114">To see additional details about a collection of trunk configuration settings, click the collection of interest, click **Edit**, and then click **Show details**.</span></span> <span data-ttu-id="a7a08-115">請注意，您一次只能查看一個主幹設定設定集合的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="a7a08-115">Note that you can view detailed information only for one collection of trunk configuration settings at a time.</span></span>

</div>

<div>

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a7a08-116">使用 Windows PowerShell Cmdlet 來查看 SIP 主幹設定資訊</span><span class="sxs-lookup"><span data-stu-id="a7a08-116">Viewing SIP Trunk Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="a7a08-117">您可以使用 Lync Server PowerShell 和 Get-CsTrunkConfiguration Cmdlet 來查看 SIP 主幹設定設定。</span><span class="sxs-lookup"><span data-stu-id="a7a08-117">SIP trunk configuration settings can be viewed by using Lync Server PowerShell and the Get-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="a7a08-118">您可以從 Lync Server 2013 管理命令介面或從遠端會話 Windows PowerShell 執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a7a08-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="a7a08-119">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="a7a08-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-sip-trunk-configuration-information"></a><span data-ttu-id="a7a08-120">若要查看 SIP 主幹設定資訊</span><span class="sxs-lookup"><span data-stu-id="a7a08-120">To view SIP trunk configuration information</span></span>

  - <span data-ttu-id="a7a08-121">若要查看所有 SIP 主幹設定設定的相關資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：</span><span class="sxs-lookup"><span data-stu-id="a7a08-121">To view information about all your SIP trunk configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsTrunkConfiguration
    
    <span data-ttu-id="a7a08-122">如此將傳回類似如下的資訊：</span><span class="sxs-lookup"><span data-stu-id="a7a08-122">That will return information similar to this:</span></span>
    
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

<span data-ttu-id="a7a08-123">如需詳細資訊，請參閱 [Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="a7a08-123">For more information, see the help topic for the [Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

