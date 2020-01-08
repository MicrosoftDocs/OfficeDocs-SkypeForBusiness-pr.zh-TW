---
title: Lync Server 2013：建立或修改使用者站台或群組的電話撥入式會議 PIN 設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify dial-in conferencing PIN settings for a site or group of users
ms:assetid: c29bab5c-2b93-48e0-ae0b-29564daaff9a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412959(v=OCS.15)
ms:contentKeyID: 48185326
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2af1dc8e3f9bde06e799c758b711f94b7c0e6411
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976949"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-dial-in-conferencing-pin-settings-in-lync-server-2013-for-a-site-or-group-of-users"></a><span data-ttu-id="2630a-102">在 Lync Server 2013 中建立或修改使用者站台或群組的電話撥入式會議 PIN 設定</span><span class="sxs-lookup"><span data-stu-id="2630a-102">Create or modify dial-in conferencing PIN settings in Lync Server 2013 for a site or group of users</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2630a-103">_**主題上次修改日期：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="2630a-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="2630a-104">請依照下列步驟來建立或修改使用者層級電話撥入式會議個人識別碼（PIN）原則。</span><span class="sxs-lookup"><span data-stu-id="2630a-104">Follow these steps to create or modify a user-level or a site-level dial-in conferencing personal identification number (PIN) policy.</span></span> <span data-ttu-id="2630a-105">如需如何變更全域 PIN 原則的詳細資料，請參閱[在 Lync Server 2013 中修改預設的電話撥入式會議 PIN 設定](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="2630a-105">For details about how to change the global PIN policy, see [Modify the default dial-in conferencing PIN settings in Lync Server 2013](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md).</span></span>

<div>

## <a name="to-create-a-user-or-site-pin-policy"></a><span data-ttu-id="2630a-106">建立使用者或網站 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="2630a-106">To create a user or site PIN policy</span></span>

1.  <span data-ttu-id="2630a-107">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署 Lync Server 2013 的網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="2630a-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="2630a-108">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="2630a-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2630a-109">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="2630a-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2630a-110">在左側導覽列中，按一下 [**會議**]，然後按一下 [ **PIN 規則**]。</span><span class="sxs-lookup"><span data-stu-id="2630a-110">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="2630a-111">在 [ **PIN 原則**] 頁面上，按一下 [**新增**]，然後執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="2630a-111">On the **PIN Policy** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="2630a-112">若要建立使用者層級原則，按一下 [**使用者原則**]。</span><span class="sxs-lookup"><span data-stu-id="2630a-112">To create a user-level policy, click **User policy**.</span></span> <span data-ttu-id="2630a-113">在 [**新 PIN 原則**] 的 [**名稱**] 中，輸入描述原則的名稱。</span><span class="sxs-lookup"><span data-stu-id="2630a-113">In **New PIN Policy**, in **Name**, type a name that describes the policy.</span></span>
    
      - <span data-ttu-id="2630a-114">若要建立網站層級原則，按一下 [**網站原則**]。</span><span class="sxs-lookup"><span data-stu-id="2630a-114">To create a site-level policy, click **Site policy**.</span></span> <span data-ttu-id="2630a-115">在 [**選取網站**搜尋] 欄位中，輸入您要為其建立原則之網站的全部或部分名稱。</span><span class="sxs-lookup"><span data-stu-id="2630a-115">In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy.</span></span> <span data-ttu-id="2630a-116">在網站清單中，按一下您想要的網站，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="2630a-116">In the list of sites, click the site you want, and then click **OK**.</span></span>

5.  <span data-ttu-id="2630a-117">在 [**描述**] 欄位中，輸入 PIN 原則的描述。</span><span class="sxs-lookup"><span data-stu-id="2630a-117">In the **Description** field, type a description of the PIN policy.</span></span>

6.  <span data-ttu-id="2630a-118">在 [**最小 pin 長度**] 欄位中，輸入或選取您要允許的最小 PIN 長度。</span><span class="sxs-lookup"><span data-stu-id="2630a-118">In the **Minimum PIN length** field, type or select the minimum PIN length that you want to allow.</span></span> <span data-ttu-id="2630a-119">預設的最小長度為5位數。</span><span class="sxs-lookup"><span data-stu-id="2630a-119">The default minimum length is five digits.</span></span>

7.  <span data-ttu-id="2630a-120">若要在封鎖使用者之前，能夠指定最大的登入嘗試次數，請選取 [**指定最大登入嘗試**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="2630a-120">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box.</span></span> <span data-ttu-id="2630a-121">如果您沒有選取此選項，則會根據 PIN 長度自動判斷允許的最大嘗試次數上限。</span><span class="sxs-lookup"><span data-stu-id="2630a-121">If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length.</span></span> <span data-ttu-id="2630a-122">根據預設，會自動決定最大嘗試次數。</span><span class="sxs-lookup"><span data-stu-id="2630a-122">By default, the maximum number of attempts is automatically determined.</span></span>

8.  <span data-ttu-id="2630a-123">如果您已選取 [**指定最大登入嘗試**] 核取方塊，請在 [**最大登入次數**] 中，輸入或選取您要允許的最大登入嘗試次數。</span><span class="sxs-lookup"><span data-stu-id="2630a-123">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>

9.  <span data-ttu-id="2630a-124">若要讓 Pin 到期，請選取 [**啟用 PIN 到期**日] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="2630a-124">To have PINs expire, select the **Enable PIN expiration** check box.</span></span> <span data-ttu-id="2630a-125">如果您沒有選取此選項，針腳將永不過期。</span><span class="sxs-lookup"><span data-stu-id="2630a-125">If you do not select this option, PINs will never expire.</span></span> <span data-ttu-id="2630a-126">根據預設，Pin 永遠不會過期。</span><span class="sxs-lookup"><span data-stu-id="2630a-126">By default, PINs never expire.</span></span>

10. <span data-ttu-id="2630a-127">如果您已選取 [**啟用 PIN 到期**日] 核取方塊，請在 **[PIN 到期日之後（天數）**] 中，輸入或選取 pin 到期前的天數。</span><span class="sxs-lookup"><span data-stu-id="2630a-127">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>

11. <span data-ttu-id="2630a-128">在 [ **PIN 記錄計數**] 中，輸入使用者必須建立才能重複使用 pin 的 pin 數。</span><span class="sxs-lookup"><span data-stu-id="2630a-128">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN.</span></span> <span data-ttu-id="2630a-129">根據預設，使用者可以重複使用他們的 Pin。</span><span class="sxs-lookup"><span data-stu-id="2630a-129">By default, users can reuse their PINs.</span></span>

12. <span data-ttu-id="2630a-130">若要在 Pin 中允許通用位數（例如順序編號和重複的數位組），請選取 [**允許常見模式**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="2630a-130">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box.</span></span> <span data-ttu-id="2630a-131">如果您沒有選取此選項，則只允許使用複雜的數位模式。</span><span class="sxs-lookup"><span data-stu-id="2630a-131">If you do not select this option, only complex patterns of digits are allowed.</span></span> <span data-ttu-id="2630a-132">根據預設，只允許使用複雜的數位模式。</span><span class="sxs-lookup"><span data-stu-id="2630a-132">By default, only complex patterns of digits are allowed.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="2630a-133">我們建議您不要允許通用模式。</span><span class="sxs-lookup"><span data-stu-id="2630a-133">We recommend that you do not allow common patterns.</span></span>

    
    </div>

13. <span data-ttu-id="2630a-134">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2630a-134">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-change-a-user-or-site-pin-policy"></a><span data-ttu-id="2630a-135">變更使用者或網站的 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="2630a-135">To change a user or site PIN policy</span></span>

1.  <span data-ttu-id="2630a-136">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署 Lync Server 2013 的網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="2630a-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="2630a-137">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="2630a-137">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2630a-138">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="2630a-138">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2630a-139">在左側導覽列中，按一下 [**會議**]，然後按一下 [ **PIN 規則**]。</span><span class="sxs-lookup"><span data-stu-id="2630a-139">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="2630a-140">在 [ **PIN 原則**] 頁面上，按一下您要變更的固定原則，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="2630a-140">On the **PIN Policy** page, click the PIN policy that you want to change, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="2630a-141">在 [**編輯 PIN 原則**] 中，修改任何原則設定（除了不能修改的原則名稱之外）。</span><span class="sxs-lookup"><span data-stu-id="2630a-141">In **Edit PIN Policy**, modify any of the policy settings (except for the policy name, which cannot be modified).</span></span>

6.  <span data-ttu-id="2630a-142">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2630a-142">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

