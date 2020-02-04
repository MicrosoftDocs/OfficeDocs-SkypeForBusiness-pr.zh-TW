---
title: 管理集中式記錄服務設定設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing the Centralized Logging Service configuration settings
ms:assetid: f455c3aa-0061-413d-bdfb-a3e78f82723d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721938(v=OCS.15)
ms:contentKeyID: 49733875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cb3b16210b3fac64c0c5bd7886849da7dd0d065
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733233"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-the-centralized-logging-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="c2cae-102">在 Lync Server 2013 中管理集中式記錄服務設定設定</span><span class="sxs-lookup"><span data-stu-id="c2cae-102">Managing the Centralized Logging Service configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2cae-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c2cae-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c2cae-104">集中式記錄服務由集中式記錄服務控制器（CLSController）所建立和使用的設定和參數加以控制和設定，以便將命令傳送到個別電腦的集中式記錄服務代理程式（CLSAgent).</span><span class="sxs-lookup"><span data-stu-id="c2cae-104">The Centralized Logging Service is controlled and configured by settings and parameters that are created and used by the Centralized Logging Service Controller (CLSController) to send commands to the individual computer’s Centralized Logging Service Agent (CLSAgent).</span></span> <span data-ttu-id="c2cae-105">Agent 會處理傳送給它的命令，以及（在 [開始] 命令中）使用案例、提供者、記錄大小、追蹤持續時間及旗標的設定，根據所提供的設定資訊來開始收集追蹤記錄。</span><span class="sxs-lookup"><span data-stu-id="c2cae-105">The agent processes the commands that are sent to it and (in the case of a Start command) uses the configuration of the scenarios, providers, log size, trace duration, and flags to begin collecting trace logs according to the configuration information provided.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="c2cae-106">並非所有針對集中式記錄服務列出的 Windows PowerShell Cmdlet 都要用於 Lync Server 2013 內部部署。</span><span class="sxs-lookup"><span data-stu-id="c2cae-106">Not all Windows PowerShell cmdlets listed for the Centralized Logging Service are intended for use with Lync Server 2013 on-premises deployments.</span></span> <span data-ttu-id="c2cae-107">雖然可能看起來很正常，但下列 Cmdlet 不是針對 Lync Server 2013 內部部署部署而設計的：</span><span class="sxs-lookup"><span data-stu-id="c2cae-107">Although they may appear to work, the following cmdlets are not designed to function with Lync Server 2013 on-premises deployments:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="c2cae-108"><STRONG>CsClsRegion Cmdlet：</STRONG> <A href="https://technet.microsoft.com/en-us/library/JJ204879(v=OCS.15)">CsClsRegion</A>、 <A href="https://technet.microsoft.com/en-us/library/JJ204746(v=OCS.15)">Set-CsClsRegion</A>、 <A href="https://technet.microsoft.com/en-us/library/JJ204658(v=OCS.15)">New-CsClsRegion</A>及<A href="https://technet.microsoft.com/en-us/library/JJ204971(v=OCS.15)">Remove-CsClsRegion</A>。</span><span class="sxs-lookup"><span data-stu-id="c2cae-108"><STRONG>CsClsRegion cmdlets:</STRONG> <A href="https://technet.microsoft.com/en-us/library/JJ204879(v=OCS.15)">Get-CsClsRegion</A>, <A href="https://technet.microsoft.com/en-us/library/JJ204746(v=OCS.15)">Set-CsClsRegion</A>, <A href="https://technet.microsoft.com/en-us/library/JJ204658(v=OCS.15)">New-CsClsRegion</A>, and <A href="https://technet.microsoft.com/en-us/library/JJ204971(v=OCS.15)">Remove-CsClsRegion</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="c2cae-109"><STRONG>CsClsSearchTerm Cmdlet：</STRONG> <A href="https://technet.microsoft.com/en-us/library/JJ205061(v=OCS.15)">CsClsSearchTerm</A>和<A href="https://technet.microsoft.com/en-us/library/JJ204911(v=OCS.15)">Set CsClsSearchTerm</A>。</span><span class="sxs-lookup"><span data-stu-id="c2cae-109"><STRONG>CsClsSearchTerm cmdlets:</STRONG> <A href="https://technet.microsoft.com/en-us/library/JJ205061(v=OCS.15)">Get-CsClsSearchTerm</A> and <A href="https://technet.microsoft.com/en-us/library/JJ204911(v=OCS.15)">Set-CsClsSearchTerm</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="c2cae-110"><STRONG>CsClsSecurityGroup Cmdlet：</STRONG> <A href="https://technet.microsoft.com/en-us/library/JJ205285(v=OCS.15)">CsClsSecurityGroup</A>、 <A href="https://technet.microsoft.com/en-us/library/JJ204700(v=OCS.15)">Set-CsClsSecurityGroup</A>、 <A href="https://technet.microsoft.com/en-us/library/JJ205359(v=OCS.15)">New-CsClsSecurityGroup</A>及<A href="https://technet.microsoft.com/en-us/library/JJ204958(v=OCS.15)">Remove-CsClsSecurityGroup</A>。</span><span class="sxs-lookup"><span data-stu-id="c2cae-110"><STRONG>CsClsSecurityGroup cmdlets:</STRONG> <A href="https://technet.microsoft.com/en-us/library/JJ205285(v=OCS.15)">Get-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/en-us/library/JJ204700(v=OCS.15)">Set-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/en-us/library/JJ205359(v=OCS.15)">New-CsClsSecurityGroup</A>, and <A href="https://technet.microsoft.com/en-us/library/JJ204958(v=OCS.15)">Remove-CsClsSecurityGroup</A>.</span></span></P></LI></UL><span data-ttu-id="c2cae-111">在這些 Cmdlet 中定義的設定將不會受到影響或導致任何不利的行為，但它們的設計目的是與 Microsoft Office 365 搭配使用，且不會在內部部署部署中產生預期的結果。</span><span class="sxs-lookup"><span data-stu-id="c2cae-111">The settings defined in these cmdlets will not hinder or cause any adverse behavior, but they are designed for use with Microsoft Office 365 and will not yield the expected results in on-premises deployments.</span></span> <span data-ttu-id="c2cae-112">這不表示這些 Cmdlet 在內部部署部署中無法使用，但其使用方式是本檔中未涵蓋的更高級主題。</span><span class="sxs-lookup"><span data-stu-id="c2cae-112">This is not to say that there is no use for these cmdlets in on-premises deployments, but their use is a more advanced topic that is not covered in this documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c2cae-113">本節內容</span><span class="sxs-lookup"><span data-stu-id="c2cae-113">In This Section</span></span>

