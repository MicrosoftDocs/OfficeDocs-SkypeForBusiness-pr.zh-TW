---
title: Lync Server 2013：設定電話撥入式會議原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure conferencing policy for dial-in
ms:assetid: 9bf926d6-0248-4352-98c3-9c5a333debbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398810(v=OCS.15)
ms:contentKeyID: 48184979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33f84ec3cb900b4283f30d67e318ab10d3625326
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204929"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-conferencing-policy-for-dial-in-in-lync-server-2013"></a><span data-ttu-id="fe771-102">在 Lync Server 2013 中設定電話撥入式會議原則</span><span class="sxs-lookup"><span data-stu-id="fe771-102">Configure conferencing policy for dial-in in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe771-103">_**主題上次修改日期：** 2014-03-21_</span><span class="sxs-lookup"><span data-stu-id="fe771-103">_**Topic Last Modified:** 2014-03-21_</span></span>

<span data-ttu-id="fe771-104">會議原則是一種使用者帳戶設定，可指定參與者的會議體驗。</span><span class="sxs-lookup"><span data-stu-id="fe771-104">Conferencing policy is a user account setting that specifies the conferencing experience for participants.</span></span> <span data-ttu-id="fe771-105">您可以建立具有網站範圍或使用者範圍的會議原則。</span><span class="sxs-lookup"><span data-stu-id="fe771-105">You can create conferencing policies with a site scope or a user scope.</span></span> <span data-ttu-id="fe771-106">會議原則設定涵蓋許多會議排程和參與的層面。</span><span class="sxs-lookup"><span data-stu-id="fe771-106">Conferencing policy settings encompass many aspects of conference scheduling and participation.</span></span> <span data-ttu-id="fe771-107">數個會議原則設定支援參與者的電話撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="fe771-107">Several conferencing policy settings support dial-in conferencing for participants.</span></span> <span data-ttu-id="fe771-108">當您設定電話撥入式會議時，應確認您的組織已正確設定這些欄位，並視需要加以修改。</span><span class="sxs-lookup"><span data-stu-id="fe771-108">When you configure dial-in conferencing, you should verify that these fields are set appropriately for your organization, and modify them as necessary.</span></span>

<span data-ttu-id="fe771-109">驗證會議原則中的下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="fe771-109">Verify the following fields in your conferencing policy:</span></span>

  - <span data-ttu-id="fe771-110">**允許參與者邀請匿名使用者**    此設定可讓會議召集人邀請匿名 (，也就是未驗證的) 參與者參加會議。</span><span class="sxs-lookup"><span data-stu-id="fe771-110">**Allow participants to invite anonymous users**   This setting allows meeting organizers to invite anonymous (that is, unauthenticated) participants to meetings.</span></span> <span data-ttu-id="fe771-111">此設定為電話撥入式會議的選用。</span><span class="sxs-lookup"><span data-stu-id="fe771-111">This setting is optional for dial-in conferencing.</span></span> <span data-ttu-id="fe771-112">預設會選取預設全域會議原則中的此設定。</span><span class="sxs-lookup"><span data-stu-id="fe771-112">This setting is selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="fe771-113">**啟用 PSTN 電話撥入式會議**    此設定可讓使用者從 PSTN 撥入，以加入會議的音訊部分。</span><span class="sxs-lookup"><span data-stu-id="fe771-113">**Enable PSTN dial-in conferencing**   This setting allows users to join the audio portion of a conference by dialing in from the PSTN.</span></span> <span data-ttu-id="fe771-114">電話撥入式會議需要此設定。</span><span class="sxs-lookup"><span data-stu-id="fe771-114">This setting is required for dial-in conferencing.</span></span> <span data-ttu-id="fe771-115">預設會選取預設全域會議原則中的此設定。</span><span class="sxs-lookup"><span data-stu-id="fe771-115">This setting is selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="fe771-116">**允許匿名參與者撥出**    此設定允許已經加入會議的匿名使用者撥出到電話號碼，以加入會議的音訊部分。</span><span class="sxs-lookup"><span data-stu-id="fe771-116">**Allow anonymous participants to dial out**   This setting allows anonymous users who are already joined to the meeting to dial out to a phone number to join the audio portion of the conference.</span></span> <span data-ttu-id="fe771-117">此設定為電話撥入式會議的選用。</span><span class="sxs-lookup"><span data-stu-id="fe771-117">This setting is optional for dial-in conferencing.</span></span> <span data-ttu-id="fe771-118">預設全域會議原則中不會選取此設定。</span><span class="sxs-lookup"><span data-stu-id="fe771-118">This setting is not selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="fe771-119">**允許未啟用 Enterprise Voice 的參與者撥出**    此設定允許未啟用 Enterprise Voice 的會議參與者和召集人撥打至電話號碼，以加入會議的音訊部分。</span><span class="sxs-lookup"><span data-stu-id="fe771-119">**Allow participants not enabled for Enterprise Voice to dial out**   This setting allows meeting participants and organizers that are not enabled for Enterprise Voice to dial out to a phone number to join the audio portion of the conference.</span></span> <span data-ttu-id="fe771-120">撥出電話是根據召集人指派的語音原則獲得授權。</span><span class="sxs-lookup"><span data-stu-id="fe771-120">The dial-out call is authorized based on the organizer’s assigned voice policy.</span></span> <span data-ttu-id="fe771-121">預設全域會議原則中不會選取此設定。</span><span class="sxs-lookup"><span data-stu-id="fe771-121">This setting is not selected by default in the default global conferencing policy.</span></span> <span data-ttu-id="fe771-122">設定預設值為停用。</span><span class="sxs-lookup"><span data-stu-id="fe771-122">The setting default value is disabled.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fe771-123">若要啟用此功能，未啟用 Enterprise Voice 的會議召集人應該會有適當的語音原則指派給他們，以授權來自該使用者組織之會議的任何撥出。</span><span class="sxs-lookup"><span data-stu-id="fe771-123">To enable this capability, a meeting organizer that is not enabled for Enterprise Voice should have an appropriate voice policy assigned to them to authorize any dial-out from a conference organized by that user.</span></span> <span data-ttu-id="fe771-124">語音原則可以指派給沒有從 Lync Server 管理命令介面中為 Enterprise Voice 啟用的使用者。</span><span class="sxs-lookup"><span data-stu-id="fe771-124">A voice policy can be assigned to a user that is not enabled for Enterprise Voice from the Lync Server Management Shell.</span></span> <span data-ttu-id="fe771-125">若使用者沒有明確指派給他的語音原則，則會使用網站語音原則來授權撥出要求。</span><span class="sxs-lookup"><span data-stu-id="fe771-125">If the user does not have a voice policy explicitly assigned to him, the site voice policy will be used to authorize the dial-out request.</span></span> <span data-ttu-id="fe771-126">如果沒有網站語音原則，則會使用通用語音原則。&nbsp;</span><span class="sxs-lookup"><span data-stu-id="fe771-126">If there is no site voice policy, the global voice policy will be used.&nbsp;</span></span>

    
    </div>

