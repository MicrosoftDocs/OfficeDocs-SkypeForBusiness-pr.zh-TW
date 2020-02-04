---
title: 驗證試驗集區與舊版集區共存
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: 597d0fa6-ca04-4521-b1c2-72d7f35ecd08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204914(v=OCS.15)
ms:contentKeyID: 48184209
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7585970a53ffd94959653555dad8a02724ba2f03
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730883"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="765a6-102">驗證試驗集區與舊版集區共存</span><span class="sxs-lookup"><span data-stu-id="765a6-102">Verify pilot pool coexistence with legacy pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="765a6-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="765a6-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<div>

## <a name="verify-the-pool-in-office-communications-server-2007-r2-administrative-tool"></a><span data-ttu-id="765a6-104">驗證 Office 通訊伺服器 2007 R2 管理工具中的資源庫</span><span class="sxs-lookup"><span data-stu-id="765a6-104">Verify the Pool in Office Communications Server 2007 R2 Administrative Tool</span></span>

1.  <span data-ttu-id="765a6-105">開啟 Office 通訊伺服器 2007 R2 管理工具。</span><span class="sxs-lookup"><span data-stu-id="765a6-105">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="765a6-106">展開 [**目錄林**] 節點，展開 [**標準版伺服器**] 或 [**企業版池**] 節點，然後展開 [池] 或 [伺服器名稱]。</span><span class="sxs-lookup"><span data-stu-id="765a6-106">Expand the **Forest** node, expand the **Standard Edition Servers** or **Enterprise pools** node, and then expand the pool or server name.</span></span>

3.  <span data-ttu-id="765a6-107">確定 Office 通訊伺服器 2007 R2 服務正在該池中執行。</span><span class="sxs-lookup"><span data-stu-id="765a6-107">Ensure that the Office Communications Server 2007 R2 services are running on the pool.</span></span>
    
    <span data-ttu-id="765a6-108">![Office Communications Server 2007 R2 管理主控台](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2 管理主控台")</span><span class="sxs-lookup"><span data-stu-id="765a6-108">![Office Communications Server 2007 R2 Admin Console](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2 Admin Console")</span></span>  

</div>

<div>

## <a name="verify-the-pilot-pool-in-lync-server-2013-control-panel"></a><span data-ttu-id="765a6-109">確認 Lync Server 2013 [控制台] 中的 [試驗] 池</span><span class="sxs-lookup"><span data-stu-id="765a6-109">Verify the Pilot Pool in Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="765a6-110">從屬於 CsAdministrator 角色成員的使用者帳戶登入 Lync Server 2013 前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="765a6-110">From a user account that is a member of the CsAdministrator role, log on to the Lync Server 2013 Front End server.</span></span>

2.  <span data-ttu-id="765a6-111">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="765a6-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="765a6-112">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="765a6-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="765a6-113">按一下 [**拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="765a6-113">Click **Topology**.</span></span>

4.  <span data-ttu-id="765a6-114">確認您部署的伺服器存在於您的試驗區池中。</span><span class="sxs-lookup"><span data-stu-id="765a6-114">Verify that the servers you deployed are present in your pilot pool.</span></span>
    
    <span data-ttu-id="765a6-115">![[Lync Server 控制台拓撲] 頁面](images/JJ204914.a3d1ba5f-c1a7-45e8-b9a5-7cb07b01af8c(OCS.15).jpg "[Lync Server 控制台拓撲] 頁面")</span><span class="sxs-lookup"><span data-stu-id="765a6-115">![Lync Server Control Panel Topology page](images/JJ204914.a3d1ba5f-c1a7-45e8-b9a5-7cb07b01af8c(OCS.15).jpg "Lync Server Control Panel Topology page")</span></span>  

</div>

<div>

## <a name="verify-lync-server-2013-services-have-started"></a><span data-ttu-id="765a6-116">驗證 Lync Server 2013 服務已啟動</span><span class="sxs-lookup"><span data-stu-id="765a6-116">Verify Lync Server 2013 services have started</span></span>

1.  <span data-ttu-id="765a6-117">在 Lync Server 2013 前端伺服器上，從 [**管理工具**] 群組開啟 [**服務**] 小工具。</span><span class="sxs-lookup"><span data-stu-id="765a6-117">On the Lync Server 2013 Front End Server, open the **Services** applet from the **Administrative Tools** group.</span></span>

2.  <span data-ttu-id="765a6-118">確認列出的服務與下圖中的清單相符。</span><span class="sxs-lookup"><span data-stu-id="765a6-118">Verify that the services listed match the list in the following figure.</span></span>
    
    <span data-ttu-id="765a6-119">![顯示已啟動 Lync 服務的服務頁面](images/JJ204914.fd35d54a-2ab6-4c09-b5e9-fd5bf10f6f51(OCS.15).jpg "顯示已啟動 Lync 服務的服務頁面")</span><span class="sxs-lookup"><span data-stu-id="765a6-119">![Services page showing Lync services started](images/JJ204914.fd35d54a-2ab6-4c09-b5e9-fd5bf10f6f51(OCS.15).jpg "Services page showing Lync services started")</span></span>  

</div>

</div>

<span> </span>

</div>

</div>

</div>

