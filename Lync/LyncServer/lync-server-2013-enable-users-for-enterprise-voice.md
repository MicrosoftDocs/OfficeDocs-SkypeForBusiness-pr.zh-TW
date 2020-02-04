---
title: Lync Server 2013：允許使用者使用企業語音
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for Enterprise Voice
ms:assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413011(v=OCS.15)
ms:contentKeyID: 48185800
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b851c8807e12456c600b2ca176b0fa5a834f0d5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736013"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-users-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="8ae9b-102">在 Lync Server 2013 中啟用企業語音的使用者</span><span class="sxs-lookup"><span data-stu-id="8ae9b-102">Enable users for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ae9b-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="8ae9b-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="8ae9b-104">在您安裝一或多個中繼伺服器的檔案之後，請設定輸出呼叫路由，以及選擇性地部署一或多個高級企業語音功能，您可以使用下列程式，讓使用者使用企業語音進行通話：</span><span class="sxs-lookup"><span data-stu-id="8ae9b-104">After you install files for one or more Mediation Servers, configure outbound call routing, and optionally deploy one or more advanced Enterprise Voice features, you can use the following procedures to enable a user to make calls by using Enterprise Voice:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8ae9b-105">在下列程式中，只有第一個程式可以使用 Lync Server [控制台] 執行。</span><span class="sxs-lookup"><span data-stu-id="8ae9b-105">Of the following procedures, only the first can be performed by using Lync Server Control Panel.</span></span> <span data-ttu-id="8ae9b-106">在其餘的程式中，您只能使用 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="8ae9b-106">For the remaining procedures, you can use only Lync Server Management Shell.</span></span>



</div>

  - <span data-ttu-id="8ae9b-107">啟用企業語音的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="8ae9b-107">Enable the user account for Enterprise Voice.</span></span>

  - <span data-ttu-id="8ae9b-108">可選指派使用者帳戶專用的語音原則。</span><span class="sxs-lookup"><span data-stu-id="8ae9b-108">(Optional) Assign the user account a user-specific voice policy.</span></span>

  - <span data-ttu-id="8ae9b-109">可選將使用者帳戶指派給使用者專用的撥號方案。</span><span class="sxs-lookup"><span data-stu-id="8ae9b-109">(Optional) Assign the user account a user-specific dial plan.</span></span>

<div>

## <a name="to-enable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="8ae9b-110">啟用企業語音的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="8ae9b-110">To enable a user account for Enterprise Voice</span></span>

1.  <span data-ttu-id="8ae9b-111">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="8ae9b-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8ae9b-112">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="8ae9b-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8ae9b-113">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="8ae9b-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8ae9b-114">在左側導覽列中，按一下 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="8ae9b-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="8ae9b-115">在 [**搜尋使用者**] 方塊中，輸入您要啟用的使用者帳戶的全部或第一部分的顯示名稱、名字、姓氏、安全帳戶管理員（SAM）帳戶名稱、SIP 位址或行統一資源識別項（URI），然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="8ae9b-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="8ae9b-116">在表格中，按一下您要為企業語音啟用的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="8ae9b-116">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6.  <span data-ttu-id="8ae9b-117">按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="8ae9b-117">On the **Edit** menu, click **Show details**.</span></span>

7.  <span data-ttu-id="8ae9b-118">在 [**編輯 Lync Server 使用者**] 頁面的 [**電話**] 底下，按一下 [**企業語音**]。</span><span class="sxs-lookup"><span data-stu-id="8ae9b-118">On the **Edit Lync Server User** page, under **Telephony**, click **Enterprise Voice**.</span></span>

8.  <span data-ttu-id="8ae9b-119">按一下 [**行 URI**]，然後輸入唯一的、標準化的電話號碼（例如電話： + 14255550200）。</span><span class="sxs-lookup"><span data-stu-id="8ae9b-119">Click **Line URI**, and then type a unique, normalized phone number (for example, tel:+14255550200).</span></span>

9.  <span data-ttu-id="8ae9b-120">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8ae9b-120">Click **Commit**.</span></span>

