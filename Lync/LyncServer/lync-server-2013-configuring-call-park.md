---
title: Lync Server 2013：設定通話駐留
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Call Park
ms:assetid: e4c5da53-7f6c-4535-bc9b-9da2026caec8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399014(v=OCS.15)
ms:contentKeyID: 48185732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69e2a1c6ef9da447688ea1ca7d0308afc0b4ab9c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975752"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-call-park-in-lync-server-2013"></a><span data-ttu-id="03684-102">在 Lync Server 2013 中設定通話駐留</span><span class="sxs-lookup"><span data-stu-id="03684-102">Configuring Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03684-103">_**主題上次修改日期：** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="03684-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="03684-104">[通話寄存] 可讓企業語音使用者從一部電話撥打電話，然後從任何電話撥出內部號碼（稱為 [通話駐留]*軌道*），稍後再取回通話。</span><span class="sxs-lookup"><span data-stu-id="03684-104">Call Park enables an Enterprise Voice user to put a call on hold from one telephone and then retrieve the call later by dialing an internal number (known as a Call Park *orbit*) from any telephone.</span></span>

<span data-ttu-id="03684-105">當您部署企業語音時，會在前端伺服器或標準版伺服器上自動安裝和啟用通話駐留使用的元件。</span><span class="sxs-lookup"><span data-stu-id="03684-105">The components that Call Park uses are automatically installed and enabled on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="03684-106">不過，您必須先設定 [通話駐留]，才能供使用者使用。</span><span class="sxs-lookup"><span data-stu-id="03684-106">However, you must configure Call Park before it is available to users.</span></span>

<span data-ttu-id="03684-107">本節將引導您完成通話寄存的設定。</span><span class="sxs-lookup"><span data-stu-id="03684-107">This section guides you through the configuration of Call Park.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="03684-108">本節內容</span><span class="sxs-lookup"><span data-stu-id="03684-108">In This Section</span></span>

  - [<span data-ttu-id="03684-109">Lync Server 2013 中的通話駐留組態先決條件和使用者權限</span><span class="sxs-lookup"><span data-stu-id="03684-109">Call Park configuration prerequisites and user rights in Lync Server 2013</span></span>](lync-server-2013-call-park-configuration-prerequisites-and-user-rights.md)

  - [<span data-ttu-id="03684-110">Lync Server 2013 中通話駐留的部署程式</span><span class="sxs-lookup"><span data-stu-id="03684-110">Deployment process for Call Park in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-call-park.md)

  - [<span data-ttu-id="03684-111">在 Lync Server 2013 中設定通話駐留軌道表格</span><span class="sxs-lookup"><span data-stu-id="03684-111">Configure the Call Park orbit table in Lync Server 2013</span></span>](lync-server-2013-configure-the-call-park-orbit-table.md)

  - [<span data-ttu-id="03684-112">在 Lync Server 2013 中設定通話駐留設定</span><span class="sxs-lookup"><span data-stu-id="03684-112">Configure Call Park settings in Lync Server 2013</span></span>](lync-server-2013-configure-call-park-settings.md)

  - [<span data-ttu-id="03684-113">在 Lync Server 2013 中自訂通話寄存音樂暫停</span><span class="sxs-lookup"><span data-stu-id="03684-113">Customize Call Park music on hold in Lync Server 2013</span></span>](lync-server-2013-customize-call-park-music-on-hold.md)

  - [<span data-ttu-id="03684-114">在 Lync Server 2013 中為使用者啟用通話駐留</span><span class="sxs-lookup"><span data-stu-id="03684-114">Enable Call Park for users in Lync Server 2013</span></span>](lync-server-2013-enable-call-park-for-users.md)

  - [<span data-ttu-id="03684-115">在 Lync Server 2013 中驗證通話寄存的正常化規則</span><span class="sxs-lookup"><span data-stu-id="03684-115">Verify normalization rules for Call Park in Lync Server 2013</span></span>](lync-server-2013-verify-normalization-rules-for-call-park.md)

  - [<span data-ttu-id="03684-116">可選在 Lync Server 2013 中確認通話駐留部署</span><span class="sxs-lookup"><span data-stu-id="03684-116">(Optional) Verify Call Park deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-call-park-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

