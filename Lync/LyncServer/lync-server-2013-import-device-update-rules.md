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
ms.openlocfilehash: 9ddeb9d37d36d6ab18467e04e4a7c46b9b8576fa
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526720"
---
# <a name="import-device-update-rules-in-lync-server-2013"></a><span data-ttu-id="11d5a-102">在 Lync Server 2013 中匯入裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="11d5a-102">Import Device Update rules in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11d5a-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="11d5a-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="11d5a-104">只能使用 Windows PowerShell 和 **Import-CsDeviceUpdate** Cmdlet 匯入裝置更新規則。</span><span class="sxs-lookup"><span data-stu-id="11d5a-104">Device update rules can be imported only by using Windows PowerShell and the **Import-CsDeviceUpdate** cmdlet.</span></span> <span data-ttu-id="11d5a-105">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="11d5a-105">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="11d5a-106">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> 。</span><span class="sxs-lookup"><span data-stu-id="11d5a-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="to-import-device-update-rules-to-a-single-web-server"></a><span data-ttu-id="11d5a-107">將裝置更新規則匯入到單一網頁伺服器</span><span class="sxs-lookup"><span data-stu-id="11d5a-107">To import device update rules to a single web server</span></span>

  - <span data-ttu-id="11d5a-108">下列命令會將裝置更新規則匯入至網頁伺服器 atl-cs-001.litwareinc.com：</span><span class="sxs-lookup"><span data-stu-id="11d5a-108">The following command imports device update rules to the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Import-CsDeviceUpdate -Identity "service:WebServer:atl-cs-001.litwareinc.com" -FileName C:\Updates\UCUpdates.cab

</div>

<div>

## <a name="to-import-device-update-rules-to-all-your-web-servers"></a><span data-ttu-id="11d5a-109">將裝置更新規則匯入至所有網頁伺服器</span><span class="sxs-lookup"><span data-stu-id="11d5a-109">To import device update rules to all your web servers</span></span>

  - <span data-ttu-id="11d5a-110">在此範例中，裝置更新規則會匯入到組織中部署的所有網頁伺服器。</span><span class="sxs-lookup"><span data-stu-id="11d5a-110">In this example, device update rules are imported to all the Web servers deployed in your organization.</span></span> <span data-ttu-id="11d5a-111">若要使用此命令， \\ \\ \\ 必須共用資料夾 atl-fs-001.litwareinc.com 更新，而且所有網頁伺服器皆可使用該資料夾。</span><span class="sxs-lookup"><span data-stu-id="11d5a-111">For this command to work, the folder \\\\atl-fs-001.litwareinc.com\\Updates must be shared and available to all the Web servers.</span></span>
    
        Get-CsService -WebServer | ForEach-Object {Import-CsDeviceUpdate -Identity $_.Identity -FileName \\atl-fs-001.litwareinc.com\Updates\UCUpdates.cab}

</div>

<span data-ttu-id="11d5a-112">如需詳細資訊，請參閱 [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="11d5a-112">For details, see the Help topic for the [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="11d5a-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="11d5a-113">See Also</span></span>


[<span data-ttu-id="11d5a-114">在 Lync Server 2013 中查看裝置更新規則的相關資訊</span><span class="sxs-lookup"><span data-stu-id="11d5a-114">View information about Device Update rules in Lync Server 2013</span></span>](lync-server-2013-view-information-about-device-update-rules.md)  
[<span data-ttu-id="11d5a-115">核准 Lync Server 2013 中的裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="11d5a-115">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