<span data-ttu-id="8ae9b-121">若要為使用者啟用企業語音，請確定使用者已獲指派語音原則和撥號方案，不論全域（預設為指派）或使用者專用。</span><span class="sxs-lookup"><span data-stu-id="8ae9b-121">To finish enabling a user for Enterprise Voice, be sure that the user is assigned a voice policy and a dial plan, whether global (assigned by default) or user-specific.</span></span>

<span data-ttu-id="8ae9b-122">根據預設，所有使用者都會獲指派全域語音原則和撥號方案。</span><span class="sxs-lookup"><span data-stu-id="8ae9b-122">By default, all users are assigned a global voice policy and dial plan.</span></span> <span data-ttu-id="8ae9b-123">如果使用者帳戶所在網站的網站層級存在語音原則或撥號方案，這些網站原則將會自動套用至使用者。</span><span class="sxs-lookup"><span data-stu-id="8ae9b-123">If a voice policy or dial plan exists at the site level for the site on which the user account is homed, those site policies will automatically apply to the user.</span></span> <span data-ttu-id="8ae9b-124">若要將每個使用者的語音原則或撥號方案套用至使用者，您必須執行**授與 CsVoicePolicy**並**授與 CsDialPlan** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8ae9b-124">To apply a per-user voice policy or dial plan to a user, you must run the **Grant-CsVoicePolicy** and **Grant-CsDialPlan** cmdlets.</span></span> <span data-ttu-id="8ae9b-125">如需詳細資訊，請參閱[Lync Server 2013 管理命令](lync-server-2013-lync-server-management-shell.md)介面檔。</span><span class="sxs-lookup"><span data-stu-id="8ae9b-125">For details, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

<div>

## <a name="voice-policy-assignment"></a><span data-ttu-id="8ae9b-126">語音原則指派</span><span class="sxs-lookup"><span data-stu-id="8ae9b-126">Voice Policy Assignment</span></span>

<span data-ttu-id="8ae9b-127">全域及網站層級語音原則會自動指派給所有已啟用企業語音的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="8ae9b-127">Global and site-level voice policies are automatically assigned to all user accounts that are enabled for Enterprise Voice.</span></span> <span data-ttu-id="8ae9b-128">您也可以建立適用于特定使用者或群組的語音原則。</span><span class="sxs-lookup"><span data-stu-id="8ae9b-128">You can also create voice policies that apply to specific users or groups.</span></span> <span data-ttu-id="8ae9b-129">這些每個使用者的原則必須明確指派給使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="8ae9b-129">These per-user policies must be explicitly assigned to the users or groups.</span></span> <span data-ttu-id="8ae9b-130">如果您想要針對所有已啟用企業語音的使用者使用全域或網站語音原則，您可以略過此區段，然後繼續本主題稍後的撥號計畫作業區段。</span><span class="sxs-lookup"><span data-stu-id="8ae9b-130">If you want to use the global or site voice policy for all users who are enabled for Enterprise Voice, you can skip this section and continue to Dial Plan Assignment section later in this topic.</span></span>

<div>

## <a name="to-assign-a-user-specific-voice-policy"></a><span data-ttu-id="8ae9b-131">指派使用者專用的語音原則</span><span class="sxs-lookup"><span data-stu-id="8ae9b-131">To assign a user-specific voice policy</span></span>

1.  <span data-ttu-id="8ae9b-132">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="8ae9b-132">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8ae9b-133">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="8ae9b-133">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="8ae9b-134">若要將現有的使用者語音原則指派給使用者，請在命令提示字元執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="8ae9b-134">To assign an existing user voice policy to a user, run the following at the command prompt:</span></span>
    
        Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
    
    <span data-ttu-id="8ae9b-135">例如：</span><span class="sxs-lookup"><span data-stu-id="8ae9b-135">For example:</span></span>
    
        Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
    
    <span data-ttu-id="8ae9b-136">在這個範例中，使用顯示名稱 Bob 凱利的使用者會獲指派「名稱**VoicePolicyJapan**」的語音原則。</span><span class="sxs-lookup"><span data-stu-id="8ae9b-136">In this example, the user with the display name Bob Kelly is assigned the voice policy with the name **VoicePolicyJapan**.</span></span>

