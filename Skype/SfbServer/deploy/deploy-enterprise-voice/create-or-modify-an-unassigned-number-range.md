---
title: 在商務用 Skype Server 中建立或修改未指定的數位範圍
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a102b226-0460-4d5c-82f9-79b8444fa958
description: 在商務用 Skype Server Enterprise Voice 中, 建立、修改或刪除未指定的號碼範圍給宣告應用程式。 這會影響如何處理未指派數位的呼叫。
ms.openlocfilehash: f3d646e2d838312ee90453c66d1e7bf239cf1537
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233522"
---
# <a name="create-or-modify-an-unassigned-number-range-in-skype-for-business-server"></a><span data-ttu-id="ebf24-104">在商務用 Skype Server 中建立或修改未指定的數位範圍</span><span class="sxs-lookup"><span data-stu-id="ebf24-104">Create or modify an unassigned number range in Skype for Business Server</span></span>
 
<span data-ttu-id="ebf24-105">在商務用 Skype Server Enterprise Voice 中, 建立、修改或刪除未指定的號碼範圍給宣告應用程式。</span><span class="sxs-lookup"><span data-stu-id="ebf24-105">Create, modify or delete unassigned number ranges for Announcement application in Skype for Business Server Enterprise Voice.</span></span> <span data-ttu-id="ebf24-106">這會影響如何處理未指派數位的呼叫。</span><span class="sxs-lookup"><span data-stu-id="ebf24-106">This affects how calls to unassigned numbers are handled.</span></span>
  
<span data-ttu-id="ebf24-107">商務用 Skype Server 可讓您說撥入電話號碼對您的組織有效, 但不會指派給使用者或電話。</span><span class="sxs-lookup"><span data-stu-id="ebf24-107">Skype for Business Server enables you to say what happens to incoming calls to phone numbers that are valid for your organization, but are not assigned to a user or a phone.</span></span> <span data-ttu-id="ebf24-108">若要處理此類通話, 您必須設定未指派的 [數位] 資料表。</span><span class="sxs-lookup"><span data-stu-id="ebf24-108">To handle such calls, you set up an unassigned number table.</span></span> <span data-ttu-id="ebf24-109">您可以使用表格, 將呼叫路由至宣告應用程式或 Exchange UM 伺服器。</span><span class="sxs-lookup"><span data-stu-id="ebf24-109">You can use the table to route the calls to an Announcement application or to an Exchange UM server.</span></span>
  
<span data-ttu-id="ebf24-110">設定未指派號碼表的方式取決於其使用方式。</span><span class="sxs-lookup"><span data-stu-id="ebf24-110">How you configure the unassigned number table depends on how you want to use it.</span></span> <span data-ttu-id="ebf24-111">您可以設定包含組織所有有效分機號碼、只包含未指派的分機號碼，或包含結合這兩種類型之號碼的表格。</span><span class="sxs-lookup"><span data-stu-id="ebf24-111">You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers.</span></span> <span data-ttu-id="ebf24-112">未指派號碼表可以同時包含已指派和未指派的號碼，但是只有在來電者撥打目前未指派的號碼時才會叫用。</span><span class="sxs-lookup"><span data-stu-id="ebf24-112">The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned.</span></span> <span data-ttu-id="ebf24-113">如果您在未指派號碼表中納入所有有效的分機號碼，可以指定每次某人離開組織時要執行的動作，而不必重新設定表格。</span><span class="sxs-lookup"><span data-stu-id="ebf24-113">If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table.</span></span> <span data-ttu-id="ebf24-114">如果您在表格中包含未指定的延伸, 您可以修改針對特定數位所發生的動作。</span><span class="sxs-lookup"><span data-stu-id="ebf24-114">If you include unassigned extensions in the table, you can modify the action that occurs for specific numbers.</span></span> <span data-ttu-id="ebf24-115">例如, 如果您變更客戶服務台的延伸, 您可以在表格中包含舊的客戶服務編號, 然後將它指派給提供新號碼的宣告。</span><span class="sxs-lookup"><span data-stu-id="ebf24-115">For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and then assign it to an announcement that provides the new number.</span></span>
  