<span data-ttu-id="c2cae-114">本節中的主題定義集中式記錄服務的配置選項、參數及設定。</span><span class="sxs-lookup"><span data-stu-id="c2cae-114">The topics in this section define the configuration options, parameters, and settings for the Centralized Logging Service.</span></span> <span data-ttu-id="c2cae-115">有關如何設定集中式記錄服務、如何取得配置設定、案例的建立、集中式記錄服務、搜尋及其他內容的相關資訊，請參閱下列主題。</span><span class="sxs-lookup"><span data-stu-id="c2cae-115">Information about how to configure the Centralized Logging Service, how to retrieve the configuration settings, creation of scenarios, management of security groups for Centralized Logging Service, searching, and more is contained in the following topics.</span></span>

  - [<span data-ttu-id="c2cae-116">在 Lync Server 2013 中管理電腦、網站和全域集中式記錄服務設定</span><span class="sxs-lookup"><span data-stu-id="c2cae-116">Managing computer, site and global Centralized Logging Service configuration in Lync Server 2013</span></span>](lync-server-2013-managing-computer-site-and-global-centralized-logging-service-configuration.md)

  - [<span data-ttu-id="c2cae-117">在 Lync Server 2013 中組態集中式記錄服務的提供者</span><span class="sxs-lookup"><span data-stu-id="c2cae-117">Configuring providers for Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-configuring-providers-for-centralized-logging-service.md)

  - [<span data-ttu-id="c2cae-118">在 Lync Server 2013 中組態集中式記錄服務的案例</span><span class="sxs-lookup"><span data-stu-id="c2cae-118">Configuring scenarios for the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-configuring-scenarios-for-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c2cae-119">請參閱</span><span class="sxs-lookup"><span data-stu-id="c2cae-119">See Also</span></span>


[<span data-ttu-id="c2cae-120">Lync Server 2013 中的集中式記錄服務概覽</span><span class="sxs-lookup"><span data-stu-id="c2cae-120">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  
[<span data-ttu-id="c2cae-121">Lync Server 2013 中的集中式記錄 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="c2cae-121">Centralized Logging cmdlets in Lync Server 2013</span></span>](lync-server-2013-centralized-logging-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

