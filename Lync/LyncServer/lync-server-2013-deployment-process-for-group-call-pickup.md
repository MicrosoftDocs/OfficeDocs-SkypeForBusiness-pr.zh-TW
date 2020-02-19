---
title: Lync Server 2013： 部署程序的群組來電接聽
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Group Call Pickup
ms:assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945615(v=OCS.15)
ms:contentKeyID: 51541444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 150434b57aa90048c1009851473349093435c116
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137182"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="3225f-102">部署程序的 Lync Server 2013 中的 [群組來電接聽</span><span class="sxs-lookup"><span data-stu-id="3225f-102">Deployment process for Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3225f-103">_**上次修改主題：** 2013年-02-25_</span><span class="sxs-lookup"><span data-stu-id="3225f-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="3225f-104">本節提供部署群組來電接聽的相關步驟的概觀。</span><span class="sxs-lookup"><span data-stu-id="3225f-104">This section provides an overview of the steps involved in deploying Group Call Pickup.</span></span> <span data-ttu-id="3225f-105">設定群組來電接聽之前，您必須部署 Enterprise Edition 或 Standard Edition 與 Enterprise Voice。</span><span class="sxs-lookup"><span data-stu-id="3225f-105">You must deploy Enterprise Edition or Standard Edition with Enterprise Voice before you configure Group Call Pickup.</span></span> <span data-ttu-id="3225f-106">群組來電接聽所需的元件會安裝並啟用當您部署企業語音。</span><span class="sxs-lookup"><span data-stu-id="3225f-106">The components required by Group Call Pickup are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="group-call-pickup-deployment-process"></a><span data-ttu-id="3225f-107">群組通話收取部署程序</span><span class="sxs-lookup"><span data-stu-id="3225f-107">Group Call Pickup Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3225f-108">階段</span><span class="sxs-lookup"><span data-stu-id="3225f-108">Phase</span></span></th>
<th><span data-ttu-id="3225f-109">步驟</span><span class="sxs-lookup"><span data-stu-id="3225f-109">Steps</span></span></th>
<th><span data-ttu-id="3225f-110">所需群組和角色</span><span class="sxs-lookup"><span data-stu-id="3225f-110">Required groups and roles</span></span></th>
<th><span data-ttu-id="3225f-111">部署文件</span><span class="sxs-lookup"><span data-stu-id="3225f-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3225f-112">啟用拓撲的 SEFAUtil resource kit 工具</span><span class="sxs-lookup"><span data-stu-id="3225f-112">Enable the SEFAUtil resource kit tool in the topology</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="3225f-113">使用<strong>New-cstrustedapplicationpool</strong> cmdlet 來建立新的受信任的應用程式集區。</span><span class="sxs-lookup"><span data-stu-id="3225f-113">Use the <strong>New-CsTrustedApplicationPool</strong> cmdlet to create a new trusted application pool.</span></span></p></li>
<li><p><span data-ttu-id="3225f-114">若要指定 SEFAUtil 工具為信任的應用程式使用<strong>New-cstrustedapplication</strong> cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3225f-114">Use the <strong>New-CsTrustedApplication</strong> cmdlet to specify the SEFAUtil tool as trusted application.</span></span></p></li>
<li><p><span data-ttu-id="3225f-115">執行<strong>Enable-cstopology</strong> cmdlet 來啟用拓撲。</span><span class="sxs-lookup"><span data-stu-id="3225f-115">Run the <strong>Enable-CsTopology</strong> cmdlet to enable the topology.</span></span></p></li>
<li><p><span data-ttu-id="3225f-116">在步驟 1 中建立信任的應用程式集區中以前端伺服器上安裝 resource kit 工具。</span><span class="sxs-lookup"><span data-stu-id="3225f-116">Install the resource kit tools on a Front End Server that is in the trusted application pool created in step 1.</span></span></p></li>
<li><p><span data-ttu-id="3225f-117">確認 SEFAUtil 正常執行藉由執行以顯示來電轉接的部署中的使用者設定。</span><span class="sxs-lookup"><span data-stu-id="3225f-117">Verify that SEFAUtil is running correctly by running it to display the call forwarding settings of a user in the deployment.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="3225f-118">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="3225f-118">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="3225f-119"><a href="lync-server-2013-deploy-the-sefautil-tool.md">部署 Lync Server 2013 的 SEFAUtil 工具</a></span><span class="sxs-lookup"><span data-stu-id="3225f-119"><a href="lync-server-2013-deploy-the-sefautil-tool.md">Deploy the SEFAUtil tool in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3225f-120">設定通話駐留軌道表中的呼叫收取的號碼範圍</span><span class="sxs-lookup"><span data-stu-id="3225f-120">Configure call pickup number ranges in the call park orbit table</span></span></p></td>
<td><p><span data-ttu-id="3225f-121">使用<strong>New-cscallparkorbit</strong> cmdlet 來建立通話駐留軌道表中的通話收取] 目錄的數字範圍和指派通話收取範圍類型 GroupPickup。</span><span class="sxs-lookup"><span data-stu-id="3225f-121">Use the <strong>New-CSCallParkOrbit</strong> cmdlet to create call pickup number ranges in the call park orbit table and assign the call pickup ranges the type GroupPickup.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="3225f-122">您必須使用 Lync Server 管理命令介面來建立、 修改、 移除和檢視通話駐留軌道表中的群組來電接聽的號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="3225f-122">You must use Lync Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="3225f-123">群組呼叫收取號碼範圍不在 Lync Server Control Panel 中使用。</span><span class="sxs-lookup"><span data-stu-id="3225f-123">Group Call Pickup number ranges are not available in Lync Server Control Panel.</span></span>


