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
ms.openlocfilehash: 55ecc35d2724fa8c635b9d4099764c25e76874c9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756227"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="export-a-voice-route-configuration-file-in-lync-server-2013"></a><span data-ttu-id="acc35-102">在 Lync Server 2013 中匯出語音路由設定檔</span><span class="sxs-lookup"><span data-stu-id="acc35-102">Export a voice route configuration file in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="acc35-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="acc35-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="acc35-104">如果您想要儲存語音路由設定，但不發佈它，請依照下列步驟使用 Lync Server [控制台] 的 [匯出及匯入] 命令來儲存及取得語音路由設定的快照。</span><span class="sxs-lookup"><span data-stu-id="acc35-104">If you want to save your voice routing configuration without publishing it, follow these steps to use the Lync Server Control Panel configuration export and import commands to save and retrieve a snapshot of your voice routing configuration.</span></span> <span data-ttu-id="acc35-105">當您匯入語音路由設定檔（vcfg），但同時又在伺服器上對語音路由設定進行變更時，Lync Server [控制台] 中的 [**語音路由**] 群組中的頁面將會顯示 [語音路由] 中有未提交的變更。</span><span class="sxs-lookup"><span data-stu-id="acc35-105">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Lync Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="acc35-106">那些未提交的變更是兩個需要調解的設定之間的差異。</span><span class="sxs-lookup"><span data-stu-id="acc35-106">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>

<span data-ttu-id="acc35-107">如果您已對群組內任何頁面上的設定進行任何未提交的變更，這些變更就會儲存在匯出的語音設定檔案（vcfg）中。</span><span class="sxs-lookup"><span data-stu-id="acc35-107">If you have made any uncommitted changes to the settings on any page within the group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="acc35-108">這可讓您在發佈變更前，在多個會話期間進行語音路由設定的變更。</span><span class="sxs-lookup"><span data-stu-id="acc35-108">This enables you to make voice routing configuration changes during multiple sessions before you publish the changes.</span></span>

<div>

## <a name="to-export-a-voice-routing-configuration"></a><span data-ttu-id="acc35-109">匯出語音路由設定</span><span class="sxs-lookup"><span data-stu-id="acc35-109">To export a voice routing configuration</span></span>

1.  <span data-ttu-id="acc35-110">以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="acc35-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="acc35-111">如需詳細資訊，請參閱[Lync Server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="acc35-111">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="acc35-112">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="acc35-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="acc35-113">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="acc35-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="acc35-114">在左側導覽列中，按一下 [**語音路由**]。</span><span class="sxs-lookup"><span data-stu-id="acc35-114">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="acc35-115">在 [**動作**] 功能表上，按一下 [**匯出配置**]。</span><span class="sxs-lookup"><span data-stu-id="acc35-115">On the **Actions** menu, click **Export configuration**.</span></span>

5.  <span data-ttu-id="acc35-116">指定位置和檔案名，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="acc35-116">Specify a location and file name, and then click **Save**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="acc35-117">請參閱</span><span class="sxs-lookup"><span data-stu-id="acc35-117">See Also</span></span>


[<span data-ttu-id="acc35-118">在 Lync Server 2013 中匯入語音路由組態檔</span><span class="sxs-lookup"><span data-stu-id="acc35-118">Import a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-import-a-voice-route-configuration-file.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

