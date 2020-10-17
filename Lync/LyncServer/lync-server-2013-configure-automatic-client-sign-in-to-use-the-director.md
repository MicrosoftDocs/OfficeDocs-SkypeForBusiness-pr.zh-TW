---
title: Lync Server 2013：設定自動用戶端 Sign-In 以使用 Director
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Automatic Client Sign-In to use the Director
ms:assetid: 85369ffc-53ae-43be-8a23-84a094faecff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398678(v=OCS.15)
ms:contentKeyID: 48184703
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e174e55a2564dcf60b0405819e2996e4bf3d8f95
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522960"
---
# <a name="configure-automatic-client-sign-in-to-use-the-director-in-lync-server-2013"></a><span data-ttu-id="b0e86-102">在 Lync Server 2013 中設定自動用戶端 Sign-In 以使用 Director</span><span class="sxs-lookup"><span data-stu-id="b0e86-102">Configure Automatic Client Sign-In to use the Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0e86-103">_**主題上次修改日期：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="b0e86-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="b0e86-104">當您部署 Lync Server 2013、Director 或 Director 集區時，建議您使用自動用戶端 Sign-In 做為最佳作法。</span><span class="sxs-lookup"><span data-stu-id="b0e86-104">When you deploy a Lync Server 2013, Director or a pool of Directors, we recommend that you use Automatic Client Sign-In as a best practice.</span></span> <span data-ttu-id="b0e86-105">如需如何設定 DNS 伺服器以進行自動用戶端登入的詳細資訊，請參閱規劃檔中的 [自動用戶端登入的 dns 需求（Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md) ）。</span><span class="sxs-lookup"><span data-stu-id="b0e86-105">For details about how to configure DNS servers for automatic client sign-in, see [DNS requirements for automatic client sign-in in Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md) in the Planning documentation.</span></span>

<span data-ttu-id="b0e86-106">如果您已部署自動用戶端 Sign-In，請參閱下列各節，以在 Director (s) 上加以設定。</span><span class="sxs-lookup"><span data-stu-id="b0e86-106">If you have already deployed Automatic Client Sign-In, see the following sections to configure it on your Director(s).</span></span>

<div>

## <a name="single-director-instance"></a><span data-ttu-id="b0e86-107">單一 Director 實例</span><span class="sxs-lookup"><span data-stu-id="b0e86-107">Single Director Instance</span></span>

<span data-ttu-id="b0e86-108">如果您已部署自動用戶端 Sign-In，而且它指向前端伺服器或前端集區，則您必須變更 DNS SRV 記錄，以指向 Director。</span><span class="sxs-lookup"><span data-stu-id="b0e86-108">If you already have Automatic Client Sign-In deployed and it is pointing to a Front End Server or a Front End pool, you need to change the DNS SRV record to point to the Director.</span></span>

</div>

<div>

## <a name="director-pool"></a><span data-ttu-id="b0e86-109">Director 集區</span><span class="sxs-lookup"><span data-stu-id="b0e86-109">Director Pool</span></span>

<span data-ttu-id="b0e86-110">如果您已部署自動用戶端 Sign-In，而且它指向前端伺服器或前端集區，則您需要變更 DNS SRV 記錄以指向 Director 集區。</span><span class="sxs-lookup"><span data-stu-id="b0e86-110">If you already have Automatic Client Sign-In deployed and it is pointing to a Front End Server or a Front End pool, you need to change the DNS SRV record to point to the Director pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

