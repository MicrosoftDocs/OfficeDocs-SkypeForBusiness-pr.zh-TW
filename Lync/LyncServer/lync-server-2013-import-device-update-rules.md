---
title: Lync Server 2013： 匯入裝置更新規則
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
ms.openlocfilehash: abcb7b911d4f7cd21fd9fbb3ac232048db8691ba
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42131316"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="import-device-update-rules-in-lync-server-2013"></a><span data-ttu-id="87f38-102">匯入 Lync Server 2013 中的裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="87f38-102">Import Device Update rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87f38-103">_**上次修改主題：** 2013年-02-23_</span><span class="sxs-lookup"><span data-stu-id="87f38-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="87f38-104">只能透過使用 Windows PowerShell 和**Import-csdeviceupdate** cmdlet 可以匯入裝置更新規則。</span><span class="sxs-lookup"><span data-stu-id="87f38-104">Device update rules can be imported only by using Windows PowerShell and the **Import-CsDeviceUpdate** cmdlet.</span></span> <span data-ttu-id="87f38-105">從 Lync Server 2013 管理命令介面或 Windows PowerShell 的遠端工作階段，可以執行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="87f38-105">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="87f38-106">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 部落格文章 「 快速開始:: 管理 Microsoft Lync Server 2010 使用遠端 PowerShell 」 在<A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>。</span><span class="sxs-lookup"><span data-stu-id="87f38-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="to-import-device-update-rules-to-a-single-web-server"></a><span data-ttu-id="87f38-107">若要匯入裝置更新規則的單一網頁伺服器</span><span class="sxs-lookup"><span data-stu-id="87f38-107">To import device update rules to a single web server</span></span>

  - <span data-ttu-id="87f38-108">下列命令會將裝置更新規則匯入網頁伺服器 atl-edge-001.litwareinc.com-atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="87f38-108">The following command imports device update rules to the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Import-CsDeviceUpdate -Identity "service:WebServer:atl-cs-001.litwareinc.com" -FileName C:\Updates\UCUpdates.cab

</div>

<div>

## <a name="to-import-device-update-rules-to-all-your-web-servers"></a><span data-ttu-id="87f38-109">若要匯入裝置更新規則至所有網頁伺服器</span><span class="sxs-lookup"><span data-stu-id="87f38-109">To import device update rules to all your web servers</span></span>

  - <span data-ttu-id="87f38-110">在這個範例中，在組織中部署的所有網頁伺服器都會匯都入裝置更新規則。</span><span class="sxs-lookup"><span data-stu-id="87f38-110">In this example, device update rules are imported to all the Web servers deployed in your organization.</span></span> <span data-ttu-id="87f38-111">此命令可工作時，該資料夾的\\ \\atl-fs-001.litwareinc.com\\更新必須是共用，並可供所有網頁伺服器。</span><span class="sxs-lookup"><span data-stu-id="87f38-111">For this command to work, the folder \\\\atl-fs-001.litwareinc.com\\Updates must be shared and available to all the Web servers.</span></span>
    
        Get-CsService -WebServer | ForEach-Object {Import-CsDeviceUpdate -Identity $_.Identity -FileName \\atl-fs-001.litwareinc.com\Updates\UCUpdates.cab}

</div>

<span data-ttu-id="87f38-112">如需詳細資訊，請參閱[Import-csdeviceupdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="87f38-112">For details, see the Help topic for the [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="87f38-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="87f38-113">See Also</span></span>


[<span data-ttu-id="87f38-114">檢視 Lync Server 2013 中的裝置更新規則的相關資訊</span><span class="sxs-lookup"><span data-stu-id="87f38-114">View information about Device Update rules in Lync Server 2013</span></span>](lync-server-2013-view-information-about-device-update-rules.md)  
[<span data-ttu-id="87f38-115">核准 Lync Server 2013 中的裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="87f38-115">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

