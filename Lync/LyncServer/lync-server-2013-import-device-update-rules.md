---
title: Lync Server 2013：匯入裝置更新規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Import Device Update rules
ms:assetid: 919e9c87-912b-4bc9-92e7-5998fc2e0bf0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994056(v=OCS.15)
ms:contentKeyID: 51803967
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 872f729584f14011d18920a676c32205d38c7f62
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763847"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-device-update-rules-in-lync-server-2013"></a><span data-ttu-id="bc4d8-102">在 Lync Server 2013 中匯入裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="bc4d8-102">Import Device Update rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc4d8-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="bc4d8-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="bc4d8-104">裝置更新規則只能使用 Windows PowerShell 和**CsDeviceUpdate** Cmdlet 來匯入。</span><span class="sxs-lookup"><span data-stu-id="bc4d8-104">Device update rules can be imported only by using Windows PowerShell and the **Import-CsDeviceUpdate** cmdlet.</span></span> <span data-ttu-id="bc4d8-105">這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。</span><span class="sxs-lookup"><span data-stu-id="bc4d8-105">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bc4d8-106">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>。</span><span class="sxs-lookup"><span data-stu-id="bc4d8-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="to-import-device-update-rules-to-a-single-web-server"></a><span data-ttu-id="bc4d8-107">將裝置更新規則匯入到單一網頁伺服器</span><span class="sxs-lookup"><span data-stu-id="bc4d8-107">To import device update rules to a single web server</span></span>

  - <span data-ttu-id="bc4d8-108">下列命令會將裝置更新規則匯入至 Web 服務器 atl-cs-001.litwareinc.com：</span><span class="sxs-lookup"><span data-stu-id="bc4d8-108">The following command imports device update rules to the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Import-CsDeviceUpdate -Identity "service:WebServer:atl-cs-001.litwareinc.com" -FileName C:\Updates\UCUpdates.cab

</div>

<div>

## <a name="to-import-device-update-rules-to-all-your-web-servers"></a><span data-ttu-id="bc4d8-109">將裝置更新規則匯入到您的所有 web 伺服器</span><span class="sxs-lookup"><span data-stu-id="bc4d8-109">To import device update rules to all your web servers</span></span>

  - <span data-ttu-id="bc4d8-110">在這個範例中，裝置更新規則會匯入到貴組織中部署的所有 Web 服務器。</span><span class="sxs-lookup"><span data-stu-id="bc4d8-110">In this example, device update rules are imported to all the Web servers deployed in your organization.</span></span> <span data-ttu-id="bc4d8-111">若要使用此命令，必須共用\\ \\資料夾\\atl-fs-001.litwareinc.com 更新，且所有 Web 服務器都能使用。</span><span class="sxs-lookup"><span data-stu-id="bc4d8-111">For this command to work, the folder \\\\atl-fs-001.litwareinc.com\\Updates must be shared and available to all the Web servers.</span></span>
    
        Get-CsService -WebServer | ForEach-Object {Import-CsDeviceUpdate -Identity $_.Identity -FileName \\atl-fs-001.litwareinc.com\Updates\UCUpdates.cab}

</div>

<span data-ttu-id="bc4d8-112">如需詳細資訊，請參閱匯[入 CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="bc4d8-112">For details, see the Help topic for the [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bc4d8-113">請參閱</span><span class="sxs-lookup"><span data-stu-id="bc4d8-113">See Also</span></span>


[<span data-ttu-id="bc4d8-114">在 Lync Server 2013 中查看裝置更新規則的相關資訊</span><span class="sxs-lookup"><span data-stu-id="bc4d8-114">View information about Device Update rules in Lync Server 2013</span></span>](lync-server-2013-view-information-about-device-update-rules.md)  
[<span data-ttu-id="bc4d8-115">在 Lync Server 2013 中核准裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="bc4d8-115">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

