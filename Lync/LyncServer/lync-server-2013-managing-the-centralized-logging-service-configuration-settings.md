---
title: 管理的集中式記錄服務組態設定
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
ms.openlocfilehash: 3b89923932b06e07ed01049895e34c960938cc88
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150013"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-the-centralized-logging-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="6915d-102">管理 Lync Server 2013 中的集中式記錄服務組態設定</span><span class="sxs-lookup"><span data-stu-id="6915d-102">Managing the Centralized Logging Service configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6915d-103">_**主題上次修改日期：** 2012年-11-01_</span><span class="sxs-lookup"><span data-stu-id="6915d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="6915d-104">The Centralized Logging Service 控制，且設定來設定和參數，是由建立及使用集中式記錄服務控制站 (CLSController) 傳送命令到個別電腦的集中式記錄服務代理程式 （Clsagent 的通訊）。</span><span class="sxs-lookup"><span data-stu-id="6915d-104">The Centralized Logging Service is controlled and configured by settings and parameters that are created and used by the Centralized Logging Service Controller (CLSController) to send commands to the individual computer’s Centralized Logging Service Agent (CLSAgent).</span></span> <span data-ttu-id="6915d-105">代理程式所處理的命令，傳送給它，並 （若是啟動命令） 使用的案例，提供者、 記錄檔的大小、 追蹤持續時間和旗標設定來開始收集根據所提供的組態資訊的追蹤記錄檔。</span><span class="sxs-lookup"><span data-stu-id="6915d-105">The agent processes the commands that are sent to it and (in the case of a Start command) uses the configuration of the scenarios, providers, log size, trace duration, and flags to begin collecting trace logs according to the configuration information provided.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="6915d-106">並非所有列出 the Centralized Logging Service 的 Windows PowerShell cmdlet 是針對 Lync Server 2013 內部部署搭配使用。</span><span class="sxs-lookup"><span data-stu-id="6915d-106">Not all Windows PowerShell cmdlets listed for the Centralized Logging Service are intended for use with Lync Server 2013 on-premises deployments.</span></span> <span data-ttu-id="6915d-107">雖然他們可能會出現運作，下列指令程式會並非設計用來與 Lync Server 2013 內部部署的運作：</span><span class="sxs-lookup"><span data-stu-id="6915d-107">Although they may appear to work, the following cmdlets are not designed to function with Lync Server 2013 on-premises deployments:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="6915d-108"><STRONG>CsClsRegion cmdlet:</STRONG> <A href="https://technet.microsoft.com/library/JJ204879(v=OCS.15)">Get-csclsregion</A>、 <A href="https://technet.microsoft.com/library/JJ204746(v=OCS.15)">Set-csclsregion</A>、 <A href="https://technet.microsoft.com/library/JJ204658(v=OCS.15)">New-csclsregion</A>及<A href="https://technet.microsoft.com/library/JJ204971(v=OCS.15)">Remove-csclsregion</A>。</span><span class="sxs-lookup"><span data-stu-id="6915d-108"><STRONG>CsClsRegion cmdlets:</STRONG> <A href="https://technet.microsoft.com/library/JJ204879(v=OCS.15)">Get-CsClsRegion</A>, <A href="https://technet.microsoft.com/library/JJ204746(v=OCS.15)">Set-CsClsRegion</A>, <A href="https://technet.microsoft.com/library/JJ204658(v=OCS.15)">New-CsClsRegion</A>, and <A href="https://technet.microsoft.com/library/JJ204971(v=OCS.15)">Remove-CsClsRegion</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="6915d-109"><STRONG>CsClsSearchTerm cmdlet:</STRONG> <A href="https://technet.microsoft.com/library/JJ205061(v=OCS.15)">Get-csclssearchterm</A>與<A href="https://technet.microsoft.com/library/JJ204911(v=OCS.15)">Set-csclssearchterm</A>。</span><span class="sxs-lookup"><span data-stu-id="6915d-109"><STRONG>CsClsSearchTerm cmdlets:</STRONG> <A href="https://technet.microsoft.com/library/JJ205061(v=OCS.15)">Get-CsClsSearchTerm</A> and <A href="https://technet.microsoft.com/library/JJ204911(v=OCS.15)">Set-CsClsSearchTerm</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="6915d-110"><STRONG>CsClsSecurityGroup cmdlet:</STRONG> <A href="https://technet.microsoft.com/library/JJ205285(v=OCS.15)">Get-csclssecuritygroup</A>、 <A href="https://technet.microsoft.com/library/JJ204700(v=OCS.15)">Set-csclssecuritygroup</A>、 <A href="https://technet.microsoft.com/library/JJ205359(v=OCS.15)">New-csclssecuritygroup</A>及<A href="https://technet.microsoft.com/library/JJ204958(v=OCS.15)">Remove-csclssecuritygroup</A>。</span><span class="sxs-lookup"><span data-stu-id="6915d-110"><STRONG>CsClsSecurityGroup cmdlets:</STRONG> <A href="https://technet.microsoft.com/library/JJ205285(v=OCS.15)">Get-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/library/JJ204700(v=OCS.15)">Set-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/library/JJ205359(v=OCS.15)">New-CsClsSecurityGroup</A>, and <A href="https://technet.microsoft.com/library/JJ204958(v=OCS.15)">Remove-CsClsSecurityGroup</A>.</span></span></P></LI></UL><span data-ttu-id="6915d-111">這些 cmdlet 中所定義的設定將不會妨礙或造成任何負面的行為，但專為與 Microsoft Office 365 搭配使用，且不會產生預期的結果，在內部部署中。</span><span class="sxs-lookup"><span data-stu-id="6915d-111">The settings defined in these cmdlets will not hinder or cause any adverse behavior, but they are designed for use with Microsoft Office 365 and will not yield the expected results in on-premises deployments.</span></span> <span data-ttu-id="6915d-112">這並不是說未使用這些指令程式在內部部署中，但其使用是更進階的主題，未涵蓋此文件中。</span><span class="sxs-lookup"><span data-stu-id="6915d-112">This is not to say that there is no use for these cmdlets in on-premises deployments, but their use is a more advanced topic that is not covered in this documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6915d-113">本章節內容</span><span class="sxs-lookup"><span data-stu-id="6915d-113">In This Section</span></span>

