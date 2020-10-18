---
title: 管理集中式記錄服務設定設定
description: 管理集中式記錄服務的配置設定。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing the Centralized Logging Service configuration settings
ms:assetid: f455c3aa-0061-413d-bdfb-a3e78f82723d
ms:mtpsurl: https://technet.microsoft.com/library/JJ721938(v=OCS.15)
ms:contentKeyID: 49733875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e25294e096b8368aa06a11e4ad851fe5d1a84c0f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572599"
---
# <a name="managing-the-centralized-logging-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="17b41-103">在 Lync Server 2013 中管理集中式記錄服務設定設定</span><span class="sxs-lookup"><span data-stu-id="17b41-103">Managing the Centralized Logging Service configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17b41-104">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="17b41-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="17b41-105">集中式記錄服務是由集中式記錄服務控制器 (CLSController) 所建立及使用的設定和參數來控制及設定，將命令傳送至個別電腦的集中式記錄服務代理 (CLSAgent) 。</span><span class="sxs-lookup"><span data-stu-id="17b41-105">The Centralized Logging Service is controlled and configured by settings and parameters that are created and used by the Centralized Logging Service Controller (CLSController) to send commands to the individual computer’s Centralized Logging Service Agent (CLSAgent).</span></span> <span data-ttu-id="17b41-106">代理程式會處理傳送給它和 (的命令，) 使用案例的設定、提供者、記錄大小、追蹤持續時間及旗標開始根據所提供的設定資訊來收集追蹤記錄檔。</span><span class="sxs-lookup"><span data-stu-id="17b41-106">The agent processes the commands that are sent to it and (in the case of a Start command) uses the configuration of the scenarios, providers, log size, trace duration, and flags to begin collecting trace logs according to the configuration information provided.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="17b41-107">並未針對集中式記錄服務列出的所有 Windows PowerShell Cmdlet，都適用于 Lync Server 2013 內部部署。</span><span class="sxs-lookup"><span data-stu-id="17b41-107">Not all Windows PowerShell cmdlets listed for the Centralized Logging Service are intended for use with Lync Server 2013 on-premises deployments.</span></span> <span data-ttu-id="17b41-108">雖然似乎可以運作，但下列 Cmdlet 並非設計為在 Lync Server 2013 內部部署中運作：</span><span class="sxs-lookup"><span data-stu-id="17b41-108">Although they may appear to work, the following cmdlets are not designed to function with Lync Server 2013 on-premises deployments:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="17b41-109"><STRONG>CsClsRegion Cmdlet：</STRONG> <A href="https://technet.microsoft.com/library/JJ204879(v=OCS.15)">Get-CsClsRegion</A>、 <A href="https://technet.microsoft.com/library/JJ204746(v=OCS.15)">Set-CsClsRegion</A>、 <A href="https://technet.microsoft.com/library/JJ204658(v=OCS.15)">New-CsClsRegion</A>及 <A href="https://technet.microsoft.com/library/JJ204971(v=OCS.15)">Remove-CsClsRegion</A>。</span><span class="sxs-lookup"><span data-stu-id="17b41-109"><STRONG>CsClsRegion cmdlets:</STRONG> <A href="https://technet.microsoft.com/library/JJ204879(v=OCS.15)">Get-CsClsRegion</A>, <A href="https://technet.microsoft.com/library/JJ204746(v=OCS.15)">Set-CsClsRegion</A>, <A href="https://technet.microsoft.com/library/JJ204658(v=OCS.15)">New-CsClsRegion</A>, and <A href="https://technet.microsoft.com/library/JJ204971(v=OCS.15)">Remove-CsClsRegion</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="17b41-110"><STRONG>CsClsSearchTerm Cmdlet：</STRONG> <A href="https://technet.microsoft.com/library/JJ205061(v=OCS.15)">Get-CsClsSearchTerm</A> 和 <A href="https://technet.microsoft.com/library/JJ204911(v=OCS.15)">Set-CsClsSearchTerm</A>。</span><span class="sxs-lookup"><span data-stu-id="17b41-110"><STRONG>CsClsSearchTerm cmdlets:</STRONG> <A href="https://technet.microsoft.com/library/JJ205061(v=OCS.15)">Get-CsClsSearchTerm</A> and <A href="https://technet.microsoft.com/library/JJ204911(v=OCS.15)">Set-CsClsSearchTerm</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="17b41-111"><STRONG>CsClsSecurityGroup Cmdlet：</STRONG> <A href="https://technet.microsoft.com/library/JJ205285(v=OCS.15)">Get-CsClsSecurityGroup</A>、 <A href="https://technet.microsoft.com/library/JJ204700(v=OCS.15)">Set-CsClsSecurityGroup</A>、 <A href="https://technet.microsoft.com/library/JJ205359(v=OCS.15)">New-CsClsSecurityGroup</A>及 <A href="https://technet.microsoft.com/library/JJ204958(v=OCS.15)">Remove-CsClsSecurityGroup</A>。</span><span class="sxs-lookup"><span data-stu-id="17b41-111"><STRONG>CsClsSecurityGroup cmdlets:</STRONG> <A href="https://technet.microsoft.com/library/JJ205285(v=OCS.15)">Get-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/library/JJ204700(v=OCS.15)">Set-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/library/JJ205359(v=OCS.15)">New-CsClsSecurityGroup</A>, and <A href="https://technet.microsoft.com/library/JJ204958(v=OCS.15)">Remove-CsClsSecurityGroup</A>.</span></span></P></LI></UL><span data-ttu-id="17b41-112">在這些 Cmdlet 中定義的設定將不會妨礙或導致任何不良行為，但其設計目的是用於 Microsoft 365，而且不會在內部部署部署中產生預期的結果。</span><span class="sxs-lookup"><span data-stu-id="17b41-112">The settings defined in these cmdlets will not hinder or cause any adverse behavior, but they are designed for use with Microsoft 365 and will not yield the expected results in on-premises deployments.</span></span> <span data-ttu-id="17b41-113">這並不是說，在內部部署中不會使用這些 Cmdlet，但是其使用是本檔中未涵蓋的更高級主題。</span><span class="sxs-lookup"><span data-stu-id="17b41-113">This is not to say that there is no use for these cmdlets in on-premises deployments, but their use is a more advanced topic that is not covered in this documentation.</span></span>


