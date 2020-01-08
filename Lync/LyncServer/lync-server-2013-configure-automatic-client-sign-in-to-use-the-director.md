---
title: Lync Server 2013：設定用戶端自動登入以使用 Director
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Automatic Client Sign-In to use the Director
ms:assetid: 85369ffc-53ae-43be-8a23-84a094faecff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398678(v=OCS.15)
ms:contentKeyID: 48184703
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63e885080879b2b7ce3cf87557b21822fe9cd26f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977865"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-automatic-client-sign-in-to-use-the-director-in-lync-server-2013"></a><span data-ttu-id="391a8-102">在 Lync Server 2013 中設定用戶端自動登入以使用 Director</span><span class="sxs-lookup"><span data-stu-id="391a8-102">Configure Automatic Client Sign-In to use the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="391a8-103">_**主題上次修改日期：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="391a8-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="391a8-104">當您部署 Lync Server 2013、主管或控制器池時，建議您使用自動用戶端登入做為最佳做法。</span><span class="sxs-lookup"><span data-stu-id="391a8-104">When you deploy a Lync Server 2013, Director or a pool of Directors, we recommend that you use Automatic Client Sign-In as a best practice.</span></span> <span data-ttu-id="391a8-105">如需有關如何設定 DNS 伺服器以進行自動用戶端登入的詳細資料，請參閱規劃檔中的[Lync Server 2013 中的自動用戶端登入的 DNS 需求](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)。</span><span class="sxs-lookup"><span data-stu-id="391a8-105">For details about how to configure DNS servers for automatic client sign-in, see [DNS requirements for automatic client sign-in in Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md) in the Planning documentation.</span></span>

<span data-ttu-id="391a8-106">如果您已經部署了自動用戶端登入，請參閱下列各節，以在您的主管上進行設定。</span><span class="sxs-lookup"><span data-stu-id="391a8-106">If you have already deployed Automatic Client Sign-In, see the following sections to configure it on your Director(s).</span></span>

<div>

## <a name="single-director-instance"></a><span data-ttu-id="391a8-107">單一控制器實例</span><span class="sxs-lookup"><span data-stu-id="391a8-107">Single Director Instance</span></span>

<span data-ttu-id="391a8-108">如果您已部署自動用戶端登入，且它指向前端伺服器或前端池，您必須將 DNS SRV 記錄變更為指向控制器。</span><span class="sxs-lookup"><span data-stu-id="391a8-108">If you already have Automatic Client Sign-In deployed and it is pointing to a Front End Server or a Front End pool, you need to change the DNS SRV record to point to the Director.</span></span>

</div>

<div>

## <a name="director-pool"></a><span data-ttu-id="391a8-109">主管池</span><span class="sxs-lookup"><span data-stu-id="391a8-109">Director Pool</span></span>

<span data-ttu-id="391a8-110">如果您已部署自動用戶端登入，且它指向前端伺服器或頂層端池，您必須將 DNS SRV 記錄變更為指向主管池。</span><span class="sxs-lookup"><span data-stu-id="391a8-110">If you already have Automatic Client Sign-In deployed and it is pointing to a Front End Server or a Front End pool, you need to change the DNS SRV record to point to the Director pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

