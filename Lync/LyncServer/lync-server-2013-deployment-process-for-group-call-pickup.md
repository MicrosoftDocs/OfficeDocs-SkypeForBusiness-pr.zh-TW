---
title: Lync Server 2013：群組呼叫收取的部署程式
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
ms.openlocfilehash: 52f7646010e4048d135e11c98d06a651f923d633
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522610"
---
# <a name="deployment-process-for-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="676a4-102">Lync Server 2013 中群組呼叫收取的部署程式</span><span class="sxs-lookup"><span data-stu-id="676a4-102">Deployment process for Group Call Pickup in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="676a4-103">_**主題上次修改日期：** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="676a4-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="676a4-104">本節提供部署群組呼叫收取相關步驟的概述。</span><span class="sxs-lookup"><span data-stu-id="676a4-104">This section provides an overview of the steps involved in deploying Group Call Pickup.</span></span> <span data-ttu-id="676a4-105">您必須先部署 Enterprise Edition 或 Standard Edition 搭配 Enterprise Voice，才能設定群組呼叫收取。</span><span class="sxs-lookup"><span data-stu-id="676a4-105">You must deploy Enterprise Edition or Standard Edition with Enterprise Voice before you configure Group Call Pickup.</span></span> <span data-ttu-id="676a4-106">當您部署企業語音時，會安裝及啟用群組通話收取所需的元件。</span><span class="sxs-lookup"><span data-stu-id="676a4-106">The components required by Group Call Pickup are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="group-call-pickup-deployment-process"></a><span data-ttu-id="676a4-107">群組呼叫收取部署程式</span><span class="sxs-lookup"><span data-stu-id="676a4-107">Group Call Pickup Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="676a4-108">階段</span><span class="sxs-lookup"><span data-stu-id="676a4-108">Phase</span></span></th>
<th><span data-ttu-id="676a4-109">步驟</span><span class="sxs-lookup"><span data-stu-id="676a4-109">Steps</span></span></th>
<th><span data-ttu-id="676a4-110">所需群組和角色</span><span class="sxs-lookup"><span data-stu-id="676a4-110">Required groups and roles</span></span></th>
<th><span data-ttu-id="676a4-111">部署文件</span><span class="sxs-lookup"><span data-stu-id="676a4-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="676a4-112">啟用拓撲中的 SEFAUtil resource 工具組工具</span><span class="sxs-lookup"><span data-stu-id="676a4-112">Enable the SEFAUtil resource kit tool in the topology</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="676a4-113">使用 <strong>New-CsTrustedApplicationPool</strong> Cmdlet 來建立新的受信任應用程式集區。</span><span class="sxs-lookup"><span data-stu-id="676a4-113">Use the <strong>New-CsTrustedApplicationPool</strong> cmdlet to create a new trusted application pool.</span></span></p></li>
<li><p><span data-ttu-id="676a4-114">使用 <strong>New-CsTrustedApplication</strong> Cmdlet，將 SEFAUtil 工具指定為信任的應用程式。</span><span class="sxs-lookup"><span data-stu-id="676a4-114">Use the <strong>New-CsTrustedApplication</strong> cmdlet to specify the SEFAUtil tool as trusted application.</span></span></p></li>
<li><p><span data-ttu-id="676a4-115">執行 <strong>Enable-CsTopology</strong> Cmdlet 以啟用拓撲。</span><span class="sxs-lookup"><span data-stu-id="676a4-115">Run the <strong>Enable-CsTopology</strong> cmdlet to enable the topology.</span></span></p></li>
<li><p><span data-ttu-id="676a4-116">在步驟1中建立的受信任應用程式集區中的前端伺服器上安裝資源工具組工具。</span><span class="sxs-lookup"><span data-stu-id="676a4-116">Install the resource kit tools on a Front End Server that is in the trusted application pool created in step 1.</span></span></p></li>
<li><p><span data-ttu-id="676a4-117">執行該 SEFAUtil 以在部署中顯示使用者的「來電轉接」設定，以確認是否正常運作。</span><span class="sxs-lookup"><span data-stu-id="676a4-117">Verify that SEFAUtil is running correctly by running it to display the call forwarding settings of a user in the deployment.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="676a4-118">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="676a4-118">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="676a4-119"><a href="lync-server-2013-deploy-the-sefautil-tool.md">在 Lync Server 2013 中部署 SEFAUtil 工具</a></span><span class="sxs-lookup"><span data-stu-id="676a4-119"><a href="lync-server-2013-deploy-the-sefautil-tool.md">Deploy the SEFAUtil tool in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="676a4-120">設定通話駐留軌道表格中的呼叫收取號碼範圍</span><span class="sxs-lookup"><span data-stu-id="676a4-120">Configure call pickup number ranges in the call park orbit table</span></span></p></td>
<td><p><span data-ttu-id="676a4-121">使用 <strong>New-CSCallParkOrbit</strong> Cmdlet 來建立通話駐留軌道表格中的呼叫收取號碼範圍，並將類型 GroupPickup 指派給電話收取範圍。</span><span class="sxs-lookup"><span data-stu-id="676a4-121">Use the <strong>New-CSCallParkOrbit</strong> cmdlet to create call pickup number ranges in the call park orbit table and assign the call pickup ranges the type GroupPickup.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="676a4-122">您必須使用 Lync Server 管理命令介面來建立、修改、移除及查看通話駐留軌道表格中的群組呼叫收取號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="676a4-122">You must use Lync Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="676a4-123">在 Lync Server 控制台中無法使用群組呼叫收取號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="676a4-123">Group Call Pickup number ranges are not available in Lync Server Control Panel.</span></span>


