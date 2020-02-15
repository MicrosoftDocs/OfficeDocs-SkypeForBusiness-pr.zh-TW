---
title: Lync Server 2013 Active Directory 支援
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory support
ms:assetid: 28ed9ac4-586d-4803-ad45-99c4fa793f54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425756(v=OCS.15)
ms:contentKeyID: 48183679
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b3ded5de5500778559efe632c5272db50b0eadbd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034113"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-support-in-lync-server-2013"></a><span data-ttu-id="87276-102">Lync Server 2013 中的 active Directory 支援</span><span class="sxs-lookup"><span data-stu-id="87276-102">Active Directory support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87276-103">_**主題上次修改日期：** 2012年-12-04_</span><span class="sxs-lookup"><span data-stu-id="87276-103">_**Topic Last Modified:** 2012-12-04_</span></span>

<span data-ttu-id="87276-104">Lync Server 2013 所支援的 Active Directory 網域服務的內部拓撲如下所示：</span><span class="sxs-lookup"><span data-stu-id="87276-104">The Active Directory Domain Services on-premises topologies that are supported by Lync Server 2013 are as follows:</span></span>

  - <span data-ttu-id="87276-105">具單一網域的單一樹系</span><span class="sxs-lookup"><span data-stu-id="87276-105">Single forest with single domain</span></span>

  - <span data-ttu-id="87276-106">具單一樹狀結構和多個網域的單一樹系</span><span class="sxs-lookup"><span data-stu-id="87276-106">Single forest with a single tree and multiple domains</span></span>

  - <span data-ttu-id="87276-107">具多重樹狀結構和斷續命名空間的單一樹系</span><span class="sxs-lookup"><span data-stu-id="87276-107">Single forest with multiple trees and disjoint namespaces</span></span>

  - <span data-ttu-id="87276-108">中央樹系拓撲中的多重樹系</span><span class="sxs-lookup"><span data-stu-id="87276-108">Multiple forests in a central forest topology</span></span>

  - <span data-ttu-id="87276-109">資源樹系拓撲中的多重樹系</span><span class="sxs-lookup"><span data-stu-id="87276-109">Multiple forests in a resource forest topology</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="87276-110">Lync Server 2013 不支援單一標籤網域。</span><span class="sxs-lookup"><span data-stu-id="87276-110">Lync Server 2013 does not support single-label domains.</span></span> <span data-ttu-id="87276-111">例如，名為<STRONG>contoso.local</STRONG>根網域與樹系支援，但是不支援名為<STRONG>本機</STRONG>的單一標籤根網域。</span><span class="sxs-lookup"><span data-stu-id="87276-111">For example, a forest with a root domain named <STRONG>contoso.local</STRONG> is supported, but a single-label root domain named <STRONG>local</STRONG> is not supported.</span></span> <span data-ttu-id="87276-112">如需詳細資訊，請參閱 Microsoft 知識庫文章 300684，「 設定資訊視窗具有單一標籤 DNS 名稱的網域 」， <A href="http://go.microsoft.com/fwlink/p/?linkid=143752">http://go.microsoft.com/fwlink/p/?linkId=143752</A>。</span><span class="sxs-lookup"><span data-stu-id="87276-112">For details, see Microsoft Knowledge Base article 300684, "Information about configuring Windows for domains with single-label DNS names," at <A href="http://go.microsoft.com/fwlink/p/?linkid=143752">http://go.microsoft.com/fwlink/p/?linkId=143752</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="87276-113">Lync Server 2013 不支援重新命名的網域。</span><span class="sxs-lookup"><span data-stu-id="87276-113">Lync Server 2013 does not support renaming domains.</span></span> <span data-ttu-id="87276-114">如果您需要重新命名其中部署 Lync Server 的網域，您需要先解除安裝 Lync Server]，然後重新命名網域，並再重新安裝 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="87276-114">If you need to rename a domain where Lync Server is deployed, you need to first uninstall Lync Server, then rename the domain, and then reinstall Lync Server.</span></span>



</div>

<span data-ttu-id="87276-115">如需支援的拓撲與內部部署的需求的詳細資訊，請參閱規劃文件中的[Active Directory 網域服務需求、 支援和 Lync Server 2013 中的拓撲](lync-server-2013-active-directory-domain-services-requirements-support-and-topologies.md)。</span><span class="sxs-lookup"><span data-stu-id="87276-115">For details about supported topologies and requirements for on-premises deployments, see [Active Directory Domain Services requirements, support, and topologies in Lync Server 2013](lync-server-2013-active-directory-domain-services-requirements-support-and-topologies.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

