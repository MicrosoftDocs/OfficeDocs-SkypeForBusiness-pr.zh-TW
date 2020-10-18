---
title: 建立或修改會議配置設定的集合
description: 建立或修改會議配置設定的集合。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of meeting configuration settings
ms:assetid: ce6773c1-a0d5-4405-8e32-33a6f3a46a1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721889(v=OCS.15)
ms:contentKeyID: 49733822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51dd68b3d149e5a96628fc3343d0d7eb3ae8020d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578239"
---
# <a name="create-or-modify-a-collection-of-meeting-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="6caad-103">在 Lync Server 2013 中建立或修改會議配置設定的集合</span><span class="sxs-lookup"><span data-stu-id="6caad-103">Create or modify a collection of meeting configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6caad-104">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="6caad-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="6caad-105">您可以使用 [會議設定] 頁面上的設定來定義會議加入體驗的各種特性。</span><span class="sxs-lookup"><span data-stu-id="6caad-105">You can use the settings on the Meeting Configuration page to define various characteristics of the meeting join experience.</span></span> <span data-ttu-id="6caad-106">根據預設，全域設定會定義加入體驗。</span><span class="sxs-lookup"><span data-stu-id="6caad-106">By default, the global settings define the join experience.</span></span> <span data-ttu-id="6caad-107">您也可以建立網站層級與集區層級會議加入設定。</span><span class="sxs-lookup"><span data-stu-id="6caad-107">You can also create site-level and pool-level meeting join settings.</span></span> <span data-ttu-id="6caad-108">如果您建立集區層級設定，這些設定會套用至該集區所主控的所有會議。</span><span class="sxs-lookup"><span data-stu-id="6caad-108">If you create pool-level settings, those settings apply to all meetings hosted by that pool.</span></span> <span data-ttu-id="6caad-109">如果您未建立集區層級設定，則會套用網站層級設定（如果有的話）。</span><span class="sxs-lookup"><span data-stu-id="6caad-109">If you do not create pool-level settings, site-level settings apply, if they exist.</span></span> <span data-ttu-id="6caad-110">如果您未定義網站層級設定，全域設定會套用至所有會議。</span><span class="sxs-lookup"><span data-stu-id="6caad-110">If you do not define site-level settings, the global settings apply to all meetings.</span></span>

<div>

## <a name="to-create-new-meeting-join-settings"></a><span data-ttu-id="6caad-111">若要建立新的會議加入設定</span><span class="sxs-lookup"><span data-stu-id="6caad-111">To create new meeting join settings</span></span>

1.  <span data-ttu-id="6caad-112">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="6caad-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6caad-113">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="6caad-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6caad-114">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="6caad-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6caad-115">在左導覽列中，按一下 [ **會議** ]，然後按一下 [ **會議**設定]。</span><span class="sxs-lookup"><span data-stu-id="6caad-115">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="6caad-116">在 [ **會議** 設定] 頁面上，按一下 [ **新增**]，然後執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="6caad-116">On the **Meeting Configuration** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="6caad-117">若要建立網站層級原則，請按一下 [ **網站**設定]。</span><span class="sxs-lookup"><span data-stu-id="6caad-117">To create a site-level policy, click **Site configuration**.</span></span> <span data-ttu-id="6caad-118">在 [ **選取網站** ] 搜尋欄位中，輸入您要定義會議加入設定之網站的全部或部分名稱。</span><span class="sxs-lookup"><span data-stu-id="6caad-118">In the **Select a Site** search field, type all or part of the name of the site for which you want to define meeting join settings.</span></span> <span data-ttu-id="6caad-119">在產生的網站清單中，按一下您想要的網站，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="6caad-119">In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="6caad-120">若要建立集區層級原則，請按一下 [ **集**區設定]。</span><span class="sxs-lookup"><span data-stu-id="6caad-120">To create a pool-level policy, click **Pool configuration**.</span></span> <span data-ttu-id="6caad-121">在 [ **選取服務** ] 搜尋欄位中，輸入您要定義會議加入設定之集區服務的全部或部分名稱。</span><span class="sxs-lookup"><span data-stu-id="6caad-121">In the **Select a Service** search field, type all or part of the name of the pool service for which you want to define meeting join settings.</span></span> <span data-ttu-id="6caad-122">在產生的服務清單中，按一下您想要的集區，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="6caad-122">In the resulting list of services, click the pool you want, and then click **OK**.</span></span>

