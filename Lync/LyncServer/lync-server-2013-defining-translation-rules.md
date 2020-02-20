---
title: Lync Server 2013： 定義轉譯規則
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
ms.openlocfilehash: 4082e5ff206a25269e54062add6fcd49c8d22108
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153765"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-translation-rules-in-lync-server-2013"></a><span data-ttu-id="783b9-102">定義 Lync Server 2013 中的 [轉譯規則</span><span class="sxs-lookup"><span data-stu-id="783b9-102">Defining translation rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="783b9-103">_**上次修改主題：** 2013年-02-22_</span><span class="sxs-lookup"><span data-stu-id="783b9-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="783b9-104">Lync Server 2013 Enterprise Voice 路由傳送來電的電話號碼正規化為 E.164 格式為基礎。</span><span class="sxs-lookup"><span data-stu-id="783b9-104">Lync Server 2013 Enterprise Voice routes calls based on phone numbers normalized to E.164 format.</span></span> <span data-ttu-id="783b9-105">這表示所有撥號的字串必須被正規化為 E.164 格式目的執行反向號碼查閱 (RNL)，讓他們可以轉譯成其比對的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="783b9-105">This means that all dialed strings must be normalized to E.164 format for the purpose of performing reverse number lookup (RNL) so they can be translated to their matching SIP URI.</span></span> <span data-ttu-id="783b9-106">Lync Server 2013 提供可用來操控的受話的識別碼，來電者 ID 呈現方式。</span><span class="sxs-lookup"><span data-stu-id="783b9-106">Lync Server 2013 provides the ability to manipulate the called ID and the caller ID presentation.</span></span>

<span data-ttu-id="783b9-107">本章節將討論如何處理呼叫的識別碼和來電者識別碼。</span><span class="sxs-lookup"><span data-stu-id="783b9-107">This section discusses how to manipulate the called ID and caller ID.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="783b9-108">本章節內容</span><span class="sxs-lookup"><span data-stu-id="783b9-108">In This Section</span></span>

  - [<span data-ttu-id="783b9-109">Lync Server 2013 中的來電者 ID 呈現方式</span><span class="sxs-lookup"><span data-stu-id="783b9-109">Caller ID presentation in Lync Server 2013</span></span>](lync-server-2013-caller-id-presentation.md)

  - [<span data-ttu-id="783b9-110">Lync Server 2013 中的受話的 ID 呈現方式</span><span class="sxs-lookup"><span data-stu-id="783b9-110">Called ID presentation in Lync Server 2013</span></span>](lync-server-2013-called-id-presentation.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="783b9-111">另請參閱</span><span class="sxs-lookup"><span data-stu-id="783b9-111">See Also</span></span>


[<span data-ttu-id="783b9-112">Lync Server 2013 中的定義正規化規則</span><span class="sxs-lookup"><span data-stu-id="783b9-112">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

