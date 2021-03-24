---
title: 在商務用 Skype Server 中建立或修改未指派號碼範圍
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a102b226-0460-4d5c-82f9-79b8444fa958
description: 在商務用 Skype Server Enterprise Voice 中建立、修改或刪除未指派的號碼範圍給宣告應用程式。 這會影響如何處理未指派號碼的呼叫。
ms.openlocfilehash: 72c9ec5b6b1e3d4577507ede0a5ed61560928f03
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093051"
---
# <a name="create-or-modify-an-unassigned-number-range-in-skype-for-business-server"></a><span data-ttu-id="041d7-104">在商務用 Skype Server 中建立或修改未指派號碼範圍</span><span class="sxs-lookup"><span data-stu-id="041d7-104">Create or modify an unassigned number range in Skype for Business Server</span></span>
 
<span data-ttu-id="041d7-105">在商務用 Skype Server Enterprise Voice 中建立、修改或刪除未指派的號碼範圍給宣告應用程式。</span><span class="sxs-lookup"><span data-stu-id="041d7-105">Create, modify or delete unassigned number ranges for Announcement application in Skype for Business Server Enterprise Voice.</span></span> <span data-ttu-id="041d7-106">這會影響如何處理未指派號碼的呼叫。</span><span class="sxs-lookup"><span data-stu-id="041d7-106">This affects how calls to unassigned numbers are handled.</span></span>
  
<span data-ttu-id="041d7-107">商務用 Skype Server 可讓您瞭解對您的組織有效的電話號碼，但未指派給使用者或電話的來電。</span><span class="sxs-lookup"><span data-stu-id="041d7-107">Skype for Business Server enables you to say what happens to incoming calls to phone numbers that are valid for your organization, but are not assigned to a user or a phone.</span></span> <span data-ttu-id="041d7-108">若要處理這類通話，您可以設定未指派的號碼表。</span><span class="sxs-lookup"><span data-stu-id="041d7-108">To handle such calls, you set up an unassigned number table.</span></span> <span data-ttu-id="041d7-109">您可以使用表格將通話路由傳送至宣告應用程式或 Exchange UM 伺服器。</span><span class="sxs-lookup"><span data-stu-id="041d7-109">You can use the table to route the calls to an Announcement application or to an Exchange UM server.</span></span>
  
<span data-ttu-id="041d7-110">設定未指派號碼表的方式取決於其使用方式。</span><span class="sxs-lookup"><span data-stu-id="041d7-110">How you configure the unassigned number table depends on how you want to use it.</span></span> <span data-ttu-id="041d7-111">您可以設定包含組織所有有效分機號碼、只包含未指派的分機號碼，或包含結合這兩種類型之號碼的表格。</span><span class="sxs-lookup"><span data-stu-id="041d7-111">You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers.</span></span> <span data-ttu-id="041d7-112">未指派號碼表可以同時包含已指派和未指派的號碼，但是只有在來電者撥打目前未指派的號碼時才會叫用。</span><span class="sxs-lookup"><span data-stu-id="041d7-112">The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned.</span></span> <span data-ttu-id="041d7-113">如果您在未指派號碼表中納入所有有效的分機號碼，可以指定每次某人離開組織時要執行的動作，而不必重新設定表格。</span><span class="sxs-lookup"><span data-stu-id="041d7-113">If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table.</span></span> <span data-ttu-id="041d7-114">如果您在表格中包含未指派的副檔名，您可以修改針對特定數位所發生的動作。</span><span class="sxs-lookup"><span data-stu-id="041d7-114">If you include unassigned extensions in the table, you can modify the action that occurs for specific numbers.</span></span> <span data-ttu-id="041d7-115">例如，如果您變更客戶服務服務台的分機號碼，您可以在資料表中包含舊的客戶服務號碼，然後將其指派給提供新號碼的宣告。</span><span class="sxs-lookup"><span data-stu-id="041d7-115">For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and then assign it to an announcement that provides the new number.</span></span>
  
## <a name="configure-unassigned-phone-numbers"></a><span data-ttu-id="041d7-116">設定未指派的電話號碼</span><span class="sxs-lookup"><span data-stu-id="041d7-116">Configure unassigned phone numbers</span></span>