## <a name="configure-unassigned-phone-numbers"></a><span data-ttu-id="ebf24-116">設定未指派的電話號碼</span><span class="sxs-lookup"><span data-stu-id="ebf24-116">Configure unassigned phone numbers</span></span>

<span data-ttu-id="ebf24-117">使用下列其中一個程式來設定宣告應用程式的未指派數量範圍。</span><span class="sxs-lookup"><span data-stu-id="ebf24-117">Use one of the following procedures to configure unassigned number ranges for the Announcement application.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ebf24-118">在您設定 [未指派的號碼] 資料表之前, 您的系統必須已定義宣告, 或已設定 Exchange 整合通訊 (UM) 自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="ebf24-118">Before you configure the unassigned number table, your system must already either have Announcements defined or an Exchange Unified Messaging (UM) Auto Attendant set up.</span></span> 
  
> [!TIP]
> <span data-ttu-id="ebf24-119">當某人呼叫未指派的號碼時, 商務用 Skype Server 會從上到下搜尋 [未指定的數位] 資料表, 並使用第一個相符的範圍。</span><span class="sxs-lookup"><span data-stu-id="ebf24-119">When someone calls an unassigned number, Skype for Business Server searches the unassigned number table from top to bottom and uses the first matching range.</span></span> <span data-ttu-id="ebf24-120">因此, 您想要執行的動作必須針對表格中的最後一個範圍指定, 才能做為最後一個手段。</span><span class="sxs-lookup"><span data-stu-id="ebf24-120">Therefore, an action that you want to be performed as a last resort should be specified for the last range in the table.</span></span> 
  
### <a name="to-use-skype-for-business-server-control-panel-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="ebf24-121">使用商務用 Skype Server 的 [控制台] 來設定未指派的電話號碼</span><span class="sxs-lookup"><span data-stu-id="ebf24-121">To use Skype for Business Server Control Panel to configure unassigned phone numbers</span></span>

1. <span data-ttu-id="ebf24-122">以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="ebf24-122">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="ebf24-123">如需詳細資訊, 請參閱**委派設定許可權**。</span><span class="sxs-lookup"><span data-stu-id="ebf24-123">For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="ebf24-124">開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="ebf24-124">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="ebf24-125">在左側導覽列中, 按一下 [**語音功能**], 然後按一下 [**未指定的號碼**]。</span><span class="sxs-lookup"><span data-stu-id="ebf24-125">In the left navigation bar, click **Voice Features**, and then click **Unassigned Number**.</span></span>
    
