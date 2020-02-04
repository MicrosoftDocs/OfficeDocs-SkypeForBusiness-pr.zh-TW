---
title: Lync Server 2013：移除未與裝置相關聯的裝置更新檔案
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove Device Update files not associated with a device
ms:assetid: ecebbf73-b456-4990-a91d-308b84d39404
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994084(v=OCS.15)
ms:contentKeyID: 51803996
ms.date: 12/12/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42a2579360fbb4af8d6f3c491f5a56c380b593d0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724243"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-device-update-files-not-associated-with-a-device-in-lync-server-2013"></a><span data-ttu-id="6bfbd-102">移除在 Lync Server 2013 中未與裝置相關聯的裝置更新檔案</span><span class="sxs-lookup"><span data-stu-id="6bfbd-102">Remove Device Update files not associated with a device in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6bfbd-103">_**主題上次修改日期：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="6bfbd-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="6bfbd-104">每次將新的裝置更新上傳到系統時，都會建立對應的裝置更新規則。</span><span class="sxs-lookup"><span data-stu-id="6bfbd-104">Each time new device updates are uploaded to the system, a corresponding device update rule is created.</span></span> <span data-ttu-id="6bfbd-105">根據預設，這些新的裝置更新規則會指派至擱置狀態。</span><span class="sxs-lookup"><span data-stu-id="6bfbd-105">By default, these new device update rules are assigned to the Pending state.</span></span> <span data-ttu-id="6bfbd-106">這表示這些規則可以在測試裝置上下載並安裝，而不是在生產裝置上，這可讓您在將更新提供給使用者之前先進行測試。</span><span class="sxs-lookup"><span data-stu-id="6bfbd-106">This means that the rules can be downloaded and installed on test devices, but not on production devices, which enables you to test the updates before making them available to users.</span></span> <span data-ttu-id="6bfbd-107">根據測試，您可以接受並部署或拒絕並刪除更新。</span><span class="sxs-lookup"><span data-stu-id="6bfbd-107">Based on the tests, you either accept and deploy or reject and delete the update.</span></span> <span data-ttu-id="6bfbd-108">當您拒絕更新時，裝置更新會從它的裝置更新規則解除關聯。</span><span class="sxs-lookup"><span data-stu-id="6bfbd-108">When you reject an update, the device update is disassociated from its device update rule.</span></span>

<div>


<span data-ttu-id="6bfbd-109">您可以使用 Windows PowerShell 和**Clear CsDeviceUpdateFile** Cmdlet 來移除不再與裝置相關聯的裝置更新檔案。</span><span class="sxs-lookup"><span data-stu-id="6bfbd-109">Device update files that are no longer associated with a device can be removed by using Windows PowerShell and the **Clear-CsDeviceUpdateFile** cmdlet.</span></span> <span data-ttu-id="6bfbd-110">這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。</span><span class="sxs-lookup"><span data-stu-id="6bfbd-110">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6bfbd-111">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>。</span><span class="sxs-lookup"><span data-stu-id="6bfbd-111">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


  - <span data-ttu-id="6bfbd-112">例如，下列命令會移除 Web 服務器 atl-cs-001.litwareinc.com 上已不再與裝置相關聯的任何裝置更新規則：</span><span class="sxs-lookup"><span data-stu-id="6bfbd-112">For example, the following command removes any device update rules on the Web server atl-cs-001.litwareinc.com that are no longer associated with a device:</span></span>
    
        Clear-CsDeviceUpdateFile -Identity "service:WebServer:atl-cs-001.litwareinc.com"

</div>

<span data-ttu-id="6bfbd-113">如需詳細資訊，請參閱[Clear CsDeviceUpdateFile](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateFile) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="6bfbd-113">For details, see the Help topic for the [Clear-CsDeviceUpdateFile](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateFile) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

