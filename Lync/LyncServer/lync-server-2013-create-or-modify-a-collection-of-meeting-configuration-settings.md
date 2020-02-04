---
title: 建立或修改會議配置設定的集合
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
ms.openlocfilehash: 0a5f80066a68b45e062a351478bea93a5c2e8fd0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763335"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-meeting-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="86b20-102">在 Lync Server 2013 中建立或修改會議配置設定的集合</span><span class="sxs-lookup"><span data-stu-id="86b20-102">Create or modify a collection of meeting configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86b20-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="86b20-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="86b20-104">您可以使用 [會議設定] 頁面上的設定來定義會議加入體驗的各種特性。</span><span class="sxs-lookup"><span data-stu-id="86b20-104">You can use the settings on the Meeting Configuration page to define various characteristics of the meeting join experience.</span></span> <span data-ttu-id="86b20-105">根據預設，全域設定會定義連接體驗。</span><span class="sxs-lookup"><span data-stu-id="86b20-105">By default, the global settings define the join experience.</span></span> <span data-ttu-id="86b20-106">您也可以建立網站層級和池層次會議加入設定。</span><span class="sxs-lookup"><span data-stu-id="86b20-106">You can also create site-level and pool-level meeting join settings.</span></span> <span data-ttu-id="86b20-107">如果您建立了 [pool] 層級設定，這些設定就會套用至該池子主持的所有會議。</span><span class="sxs-lookup"><span data-stu-id="86b20-107">If you create pool-level settings, those settings apply to all meetings hosted by that pool.</span></span> <span data-ttu-id="86b20-108">如果您沒有建立池層級設定，就會套用網站層級設定（如果存在的話）。</span><span class="sxs-lookup"><span data-stu-id="86b20-108">If you do not create pool-level settings, site-level settings apply, if they exist.</span></span> <span data-ttu-id="86b20-109">如果您沒有定義網站層級設定，全域設定就會套用至所有會議。</span><span class="sxs-lookup"><span data-stu-id="86b20-109">If you do not define site-level settings, the global settings apply to all meetings.</span></span>

<div>

## <a name="to-create-new-meeting-join-settings"></a><span data-ttu-id="86b20-110">建立新的會議加入設定</span><span class="sxs-lookup"><span data-stu-id="86b20-110">To create new meeting join settings</span></span>

1.  <span data-ttu-id="86b20-111">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="86b20-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="86b20-112">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="86b20-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="86b20-113">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="86b20-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="86b20-114">在左側導覽列中，按一下 [**會議**]，然後按一下 [**會議配置**]。</span><span class="sxs-lookup"><span data-stu-id="86b20-114">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="86b20-115">在 [**會議**設定] 頁面上，按一下 [**新增**]，然後執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="86b20-115">On the **Meeting Configuration** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="86b20-116">若要建立網站層級原則，按一下 [**網站**設定]。</span><span class="sxs-lookup"><span data-stu-id="86b20-116">To create a site-level policy, click **Site configuration**.</span></span> <span data-ttu-id="86b20-117">在 [**選取網站**搜尋] 欄位中，輸入您要定義會議加入設定的網站名稱全部或部分名稱。</span><span class="sxs-lookup"><span data-stu-id="86b20-117">In the **Select a Site** search field, type all or part of the name of the site for which you want to define meeting join settings.</span></span> <span data-ttu-id="86b20-118">在產生的網站清單中，按一下您想要的網站，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="86b20-118">In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="86b20-119">若要建立池層級原則，請按一下 [**池**設定]。</span><span class="sxs-lookup"><span data-stu-id="86b20-119">To create a pool-level policy, click **Pool configuration**.</span></span> <span data-ttu-id="86b20-120">在 [**選取服務**搜尋] 欄位中，輸入您要定義會議加入設定的全部或部分的 [池服務] 名稱。</span><span class="sxs-lookup"><span data-stu-id="86b20-120">In the **Select a Service** search field, type all or part of the name of the pool service for which you want to define meeting join settings.</span></span> <span data-ttu-id="86b20-121">在產生的服務清單中，按一下您想要的 [池]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="86b20-121">In the resulting list of services, click the pool you want, and then click **OK**.</span></span>

5.  <span data-ttu-id="86b20-122">若要傳送透過大廳從公用交換電話網絡（PSTN）撥入的參與者，請清除**PSTN 呼叫者略過大廳**核取方塊。</span><span class="sxs-lookup"><span data-stu-id="86b20-122">To route participants who dial in from the public switched telephone network (PSTN) through the lobby, clear the **PSTN callers bypass lobby** check box.</span></span> <span data-ttu-id="86b20-123">根據預設，從 PSTN 撥入的參與者會直接進入會議。</span><span class="sxs-lookup"><span data-stu-id="86b20-123">By default, participants dialing in from the PSTN go directly to the meeting.</span></span>

