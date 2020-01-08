---
title: Lync Server 2013：群組呼叫挑選的部署程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for Group Call Pickup
ms:assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945615(v=OCS.15)
ms:contentKeyID: 51541444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04ff5eda01c5436240c0baca2b1711bba8e9c996
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975624"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="8e369-102">Lync Server 2013 中群組呼叫挑選的部署程式</span><span class="sxs-lookup"><span data-stu-id="8e369-102">Deployment process for Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e369-103">_**主題上次修改日期：** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="8e369-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="8e369-104">本節概要說明部署群組呼叫挑選時所涉及的步驟。</span><span class="sxs-lookup"><span data-stu-id="8e369-104">This section provides an overview of the steps involved in deploying Group Call Pickup.</span></span> <span data-ttu-id="8e369-105">您必須先使用企業語音部署企業版或標準版，才能設定群組呼叫挑選。</span><span class="sxs-lookup"><span data-stu-id="8e369-105">You must deploy Enterprise Edition or Standard Edition with Enterprise Voice before you configure Group Call Pickup.</span></span> <span data-ttu-id="8e369-106">當您部署企業語音時，會安裝並啟用群組通話挑選所需的元件。</span><span class="sxs-lookup"><span data-stu-id="8e369-106">The components required by Group Call Pickup are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="group-call-pickup-deployment-process"></a><span data-ttu-id="8e369-107">群組呼叫進行挑選部署程式</span><span class="sxs-lookup"><span data-stu-id="8e369-107">Group Call Pickup Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8e369-108">分</span><span class="sxs-lookup"><span data-stu-id="8e369-108">Phase</span></span></th>
<th><span data-ttu-id="8e369-109">步驟</span><span class="sxs-lookup"><span data-stu-id="8e369-109">Steps</span></span></th>
<th><span data-ttu-id="8e369-110">必要的群組和角色</span><span class="sxs-lookup"><span data-stu-id="8e369-110">Required groups and roles</span></span></th>
<th><span data-ttu-id="8e369-111">部署檔</span><span class="sxs-lookup"><span data-stu-id="8e369-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e369-112">在拓撲中啟用 SEFAUtil 資源套件工具</span><span class="sxs-lookup"><span data-stu-id="8e369-112">Enable the SEFAUtil resource kit tool in the topology</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="8e369-113">使用<strong>新的 CsTrustedApplicationPool</strong> Cmdlet 來建立新的受信任的應用程式池。</span><span class="sxs-lookup"><span data-stu-id="8e369-113">Use the <strong>New-CsTrustedApplicationPool</strong> cmdlet to create a new trusted application pool.</span></span></p></li>
<li><p><span data-ttu-id="8e369-114">使用<strong>新的 CsTrustedApplication</strong> Cmdlet，將 SEFAUtil 工具指定為受信任的應用程式。</span><span class="sxs-lookup"><span data-stu-id="8e369-114">Use the <strong>New-CsTrustedApplication</strong> cmdlet to specify the SEFAUtil tool as trusted application.</span></span></p></li>
<li><p><span data-ttu-id="8e369-115">執行<strong>enable-CsTopology</strong> Cmdlet 來啟用拓撲。</span><span class="sxs-lookup"><span data-stu-id="8e369-115">Run the <strong>Enable-CsTopology</strong> cmdlet to enable the topology.</span></span></p></li>
<li><p><span data-ttu-id="8e369-116">在步驟1中建立的受信任的應用程式池中，在前端伺服器上安裝資源套件工具。</span><span class="sxs-lookup"><span data-stu-id="8e369-116">Install the resource kit tools on a Front End Server that is in the trusted application pool created in step 1.</span></span></p></li>
<li><p><span data-ttu-id="8e369-117">執行此程式以驗證 SEFAUtil 是否正常運作，只要執行它，即可在部署中顯示使用者的來電轉接設定。</span><span class="sxs-lookup"><span data-stu-id="8e369-117">Verify that SEFAUtil is running correctly by running it to display the call forwarding settings of a user in the deployment.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="8e369-118">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="8e369-118">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="8e369-119"><a href="lync-server-2013-deploy-the-sefautil-tool.md">在 Lync Server 2013 中部署 SEFAUtil 工具</a></span><span class="sxs-lookup"><span data-stu-id="8e369-119"><a href="lync-server-2013-deploy-the-sefautil-tool.md">Deploy the SEFAUtil tool in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e369-120">在 [呼叫公園軌道軌道] 表格中設定呼叫挑選編號範圍</span><span class="sxs-lookup"><span data-stu-id="8e369-120">Configure call pickup number ranges in the call park orbit table</span></span></p></td>
<td><p><span data-ttu-id="8e369-121">使用<strong>CSCallParkOrbit</strong> Cmdlet，在 [通話駐留軌道] 表格中建立呼叫挑選編號範圍，並將 [呼叫拾取] 範圍指派給 type GroupPickup。</span><span class="sxs-lookup"><span data-stu-id="8e369-121">Use the <strong>New-CSCallParkOrbit</strong> cmdlet to create call pickup number ranges in the call park orbit table and assign the call pickup ranges the type GroupPickup.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="8e369-122">您必須使用 Lync Server 管理命令介面來建立、修改、移除及查看 [通話寄存軌道] 表格中的 [群組呼叫挑選號碼] 範圍。</span><span class="sxs-lookup"><span data-stu-id="8e369-122">You must use Lync Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="8e369-123">在 Lync Server [控制台] 中無法使用 [群組呼叫挑選號碼] 範圍。</span><span class="sxs-lookup"><span data-stu-id="8e369-123">Group Call Pickup number ranges are not available in Lync Server Control Panel.</span></span>


