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
ms.openlocfilehash: 85c4f1dc3b07d56e97211d6d5caf549e72caa177
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521680"
---
# <a name="defining-translation-rules-in-lync-server-2013"></a><span data-ttu-id="26c55-102">在 Lync Server 2013 中定義轉譯規則</span><span class="sxs-lookup"><span data-stu-id="26c55-102">Defining translation rules in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="26c55-103">_**主題上次修改日期：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="26c55-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="26c55-104">Lync Server 2013 Enterprise Voice 路由會根據標準化為 e.164 格式的電話號碼進行呼叫。</span><span class="sxs-lookup"><span data-stu-id="26c55-104">Lync Server 2013 Enterprise Voice routes calls based on phone numbers normalized to E.164 format.</span></span> <span data-ttu-id="26c55-105">這表示所有撥打的字串都必須正常化為 e.164 格式，以執行反向號碼查閱 (RNL) ，使其可轉譯成比對其相符的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="26c55-105">This means that all dialed strings must be normalized to E.164 format for the purpose of performing reverse number lookup (RNL) so they can be translated to their matching SIP URI.</span></span> <span data-ttu-id="26c55-106">Lync Server 2013 可讓您操縱所叫識別碼及來電者識別碼簡報。</span><span class="sxs-lookup"><span data-stu-id="26c55-106">Lync Server 2013 provides the ability to manipulate the called ID and the caller ID presentation.</span></span>

<span data-ttu-id="26c55-107">本節討論如何操縱叫用識別碼及來電者識別碼。</span><span class="sxs-lookup"><span data-stu-id="26c55-107">This section discusses how to manipulate the called ID and caller ID.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="26c55-108">本章節內容</span><span class="sxs-lookup"><span data-stu-id="26c55-108">In This Section</span></span>

  - [<span data-ttu-id="26c55-109">Lync Server 2013 中的呼叫者識別碼簡報</span><span class="sxs-lookup"><span data-stu-id="26c55-109">Caller ID presentation in Lync Server 2013</span></span>](lync-server-2013-caller-id-presentation.md)

  - [<span data-ttu-id="26c55-110">Lync Server 2013 中稱為「識別碼簡報」</span><span class="sxs-lookup"><span data-stu-id="26c55-110">Called ID presentation in Lync Server 2013</span></span>](lync-server-2013-called-id-presentation.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="26c55-111">另請參閱</span><span class="sxs-lookup"><span data-stu-id="26c55-111">See Also</span></span>


[<span data-ttu-id="26c55-112">在 Lync Server 2013 中定義正常化規則</span><span class="sxs-lookup"><span data-stu-id="26c55-112">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