<span data-ttu-id="041d7-117">使用下列其中一個程式來設定宣告應用程式的未指派號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="041d7-117">Use one of the following procedures to configure unassigned number ranges for the Announcement application.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="041d7-118">在您設定未指派的號碼表之前，您的系統必須已定義宣告，或是已設定 Exchange 整合通訊 (UM) 自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="041d7-118">Before you configure the unassigned number table, your system must already either have Announcements defined or an Exchange Unified Messaging (UM) Auto Attendant set up.</span></span> 
  
> [!TIP]
> <span data-ttu-id="041d7-119">當某人呼叫未指派的號碼時，商務用 Skype 伺服器會從上到下搜尋未指派號碼表格，並使用第一個相符的範圍。</span><span class="sxs-lookup"><span data-stu-id="041d7-119">When someone calls an unassigned number, Skype for Business Server searches the unassigned number table from top to bottom and uses the first matching range.</span></span> <span data-ttu-id="041d7-120">因此，應為表格中的最後一個範圍指定您想要執行做為最後一個手段的動作。</span><span class="sxs-lookup"><span data-stu-id="041d7-120">Therefore, an action that you want to be performed as a last resort should be specified for the last range in the table.</span></span> 
  
### <a name="to-use-skype-for-business-server-control-panel-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="041d7-121">使用商務用 Skype Server 控制台設定未指派的電話號碼</span><span class="sxs-lookup"><span data-stu-id="041d7-121">To use Skype for Business Server Control Panel to configure unassigned phone numbers</span></span>

1. <span data-ttu-id="041d7-122">以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="041d7-122">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="041d7-123">如需詳細資訊，請參閱＜**Delegate Setup Permissions**＞。</span><span class="sxs-lookup"><span data-stu-id="041d7-123">For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="041d7-124">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="041d7-124">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="041d7-125">在左導覽列中，依序按一下 [ **語音功能**] 和 [ **未指派的號碼**]。</span><span class="sxs-lookup"><span data-stu-id="041d7-125">In the left navigation bar, click **Voice Features**, and then click **Unassigned Number**.</span></span>
    
