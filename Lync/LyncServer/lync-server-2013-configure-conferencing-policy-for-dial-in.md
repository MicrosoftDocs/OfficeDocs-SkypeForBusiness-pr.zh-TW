---
title: Lync Server 2013：設定電話撥入式會議的會議原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure conferencing policy for dial-in
ms:assetid: 9bf926d6-0248-4352-98c3-9c5a333debbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398810(v=OCS.15)
ms:contentKeyID: 48184979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74621fee97a1e6721f8772b265761b62b1b9f266
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982465"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-conferencing-policy-for-dial-in-in-lync-server-2013"></a><span data-ttu-id="674f8-102">在 Lync Server 2013 中設定電話撥入式會議的會議原則</span><span class="sxs-lookup"><span data-stu-id="674f8-102">Configure conferencing policy for dial-in in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="674f8-103">_**主題上次修改日期：** 2014-03-21_</span><span class="sxs-lookup"><span data-stu-id="674f8-103">_**Topic Last Modified:** 2014-03-21_</span></span>

<span data-ttu-id="674f8-104">[會議原則] 是一個使用者帳戶設定，可為參與者指定會議體驗。</span><span class="sxs-lookup"><span data-stu-id="674f8-104">Conferencing policy is a user account setting that specifies the conferencing experience for participants.</span></span> <span data-ttu-id="674f8-105">您可以使用網站範圍或使用者範圍建立會議原則。</span><span class="sxs-lookup"><span data-stu-id="674f8-105">You can create conferencing policies with a site scope or a user scope.</span></span> <span data-ttu-id="674f8-106">會議原則設定涵蓋了會議排程與參與的許多方面。</span><span class="sxs-lookup"><span data-stu-id="674f8-106">Conferencing policy settings encompass many aspects of conference scheduling and participation.</span></span> <span data-ttu-id="674f8-107">幾個會議原則設定支援參與者的電話撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="674f8-107">Several conferencing policy settings support dial-in conferencing for participants.</span></span> <span data-ttu-id="674f8-108">當您設定電話撥入式會議時，應確認這些欄位已針對您的組織進行適當的設定，並視需要加以修改。</span><span class="sxs-lookup"><span data-stu-id="674f8-108">When you configure dial-in conferencing, you should verify that these fields are set appropriately for your organization, and modify them as necessary.</span></span>

<span data-ttu-id="674f8-109">驗證會議原則中的下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="674f8-109">Verify the following fields in your conferencing policy:</span></span>

  - <span data-ttu-id="674f8-110">**[允許參與者邀請匿名使用者**   ] 此設定可讓會議召集人邀請匿名（也就是未驗證）參與者加入會議。</span><span class="sxs-lookup"><span data-stu-id="674f8-110">**Allow participants to invite anonymous users**   This setting allows meeting organizers to invite anonymous (that is, unauthenticated) participants to meetings.</span></span> <span data-ttu-id="674f8-111">此設定為電話撥入式會議的選用。</span><span class="sxs-lookup"><span data-stu-id="674f8-111">This setting is optional for dial-in conferencing.</span></span> <span data-ttu-id="674f8-112">預設的全域會議原則預設會選取此設定。</span><span class="sxs-lookup"><span data-stu-id="674f8-112">This setting is selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="674f8-113">**啟用 PSTN 電話撥入式會議**   此設定可讓使用者透過撥入 PSTN 來加入會議的音訊部分。</span><span class="sxs-lookup"><span data-stu-id="674f8-113">**Enable PSTN dial-in conferencing**   This setting allows users to join the audio portion of a conference by dialing in from the PSTN.</span></span> <span data-ttu-id="674f8-114">電話撥入式會議需要此設定。</span><span class="sxs-lookup"><span data-stu-id="674f8-114">This setting is required for dial-in conferencing.</span></span> <span data-ttu-id="674f8-115">預設的全域會議原則預設會選取此設定。</span><span class="sxs-lookup"><span data-stu-id="674f8-115">This setting is selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="674f8-116">**[允許匿名參與者撥號**   ] 此設定可讓已加入會議的匿名使用者撥出電話號碼，以加入會議的音訊部分。</span><span class="sxs-lookup"><span data-stu-id="674f8-116">**Allow anonymous participants to dial out**   This setting allows anonymous users who are already joined to the meeting to dial out to a phone number to join the audio portion of the conference.</span></span> <span data-ttu-id="674f8-117">此設定為電話撥入式會議的選用。</span><span class="sxs-lookup"><span data-stu-id="674f8-117">This setting is optional for dial-in conferencing.</span></span> <span data-ttu-id="674f8-118">預設的全域會議原則預設不會選取此設定。</span><span class="sxs-lookup"><span data-stu-id="674f8-118">This setting is not selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="674f8-119">**[允許未啟用企業語音的參與者撥號**   ] 此設定可讓未啟用企業語音的會議參與者和召集人撥出電話號碼以加入會議的音訊部分。</span><span class="sxs-lookup"><span data-stu-id="674f8-119">**Allow participants not enabled for Enterprise Voice to dial out**   This setting allows meeting participants and organizers that are not enabled for Enterprise Voice to dial out to a phone number to join the audio portion of the conference.</span></span> <span data-ttu-id="674f8-120">撥出通話是根據召集人指派的語音原則進行授權。</span><span class="sxs-lookup"><span data-stu-id="674f8-120">The dial-out call is authorized based on the organizer’s assigned voice policy.</span></span> <span data-ttu-id="674f8-121">預設的全域會議原則預設不會選取此設定。</span><span class="sxs-lookup"><span data-stu-id="674f8-121">This setting is not selected by default in the default global conferencing policy.</span></span> <span data-ttu-id="674f8-122">[設定預設值] 為 [停用]。</span><span class="sxs-lookup"><span data-stu-id="674f8-122">The setting default value is disabled.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="674f8-123">若要啟用這項功能，沒有為企業語音啟用的會議召集人應該已指派適當的語音原則，以授權來自該使用者組織之會議的任何撥出。</span><span class="sxs-lookup"><span data-stu-id="674f8-123">To enable this capability, a meeting organizer that is not enabled for Enterprise Voice should have an appropriate voice policy assigned to them to authorize any dial-out from a conference organized by that user.</span></span> <span data-ttu-id="674f8-124">您可以從 Lync Server 管理命令介面將語音原則指派給未啟用企業語音的使用者。</span><span class="sxs-lookup"><span data-stu-id="674f8-124">A voice policy can be assigned to a user that is not enabled for Enterprise Voice from the Lync Server Management Shell.</span></span> <span data-ttu-id="674f8-125">如果使用者沒有明確指派給他的語音原則，網站語音原則將用來授權撥出要求。</span><span class="sxs-lookup"><span data-stu-id="674f8-125">If the user does not have a voice policy explicitly assigned to him, the site voice policy will be used to authorize the dial-out request.</span></span> <span data-ttu-id="674f8-126">如果沒有網站語音原則，就會使用全域語音原則。&nbsp;</span><span class="sxs-lookup"><span data-stu-id="674f8-126">If there is no site voice policy, the global voice policy will be used.&nbsp;</span></span>

    
    </div>

