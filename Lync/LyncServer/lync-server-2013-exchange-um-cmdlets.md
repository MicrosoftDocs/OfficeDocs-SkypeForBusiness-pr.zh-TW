---
title: Lync Server 2013： Exchange UM Cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exchange UM cmdlets
ms:assetid: 32922b9f-590d-41cc-ba57-9ed5f1caa814
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415642(v=OCS.15)
ms:contentKeyID: 48183786
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2cc9d63189d66e6e5255ca7c0d34a717cc2eb514
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756247"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exchange-um-cmdlets-in-lync-server-2013"></a><span data-ttu-id="c4404-102">Lync Server 2013 中的 Exchange UM Cmdlet</span><span class="sxs-lookup"><span data-stu-id="c4404-102">Exchange UM cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4404-103">_**主題上次修改日期：** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="c4404-103">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="c4404-104">Microsoft Lync Server 2013 與 Exchange 整合通訊（UM）搭配使用，以實現託管語音信箱的自動語音應答及訂閱者存取。</span><span class="sxs-lookup"><span data-stu-id="c4404-104">Microsoft Lync Server 2013 works together with Exchange Unified Messaging (UM) to implement Auto Attendant and Subscriber Access for hosted voice mail.</span></span> <span data-ttu-id="c4404-105">您可以透過 Lync Server 管理命令介面中的 Cmdlet 管理這些功能。</span><span class="sxs-lookup"><span data-stu-id="c4404-105">These features can be managed through cmdlets in the Lync Server Management Shell.</span></span>

<div>

## <a name="exchange-um-cmdlets"></a><span data-ttu-id="c4404-106">Exchange UM Cmdlet</span><span class="sxs-lookup"><span data-stu-id="c4404-106">Exchange UM Cmdlets</span></span>

<span data-ttu-id="c4404-107">下列 Cmdlet 可用於管理 Exchange UM</span><span class="sxs-lookup"><span data-stu-id="c4404-107">The following cmdlets can be used to manage Exchange UM</span></span>

<span data-ttu-id="c4404-108">**Exchange UM**</span><span class="sxs-lookup"><span data-stu-id="c4404-108">**Exchange UM**</span></span>

  - <span></span>  
    <span data-ttu-id="c4404-109">[CsExUmContact](https://technet.microsoft.com/en-us/library/Gg412725(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c4404-109">[Get-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg412725(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c4404-110">[移動流覽 CsExUmContact](https://technet.microsoft.com/en-us/library/Gg425842(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c4404-110">[Move-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg425842(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c4404-111">[新-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg398139(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c4404-111">[New-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg398139(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c4404-112">[移除-CsExUmContact](rehttps://technet.microsoft.com/en-us/library/Gg425842(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c4404-112">[Remove-CsExUmContact](rehttps://technet.microsoft.com/en-us/library/Gg425842(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c4404-113">[Set-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg412944(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c4404-113">[Set-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg412944(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="c4404-114">[Test-CsExStorageConnectivity](https://technet.microsoft.com/en-us/library/JJ204740(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c4404-114">[Test-CsExStorageConnectivity](https://technet.microsoft.com/en-us/library/JJ204740(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="c4404-115">[Test-CsExStorageNotification](https://technet.microsoft.com/en-us/library/JJ205331(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c4404-115">[Test-CsExStorageNotification](https://technet.microsoft.com/en-us/library/JJ205331(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="c4404-116">[Test-CsExUMConnectivity](https://technet.microsoft.com/en-us/library/JJ204784(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c4404-116">[Test-CsExUMConnectivity](https://technet.microsoft.com/en-us/library/JJ204784(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="c4404-117">[Test-CsExUMVoiceMail](https://technet.microsoft.com/en-us/library/JJ205058(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c4404-117">[Test-CsExUMVoiceMail](https://technet.microsoft.com/en-us/library/JJ205058(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c4404-118">[CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg398348(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c4404-118">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg398348(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c4404-119">[授與 CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg412829(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c4404-119">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg412829(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c4404-120">[新-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg398653(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c4404-120">[New-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg398653(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c4404-121">[移除-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg398211(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c4404-121">[Remove-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg398211(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c4404-122">[Set-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg412722(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c4404-122">[Set-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg412722(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c4404-123">[CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425732(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c4404-123">[Get-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425732(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c4404-124">[新-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425849(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c4404-124">[New-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425849(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c4404-125">[移除-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398573(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c4404-125">[Remove-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398573(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c4404-126">[Set-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg412948(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c4404-126">[Set-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg412948(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c4404-127">請參閱</span><span class="sxs-lookup"><span data-stu-id="c4404-127">See Also</span></span>


[<span data-ttu-id="c4404-128">Lync Server PowerShell 博客</span><span class="sxs-lookup"><span data-stu-id="c4404-128">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

