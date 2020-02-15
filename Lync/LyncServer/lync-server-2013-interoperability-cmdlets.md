---
title: Lync Server 2013： 互通性 cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Interoperability cmdlets
ms:assetid: 18444a0b-7b66-4540-a262-775ea10b3b7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204714(v=OCS.15)
ms:contentKeyID: 48183527
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23c32967da142d48d15a8fec484134c11af9170a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046266"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="interoperability-cmdlets-in-lync-server-2013"></a><span data-ttu-id="d3e3f-102">Lync Server 2013 中的互通性 cmdlet</span><span class="sxs-lookup"><span data-stu-id="d3e3f-102">Interoperability cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d3e3f-103">_**主題上次修改日期：** 2012 年 06 月 27 日_</span><span class="sxs-lookup"><span data-stu-id="d3e3f-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="d3e3f-104">互通性 cmdlet 可用於設定伺服器對伺服器驗證和 Microsoft Lync Server 2013 與其他伺服器產品，例如 Microsoft Exchange Server 2013 之間的授權。</span><span class="sxs-lookup"><span data-stu-id="d3e3f-104">The interoperability cmdlets are used to configure server-to-server authentication and authorization between Microsoft Lync Server 2013 and other server products such as Microsoft Exchange Server 2013.</span></span> <span data-ttu-id="d3e3f-105">伺服器對伺服器驗證和授權可讓這些伺服器緊密交換及共用資料。</span><span class="sxs-lookup"><span data-stu-id="d3e3f-105">Server-to-server authentication and authorization enables these servers to seamless exchange and share data.</span></span>

<div>

## <a name="interoperability-cmdlets"></a><span data-ttu-id="d3e3f-106">互通性 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="d3e3f-106">Interoperability Cmdlets</span></span>

<span data-ttu-id="d3e3f-107">下列是 cmdlet 的直接用於設定及管理 Microsoft Lync Server 2013 與其他伺服器產品之間的互通性與相關清單：</span><span class="sxs-lookup"><span data-stu-id="d3e3f-107">The following is a list of cmdlets that relate directly to configuring and managing interoperability between Microsoft Lync Server 2013 and other server products:</span></span>

<span data-ttu-id="d3e3f-108">**互通性 Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="d3e3f-108">**Interoperability Cmdlets**</span></span>

  - <span data-ttu-id="d3e3f-109">[Get-csoauthconfiguration](https://technet.microsoft.com/library/JJ205155(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d3e3f-109">[Get-CsOAuthConfiguration](https://technet.microsoft.com/library/JJ205155(v=OCS.15))</span></span>

  - <span data-ttu-id="d3e3f-110">[Set-csoauthconfiguration](https://technet.microsoft.com/library/JJ204841(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d3e3f-110">[Set-CsOAuthConfiguration](https://technet.microsoft.com/library/JJ204841(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="d3e3f-111">[Get-csoauthserver](https://technet.microsoft.com/library/JJ205238(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d3e3f-111">[Get-CsOAuthServer](https://technet.microsoft.com/library/JJ205238(v=OCS.15))</span></span>

  - <span data-ttu-id="d3e3f-112">[New-csoauthserver](https://technet.microsoft.com/library/JJ205206(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d3e3f-112">[New-CsOAuthServer](https://technet.microsoft.com/library/JJ205206(v=OCS.15))</span></span>

  - <span data-ttu-id="d3e3f-113">[Remove-csoauthserver](https://technet.microsoft.com/library/JJ205408(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d3e3f-113">[Remove-CsOAuthServer](https://technet.microsoft.com/library/JJ205408(v=OCS.15))</span></span>

  - <span data-ttu-id="d3e3f-114">[Set-csoauthserver](https://technet.microsoft.com/library/JJ204896(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d3e3f-114">[Set-CsOAuthServer](https://technet.microsoft.com/library/JJ204896(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="d3e3f-115">[Get-cspartnerapplication](https://technet.microsoft.com/library/JJ205128(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d3e3f-115">[Get-CsPartnerApplication](https://technet.microsoft.com/library/JJ205128(v=OCS.15))</span></span>

  - <span data-ttu-id="d3e3f-116">[New-cspartnerapplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d3e3f-116">[New-CsPartnerApplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15))</span></span>

  - <span data-ttu-id="d3e3f-117">[Remove-cspartnerapplication](https://technet.microsoft.com/library/JJ204820(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d3e3f-117">[Remove-CsPartnerApplication](https://technet.microsoft.com/library/JJ204820(v=OCS.15))</span></span>

  - <span data-ttu-id="d3e3f-118">[Set-cspartnerapplication](https://technet.microsoft.com/library/JJ204755(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d3e3f-118">[Set-CsPartnerApplication](https://technet.microsoft.com/library/JJ204755(v=OCS.15))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

