---
title: Lync Server 2013：管理通話駐留
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Call Park
ms:assetid: 9554cdf6-8e7c-48c8-94dd-f28e2befefdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688140(v=OCS.15)
ms:contentKeyID: 49733740
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 046467dbe10e66d767d1ce8044984b3de0be1243
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505910"
---
# <a name="managing-call-park-in-lync-server-2013"></a><span data-ttu-id="fff70-102">在 Lync Server 2013 中管理通話駐留</span><span class="sxs-lookup"><span data-stu-id="fff70-102">Managing Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fff70-103">_**主題上次修改日期：** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="fff70-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="fff70-104">通話駐留應用程式可讓企業語音使用者從一部電話接聽來電，然後在稍後從任何電話取回通話。</span><span class="sxs-lookup"><span data-stu-id="fff70-104">The Call Park application enables an Enterprise Voice user to put a call on hold from one telephone and then retrieve the call later from any telephone.</span></span> <span data-ttu-id="fff70-105">當使用者公園通話時，Lync Server 會將來電轉接至暫時號碼（稱為 *軌道*），在此呼叫中，來電會保留，直到有人將通話或超時。</span><span class="sxs-lookup"><span data-stu-id="fff70-105">When the user parks a call, Lync Server transfers the call to a temporary number, called an *orbit*, where the call is held until someone retrieves it or it times out.</span></span>

<span data-ttu-id="fff70-106">本節中的主題會針對您可以在部署中執行來自訂和維護通話駐留應用程式的工作，提供逐步程式。</span><span class="sxs-lookup"><span data-stu-id="fff70-106">Topics in this section provide step-by-step procedures for tasks that you can perform to customize and maintain the Call Park application in your deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fff70-107">本章節內容</span><span class="sxs-lookup"><span data-stu-id="fff70-107">In This Section</span></span>

  - [<span data-ttu-id="fff70-108">在 Lync Server 2013 中設定休止通話的電話號碼分機號碼</span><span class="sxs-lookup"><span data-stu-id="fff70-108">Configure phone number extensions for parking calls in Lync Server 2013</span></span>](lync-server-2013-configure-phone-number-extensions-for-parking-calls.md)

  - [<span data-ttu-id="fff70-109">在 Lync Server 2013 中設定通話駐留設定</span><span class="sxs-lookup"><span data-stu-id="fff70-109">Configure Call Park settings in Lync Server 2013</span></span>](lync-server-2013-configure-call-park-settings.md)

  - [<span data-ttu-id="fff70-110">在 Lync Server 2013 中自訂通話駐留的等候音樂</span><span class="sxs-lookup"><span data-stu-id="fff70-110">Customize Call Park music on hold in Lync Server 2013</span></span>](lync-server-2013-customize-call-park-music-on-hold.md)

  - [<span data-ttu-id="fff70-111">在 Lync Server 2013 中的嚴重損壞修復期間管理通話駐留</span><span class="sxs-lookup"><span data-stu-id="fff70-111">Manage Call Park during disaster recovery in Lync Server 2013</span></span>](lync-server-2013-manage-call-park-during-disaster-recovery.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