4. <span data-ttu-id="ebf24-126">在 [**未指定的號碼**] 頁面上, 執行下列其中一項操作:</span><span class="sxs-lookup"><span data-stu-id="ebf24-126">On the **Unassigned Number** page, do one of the following:</span></span>
    
   - <span data-ttu-id="ebf24-127">若要建立新的編號範圍, 請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="ebf24-127">To create a new number range, click **New**.</span></span> <span data-ttu-id="ebf24-128">在 [**名稱**] 中, 輸入此數位範圍的識別名稱。</span><span class="sxs-lookup"><span data-stu-id="ebf24-128">In **Name**, type an identifying name for this range of numbers.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="ebf24-129">在您將新的未指派的數位範圍提交至資料庫之後, 您就無法變更此名稱。</span><span class="sxs-lookup"><span data-stu-id="ebf24-129">After you commit the new unassigned number range to the database, you cannot change this name.</span></span> 
  
   - <span data-ttu-id="ebf24-130">若要修改現有的數位範圍, 請在 [搜尋] 欄位中輸入全部或部分的數位範圍名稱。</span><span class="sxs-lookup"><span data-stu-id="ebf24-130">To modify an existing number range, type all or part of the name of the number range in the search field.</span></span> <span data-ttu-id="ebf24-131">在產生的數位範圍清單中, 按一下您想要的名稱, 按一下 [**編輯**], 然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="ebf24-131">In the resulting list of number ranges, click the name you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="ebf24-132">在第一個 [**數位範圍**] 欄位中, 輸入範圍的起始編號, 然後在 [第二個**數位範圍**] 欄位中, 輸入範圍的結束數位。</span><span class="sxs-lookup"><span data-stu-id="ebf24-132">In the first **Number range** field, type the beginning number of the range, and in the second **Number range** field, type the ending number of the range.</span></span>
    
   - <span data-ttu-id="ebf24-133">該範圍的起始號碼必須小於或等於範圍的結束號碼。</span><span class="sxs-lookup"><span data-stu-id="ebf24-133">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>
    
   - <span data-ttu-id="ebf24-134">如果範圍的起始編號或範圍的結束數位包含分機號碼, 則起始編號與範圍的結束數位都必須包含延伸, 且起始編號和所需的延伸號碼必須是相同的。結束數位。</span><span class="sxs-lookup"><span data-stu-id="ebf24-134">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span>
    
   - <span data-ttu-id="ebf24-135">這個數位必須符合正則運算式 (電話:) 嗎？ (\+)?[1-9] \d{0,17}(; ext = [1-9] \d{0,9})？。</span><span class="sxs-lookup"><span data-stu-id="ebf24-135">The number must match the regular expression (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?.</span></span> <span data-ttu-id="ebf24-136">這表示數位可能會從電話號碼開始: (如果您沒有指定該字串, 會自動為您新增)、加號 (+), 以及1到9的數位。</span><span class="sxs-lookup"><span data-stu-id="ebf24-136">This means the number may begin with the string tel: (if you don't specify that string, it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="ebf24-137">電話號碼最多可達 17 位，且後面可以再加分機，格式為 ;ext= 分機號碼。</span><span class="sxs-lookup"><span data-stu-id="ebf24-137">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span>
    
6. <span data-ttu-id="ebf24-138">在 [**宣告服務**] 中, 執行下列其中一項操作:</span><span class="sxs-lookup"><span data-stu-id="ebf24-138">In **Announcement service**, do one of the following:</span></span> 
    
   - <span data-ttu-id="ebf24-139">按一下 [**宣告**]。</span><span class="sxs-lookup"><span data-stu-id="ebf24-139">Click **Announcement**.</span></span>
    
   - <span data-ttu-id="ebf24-140">按一下 [ **EXCHANGE UM**]。</span><span class="sxs-lookup"><span data-stu-id="ebf24-140">Click **Exchange UM**.</span></span>
    
7. <span data-ttu-id="ebf24-141">如果您在上一個步驟中按一下 [**宣告**], 請執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="ebf24-141">If, in the previous step, you clicked **Announcement**, do the following:</span></span>
    
    <span data-ttu-id="ebf24-142">是.</span><span class="sxs-lookup"><span data-stu-id="ebf24-142">a.</span></span> <span data-ttu-id="ebf24-143">在 [**目的地伺服器的 FQDN**] 底下, 按一下 [**選取**], 然後按一下執行宣告應用程式的應用程式服務識別碼, 該應用程式服務會處理撥入呼叫到此未指定號碼的範圍, 然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="ebf24-143">Under **FQDN of destination server**, click **Select**, click the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers, and then click **OK**.</span></span>
    
    <span data-ttu-id="ebf24-144">乙.</span><span class="sxs-lookup"><span data-stu-id="ebf24-144">b.</span></span> <span data-ttu-id="ebf24-145">在 [**宣告**] 中, 按一下要在此未指定編號範圍中播放的宣告。</span><span class="sxs-lookup"><span data-stu-id="ebf24-145">In **Announcement**, click the announcement to be played for this range of unassigned numbers.</span></span>
    
8. <span data-ttu-id="ebf24-146">如果您在上一個步驟中按一下 [ **EXCHANGE UM**], 請在 [**自動語音應答電話號碼**] 底下, 按一下 [**選取**], 然後按一下要用於此未指定號碼範圍的電話號碼, 然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="ebf24-146">If, in the previous step, you clicked **Exchange UM**, under **Auto Attendant phone number**, click **Select**, click the phone number to be used for this range of unassigned numbers, and then click **OK**.</span></span>
    
9. <span data-ttu-id="ebf24-147">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ebf24-147">Click **OK**.</span></span>
    
10. <span data-ttu-id="ebf24-148">在 [**未指定的號碼**] 頁面上, 確定未指定的數位範圍是依您想要的順序排列。</span><span class="sxs-lookup"><span data-stu-id="ebf24-148">On the **Unassigned Number** page, be sure that the unassigned number ranges are arranged in the order that you want.</span></span> <span data-ttu-id="ebf24-149">若要變更範圍在表格中的位置, 請在範圍清單中按一下一或多個連續的名稱, 然後按一下向上箭號或向下箭號。</span><span class="sxs-lookup"><span data-stu-id="ebf24-149">To change a range's position in the table, click one or more consecutive names in the list of ranges, and then click the up arrow or the down arrow.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="ebf24-150">商務用 Skype Server 會從上到下搜尋 [未指定的數位] 資料表, 並使用符合未指定數位的第一個範圍。</span><span class="sxs-lookup"><span data-stu-id="ebf24-150">Skype for Business Server searches the unassigned number table from top to bottom and uses the first range that matches the unassigned number.</span></span> <span data-ttu-id="ebf24-151">如果您有重迭的範圍, 且一個範圍指定了 [最後一個滑雪場] 動作, 請確定該範圍位於清單底部。</span><span class="sxs-lookup"><span data-stu-id="ebf24-151">If you have overlapping ranges and one range specifies a last resort action, make sure that range is at the bottom of the list.</span></span> 
  
11. <span data-ttu-id="ebf24-152">當您以您想要的順序排列 [未指定的數位範圍] 時, 請按一下 [**全部確認**]。</span><span class="sxs-lookup"><span data-stu-id="ebf24-152">When you have the unassigned number ranges in the order that you want, click **Commit all**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="ebf24-153">使用商務用 Skype Server Management Shell 來設定未指派的電話號碼</span><span class="sxs-lookup"><span data-stu-id="ebf24-153">To use Skype for Business Server Management Shell to configure unassigned phone numbers</span></span>

1. <span data-ttu-id="ebf24-154">登入商務用 Skype Server Management Shell 的電腦是以 RTCUniversalServerAdmins 群組的成員或必要的使用者權利來安裝, 如**委派設定許可權**中所述。</span><span class="sxs-lookup"><span data-stu-id="ebf24-154">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="ebf24-155">啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="ebf24-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="ebf24-156">使用 [**新-CsUnassignedNumber** ] 來建立新的 [未指定的數位範圍]。</span><span class="sxs-lookup"><span data-stu-id="ebf24-156">Use **New-CsUnassignedNumber** to create a new unassigned number range.</span></span> <span data-ttu-id="ebf24-157">使用 [**設定] CsUnassignedNumber**來修改現有的未指派數位範圍。</span><span class="sxs-lookup"><span data-stu-id="ebf24-157">Use **Set-CsUnassignedNumber** to modify an existing unassigned number range.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="ebf24-158">如果您有重迭的範圍, 且想要以特定順序套用範圍, 請包含 Priority 參數。</span><span class="sxs-lookup"><span data-stu-id="ebf24-158">If you have overlapping ranges and want the ranges to be applied in a specific order, include the Priority parameter.</span></span> <span data-ttu-id="ebf24-159">具有最高優先順序的範圍會套用至通話。</span><span class="sxs-lookup"><span data-stu-id="ebf24-159">The range with the highest priority will be applied to the call.</span></span> <span data-ttu-id="ebf24-160">值0代表最高優先順序。</span><span class="sxs-lookup"><span data-stu-id="ebf24-160">The value 0 represents the highest priority.</span></span>
  
    <span data-ttu-id="ebf24-161">在命令列上, 執行下列其中一項操作:</span><span class="sxs-lookup"><span data-stu-id="ebf24-161">At the command line, do one of the following:</span></span>
    
   - <span data-ttu-id="ebf24-162">若要為宣告服務建立數位範圍, 請執行:</span><span class="sxs-lookup"><span data-stu-id="ebf24-162">To create a number range for an Announcement service, run:</span></span>
    
     ```
     New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
     ```

   - <span data-ttu-id="ebf24-163">或者, 若要建立 Exchange UM 自動語音應答的數位範圍, 請執行:</span><span class="sxs-lookup"><span data-stu-id="ebf24-163">Or, to create a number range for Exchange UM Auto Attendant, run:</span></span>
    
     ```
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
     ```

     <span data-ttu-id="ebf24-164">例如：</span><span class="sxs-lookup"><span data-stu-id="ebf24-164">For example:</span></span>
    
     ```
     New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
     ```

     <span data-ttu-id="ebf24-165">或</span><span class="sxs-lookup"><span data-stu-id="ebf24-165">Or</span></span>
    
     ```
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
     ```

     <span data-ttu-id="ebf24-166">下列範例顯示如何修改現有未指定的數位範圍中的數位:</span><span class="sxs-lookup"><span data-stu-id="ebf24-166">The following example shows how to modify the numbers in an existing unassigned number range:</span></span>
    
     ```
     Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"
     ```

## <a name="delete-an-unnasigned-number-range"></a><span data-ttu-id="ebf24-167">刪除 unnasigned 的數位範圍</span><span class="sxs-lookup"><span data-stu-id="ebf24-167">Delete an unnasigned number range</span></span>

### <a name="to-use-skype-for-business-server-control-panel-to-delete-an-unassigned-number-range"></a><span data-ttu-id="ebf24-168">使用商務用 Skype Server 的 [控制台] 刪除未指定的數位範圍</span><span class="sxs-lookup"><span data-stu-id="ebf24-168">To use Skype for Business Server Control Panel to delete an unassigned number range</span></span>

1.  <span data-ttu-id="ebf24-169">以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="ebf24-169">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="ebf24-170">如需詳細資訊, 請參閱**委派設定許可權**。</span><span class="sxs-lookup"><span data-stu-id="ebf24-170">For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="ebf24-171">開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="ebf24-171">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="ebf24-172">在左側導覽列中, 按一下 [**語音功能**], 然後按一下 [**未指定的號碼**]。</span><span class="sxs-lookup"><span data-stu-id="ebf24-172">In the left navigation bar, click **Voice Features** and then click **Unassigned Number**.</span></span>
    
4. <span data-ttu-id="ebf24-173">在 [**未指定的號碼**] 頁面上, 于 [搜尋] 欄位中, 輸入您要刪除的未指派數位範圍的全部或部分名稱。</span><span class="sxs-lookup"><span data-stu-id="ebf24-173">On the **Unassigned Number** page, in the search field, type all or part of the name of the unassigned number range you want to delete.</span></span>
    
5. <span data-ttu-id="ebf24-174">在產生的數位範圍清單中, 按一下名稱, 按一下 [**編輯**], 然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="ebf24-174">In the resulting list of number ranges, click the name, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="ebf24-175">按一下 [**全部確認**]。</span><span class="sxs-lookup"><span data-stu-id="ebf24-175">Click **Commit all**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-delete-an-unassigned-number-range"></a><span data-ttu-id="ebf24-176">若要使用商務用 Skype Server Management Shell 來刪除未指定的數位範圍</span><span class="sxs-lookup"><span data-stu-id="ebf24-176">To use Skype for Business Server Management Shell to delete an unassigned number range</span></span>

1. <span data-ttu-id="ebf24-177">登入商務用 Skype Server Management Shell 的電腦是以 RTCUniversalServerAdmins 群組的成員或必要的使用者權利來安裝, 如**委派設定許可權**中所述。</span><span class="sxs-lookup"><span data-stu-id="ebf24-177">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="ebf24-178">啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="ebf24-178">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="ebf24-179">在命令列中, 輸入:</span><span class="sxs-lookup"><span data-stu-id="ebf24-179">At the command line, type:</span></span>
    
   ```
   Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
   ```

    <span data-ttu-id="ebf24-180">例如：</span><span class="sxs-lookup"><span data-stu-id="ebf24-180">For example:</span></span>
    
   ```
   Remove-CsUnassignedNumber -Identity "Unassigned range 1"
   ```

    > [!NOTE]
    > <span data-ttu-id="ebf24-181">如需更多選項的詳細資訊, 請參閱[移除-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/remove-cscallparkorbit?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="ebf24-181">For details about more options, see [Remove-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/remove-cscallparkorbit?view=skype-ps).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ebf24-182">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ebf24-182">See also</span></span>

[<span data-ttu-id="ebf24-183">New-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="ebf24-183">New-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csunassignednumber?view=skype-ps)
  
[<span data-ttu-id="ebf24-184">Set-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="ebf24-184">Set-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csunassignednumber?view=skype-ps)
  
[<span data-ttu-id="ebf24-185">CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="ebf24-185">Get-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csunassignednumber?view=skype-ps)