<span data-ttu-id="fe771-127">本節中的程式說明如何修改會議原則。</span><span class="sxs-lookup"><span data-stu-id="fe771-127">The procedure in this section explains how to modify conferencing policy.</span></span> <span data-ttu-id="fe771-128">如需如何設定所有設定以定義預設會議原則中的參與者經驗的詳細資訊，請參閱在[Lync Server 2013 中建立或修改會議配置設定的集合](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="fe771-128">For details about how to configure all of the settings that define the participant experience in the default conferencing policy, see [Create or modify a collection of meeting configuration settings in Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span></span> <span data-ttu-id="fe771-129">如需如何為特定使用者或使用者群組建立會議原則的詳細資訊，請參閱[建立或修改 Lync Server 2013 中的會議原則](lync-server-2013-create-or-modify-a-conferencing-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="fe771-129">For details about how to create a conferencing policy for a specific user or group of users, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span></span> <span data-ttu-id="fe771-130">如需所有可用之會議原則設定的清單，請參閱[Lync Server 2013 的會議原則設定參考](lync-server-2013-conferencing-policy-settings-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="fe771-130">For a list of all available conferencing policy settings, see [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<div>

## <a name="to-modify-the-conferencing-policy-for-dial-in"></a><span data-ttu-id="fe771-131">若要修改電話撥入式會議原則</span><span class="sxs-lookup"><span data-stu-id="fe771-131">To modify the conferencing policy for dial-in</span></span>

1.  <span data-ttu-id="fe771-132">以 RTCUniversalServerAdmins 群組成員或 **Cs-ServerAdministrator**、**CsAdministrator** 角色成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="fe771-132">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="fe771-133">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="fe771-133">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fe771-134">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="fe771-134">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fe771-135">在左側導覽列中，按一下 **[會議]**。</span><span class="sxs-lookup"><span data-stu-id="fe771-135">In the left navigation bar, click **Conferencing**.</span></span>

4.  <span data-ttu-id="fe771-136">在 [**會議原則**] 索引標籤上，按兩下會議原則名稱，以開啟 [**編輯會議原則**] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="fe771-136">On the **Conferencing Policy** tab, double-click a conferencing policy name to open the **Edit Conferencing Policy** dialog box.</span></span>

5.  <span data-ttu-id="fe771-137">確認電話撥入式會議的欄位適用于您的組織，必要時會修改設定。</span><span class="sxs-lookup"><span data-stu-id="fe771-137">Verify that the fields for dial-in conferencing are appropriate for your organization, and modify the settings if necessary.</span></span>

6.  <span data-ttu-id="fe771-138">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="fe771-138">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

