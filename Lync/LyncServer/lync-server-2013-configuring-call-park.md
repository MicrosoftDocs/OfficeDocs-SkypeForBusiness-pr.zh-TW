---
title: Lync Server 2013：設定通話駐留
description: Lync Server 2013：設定通話駐留。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Call Park
ms:assetid: e4c5da53-7f6c-4535-bc9b-9da2026caec8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399014(v=OCS.15)
ms:contentKeyID: 48185732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d2708f26fae5706afc31aa195b9fdb82536247b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568749"
---
# <a name="configuring-call-park-in-lync-server-2013"></a><span data-ttu-id="4b983-103">在 Lync Server 2013 中設定通話駐留</span><span class="sxs-lookup"><span data-stu-id="4b983-103">Configuring Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b983-104">_**主題上次修改日期：** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="4b983-104">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="4b983-105">通話駐留可讓企業語音使用者從一部電話接聽來電，然後再撥打此通話的內部號碼 (稱為通話駐留 *軌道*) 從任何電話）。</span><span class="sxs-lookup"><span data-stu-id="4b983-105">Call Park enables an Enterprise Voice user to put a call on hold from one telephone and then retrieve the call later by dialing an internal number (known as a Call Park *orbit*) from any telephone.</span></span>

<span data-ttu-id="4b983-106">當您部署企業語音時，會自動在前端伺服器或 Standard Edition server 上安裝及啟用呼叫駐留所使用的元件。</span><span class="sxs-lookup"><span data-stu-id="4b983-106">The components that Call Park uses are automatically installed and enabled on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="4b983-107">不過，您必須先設定通話駐留，使用者才能使用它。</span><span class="sxs-lookup"><span data-stu-id="4b983-107">However, you must configure Call Park before it is available to users.</span></span>

<span data-ttu-id="4b983-108">本節會引導您完成通話駐留的設定。</span><span class="sxs-lookup"><span data-stu-id="4b983-108">This section guides you through the configuration of Call Park.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4b983-109">本章節內容</span><span class="sxs-lookup"><span data-stu-id="4b983-109">In This Section</span></span>

  - [<span data-ttu-id="4b983-110">Lync Server 2013 中的通話駐留設定必要條件和使用者權限</span><span class="sxs-lookup"><span data-stu-id="4b983-110">Call Park configuration prerequisites and user rights in Lync Server 2013</span></span>](lync-server-2013-call-park-configuration-prerequisites-and-user-rights.md)

  - [<span data-ttu-id="4b983-111">Lync Server 2013 中通話駐留的部署程式</span><span class="sxs-lookup"><span data-stu-id="4b983-111">Deployment process for Call Park in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-call-park.md)

  - [<span data-ttu-id="4b983-112">在 Lync Server 2013 中設定通話駐留軌道表格</span><span class="sxs-lookup"><span data-stu-id="4b983-112">Configure the Call Park orbit table in Lync Server 2013</span></span>](lync-server-2013-configure-the-call-park-orbit-table.md)

  - [<span data-ttu-id="4b983-113">在 Lync Server 2013 中設定通話駐留設定</span><span class="sxs-lookup"><span data-stu-id="4b983-113">Configure Call Park settings in Lync Server 2013</span></span>](lync-server-2013-configure-call-park-settings.md)

  - [<span data-ttu-id="4b983-114">在 Lync Server 2013 中自訂通話駐留的等候音樂</span><span class="sxs-lookup"><span data-stu-id="4b983-114">Customize Call Park music on hold in Lync Server 2013</span></span>](lync-server-2013-customize-call-park-music-on-hold.md)

  - [<span data-ttu-id="4b983-115">在 Lync Server 2013 中為使用者啟用通話駐留</span><span class="sxs-lookup"><span data-stu-id="4b983-115">Enable Call Park for users in Lync Server 2013</span></span>](lync-server-2013-enable-call-park-for-users.md)

  - [<span data-ttu-id="4b983-116">在 Lync Server 2013 中驗證通話駐留的正規化規則</span><span class="sxs-lookup"><span data-stu-id="4b983-116">Verify normalization rules for Call Park in Lync Server 2013</span></span>](lync-server-2013-verify-normalization-rules-for-call-park.md)

  - [<span data-ttu-id="4b983-117"> (選用) 在 Lync Server 2013 中驗證通話駐留部署</span><span class="sxs-lookup"><span data-stu-id="4b983-117">(Optional) Verify Call Park deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-call-park-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

