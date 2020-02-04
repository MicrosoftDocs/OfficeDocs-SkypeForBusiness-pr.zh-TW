---
title: Lync Server 2013：將會議裝置移至新的註冊機構池
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move a conferencing device to a new Registrar pool
ms:assetid: 26e02ca3-e881-4f90-8bf0-b13649108100
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994025(v=OCS.15)
ms:contentKeyID: 51803934
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69afbc1dbb33f43f8ed6a1f056f7d4a610b110c4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756747"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-a-conferencing-device-to-a-new-registrar-pool-in-lync-server-2013"></a><span data-ttu-id="b3958-102">在 Lync Server 2013 中將會議裝置移至新的註冊機構池</span><span class="sxs-lookup"><span data-stu-id="b3958-102">Move a conferencing device to a new Registrar pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3958-103">_**主題上次修改日期：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="b3958-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="b3958-104">使用**CsMeetingRoom** Cmdlet，將會議裝置從一個註冊機構池移至另一個。</span><span class="sxs-lookup"><span data-stu-id="b3958-104">Move a conferencing device from one Registrar pool to another by using the **Move-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="b3958-105">這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。</span><span class="sxs-lookup"><span data-stu-id="b3958-105">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b3958-106">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>。</span><span class="sxs-lookup"><span data-stu-id="b3958-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="moving-a-conferencing-device-to-a-new-registrar-pool"></a><span data-ttu-id="b3958-107">將會議裝置移至新的註冊機構池</span><span class="sxs-lookup"><span data-stu-id="b3958-107">Moving a Conferencing Device to a New Registrar Pool</span></span>

  - <span data-ttu-id="b3958-108">若要移動會議裝置，您必須指定要移動的聊天室身分識別，然後將目標參數設定為裝置將會移至的註冊機構池的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="b3958-108">To move a conferencing device, you must specify the identity of the room to be moved, and then set the Target parameter to the fully qualified domain name (FQDN) of the Registrar pool the device will be moved to.</span></span> <span data-ttu-id="b3958-109">例如：</span><span class="sxs-lookup"><span data-stu-id="b3958-109">For example:</span></span>
    
        Move-CsMeetingRoom -Target "atl-cs-001.litwareinc.com" -Identity "Room 14"

</div>

<span data-ttu-id="b3958-110">如需詳細資訊，請參閱[移動流覽 CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Move-CsMeetingRoom) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="b3958-110">For details, see the Help topic for the [Move-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Move-CsMeetingRoom) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

