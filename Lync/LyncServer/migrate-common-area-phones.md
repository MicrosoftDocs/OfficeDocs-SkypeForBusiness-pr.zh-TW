---
title: 移轉公共區域電話
description: 遷移公共區域電話。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Common Area Phones
ms:assetid: 31bd26fc-861b-45c6-8221-18df16e575de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688015(v=OCS.15)
ms:contentKeyID: 49733604
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b8df4d94a3db3274df7e4e82ed2185c3626de12
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579349"
---
# <a name="migrate-common-area-phones"></a><span data-ttu-id="3c821-103">移轉公共區域電話</span><span class="sxs-lookup"><span data-stu-id="3c821-103">Migrate Common Area Phones</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c821-104">_**主題上次修改日期：** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="3c821-104">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="3c821-105">公共區域電話為最常在共用工作區或公共區域 (例如大廳、廚房或工廠) 的 IP 電話。</span><span class="sxs-lookup"><span data-stu-id="3c821-105">Common Area Phones are IP phones that most often reside in a shared workspace or common area, like a lobby, kitchen, or factory floor.</span></span> <span data-ttu-id="3c821-106">一般區域電話不需要連線到電腦，就能提供 Lync Server UC 功能。</span><span class="sxs-lookup"><span data-stu-id="3c821-106">Common Area Phones do not need to be connected to a computer to provide Lync Server UC functionality.</span></span> <span data-ttu-id="3c821-107">將 Lync Server 2010 部署遷移至 Lync Server 2013 之後，您還必須遷移與舊版通用區域電話相關聯的連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="3c821-107">After migrating an Lync Server 2010 deployment to Lync Server 2013, you must also migrate the contact objects associated with the legacy Common Area Phone.</span></span> <span data-ttu-id="3c821-108">使用 Lync Server 管理命令介面您會先取得與 Lync Server 2010 通用區域電話相關聯的所有連絡人物件，然後將這些物件移至 Lync Server 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="3c821-108">Using Lync Server Management Shell you will first retrieve all contact objects associated with the Lync Server 2010 Common Area Phones, and then move those objects to the Lync Server 2013 pool.</span></span>

<span data-ttu-id="3c821-109">**移轉公共區域電話**</span><span class="sxs-lookup"><span data-stu-id="3c821-109">**Migrate Common Area Phones**</span></span>

1.  <span data-ttu-id="3c821-110">在 Lync Server 2013 前端伺服器上，開啟 [Lync Server 管理命令介面]。</span><span class="sxs-lookup"><span data-stu-id="3c821-110">From the Lync Server 2013 Front End server, open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="3c821-111">從命令列輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="3c821-111">From the command line, type the following:</span></span>
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net

3.  <span data-ttu-id="3c821-112">若要確認已將所有連絡人物件移至 Lync Server 2013 集區，請從 Lync Server 管理命令介面輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="3c821-112">To verify all contact objects have been moved to the Lync Server 2013 pool, from the Lync Server Management Shell type the following:</span></span>
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
    
    <span data-ttu-id="3c821-113">確認所有連絡人物件現在已與 Lync Server 2013 集區相關聯。</span><span class="sxs-lookup"><span data-stu-id="3c821-113">Verify all contact objects are now associated with the Lync Server 2013 pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