</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="17b41-114">本章節內容</span><span class="sxs-lookup"><span data-stu-id="17b41-114">In This Section</span></span>

<span data-ttu-id="17b41-115">本節中的主題會定義集中式記錄服務的配置選項、參數和設定。</span><span class="sxs-lookup"><span data-stu-id="17b41-115">The topics in this section define the configuration options, parameters, and settings for the Centralized Logging Service.</span></span> <span data-ttu-id="17b41-116">下列主題中包含如何設定集中式記錄服務、如何取回設定設定、建立案例、安全性群組管理以進行集中式記錄服務、搜尋等相關資訊。</span><span class="sxs-lookup"><span data-stu-id="17b41-116">Information about how to configure the Centralized Logging Service, how to retrieve the configuration settings, creation of scenarios, management of security groups for Centralized Logging Service, searching, and more is contained in the following topics.</span></span>

  - [<span data-ttu-id="17b41-117">在 Lync Server 2013 中管理電腦、網站和全域集中式記錄服務設定</span><span class="sxs-lookup"><span data-stu-id="17b41-117">Managing computer, site and global Centralized Logging Service configuration in Lync Server 2013</span></span>](lync-server-2013-managing-computer-site-and-global-centralized-logging-service-configuration.md)

  - [<span data-ttu-id="17b41-118">在 Lync Server 2013 中設定集中式記錄服務的提供者</span><span class="sxs-lookup"><span data-stu-id="17b41-118">Configuring providers for Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-configuring-providers-for-centralized-logging-service.md)

  - [<span data-ttu-id="17b41-119">在 Lync Server 2013 中設定集中式記錄服務的案例</span><span class="sxs-lookup"><span data-stu-id="17b41-119">Configuring scenarios for the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-configuring-scenarios-for-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="17b41-120">另請參閱</span><span class="sxs-lookup"><span data-stu-id="17b41-120">See Also</span></span>


[<span data-ttu-id="17b41-121">Lync Server 2013 中的集中式記錄服務概述</span><span class="sxs-lookup"><span data-stu-id="17b41-121">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  
[<span data-ttu-id="17b41-122">Lync Server 2013 中的集中式記錄 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="17b41-122">Centralized Logging cmdlets in Lync Server 2013</span></span>](lync-server-2013-centralized-logging-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