<span data-ttu-id="8ae9b-137">如需指派使用者特定語音原則或執行**Grant CsVoicePolicy** Cmdlet 的詳細資料，請參閱[Lync Server 2013 管理命令](lync-server-2013-lync-server-management-shell.md)介面檔。</span><span class="sxs-lookup"><span data-stu-id="8ae9b-137">For details about assigning a user-specific voice policy or about running the **Grant-CsVoicePolicy** cmdlet, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

</div>

<span id="BKMK_DialPlanAssignment"></span>

<div>

## <a name="dial-plan-assignment"></a><span data-ttu-id="8ae9b-138">撥號方案指派</span><span class="sxs-lookup"><span data-stu-id="8ae9b-138">Dial Plan Assignment</span></span>

<span data-ttu-id="8ae9b-139">若要為企業語音或電話撥入式會議的使用者完成使用者帳戶設定，必須為使用者指派撥號方案。</span><span class="sxs-lookup"><span data-stu-id="8ae9b-139">To complete user account configuration for either users of Enterprise Voice or users of dial-in conferencing, the user must be assigned a dial plan.</span></span> <span data-ttu-id="8ae9b-140">如果您不明確指派現有的每個使用者撥號方案，使用者帳戶就會自動使用全域撥號方案，或（如果有的話）。</span><span class="sxs-lookup"><span data-stu-id="8ae9b-140">User accounts will automatically use the global dial plan or, if one exists, the site-level dial plan, when you do not explicitly assign an existing per-user dial plan.</span></span> <span data-ttu-id="8ae9b-141">如果您想要針對所有已啟用企業語音的使用者使用全域或網站撥號方案，您可以略過本節。</span><span class="sxs-lookup"><span data-stu-id="8ae9b-141">If you want to use the global or site dial plan for all users who are enabled for Enterprise Voice, you can skip this section.</span></span>

<div>

## <a name="to-assign-a-dial-plan"></a><span data-ttu-id="8ae9b-142">指派撥號方案</span><span class="sxs-lookup"><span data-stu-id="8ae9b-142">To assign a dial plan</span></span>

1.  <span data-ttu-id="8ae9b-143">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="8ae9b-143">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8ae9b-144">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="8ae9b-144">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="8ae9b-145">若要指派使用者特定的撥號方案，請在命令提示字元執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="8ae9b-145">To assign a user-specific dial plan, run the following at the command prompt:</span></span>
    
        Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
    
    <span data-ttu-id="8ae9b-146">例如：</span><span class="sxs-lookup"><span data-stu-id="8ae9b-146">For example:</span></span>
    
        Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
    
    <span data-ttu-id="8ae9b-147">在這個範例中，使用顯示名稱 Bob 凱利的使用者會被指派名稱為**DialPlanJapan**的使用者撥號計畫。</span><span class="sxs-lookup"><span data-stu-id="8ae9b-147">In this example, the user with the display name Bob Kelly is assigned the user dial plan with the name **DialPlanJapan**.</span></span>

<span data-ttu-id="8ae9b-148">如需指派使用者撥號方案或執行**授與 CsDialPlan** Cmdlet 的詳細資料，請參閱[Lync Server 2013 管理命令](lync-server-2013-lync-server-management-shell.md)介面檔。</span><span class="sxs-lookup"><span data-stu-id="8ae9b-148">For details about assigning a user dial plan or about running the **Grant-CsDialPlan** cmdlet, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8ae9b-149">請參閱</span><span class="sxs-lookup"><span data-stu-id="8ae9b-149">See Also</span></span>


[<span data-ttu-id="8ae9b-150">在 Lync Server 2013 中停用企業語音的使用者</span><span class="sxs-lookup"><span data-stu-id="8ae9b-150">Disable a user for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-disable-a-user-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