</div>
<div>

> [!NOTE]  
> <span data-ttu-id="676a4-124">為了與現有撥號對應表無縫整合，號碼範圍通常會設定為虛擬擴充區塊。</span><span class="sxs-lookup"><span data-stu-id="676a4-124">For seamless integration with existing dial plans, number ranges are typically configured as a block of virtual extensions.</span></span> <span data-ttu-id="676a4-125">指派直接向內撥號 (，不支援通話駐留軌道表格中的範圍編號) 數位。</span><span class="sxs-lookup"><span data-stu-id="676a4-125">Assigning Direct Inward Dialing (DID) numbers as range numbers in the call park orbit table is not supported.</span></span>


</div></td>
<td><p><span data-ttu-id="676a4-126">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="676a4-126">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="676a4-127">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="676a4-127">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="676a4-128">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="676a4-128">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="676a4-129">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="676a4-129">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="676a4-130"><a href="lync-server-2013-configure-call-pickup-group-numbers.md">在 Lync Server 2013 中設定呼叫收取群組號碼</a></span><span class="sxs-lookup"><span data-stu-id="676a4-130"><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Configure call pickup group numbers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="676a4-131">將來電收取號碼指派給使用者，並為使用者啟用群組呼叫收取功能</span><span class="sxs-lookup"><span data-stu-id="676a4-131">Assign a call pickup number to users, and enable Group Call Pickup for the users</span></span></p></td>
<td><p><span data-ttu-id="676a4-132">使用 SEFAUtil resource 成套工具中的/enablegrouppickup 參數，啟用群組呼叫收取，並為使用者指派呼叫收取號碼。</span><span class="sxs-lookup"><span data-stu-id="676a4-132">Use the /enablegrouppickup parameter in the SEFAUtil resource kit tool to enable Group Call Pickup and assign a call pickup number for users.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="676a4-133"><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">為 Lync Server 2013 中的使用者啟用群組呼叫收取，並指派群組號碼</a></span><span class="sxs-lookup"><span data-stu-id="676a4-133"><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="676a4-134">通知使用者他們所指派的來電收取號碼和其他相關數目</span><span class="sxs-lookup"><span data-stu-id="676a4-134">Notify users of their assigned call pickup number and any other number of interest</span></span></p></td>
<td><p><span data-ttu-id="676a4-135">由於任何使用者都可以取回對群組呼叫收取使用者所撥打的電話，因此使用者可能會想要監視一個以上的群組。</span><span class="sxs-lookup"><span data-stu-id="676a4-135">Because any user can retrieve a call made to a Group Call Pickup user, users may want to monitor more than one group.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="676a4-136"><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">在 Lync Server 2013 中通訊群組呼叫收取指派給使用者</a></span><span class="sxs-lookup"><span data-stu-id="676a4-136"><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">Communicate Group Call Pickup assignments to users in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="676a4-137">驗證群組是否呼叫收取部署</span><span class="sxs-lookup"><span data-stu-id="676a4-137">Verify your Group Call Pickup deployment</span></span></p></td>
<td><p><span data-ttu-id="676a4-138">測試放入和取回通話，以確保您的設定如預期般運作。</span><span class="sxs-lookup"><span data-stu-id="676a4-138">Test placing and retrieving calls to make sure that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="676a4-139"><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md"> (選用) 驗證 Lync Server 2013 中的群組呼叫收取部署</a></span><span class="sxs-lookup"><span data-stu-id="676a4-139"><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">(Optional) Verify the Group Call Pickup deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