4. <span data-ttu-id="041d7-126">在 [ **未指派的號碼** ] 頁面上，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="041d7-126">On the **Unassigned Number** page, do one of the following:</span></span>
    
   - <span data-ttu-id="041d7-127">若要建立新的號碼範圍，請按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="041d7-127">To create a new number range, click **New**.</span></span> <span data-ttu-id="041d7-128">在 **[名稱]** 中，輸入此號碼範圍的識別名稱。</span><span class="sxs-lookup"><span data-stu-id="041d7-128">In **Name**, type an identifying name for this range of numbers.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="041d7-129">在您認可新的未指派號碼範圍至資料庫之後，就無法變更此名稱。</span><span class="sxs-lookup"><span data-stu-id="041d7-129">After you commit the new unassigned number range to the database, you cannot change this name.</span></span> 
  
   - <span data-ttu-id="041d7-130">若要修改現有的號碼範圍，請在 [搜尋] 欄位中輸入編號範圍的全部或部分名稱。</span><span class="sxs-lookup"><span data-stu-id="041d7-130">To modify an existing number range, type all or part of the name of the number range in the search field.</span></span> <span data-ttu-id="041d7-131">在產生的號碼範圍清單中，按一下您想要的名稱，然後按一下 [ **編輯**]，再按一下 [ **顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="041d7-131">In the resulting list of number ranges, click the name you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="041d7-132">在第一個 **[號碼範圍]** 欄位中輸入範圍的開始號碼，在第二個 **[號碼範圍]** 欄位中輸入範圍的結束號碼。</span><span class="sxs-lookup"><span data-stu-id="041d7-132">In the first **Number range** field, type the beginning number of the range, and in the second **Number range** field, type the ending number of the range.</span></span>
    
   - <span data-ttu-id="041d7-133">該範圍的起始號碼必須小於或等於範圍的結束號碼。</span><span class="sxs-lookup"><span data-stu-id="041d7-133">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>
    
   - <span data-ttu-id="041d7-134">如果範圍的開始號碼或範圍的結束號碼包含分機號碼，則範圍的開始號碼和結束號碼都必須包含分機，且開始號碼和結束號碼的分機號碼必須相同。</span><span class="sxs-lookup"><span data-stu-id="041d7-134">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span>
    
   - <span data-ttu-id="041d7-135">此數位必須符合正則運算式 `(tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?` 。</span><span class="sxs-lookup"><span data-stu-id="041d7-135">The number must match the regular expression `(tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?`.</span></span> <span data-ttu-id="041d7-136">這表示數位可以以字串開頭 `tel:` (如果您未指定該字串，將會自動為您新增) 、加號 (+) 及數位1到9。</span><span class="sxs-lookup"><span data-stu-id="041d7-136">This means the number may begin with the string `tel:` (if you don't specify that string, it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="041d7-137">電話號碼最多可達 17 位，且後面可以再加分機，格式為 ;ext= 分機號碼。</span><span class="sxs-lookup"><span data-stu-id="041d7-137">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span>
    
6. <span data-ttu-id="041d7-138">在 **[宣告服務]** 中，執行下列其中一個動作：</span><span class="sxs-lookup"><span data-stu-id="041d7-138">In **Announcement service**, do one of the following:</span></span> 
    
   - <span data-ttu-id="041d7-139">按一下 **[宣告]**。</span><span class="sxs-lookup"><span data-stu-id="041d7-139">Click **Announcement**.</span></span>
    
   - <span data-ttu-id="041d7-140">按一下 **[Exchange UM]**。</span><span class="sxs-lookup"><span data-stu-id="041d7-140">Click **Exchange UM**.</span></span>
    
7. <span data-ttu-id="041d7-141">如果您在上一個步驟按了 **[宣告]**，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="041d7-141">If, in the previous step, you clicked **Announcement**, do the following:</span></span>
    
    <span data-ttu-id="041d7-142">a.</span><span class="sxs-lookup"><span data-stu-id="041d7-142">a.</span></span> <span data-ttu-id="041d7-143">在 **[目的地伺服器的 FQDN]** 下方按一下 **[選取]**，按一下執行宣告應用程式之應用程式服務的服務 ID (此服務會處理此未指派號碼範圍的來電)，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="041d7-143">Under **FQDN of destination server**, click **Select**, click the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers, and then click **OK**.</span></span>
    
    <span data-ttu-id="041d7-144">b.</span><span class="sxs-lookup"><span data-stu-id="041d7-144">b.</span></span> <span data-ttu-id="041d7-145">在 **[宣告]** 中，按一下要針對此未指派號碼範圍播放的宣告。</span><span class="sxs-lookup"><span data-stu-id="041d7-145">In **Announcement**, click the announcement to be played for this range of unassigned numbers.</span></span>
    
8. <span data-ttu-id="041d7-146">如果您在上一個步驟按了 **[Exchange UM]**，請在 **[自動語音應答電話號碼]** 下方按一下 **[選取]**，按一下要用於此未指派號碼範圍的電話號碼，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="041d7-146">If, in the previous step, you clicked **Exchange UM**, under **Auto Attendant phone number**, click **Select**, click the phone number to be used for this range of unassigned numbers, and then click **OK**.</span></span>
    
9. <span data-ttu-id="041d7-147">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="041d7-147">Click **OK**.</span></span>
    
10. <span data-ttu-id="041d7-148">在 [ **未指派的號碼** ] 頁面上，確定未指派的號碼範圍以您想要的順序排列。</span><span class="sxs-lookup"><span data-stu-id="041d7-148">On the **Unassigned Number** page, be sure that the unassigned number ranges are arranged in the order that you want.</span></span> <span data-ttu-id="041d7-149">若要變更某個範圍在表格中的位置，請在範圍清單中按一下一個或多個連續的名稱，然後按一下向上鍵或向下箭號。</span><span class="sxs-lookup"><span data-stu-id="041d7-149">To change a range's position in the table, click one or more consecutive names in the list of ranges, and then click the up arrow or the down arrow.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="041d7-150">商務用 Skype Server 會從上到下搜尋未指派號碼表格，並使用符合未指派號碼的第一個範圍。</span><span class="sxs-lookup"><span data-stu-id="041d7-150">Skype for Business Server searches the unassigned number table from top to bottom and uses the first range that matches the unassigned number.</span></span> <span data-ttu-id="041d7-151">如果您有重疊的範圍，且有一個範圍指定最後採取的動作，請確定該範圍位於清單底部。</span><span class="sxs-lookup"><span data-stu-id="041d7-151">If you have overlapping ranges and one range specifies a last resort action, make sure that range is at the bottom of the list.</span></span> 
  
11. <span data-ttu-id="041d7-152">當您以您想要的順序排列未指派的號碼範圍時，請按一下 [ **全部認可**]。</span><span class="sxs-lookup"><span data-stu-id="041d7-152">When you have the unassigned number ranges in the order that you want, click **Commit all**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="041d7-153">使用商務用 Skype Server 管理命令介面設定未指派的電話號碼</span><span class="sxs-lookup"><span data-stu-id="041d7-153">To use Skype for Business Server Management Shell to configure unassigned phone numbers</span></span>

1. <span data-ttu-id="041d7-154">登入安裝商務用 Skype Server 管理命令介面的電腦，並將其安裝為 RTCUniversalServerAdmins 群組的成員，或使用 **委派安裝許可權** 中所述的必要使用者權限。</span><span class="sxs-lookup"><span data-stu-id="041d7-154">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="041d7-155">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="041d7-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="041d7-156">使用 **New-CsUnassignedNumber** 建立新的未指派號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="041d7-156">Use **New-CsUnassignedNumber** to create a new unassigned number range.</span></span> <span data-ttu-id="041d7-157">使用 **Set-CsUnassignedNumber** 修改現有的未指派號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="041d7-157">Use **Set-CsUnassignedNumber** to modify an existing unassigned number range.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="041d7-158">如果您有重疊的範圍，且想要依特定順序套用範圍，請包含 Priority 參數。</span><span class="sxs-lookup"><span data-stu-id="041d7-158">If you have overlapping ranges and want the ranges to be applied in a specific order, include the Priority parameter.</span></span> <span data-ttu-id="041d7-159">具有最高優先順序的範圍會套用至通話。</span><span class="sxs-lookup"><span data-stu-id="041d7-159">The range with the highest priority will be applied to the call.</span></span> <span data-ttu-id="041d7-160">值0代表最高優先順序。</span><span class="sxs-lookup"><span data-stu-id="041d7-160">The value 0 represents the highest priority.</span></span>
  
    <span data-ttu-id="041d7-161">在命令列中，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="041d7-161">At the command line, do one of the following:</span></span>
    
   - <span data-ttu-id="041d7-162">若要建立宣告服務的號碼範圍，請執行：</span><span class="sxs-lookup"><span data-stu-id="041d7-162">To create a number range for an Announcement service, run:</span></span>
    
     ```powershell
     New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
     ```

   - <span data-ttu-id="041d7-163">或者，若要建立 Exchange UM 自動語音應答的號碼範圍，請執行：</span><span class="sxs-lookup"><span data-stu-id="041d7-163">Or, to create a number range for Exchange UM Auto Attendant, run:</span></span>
    
     ```powershell
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
     ```

     <span data-ttu-id="041d7-164">例如：</span><span class="sxs-lookup"><span data-stu-id="041d7-164">For example:</span></span>
    
     ```powershell
     New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
     ```

     <span data-ttu-id="041d7-165">或</span><span class="sxs-lookup"><span data-stu-id="041d7-165">Or</span></span>
    
     ```powershell
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
     ```

     <span data-ttu-id="041d7-166">下列範例會顯示如何修改現有未指派號碼範圍中的號碼：</span><span class="sxs-lookup"><span data-stu-id="041d7-166">The following example shows how to modify the numbers in an existing unassigned number range:</span></span>
    
     ```powershell
     Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"
     ```

## <a name="delete-an-unnasigned-number-range"></a><span data-ttu-id="041d7-167">刪除 unnasigned 號碼範圍</span><span class="sxs-lookup"><span data-stu-id="041d7-167">Delete an unnasigned number range</span></span>

### <a name="to-use-skype-for-business-server-control-panel-to-delete-an-unassigned-number-range"></a><span data-ttu-id="041d7-168">使用商務用 Skype Server 控制台刪除未指派的號碼範圍</span><span class="sxs-lookup"><span data-stu-id="041d7-168">To use Skype for Business Server Control Panel to delete an unassigned number range</span></span>

1.  <span data-ttu-id="041d7-169">以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="041d7-169">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="041d7-170">如需詳細資訊，請參閱＜**Delegate Setup Permissions**＞。</span><span class="sxs-lookup"><span data-stu-id="041d7-170">For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="041d7-171">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="041d7-171">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="041d7-172">在左側導覽列中，依序按一下 **[語音功能]** 和 **[未指派的號碼]**。</span><span class="sxs-lookup"><span data-stu-id="041d7-172">In the left navigation bar, click **Voice Features** and then click **Unassigned Number**.</span></span>
    
4. <span data-ttu-id="041d7-173">在 [ **未指派的號碼** ] 頁面上的搜尋欄位中，輸入您要刪除之未指派號碼範圍的全部或部分名稱。</span><span class="sxs-lookup"><span data-stu-id="041d7-173">On the **Unassigned Number** page, in the search field, type all or part of the name of the unassigned number range you want to delete.</span></span>
    
5. <span data-ttu-id="041d7-174">在產生的編號範圍清單中，按一下名稱，按一下 [ **編輯**]，然後按一下 [ **刪除**]。</span><span class="sxs-lookup"><span data-stu-id="041d7-174">In the resulting list of number ranges, click the name, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="041d7-175">按一下 [ **全部認可**]。</span><span class="sxs-lookup"><span data-stu-id="041d7-175">Click **Commit all**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-delete-an-unassigned-number-range"></a><span data-ttu-id="041d7-176">若要使用商務用 Skype Server 管理命令介面來刪除未指派的號碼範圍</span><span class="sxs-lookup"><span data-stu-id="041d7-176">To use Skype for Business Server Management Shell to delete an unassigned number range</span></span>

1. <span data-ttu-id="041d7-177">登入安裝商務用 Skype Server 管理命令介面的電腦，並將其安裝為 RTCUniversalServerAdmins 群組的成員，或使用 **委派安裝許可權** 中所述的必要使用者權限。</span><span class="sxs-lookup"><span data-stu-id="041d7-177">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="041d7-178">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="041d7-178">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="041d7-179">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="041d7-179">At the command line, type:</span></span>
    
   ```powershell
   Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
   ```

    <span data-ttu-id="041d7-180">例如：</span><span class="sxs-lookup"><span data-stu-id="041d7-180">For example:</span></span>
    
   ```powershell
   Remove-CsUnassignedNumber -Identity "Unassigned range 1"
   ```

    > [!NOTE]
    > <span data-ttu-id="041d7-181">如需更多選項的詳細資訊，請參閱 [Remove-CsCallParkOrbit](/powershell/module/skype/remove-cscallparkorbit?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="041d7-181">For details about more options, see [Remove-CsCallParkOrbit](/powershell/module/skype/remove-cscallparkorbit?view=skype-ps).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="041d7-182">另請參閱</span><span class="sxs-lookup"><span data-stu-id="041d7-182">See also</span></span>

[<span data-ttu-id="041d7-183">New-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="041d7-183">New-CsUnassignedNumber</span></span>](/powershell/module/skype/new-csunassignednumber?view=skype-ps)
  
[<span data-ttu-id="041d7-184">Set-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="041d7-184">Set-CsUnassignedNumber</span></span>](/powershell/module/skype/set-csunassignednumber?view=skype-ps)
  
[<span data-ttu-id="041d7-185">CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="041d7-185">Get-CsUnassignedNumber</span></span>](/powershell/module/skype/get-csunassignednumber?view=skype-ps)