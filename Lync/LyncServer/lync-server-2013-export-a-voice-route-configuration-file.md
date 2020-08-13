---
title: Lync Server 2013：匯出語音路由設定檔
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export a voice route configuration file
ms:assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398081(v=OCS.15)
ms:contentKeyID: 48183248
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b1549cabf8163275c202075dcfc7ef081b38d20
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202379"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="export-a-voice-route-configuration-file-in-lync-server-2013"></a><span data-ttu-id="2c91f-102">在 Lync Server 2013 中匯出語音路由設定檔</span><span class="sxs-lookup"><span data-stu-id="2c91f-102">Export a voice route configuration file in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c91f-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="2c91f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="2c91f-104">如果您想要儲存語音路由設定，但未發佈它，請遵循下列步驟，使用 Lync Server 控制台的 [匯出] 和 [匯入] 命令，儲存並取得您的語音路由設定快照。</span><span class="sxs-lookup"><span data-stu-id="2c91f-104">If you want to save your voice routing configuration without publishing it, follow these steps to use the Lync Server Control Panel configuration export and import commands to save and retrieve a snapshot of your voice routing configuration.</span></span> <span data-ttu-id="2c91f-105">當您匯入語音路由設定檔 (。 vcfg) ，但目前在伺服器上對語音路由設定進行變更時，Lync Server [控制台] 中的 [**語音**路由] 群組中的頁面會指出有未認可的變更可供語音路由使用。</span><span class="sxs-lookup"><span data-stu-id="2c91f-105">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Lync Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="2c91f-106">這些未認可的變更會使兩個設定出現差異且需要重新調整。</span><span class="sxs-lookup"><span data-stu-id="2c91f-106">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>

<span data-ttu-id="2c91f-107">如果您已對群組內任何頁面上的設定進行任何未認可的變更，則所做的變更會儲存在匯出的語音設定檔中 (。 vcfg) 。</span><span class="sxs-lookup"><span data-stu-id="2c91f-107">If you have made any uncommitted changes to the settings on any page within the group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="2c91f-108">這可讓您在發佈變更之前，在多個會話期間進行語音路由設定變更。</span><span class="sxs-lookup"><span data-stu-id="2c91f-108">This enables you to make voice routing configuration changes during multiple sessions before you publish the changes.</span></span>

<div>

## <a name="to-export-a-voice-routing-configuration"></a><span data-ttu-id="2c91f-109">若要匯出語音路由設定</span><span class="sxs-lookup"><span data-stu-id="2c91f-109">To export a voice routing configuration</span></span>

1.  <span data-ttu-id="2c91f-110">以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="2c91f-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="2c91f-111">如需詳細資訊，請參閱[在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="2c91f-111">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="2c91f-112">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="2c91f-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2c91f-113">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="2c91f-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2c91f-114">在左導覽列中，按一下 **[語音路由]**。</span><span class="sxs-lookup"><span data-stu-id="2c91f-114">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="2c91f-115">在 **[執行]** 功能表上，按一下 **[匯出設定]**。</span><span class="sxs-lookup"><span data-stu-id="2c91f-115">On the **Actions** menu, click **Export configuration**.</span></span>

5.  <span data-ttu-id="2c91f-116">指定位置和檔案名稱，然後按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="2c91f-116">Specify a location and file name, and then click **Save**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2c91f-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2c91f-117">See Also</span></span>


[<span data-ttu-id="2c91f-118">在 Lync Server 2013 中匯入語音路由設定檔</span><span class="sxs-lookup"><span data-stu-id="2c91f-118">Import a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-import-a-voice-route-configuration-file.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

