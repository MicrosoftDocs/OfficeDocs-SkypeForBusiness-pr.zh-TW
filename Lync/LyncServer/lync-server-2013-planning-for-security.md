---
title: Lync Server 2013：安全性規劃
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for security
ms:assetid: 17eeba87-cafa-4e9b-852d-c017a7d10d59
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn342827(v=OCS.15)
ms:contentKeyID: 56107267
ms.date: 06/22/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02028b3ed63fe8f5cd40fd118bd36c73af9d15cd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725203"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-security-in-lync-server-2013"></a><span data-ttu-id="c6659-102">Lync Server 2013 中的安全性規劃</span><span class="sxs-lookup"><span data-stu-id="c6659-102">Planning for security in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6659-103">_**主題上次修改日期：** 2016-06-22_</span><span class="sxs-lookup"><span data-stu-id="c6659-103">_**Topic Last Modified:** 2016-06-22_</span></span>

<span data-ttu-id="c6659-104">使用此安全性區段來評估與管理您的 Lync Server 2013 部署的安全性風險。</span><span class="sxs-lookup"><span data-stu-id="c6659-104">Use this security section to assess and manage security risks to your deployment of Lync Server 2013.</span></span>

<span data-ttu-id="c6659-105">即使您的 Lync Server 2013 部署適中，您的網路中也可能有自己的安全性檔案的元件。</span><span class="sxs-lookup"><span data-stu-id="c6659-105">Even if your Lync Server 2013 deployment is modest, you probably have components in your network that have their own security documentation.</span></span> <span data-ttu-id="c6659-106">因此，此區段不太可能涵蓋與您的部署有關之所有元件和區域的安全性的所有方面。</span><span class="sxs-lookup"><span data-stu-id="c6659-106">Therefore, it is unlikely that this section covers all aspects of security for all components and areas that are pertinent to your deployment.</span></span>

<span data-ttu-id="c6659-107">使用此章節作為開始使用 Lync Server 2013 部署安全性的起點。</span><span class="sxs-lookup"><span data-stu-id="c6659-107">Use this section as a starting point to address the security of your Lync Server 2013 deployment.</span></span> <span data-ttu-id="c6659-108">它提供評估與管理最常見的安全性風險的一般指導方針和最佳做法。</span><span class="sxs-lookup"><span data-stu-id="c6659-108">It provides general guidelines and best practices for assessing and managing the most common security risks.</span></span> <span data-ttu-id="c6659-109">其他產品和安全性資源列在每個主題的結尾。</span><span class="sxs-lookup"><span data-stu-id="c6659-109">Additional product and security resources are listed at the end of each topic.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c6659-110">安全性是一個不斷發展的主題。</span><span class="sxs-lookup"><span data-stu-id="c6659-110">Security is a constantly evolving topic.</span></span> <span data-ttu-id="c6659-111">隨著新的威脅與解決方案的出現，過期的檔、解決方案、方法及程式應該使用最新的資料來取代。</span><span class="sxs-lookup"><span data-stu-id="c6659-111">As new threats and solutions arise, outdated documents, solutions, methods, and procedures should be replaced with up-to-date material.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c6659-112">本節內容</span><span class="sxs-lookup"><span data-stu-id="c6659-112">In This Section</span></span>

  - [<span data-ttu-id="c6659-113">Lync Server 2013 的主要安全性功能</span><span class="sxs-lookup"><span data-stu-id="c6659-113">Key security features in Lync Server 2013</span></span>](lync-server-2013-key-security-features.md)

  - [<span data-ttu-id="c6659-114">現代的日期計算中的常見安全性威脅</span><span class="sxs-lookup"><span data-stu-id="c6659-114">Common security threats in modern day computing</span></span>](lync-server-2013-common-security-threats-in-modern-day-computing.md)

  - [<span data-ttu-id="c6659-115">Lync Server 2013 的防毒掃描排除項目</span><span class="sxs-lookup"><span data-stu-id="c6659-115">Antivirus scanning exclusions for Lync Server 2013</span></span>](lync-server-2013-antivirus-scanning-exclusions.md)

  - [<span data-ttu-id="c6659-116">Lync Server 2013 的安全性架構</span><span class="sxs-lookup"><span data-stu-id="c6659-116">Security framework for Lync Server 2013</span></span>](lync-server-2013-security-framework-for-lync-server.md)

  - [<span data-ttu-id="c6659-117">針對 Lync Server 2013 的核心基礎結構解決威脅</span><span class="sxs-lookup"><span data-stu-id="c6659-117">Addressing threats to your core infrastructure for Lync Server 2013</span></span>](lync-server-2013-addressing-threats-to-your-core-infrastructure.md)

  - [<span data-ttu-id="c6659-118">在 Lync Server 2013  中部署 SQL Server 非標準連接埠和別名</span><span class="sxs-lookup"><span data-stu-id="c6659-118">Deploying a SQL Server nonstandard port and alias in Lync Server 2013</span></span>](deploying-a-sql-server-nonstandard-port-and-alias-in-lync-server-2013.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

