---
title: 移轉公共區域電話
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Common Area Phones
ms:assetid: 31bd26fc-861b-45c6-8221-18df16e575de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688015(v=OCS.15)
ms:contentKeyID: 49733604
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cba32f8aa95b870190280aebd94d51bdbeec0f2b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762951"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-common-area-phones"></a><span data-ttu-id="aa7af-102">移轉公共區域電話</span><span class="sxs-lookup"><span data-stu-id="aa7af-102">Migrate Common Area Phones</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa7af-103">_**主題上次修改日期：** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="aa7af-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="aa7af-104">常見的區域手機是最常位於共用工作區或常見區域（例如大廳、廚房或工廠地面）的 IP 電話。</span><span class="sxs-lookup"><span data-stu-id="aa7af-104">Common Area Phones are IP phones that most often reside in a shared workspace or common area, like a lobby, kitchen, or factory floor.</span></span> <span data-ttu-id="aa7af-105">常見的區域電話不需要連線到電腦，就能提供 Lync Server UC 功能。</span><span class="sxs-lookup"><span data-stu-id="aa7af-105">Common Area Phones do not need to be connected to a computer to provide Lync Server UC functionality.</span></span> <span data-ttu-id="aa7af-106">將 Lync Server 2010 部署遷移至 Lync Server 2013 之後，您也必須遷移與舊版常見區域手機相關聯的連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="aa7af-106">After migrating an Lync Server 2010 deployment to Lync Server 2013, you must also migrate the contact objects associated with the legacy Common Area Phone.</span></span> <span data-ttu-id="aa7af-107">使用 Lync Server 管理命令介面，您將會首先檢索與 Lync Server 2010 常見區域手機相關的所有連絡人物件，然後將這些物件移至 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="aa7af-107">Using Lync Server Management Shell you will first retrieve all contact objects associated with the Lync Server 2010 Common Area Phones, and then move those objects to the Lync Server 2013 pool.</span></span>

<span data-ttu-id="aa7af-108">**移轉公共區域電話**</span><span class="sxs-lookup"><span data-stu-id="aa7af-108">**Migrate Common Area Phones**</span></span>

1.  <span data-ttu-id="aa7af-109">從 Lync Server 2013 前端伺服器，開啟 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="aa7af-109">From the Lync Server 2013 Front End server, open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="aa7af-110">在命令列中，輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="aa7af-110">From the command line, type the following:</span></span>
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net

3.  <span data-ttu-id="aa7af-111">若要確認已將所有連絡人物件移至 Lync Server 2013 池，請從 Lync Server 管理命令介面輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="aa7af-111">To verify all contact objects have been moved to the Lync Server 2013 pool, from the Lync Server Management Shell type the following:</span></span>
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
    
    <span data-ttu-id="aa7af-112">確認所有連絡人物件現在都與 Lync Server 2013 池相關聯。</span><span class="sxs-lookup"><span data-stu-id="aa7af-112">Verify all contact objects are now associated with the Lync Server 2013 pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