</div>
<div>

> [!NOTE]  
> <span data-ttu-id="3225f-124">與現有的撥號對應表計劃的緊密整合，針對號碼範圍通常設定為虛擬分機區塊。</span><span class="sxs-lookup"><span data-stu-id="3225f-124">For seamless integration with existing dial plans, number ranges are typically configured as a block of virtual extensions.</span></span> <span data-ttu-id="3225f-125">不支援將直接向內撥號 (DID) 號碼指派為通話駐留軌道表中的 range 數字。</span><span class="sxs-lookup"><span data-stu-id="3225f-125">Assigning Direct Inward Dialing (DID) numbers as range numbers in the call park orbit table is not supported.</span></span>


</div></td>
<td><p><span data-ttu-id="3225f-126">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="3225f-126">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="3225f-127">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="3225f-127">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="3225f-128">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="3225f-128">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="3225f-129">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="3225f-129">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="3225f-130"><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Lync Server 2013 中設定呼叫收取群組號碼</a></span><span class="sxs-lookup"><span data-stu-id="3225f-130"><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Configure call pickup group numbers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3225f-131">呼叫收取號碼指派給使用者，並為使用者啟用群組來電接聽</span><span class="sxs-lookup"><span data-stu-id="3225f-131">Assign a call pickup number to users, and enable Group Call Pickup for the users</span></span></p></td>
<td><p><span data-ttu-id="3225f-132">若要啟用群組來電接聽，並指派使用者的通話收取數字，SEFAUtil resource kit 工具中使用 /enablegrouppickup 參數。</span><span class="sxs-lookup"><span data-stu-id="3225f-132">Use the /enablegrouppickup parameter in the SEFAUtil resource kit tool to enable Group Call Pickup and assign a call pickup number for users.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="3225f-133"><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">啟用群組來電接聽 Lync Server 2013 中的使用者並指派群組編號</a></span><span class="sxs-lookup"><span data-stu-id="3225f-133"><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3225f-134">通知使用者其指派的通話收取] 目錄的數字和其他任何數字的利息</span><span class="sxs-lookup"><span data-stu-id="3225f-134">Notify users of their assigned call pickup number and any other number of interest</span></span></p></td>
<td><p><span data-ttu-id="3225f-135">因為任何使用者可以擷取對群組來電接聽使用者的呼叫，使用者可能會想要監視多個群組。</span><span class="sxs-lookup"><span data-stu-id="3225f-135">Because any user can retrieve a call made to a Group Call Pickup user, users may want to monitor more than one group.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="3225f-136"><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">通訊群組來電接聽指派給 Lync Server 2013 中的使用者</a></span><span class="sxs-lookup"><span data-stu-id="3225f-136"><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">Communicate Group Call Pickup assignments to users in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3225f-137">確認群組來電接聽部署</span><span class="sxs-lookup"><span data-stu-id="3225f-137">Verify your Group Call Pickup deployment</span></span></p></td>
<td><p><span data-ttu-id="3225f-138">測試放置，並擷取通話，請確定您的設定如預期般運作。</span><span class="sxs-lookup"><span data-stu-id="3225f-138">Test placing and retrieving calls to make sure that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="3225f-139"><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">（選用）確認 Lync Server 2013 中的群組來電接聽部署</a></span><span class="sxs-lookup"><span data-stu-id="3225f-139"><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">(Optional) Verify the Group Call Pickup deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