</div>
<div>

> [!NOTE]  
> <span data-ttu-id="8e369-124">若要與現有的撥號方案進行無縫整合，數位範圍通常會設定為虛擬延伸區塊。</span><span class="sxs-lookup"><span data-stu-id="8e369-124">For seamless integration with existing dial plans, number ranges are typically configured as a block of virtual extensions.</span></span> <span data-ttu-id="8e369-125">不支援在 [通話駐留軌道] 表格中，將直向內撥（已有）數位指派為範圍數位。</span><span class="sxs-lookup"><span data-stu-id="8e369-125">Assigning Direct Inward Dialing (DID) numbers as range numbers in the call park orbit table is not supported.</span></span>


</div></td>
<td><p><span data-ttu-id="8e369-126">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="8e369-126">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="8e369-127">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="8e369-127">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="8e369-128">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="8e369-128">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="8e369-129">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="8e369-129">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="8e369-130"><a href="lync-server-2013-configure-call-pickup-group-numbers.md">在 Lync Server 2013 中設定呼叫挑選群組號碼</a></span><span class="sxs-lookup"><span data-stu-id="8e369-130"><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Configure call pickup group numbers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e369-131">指派呼叫挑選號碼給使用者，並為使用者啟用群組呼叫分揀</span><span class="sxs-lookup"><span data-stu-id="8e369-131">Assign a call pickup number to users, and enable Group Call Pickup for the users</span></span></p></td>
<td><p><span data-ttu-id="8e369-132">在 SEFAUtil 資源套件工具中使用/enablegrouppickup 參數，以啟用群組通話分揀，並為使用者指派呼叫挑選號碼。</span><span class="sxs-lookup"><span data-stu-id="8e369-132">Use the /enablegrouppickup parameter in the SEFAUtil resource kit tool to enable Group Call Pickup and assign a call pickup number for users.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="8e369-133"><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">在 Lync Server 2013 中為使用者啟用群組呼叫挑選，並指派群組號碼</a></span><span class="sxs-lookup"><span data-stu-id="8e369-133"><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e369-134">通知使用者已指派的電話提貨號碼和任何其他感興趣的號碼</span><span class="sxs-lookup"><span data-stu-id="8e369-134">Notify users of their assigned call pickup number and any other number of interest</span></span></p></td>
<td><p><span data-ttu-id="8e369-135">因為任何使用者都可以撥打對群組呼叫使用者所做的通話，所以使用者可能想要監視一個以上的群組。</span><span class="sxs-lookup"><span data-stu-id="8e369-135">Because any user can retrieve a call made to a Group Call Pickup user, users may want to monitor more than one group.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="8e369-136"><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">在 Lync Server 2013 中將群組呼叫挑選指派給使用者</a></span><span class="sxs-lookup"><span data-stu-id="8e369-136"><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">Communicate Group Call Pickup assignments to users in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e369-137">驗證您的群組呼叫裝貨部署</span><span class="sxs-lookup"><span data-stu-id="8e369-137">Verify your Group Call Pickup deployment</span></span></p></td>
<td><p><span data-ttu-id="8e369-138">測試放及檢索通話，以確保您的設定如預期的那樣正常運作。</span><span class="sxs-lookup"><span data-stu-id="8e369-138">Test placing and retrieving calls to make sure that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="8e369-139"><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">可選在 Lync Server 2013 中驗證群組呼叫裝貨部署</a></span><span class="sxs-lookup"><span data-stu-id="8e369-139"><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">(Optional) Verify the Group Call Pickup deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