5.  <span data-ttu-id="6caad-123">若要透過會議廳從公用交換電話網路 (PSTN) 傳送從公用交換電話網路撥號的參與者，請清除 [ **PSTN 來電者旁路會議廳** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="6caad-123">To route participants who dial in from the public switched telephone network (PSTN) through the lobby, clear the **PSTN callers bypass lobby** check box.</span></span> <span data-ttu-id="6caad-124">根據預設，從 PSTN 撥入的參與者會直接進入會議。</span><span class="sxs-lookup"><span data-stu-id="6caad-124">By default, participants dialing in from the PSTN go directly to the meeting.</span></span>

6.  <span data-ttu-id="6caad-125">若要設定在會議中誰可以是簡報者，請在 [ **指定為簡報者**] 中，執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="6caad-125">To configure who can be a presenter in the meeting, in **Designate as presenter**, do one of the following:</span></span>
    
      - <span data-ttu-id="6caad-126">若不允許召集人以外的任何人員成為簡報者，請按一下 [ **無**]。</span><span class="sxs-lookup"><span data-stu-id="6caad-126">To not allow anyone other than the organizer to be a presenter, click **None**.</span></span>
    
      - <span data-ttu-id="6caad-127">若只要允許屬於組織成員的參與者成為簡報者，請按一下 [ **公司**]。</span><span class="sxs-lookup"><span data-stu-id="6caad-127">To allow only participants who are members of your organization to be a presenter, click **Company**.</span></span> <span data-ttu-id="6caad-128">這是預設設定。</span><span class="sxs-lookup"><span data-stu-id="6caad-128">This is the default setting.</span></span>
    
      - <span data-ttu-id="6caad-129">若要允許任何參與者成為簡報者，請按一下 [ **所有人**]。</span><span class="sxs-lookup"><span data-stu-id="6caad-129">To allow any participants to be a presenter, click **Everyone**.</span></span>

7.  <span data-ttu-id="6caad-130">若要讓召集人在排程會議時選取會議類型，請清除 [ **依預設指派會議類型** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="6caad-130">To have the organizer select a conference type when scheduling a meeting, clear the **Assigned conference type by default** check box.</span></span> <span data-ttu-id="6caad-131">依預設，會自動指派會議類型。</span><span class="sxs-lookup"><span data-stu-id="6caad-131">By default, the conference type is automatically assigned.</span></span>

8.  <span data-ttu-id="6caad-132">若要防止匿名 (未驗證的使用者自動獲准) 使用者，請清除 [ **預設會承認匿名使用者** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="6caad-132">To prevent anonymous (unauthenticated) users from being automatically admitted, clear the **Admit anonymous users by default** check box.</span></span> <span data-ttu-id="6caad-133">根據預設，匿名使用者會自動獲准參加會議。</span><span class="sxs-lookup"><span data-stu-id="6caad-133">By default, anonymous users are automatically admitted to meetings.</span></span>

9.  <span data-ttu-id="6caad-134">若要自訂傳送給參與者的會議邀請，請執行下列動作。</span><span class="sxs-lookup"><span data-stu-id="6caad-134">To customize the meeting invite that is sent out to participants, do the following.</span></span> <span data-ttu-id="6caad-135">請注意，URLs 和自訂頁腳文字的最大長度為1KB。</span><span class="sxs-lookup"><span data-stu-id="6caad-135">Note that the maximum length for URLs and custom footer text is 1KB.</span></span> <span data-ttu-id="6caad-136">除了 [說明 **URL**] 之外，如果您沒有指定自訂專案的值，這些自訂專案不會包含在會議中。</span><span class="sxs-lookup"><span data-stu-id="6caad-136">Except for **Help URL**, if you do not specify a value for the customizations, they will not be included in the meeting.</span></span> <span data-ttu-id="6caad-137">如果不包含自訂的 help URL，則會在邀請中顯示 Lync 的預設說明 URL。</span><span class="sxs-lookup"><span data-stu-id="6caad-137">If you do not include a custom help URL, the default help URL for Lync will be displayed in the invite.</span></span>
    
      - <span data-ttu-id="6caad-138">若要自訂出現在會議邀請中的標誌，請在 [ **標誌 URL**] 中輸入標誌的位置。</span><span class="sxs-lookup"><span data-stu-id="6caad-138">To customize the logo that appears in the meeting invite, in **Logo URL**, enter the location of the logo.</span></span>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="6caad-139">此徽標必須是大小為 188 x 30 圖元的 GIF 或 JPG 影像。</span><span class="sxs-lookup"><span data-stu-id="6caad-139">The logo must be a GIF or JPG image with a size of 188 by 30 pixels.</span></span>

        
        </div>
    
      - <span data-ttu-id="6caad-140">若要自訂出現在會議邀請中的解說文字，請在 [說明 **URL**] 中輸入説明文字的位置。</span><span class="sxs-lookup"><span data-stu-id="6caad-140">To customize the help text that appears in the meeting invite, in **Help URL**, enter the location of the help text.</span></span>
    
      - <span data-ttu-id="6caad-141">若要自訂出現在會議邀請中的法律文字，請在 [ **合法文字 URL**] 中輸入法律文字的位置。</span><span class="sxs-lookup"><span data-stu-id="6caad-141">To customize the legal text that appears in the meeting invite, in **Legal text URL**, enter the location of the legal text.</span></span>
    
      - <span data-ttu-id="6caad-142">若要自訂出現在會議邀請中的頁腳文字，請在 [ **自訂頁腳文字**] 中輸入文字。</span><span class="sxs-lookup"><span data-stu-id="6caad-142">To customize the footer text that appears in the meeting invite, in **Custom footer text**, enter text.</span></span>

10. <span data-ttu-id="6caad-143">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="6caad-143">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-collection-of-meeting-configurations"></a><span data-ttu-id="6caad-144">修改現有會議組態集合</span><span class="sxs-lookup"><span data-stu-id="6caad-144">To modify an existing collection of meeting configurations</span></span>

1.  <span data-ttu-id="6caad-145">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="6caad-145">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6caad-146">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="6caad-146">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6caad-147">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="6caad-147">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6caad-148">在左導覽列中，按一下 [ **會議** ]，然後按一下 [ **會議**設定]。</span><span class="sxs-lookup"><span data-stu-id="6caad-148">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="6caad-149">在會議設定清單中，按一下您要變更的設定，然後按一下 [ **編輯**]，再按一下 [ **顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="6caad-149">In the list of meeting configurations, click the configuration that you want to change, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="6caad-150">在 [ **編輯會議**設定] 中，修改設定名稱以外的任何設定，但無法修改。</span><span class="sxs-lookup"><span data-stu-id="6caad-150">In **Edit Meeting Configuration**, modify any of the configuration settings, except for the configuration name, which cannot be modified.</span></span>

6.  <span data-ttu-id="6caad-151">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="6caad-151">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-new-meeting-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="6caad-152">使用 Windows PowerShell Cmdlet 建立新的會議配置設定</span><span class="sxs-lookup"><span data-stu-id="6caad-152">Creating New Meeting Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="6caad-153">您只能使用 Windows PowerShell 和 New-CsMeetingConfiguration 指令程式) ，在網站範圍上建立會議設定設定 (。</span><span class="sxs-lookup"><span data-stu-id="6caad-153">Meeting configuration settings can be created (at the site scope only) by using Windows PowerShell and the New-CsMeetingConfiguration cmdlet.</span></span> <span data-ttu-id="6caad-154">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6caad-154">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="6caad-155">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="6caad-155">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-meeting-configuration-settings-that-use-the-default-values"></a><span data-ttu-id="6caad-156">若要建立使用預設值的會議設定</span><span class="sxs-lookup"><span data-stu-id="6caad-156">To create meeting configuration settings that use the default values</span></span>

  - <span data-ttu-id="6caad-157">這個命令會為 Redmond 網站建立一組新的會議配置設定：</span><span class="sxs-lookup"><span data-stu-id="6caad-157">This command creates a new set of meeting configuration settings for the Redmond site:</span></span>
    
        New-CsMeetingConfiguration -Identity "site:Redmond"
    
    <span data-ttu-id="6caad-158">由於上述命令中未指定任何 (必要 Identity 參數) 以外的參數，因此新的會議設定會使用其所有屬性的預設值。</span><span class="sxs-lookup"><span data-stu-id="6caad-158">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new meeting configuration settings will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-change-a-property-value-when-creating-meeting-configuration-settings"></a><span data-ttu-id="6caad-159">在建立會議設定設定時變更屬性值</span><span class="sxs-lookup"><span data-stu-id="6caad-159">To change a property value when creating meeting configuration settings</span></span>

  - <span data-ttu-id="6caad-160">若要建立使用不同屬性質的設定，只需要加入適當的參數和參數值即可。</span><span class="sxs-lookup"><span data-stu-id="6caad-160">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="6caad-161">例如，若要建立會議設定的集合，根據預設，承認所有人都可以加入會議，以供簡報者使用類似如下的命令：</span><span class="sxs-lookup"><span data-stu-id="6caad-161">For example, to create a collection of meeting configuration settings that, by default, admit everyone to a meeting as a presenter use a command like this:</span></span>
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-meeting-configuration-settings"></a><span data-ttu-id="6caad-162">在建立會議設定設定時變更多個屬性值</span><span class="sxs-lookup"><span data-stu-id="6caad-162">To change multiple property values when creating meeting configuration settings</span></span>

  - <span data-ttu-id="6caad-163">多項屬性值可透過加入多個參數加以修改。</span><span class="sxs-lookup"><span data-stu-id="6caad-163">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="6caad-164">例如，此命令會 admits 所有人做為簡報者會議，也會強制 PSTN 使用者在大廳等候後，直到他們正式獲准參加會議為止：</span><span class="sxs-lookup"><span data-stu-id="6caad-164">For example, this command admits everyone to a meeting as a presenter and also forces PSTN users to wait in the lobby until they are formally admitted to the meeting:</span></span>
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True

</div>

<span data-ttu-id="6caad-165">如需詳細資訊，請參閱 [New-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg398065(v=OCS.15)) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="6caad-165">For more information, see the help topic for the [New-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg398065(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