6.  <span data-ttu-id="86b20-124">若要設定在會議中可成為簡報者的人員，請在 [**指定為簡報者**] 中，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="86b20-124">To configure who can be a presenter in the meeting, in **Designate as presenter**, do one of the following:</span></span>
    
      - <span data-ttu-id="86b20-125">若要不允許召集人以外的任何人成為簡報者，請按一下 [**無**]。</span><span class="sxs-lookup"><span data-stu-id="86b20-125">To not allow anyone other than the organizer to be a presenter, click **None**.</span></span>
    
      - <span data-ttu-id="86b20-126">若要只允許作為您組織成員的參與者成為簡報者，請按一下 [**公司**]。</span><span class="sxs-lookup"><span data-stu-id="86b20-126">To allow only participants who are members of your organization to be a presenter, click **Company**.</span></span> <span data-ttu-id="86b20-127">這是預設設定。</span><span class="sxs-lookup"><span data-stu-id="86b20-127">This is the default setting.</span></span>
    
      - <span data-ttu-id="86b20-128">若要讓任何參與者成為簡報者，請按一下 [**所有人**]。</span><span class="sxs-lookup"><span data-stu-id="86b20-128">To allow any participants to be a presenter, click **Everyone**.</span></span>

7.  <span data-ttu-id="86b20-129">若要讓召集人在排程會議時選取會議類型，請清除 [**預設為指派的會議類型**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="86b20-129">To have the organizer select a conference type when scheduling a meeting, clear the **Assigned conference type by default** check box.</span></span> <span data-ttu-id="86b20-130">根據預設，會自動指派會議類型。</span><span class="sxs-lookup"><span data-stu-id="86b20-130">By default, the conference type is automatically assigned.</span></span>

8.  <span data-ttu-id="86b20-131">若要防止匿名（未經授權）使用者自動獲准，請清除 [**預設承認匿名使用者**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="86b20-131">To prevent anonymous (unauthenticated) users from being automatically admitted, clear the **Admit anonymous users by default** check box.</span></span> <span data-ttu-id="86b20-132">根據預設，匿名使用者會自動獲准參加會議。</span><span class="sxs-lookup"><span data-stu-id="86b20-132">By default, anonymous users are automatically admitted to meetings.</span></span>

9.  <span data-ttu-id="86b20-133">若要自訂傳送給參與者的會議邀請，請執行下列動作。</span><span class="sxs-lookup"><span data-stu-id="86b20-133">To customize the meeting invite that is sent out to participants, do the following.</span></span> <span data-ttu-id="86b20-134">請注意，Url 和自訂頁尾文字的最大長度為1KB。</span><span class="sxs-lookup"><span data-stu-id="86b20-134">Note that the maximum length for URLs and custom footer text is 1KB.</span></span> <span data-ttu-id="86b20-135">除了說明**URL**之外，如果您沒有指定自訂專案的值，就不會包含在會議中。</span><span class="sxs-lookup"><span data-stu-id="86b20-135">Except for **Help URL**, if you do not specify a value for the customizations, they will not be included in the meeting.</span></span> <span data-ttu-id="86b20-136">如果您不包含自訂的說明 URL，則 Lync 的預設說明 URL 將會顯示在邀請中。</span><span class="sxs-lookup"><span data-stu-id="86b20-136">If you do not include a custom help URL, the default help URL for Lync will be displayed in the invite.</span></span>
    
      - <span data-ttu-id="86b20-137">若要自訂會議邀請中出現的標誌，請在 [**標誌 URL**] 中輸入標誌的位置。</span><span class="sxs-lookup"><span data-stu-id="86b20-137">To customize the logo that appears in the meeting invite, in **Logo URL**, enter the location of the logo.</span></span>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="86b20-138">標誌必須是一個大小為 188 x 30 圖元的 GIF 或 JPG 影像。</span><span class="sxs-lookup"><span data-stu-id="86b20-138">The logo must be a GIF or JPG image with a size of 188 by 30 pixels.</span></span>

        
        </div>
    
      - <span data-ttu-id="86b20-139">若要自訂會議邀請中出現的解說文字，請在 [說明] **URL**中輸入解說文字的位置。</span><span class="sxs-lookup"><span data-stu-id="86b20-139">To customize the help text that appears in the meeting invite, in **Help URL**, enter the location of the help text.</span></span>
    
      - <span data-ttu-id="86b20-140">若要自訂會議邀請中出現的法律文字，請在 [**合法文字 URL**] 中輸入法律文字的位置。</span><span class="sxs-lookup"><span data-stu-id="86b20-140">To customize the legal text that appears in the meeting invite, in **Legal text URL**, enter the location of the legal text.</span></span>
    
      - <span data-ttu-id="86b20-141">若要自訂會議邀請中顯示的頁尾文字，請在 [**自訂頁尾文字**] 中輸入文字。</span><span class="sxs-lookup"><span data-stu-id="86b20-141">To customize the footer text that appears in the meeting invite, in **Custom footer text**, enter text.</span></span>

10. <span data-ttu-id="86b20-142">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="86b20-142">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-collection-of-meeting-configurations"></a><span data-ttu-id="86b20-143">修改現有的會議組態集合</span><span class="sxs-lookup"><span data-stu-id="86b20-143">To modify an existing collection of meeting configurations</span></span>

1.  <span data-ttu-id="86b20-144">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="86b20-144">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="86b20-145">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="86b20-145">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="86b20-146">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="86b20-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="86b20-147">在左側導覽列中，按一下 [**會議**]，然後按一下 [**會議配置**]。</span><span class="sxs-lookup"><span data-stu-id="86b20-147">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="86b20-148">在會議配置清單中，按一下您要變更的設定，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="86b20-148">In the list of meeting configurations, click the configuration that you want to change, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="86b20-149">在 [**編輯會議**設定] 中，修改任何設定的設定，除了不能修改的配置名稱。</span><span class="sxs-lookup"><span data-stu-id="86b20-149">In **Edit Meeting Configuration**, modify any of the configuration settings, except for the configuration name, which cannot be modified.</span></span>

6.  <span data-ttu-id="86b20-150">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="86b20-150">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-new-meeting-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="86b20-151">使用 Windows PowerShell Cmdlet 建立新的會議配置設定</span><span class="sxs-lookup"><span data-stu-id="86b20-151">Creating New Meeting Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="86b20-152">您可以使用 Windows PowerShell 和 CsMeetingConfiguration Cmdlet 來建立會議設定設定（僅限在網站範圍內）。</span><span class="sxs-lookup"><span data-stu-id="86b20-152">Meeting configuration settings can be created (at the site scope only) by using Windows PowerShell and the New-CsMeetingConfiguration cmdlet.</span></span> <span data-ttu-id="86b20-153">這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。</span><span class="sxs-lookup"><span data-stu-id="86b20-153">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="86b20-154">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="86b20-154">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-meeting-configuration-settings-that-use-the-default-values"></a><span data-ttu-id="86b20-155">若要建立使用預設值的會議設定設定</span><span class="sxs-lookup"><span data-stu-id="86b20-155">To create meeting configuration settings that use the default values</span></span>

  - <span data-ttu-id="86b20-156">這個命令會針對雷德蒙的網站建立一組新的會議配置設定：</span><span class="sxs-lookup"><span data-stu-id="86b20-156">This command creates a new set of meeting configuration settings for the Redmond site:</span></span>
    
        New-CsMeetingConfiguration -Identity "site:Redmond"
    
    <span data-ttu-id="86b20-157">因為在上述命令中沒有指定任何參數（除了是強制身分識別參數），所以新的會議設定會針對其所有屬性使用預設值。</span><span class="sxs-lookup"><span data-stu-id="86b20-157">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new meeting configuration settings will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-change-a-property-value-when-creating-meeting-configuration-settings"></a><span data-ttu-id="86b20-158">若要在建立會議設定設定時變更屬性值</span><span class="sxs-lookup"><span data-stu-id="86b20-158">To change a property value when creating meeting configuration settings</span></span>

  - <span data-ttu-id="86b20-159">若要建立使用不同屬性值的設定，只要包含適當的參數和參數值即可。</span><span class="sxs-lookup"><span data-stu-id="86b20-159">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="86b20-160">例如，若要建立會議設定的集合，根據預設，承認所有人都可以以演講者身分參與會議，請使用如下所示的命令：</span><span class="sxs-lookup"><span data-stu-id="86b20-160">For example, to create a collection of meeting configuration settings that, by default, admit everyone to a meeting as a presenter use a command like this:</span></span>
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-meeting-configuration-settings"></a><span data-ttu-id="86b20-161">若要在建立會議設定設定時變更多個屬性值</span><span class="sxs-lookup"><span data-stu-id="86b20-161">To change multiple property values when creating meeting configuration settings</span></span>

  - <span data-ttu-id="86b20-162">您可以透過包含多個參數來修改多個屬性值。</span><span class="sxs-lookup"><span data-stu-id="86b20-162">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="86b20-163">例如，此命令會允許所有人加入會議，同時也會強制 PSTN 使用者在大廳等候，直到正式獲准參加會議：</span><span class="sxs-lookup"><span data-stu-id="86b20-163">For example, this command admits everyone to a meeting as a presenter and also forces PSTN users to wait in the lobby until they are formally admitted to the meeting:</span></span>
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True

</div>

<span data-ttu-id="86b20-164">如需詳細資訊，請參閱[新版-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg398065(v=OCS.15)) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="86b20-164">For more information, see the help topic for the [New-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg398065(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

