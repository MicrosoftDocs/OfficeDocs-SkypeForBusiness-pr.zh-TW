---
title: Lync Server 2013：針對使用者啟用通話駐留
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Call Park for users
ms:assetid: 9430763f-3394-467c-9c6d-426bf761604e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398753(v=OCS.15)
ms:contentKeyID: 48184814
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd89ba10f5cae16e88c65e6e56178fc517c71213
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736243"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-call-park-for-users-in-lync-server-2013"></a><span data-ttu-id="0bb86-102">在 Lync Server 2013 中為使用者啟用通話駐留</span><span class="sxs-lookup"><span data-stu-id="0bb86-102">Enable Call Park for users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0bb86-103">_**主題上次修改日期：** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="0bb86-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="0bb86-104">使用者在語音原則中啟用通話駐留前，不能寄存通話或取得停用通話。</span><span class="sxs-lookup"><span data-stu-id="0bb86-104">Users cannot park calls or retrieve parked calls until they are enabled for Call Park in voice policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0bb86-105">根據預設，會停用所有使用者的 [通話駐留]。</span><span class="sxs-lookup"><span data-stu-id="0bb86-105">By default, Call Park is disabled for all users.</span></span>



</div>

<span data-ttu-id="0bb86-106">您可以在全域範圍或在網站範圍或使用者範圍中啟用通話駐留。</span><span class="sxs-lookup"><span data-stu-id="0bb86-106">You can enable Call Park at the global scope, or at the site scope or user scope.</span></span> <span data-ttu-id="0bb86-107">[使用者範圍] 的優先順序高於 [網站範圍]，而 [網站範圍] 的優先順序高於 [全域範圍]。</span><span class="sxs-lookup"><span data-stu-id="0bb86-107">User scope takes precedence over site scope, and site scope takes precedence over global scope.</span></span> <span data-ttu-id="0bb86-108">如果您有多個語音原則，請查看所有原則來啟用通話駐留，而不只是全域原則。</span><span class="sxs-lookup"><span data-stu-id="0bb86-108">If you have multiple voice policies, review all the policies to enable Call Park, not just the global policy.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-enable-call-park-for-users"></a><span data-ttu-id="0bb86-109">使用 Lync Server [控制台] 為使用者啟用通話駐留</span><span class="sxs-lookup"><span data-stu-id="0bb86-109">To Use Lync Server Control Panel to Enable Call Park for Users</span></span>

1.  <span data-ttu-id="0bb86-110">以**RTCUniversalServerAdmins**群組的成員或**CsVoiceAdministrator**、 **CsServerAdministrator**或**CsAdministrator**系統管理角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="0bb86-110">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>

2.  <span data-ttu-id="0bb86-111">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="0bb86-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0bb86-112">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="0bb86-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0bb86-113">在左側導覽列中，按一下 [**語音路由**]。</span><span class="sxs-lookup"><span data-stu-id="0bb86-113">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="0bb86-114">按一下 [**語音原則**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="0bb86-114">Click the **Voice Policy** tab.</span></span>

5.  <span data-ttu-id="0bb86-115">按兩下現有的語音原則，以開啟 [**編輯語音原則**] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="0bb86-115">Double-click an existing voice policy to open the **Edit Voice Policy** dialog box.</span></span>

6.  <span data-ttu-id="0bb86-116">在 [**呼叫功能**] 底下，選取 [**啟用通話駐留**]。</span><span class="sxs-lookup"><span data-stu-id="0bb86-116">Under **Calling features**, select **Enable call park**.</span></span>

7.  <span data-ttu-id="0bb86-117">按一下 **[確定]** 儲存語音原則</span><span class="sxs-lookup"><span data-stu-id="0bb86-117">Click **OK** to save the voice policy</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-enable-call-park-for-users"></a><span data-ttu-id="0bb86-118">若要使用 Cmdlet 來為使用者啟用通話駐留</span><span class="sxs-lookup"><span data-stu-id="0bb86-118">To Use Cmdlets to Enable Call Park for Users</span></span>

1.  <span data-ttu-id="0bb86-119">以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 系統管理角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="0bb86-119">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator administrative role.</span></span>

2.  <span data-ttu-id="0bb86-120">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="0bb86-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="0bb86-121">用盡</span><span class="sxs-lookup"><span data-stu-id="0bb86-121">Run:</span></span>
    
        Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
    
    <span data-ttu-id="0bb86-122">例如，若要針對預設的全域語音原則啟用通話駐留，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="0bb86-122">For example, to enable Call Park for the default global voice policy:</span></span>
    
        Set-CsVoicePolicy -EnableCallPark $true

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0bb86-123">請參閱</span><span class="sxs-lookup"><span data-stu-id="0bb86-123">See Also</span></span>


[<span data-ttu-id="0bb86-124">在 Lync Server 2013 中建立語音原則和設定 PSTN 使用記錄</span><span class="sxs-lookup"><span data-stu-id="0bb86-124">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

