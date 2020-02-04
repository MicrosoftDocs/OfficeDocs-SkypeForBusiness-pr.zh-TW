---
title: Lync Server 2013：定義轉譯規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining translation rules
ms:assetid: 4f6b975a-77e6-474c-9171-b139d84138c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398322(v=OCS.15)
ms:contentKeyID: 48184093
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bd6b46dbe0362f81cdaf6a1bf52a27112604a46
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728293"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-translation-rules-in-lync-server-2013"></a><span data-ttu-id="71b5d-102">在 Lync Server 2013 中定義轉譯規則</span><span class="sxs-lookup"><span data-stu-id="71b5d-102">Defining translation rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71b5d-103">_**主題上次修改日期：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="71b5d-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="71b5d-104">Lync Server 2013 企業語音路由呼叫依據以正常化為 E. 164 格式的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="71b5d-104">Lync Server 2013 Enterprise Voice routes calls based on phone numbers normalized to E.164 format.</span></span> <span data-ttu-id="71b5d-105">這表示，所有撥號字串都必須正常化為 E.i 格式，才能執行反向數位查閱（RNL），因此可以將它們轉換成相符的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="71b5d-105">This means that all dialed strings must be normalized to E.164 format for the purpose of performing reverse number lookup (RNL) so they can be translated to their matching SIP URI.</span></span> <span data-ttu-id="71b5d-106">Lync Server 2013 提供操縱呼叫 ID 與本機號碼簡報的功能。</span><span class="sxs-lookup"><span data-stu-id="71b5d-106">Lync Server 2013 provides the ability to manipulate the called ID and the caller ID presentation.</span></span>

<span data-ttu-id="71b5d-107">本節討論如何操作稱為 ID 和本機號碼。</span><span class="sxs-lookup"><span data-stu-id="71b5d-107">This section discusses how to manipulate the called ID and caller ID.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="71b5d-108">本節內容</span><span class="sxs-lookup"><span data-stu-id="71b5d-108">In This Section</span></span>

  - [<span data-ttu-id="71b5d-109">Lync Server 2013 中的本機號碼簡報</span><span class="sxs-lookup"><span data-stu-id="71b5d-109">Caller ID presentation in Lync Server 2013</span></span>](lync-server-2013-caller-id-presentation.md)

  - [<span data-ttu-id="71b5d-110">在 Lync Server 2013 中呼叫 ID 簡報</span><span class="sxs-lookup"><span data-stu-id="71b5d-110">Called ID presentation in Lync Server 2013</span></span>](lync-server-2013-called-id-presentation.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="71b5d-111">請參閱</span><span class="sxs-lookup"><span data-stu-id="71b5d-111">See Also</span></span>


[<span data-ttu-id="71b5d-112">在 Lync Server 2013 中定義正規化規則</span><span class="sxs-lookup"><span data-stu-id="71b5d-112">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

