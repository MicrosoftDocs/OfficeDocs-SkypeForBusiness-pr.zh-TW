---
title: Lync Server 2013：為使用者啟用通話駐留
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
ms.openlocfilehash: 9345cdf2665a5a02d04a372606b95111d870a727
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528780"
---
# <a name="enable-call-park-for-users-in-lync-server-2013"></a><span data-ttu-id="ef7f9-102">在 Lync Server 2013 中為使用者啟用通話駐留</span><span class="sxs-lookup"><span data-stu-id="ef7f9-102">Enable Call Park for users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef7f9-103">_**主題上次修改日期：** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="ef7f9-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="ef7f9-104">使用者在語音原則中為通話駐留啟用電話時，無法寄存通話或取得寄存的通話。</span><span class="sxs-lookup"><span data-stu-id="ef7f9-104">Users cannot park calls or retrieve parked calls until they are enabled for Call Park in voice policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ef7f9-105">預設會停用所有使用者的通話駐留。</span><span class="sxs-lookup"><span data-stu-id="ef7f9-105">By default, Call Park is disabled for all users.</span></span>



</div>

<span data-ttu-id="ef7f9-106">您可以在全域範圍或網站範圍或使用者範圍上啟用通話駐留。</span><span class="sxs-lookup"><span data-stu-id="ef7f9-106">You can enable Call Park at the global scope, or at the site scope or user scope.</span></span> <span data-ttu-id="ef7f9-107">使用者範圍優先于網站範圍，而網站範圍優先于全域範圍。</span><span class="sxs-lookup"><span data-stu-id="ef7f9-107">User scope takes precedence over site scope, and site scope takes precedence over global scope.</span></span> <span data-ttu-id="ef7f9-108">如果您有多個語音原則，請複習所有原則以啟用通話駐留，而不只是全域原則。</span><span class="sxs-lookup"><span data-stu-id="ef7f9-108">If you have multiple voice policies, review all the policies to enable Call Park, not just the global policy.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-enable-call-park-for-users"></a><span data-ttu-id="ef7f9-109">使用 Lync Server 控制台為使用者啟用通話駐留</span><span class="sxs-lookup"><span data-stu-id="ef7f9-109">To Use Lync Server Control Panel to Enable Call Park for Users</span></span>

1.  <span data-ttu-id="ef7f9-110">以 **RTCUniversalServerAdmins** 群組成員的身分，或是 **CsVoiceAdministrator**、 **CsServerAdministrator**或 **CsAdministrator** 系統管理角色的成員身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="ef7f9-110">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>

2.  <span data-ttu-id="ef7f9-111">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="ef7f9-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ef7f9-112">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="ef7f9-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ef7f9-113">在左導覽列中，按一下 **[語音路由]**。</span><span class="sxs-lookup"><span data-stu-id="ef7f9-113">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="ef7f9-114">按一下 [ **語音原則** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="ef7f9-114">Click the **Voice Policy** tab.</span></span>

5.  <span data-ttu-id="ef7f9-115">按兩下現有的語音原則，以開啟 [ **編輯語音原則** ] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="ef7f9-115">Double-click an existing voice policy to open the **Edit Voice Policy** dialog box.</span></span>

6.  <span data-ttu-id="ef7f9-116">在 [ **通話功能**] 底下，選取 [ **啟用通話駐留**]。</span><span class="sxs-lookup"><span data-stu-id="ef7f9-116">Under **Calling features**, select **Enable call park**.</span></span>

7.  <span data-ttu-id="ef7f9-117">按一下 **[確定]** 以儲存語音原則</span><span class="sxs-lookup"><span data-stu-id="ef7f9-117">Click **OK** to save the voice policy</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-enable-call-park-for-users"></a><span data-ttu-id="ef7f9-118">若要使用 Cmdlet 為使用者啟用通話駐留</span><span class="sxs-lookup"><span data-stu-id="ef7f9-118">To Use Cmdlets to Enable Call Park for Users</span></span>

1.  <span data-ttu-id="ef7f9-119">以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 系統管理角色的成員身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="ef7f9-119">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator administrative role.</span></span>

2.  <span data-ttu-id="ef7f9-120">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="ef7f9-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ef7f9-121">運行：</span><span class="sxs-lookup"><span data-stu-id="ef7f9-121">Run:</span></span>
    
        Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
    
    <span data-ttu-id="ef7f9-122">例如，若要啟用預設全域語音原則的通話駐留：</span><span class="sxs-lookup"><span data-stu-id="ef7f9-122">For example, to enable Call Park for the default global voice policy:</span></span>
    
        Set-CsVoicePolicy -EnableCallPark $true

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ef7f9-123">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ef7f9-123">See Also</span></span>


[<span data-ttu-id="ef7f9-124">在 Lync Server 2013 中建立語音原則和設定 PSTN 使用方式記錄</span><span class="sxs-lookup"><span data-stu-id="ef7f9-124">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

