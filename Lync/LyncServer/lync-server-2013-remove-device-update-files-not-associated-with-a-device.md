---
title: Lync Server 2013：移除與裝置無關聯的裝置更新檔
description: Lync Server 2013：移除與裝置無關聯的裝置更新檔案。
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
ms.openlocfilehash: 8338f7274d1d27e2290d822324986238f4856fe4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553499"
---
# <a name="remove-device-update-files-not-associated-with-a-device-in-lync-server-2013"></a><span data-ttu-id="e0c6c-103">在 Lync Server 2013 中移除與裝置無關聯的裝置更新檔</span><span class="sxs-lookup"><span data-stu-id="e0c6c-103">Remove Device Update files not associated with a device in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0c6c-104">_**主題上次修改日期：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="e0c6c-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="e0c6c-105">每次將新裝置更新上傳至系統時，就會建立對應的裝置更新規則。</span><span class="sxs-lookup"><span data-stu-id="e0c6c-105">Each time new device updates are uploaded to the system, a corresponding device update rule is created.</span></span> <span data-ttu-id="e0c6c-106">依預設，這些新的裝置更新規則會指派給擱置狀態。</span><span class="sxs-lookup"><span data-stu-id="e0c6c-106">By default, these new device update rules are assigned to the Pending state.</span></span> <span data-ttu-id="e0c6c-107">這表示可以在測試裝置上下載和安裝規則，而不是在生產裝置上進行測試，這樣可讓您先測試更新，然後再讓使用者使用。</span><span class="sxs-lookup"><span data-stu-id="e0c6c-107">This means that the rules can be downloaded and installed on test devices, but not on production devices, which enables you to test the updates before making them available to users.</span></span> <span data-ttu-id="e0c6c-108">根據測試，您可以接受並部署或拒絕和刪除更新。</span><span class="sxs-lookup"><span data-stu-id="e0c6c-108">Based on the tests, you either accept and deploy or reject and delete the update.</span></span> <span data-ttu-id="e0c6c-109">當您拒絕更新時，裝置更新會與其裝置更新規則解除關聯。</span><span class="sxs-lookup"><span data-stu-id="e0c6c-109">When you reject an update, the device update is disassociated from its device update rule.</span></span>

<div>


<span data-ttu-id="e0c6c-110">使用 Windows PowerShell 和 **CsDeviceUpdateFile** 指令程式，可以移除與裝置不再相關聯的裝置更新檔案。</span><span class="sxs-lookup"><span data-stu-id="e0c6c-110">Device update files that are no longer associated with a device can be removed by using Windows PowerShell and the **Clear-CsDeviceUpdateFile** cmdlet.</span></span> <span data-ttu-id="e0c6c-111">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e0c6c-111">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e0c6c-112">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> 。</span><span class="sxs-lookup"><span data-stu-id="e0c6c-112">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


  - <span data-ttu-id="e0c6c-113">例如，下列命令會移除網頁伺服器 atl-cs-001.litwareinc.com 上任何已不再與裝置相關聯的裝置更新規則：</span><span class="sxs-lookup"><span data-stu-id="e0c6c-113">For example, the following command removes any device update rules on the Web server atl-cs-001.litwareinc.com that are no longer associated with a device:</span></span>
    
        Clear-CsDeviceUpdateFile -Identity "service:WebServer:atl-cs-001.litwareinc.com"

</div>

<span data-ttu-id="e0c6c-114">如需詳細資訊，請參閱 Help 主題 for the [CsDeviceUpdateFile](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateFile) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e0c6c-114">For details, see the Help topic for the [Clear-CsDeviceUpdateFile](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateFile) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