<span data-ttu-id="6915d-114">本節中的主題定義組態選項、 參數及 the Centralized Logging Service 的設定。</span><span class="sxs-lookup"><span data-stu-id="6915d-114">The topics in this section define the configuration options, parameters, and settings for the Centralized Logging Service.</span></span> <span data-ttu-id="6915d-115">有關如何設定 the Centralized Logging Service，資訊來擷取組態設定、 建立案例、 管理安全性群組的集中式記錄服務，請搜尋，以及多個包含下列主題。</span><span class="sxs-lookup"><span data-stu-id="6915d-115">Information about how to configure the Centralized Logging Service, how to retrieve the configuration settings, creation of scenarios, management of security groups for Centralized Logging Service, searching, and more is contained in the following topics.</span></span>

  - [<span data-ttu-id="6915d-116">管理電腦、 網站及 Lync Server 2013 中全域的集中式記錄服務組態</span><span class="sxs-lookup"><span data-stu-id="6915d-116">Managing computer, site and global Centralized Logging Service configuration in Lync Server 2013</span></span>](lync-server-2013-managing-computer-site-and-global-centralized-logging-service-configuration.md)

  - [<span data-ttu-id="6915d-117">在 Lync Server 2013 中設定集中式記錄服務提供的者</span><span class="sxs-lookup"><span data-stu-id="6915d-117">Configuring providers for Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-configuring-providers-for-centralized-logging-service.md)

  - [<span data-ttu-id="6915d-118">集中式記錄服務的 Lync Server 2013 中設定案例</span><span class="sxs-lookup"><span data-stu-id="6915d-118">Configuring scenarios for the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-configuring-scenarios-for-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6915d-119">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6915d-119">See Also</span></span>


[<span data-ttu-id="6915d-120">Lync Server 2013 中的集中式的記錄服務概觀</span><span class="sxs-lookup"><span data-stu-id="6915d-120">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  
[<span data-ttu-id="6915d-121">Lync Server 2013 中的集中式的記錄 cmdlet</span><span class="sxs-lookup"><span data-stu-id="6915d-121">Centralized Logging cmdlets in Lync Server 2013</span></span>](lync-server-2013-centralized-logging-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