<span data-ttu-id="674f8-127">本節中的程式說明如何修改會議原則。</span><span class="sxs-lookup"><span data-stu-id="674f8-127">The procedure in this section explains how to modify conferencing policy.</span></span> <span data-ttu-id="674f8-128">如需有關如何設定在預設會議原則中定義參與者體驗的所有設定的詳細資訊，請參閱[在 Lync Server 2013 中建立或修改會議配置設定的集合](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="674f8-128">For details about how to configure all of the settings that define the participant experience in the default conferencing policy, see [Create or modify a collection of meeting configuration settings in Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span></span> <span data-ttu-id="674f8-129">如需如何為特定使用者或使用者群組建立會議原則的詳細資料，請參閱[在 Lync Server 2013 中建立或修改會議原則](lync-server-2013-create-or-modify-a-conferencing-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="674f8-129">For details about how to create a conferencing policy for a specific user or group of users, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span></span> <span data-ttu-id="674f8-130">如需所有可用會議原則設定的清單，請參閱[Lync Server 2013 的會議原則設定參考](lync-server-2013-conferencing-policy-settings-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="674f8-130">For a list of all available conferencing policy settings, see [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<div>

## <a name="to-modify-the-conferencing-policy-for-dial-in"></a><span data-ttu-id="674f8-131">修改電話撥入式會議原則</span><span class="sxs-lookup"><span data-stu-id="674f8-131">To modify the conferencing policy for dial-in</span></span>

1.  <span data-ttu-id="674f8-132">以 RTCUniversalServerAdmins 群組的成員或**Cs-ServerAdministrator**或**CsAdministrator**角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="674f8-132">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="674f8-133">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="674f8-133">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="674f8-134">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="674f8-134">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="674f8-135">在左側導覽列中，按一下 [**會議**]。</span><span class="sxs-lookup"><span data-stu-id="674f8-135">In the left navigation bar, click **Conferencing**.</span></span>

4.  <span data-ttu-id="674f8-136">在 [**會議原則**] 索引標籤上，按兩下會議原則名稱，以開啟 [**編輯會議原則**] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="674f8-136">On the **Conferencing Policy** tab, double-click a conferencing policy name to open the **Edit Conferencing Policy** dialog box.</span></span>

5.  <span data-ttu-id="674f8-137">確認電話撥入式會議的欄位適合您的組織，並視需要修改設定。</span><span class="sxs-lookup"><span data-stu-id="674f8-137">Verify that the fields for dial-in conferencing are appropriate for your organization, and modify the settings if necessary.</span></span>

6.  <span data-ttu-id="674f8-138">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="674f8-138">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

