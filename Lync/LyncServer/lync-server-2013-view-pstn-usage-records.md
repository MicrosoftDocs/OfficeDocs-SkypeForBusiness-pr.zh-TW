---
title: Lync Server 2013：查看 PSTN 使用方式記錄
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View PSTN usage records
ms:assetid: 65025c78-c263-472c-9ff9-e170588f10b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398458(v=OCS.15)
ms:contentKeyID: 48184361
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 558efe06fb8a91a4a1f923b004756b5791e4367e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518440"
---
# <a name="view-pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="3d120-102">在 Lync Server 2013 中查看 PSTN 使用方式記錄</span><span class="sxs-lookup"><span data-stu-id="3d120-102">View PSTN usage records in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d120-103">_**主題上次修改日期：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="3d120-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="3d120-104">公用交換電話網路 (PSTN) 使用方式記錄會指定組織內的各個使用者或使用者群組可以進行的通話等級 (如內線、當地或長途電話)。</span><span class="sxs-lookup"><span data-stu-id="3d120-104">A public switched telephone network (PSTN) usage record specifies a class of call (such as internal, local, or long distance) that can be made by various users or groups of users in an organization.</span></span> <span data-ttu-id="3d120-105">如需詳細資訊，請參閱規劃檔中的 [Lync Server 2013 中的 PSTN 使用方式記錄](lync-server-2013-pstn-usage-records.md) 。</span><span class="sxs-lookup"><span data-stu-id="3d120-105">For details, see [PSTN usage records in Lync Server 2013](lync-server-2013-pstn-usage-records.md) in the Planning documentation.</span></span>

<div>

## <a name="to-view-a-pstn-usage-record-by-using-lync-server-control-panel"></a><span data-ttu-id="3d120-106">使用 Lync Server 控制台來查看 PSTN 使用方式記錄</span><span class="sxs-lookup"><span data-stu-id="3d120-106">To view a PSTN usage record by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="3d120-107">以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="3d120-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="3d120-108">如需詳細資訊，請參閱 [在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="3d120-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="3d120-109">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="3d120-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3d120-110">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="3d120-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3d120-111">在左導覽列中，按一下 **[語音路由]**，然後按一下 **[PSTN 使用方式]**。</span><span class="sxs-lookup"><span data-stu-id="3d120-111">In the left navigation bar, click **Voice Routing** and then click **PSTN Usage**.</span></span>

4.  <span data-ttu-id="3d120-112">在 **[PSTN 使用方式]** 頁面上，反白想要檢視的 PSTN 使用方式記錄，並按一下 **[編輯]**，然後按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="3d120-112">On the **PSTN Usage** page, highlight the PSTN usage record you want to view, click **Edit** and then click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3d120-113">所選取 PSTN 使用方式記錄的唯讀頁面顯示相關聯的路由及相關聯的語音原則。</span><span class="sxs-lookup"><span data-stu-id="3d120-113">A read-only page of the selected PSTN usage record shows the associated routes and associated voice policies.</span></span>

    
    </div>

</div>

<div>

## <a name="viewing-pstn-usage-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3d120-114">使用 Windows PowerShell Cmdlet 來查看 PSTN 使用狀況資訊</span><span class="sxs-lookup"><span data-stu-id="3d120-114">Viewing PSTN Usage Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="3d120-115">您也可以使用 Windows PowerShell 和 **Get-CsPstnUsage** Cmdlet 來查看 PSTN 使用方式。</span><span class="sxs-lookup"><span data-stu-id="3d120-115">You can also view PSTN usages by using Windows PowerShell and the **Get-CsPstnUsage** cmdlet.</span></span> <span data-ttu-id="3d120-116">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3d120-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="3d120-117">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="3d120-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-pstn-usage-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3d120-118">使用 Windows PowerShell Cmdlet 來查看 PSTN 使用狀況資訊</span><span class="sxs-lookup"><span data-stu-id="3d120-118">To view PSTN usage information by using Windows PowerShell cmdlets</span></span>

  - <span data-ttu-id="3d120-119">若要查看所有 PSTN 使用方式的相關資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：</span><span class="sxs-lookup"><span data-stu-id="3d120-119">To view information about all of your PSTN usages, type the following command in the Lync Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsPstnUsage
    
    <span data-ttu-id="3d120-120">此命令會傳回與下列相似的資訊：</span><span class="sxs-lookup"><span data-stu-id="3d120-120">This command returns information similar to the following:</span></span>
    
        Identity : Global
        Usage    : {Internal, Local, Long Distance}

</div>

<span data-ttu-id="3d120-121">如需詳細資訊，請參閱 [Get-CsPstnUsage](https://docs.microsoft.com/powershell/module/skype/Get-CsPstnUsage)。</span><span class="sxs-lookup"><span data-stu-id="3d120-121">For details, see [Get-CsPstnUsage](https://docs.microsoft.com/powershell/module/skype/Get-CsPstnUsage).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3d120-122">另請參閱</span><span class="sxs-lookup"><span data-stu-id="3d120-122">See Also</span></span>


[<span data-ttu-id="3d120-123">在 Lync Server 2013 中建立語音原則和設定 PSTN 使用方式記錄</span><span class="sxs-lookup"><span data-stu-id="3d120-123">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="3d120-124">在 Lync Server 2013 中修改語音原則和設定 PSTN 使用方式記錄</span><span class="sxs-lookup"><span data-stu-id="3d120-124">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

