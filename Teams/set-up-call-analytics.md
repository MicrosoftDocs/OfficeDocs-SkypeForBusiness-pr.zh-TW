---
title: 設定通話分析
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: fbf7247a-84ae-46cc-9204-2c45b1c734cd
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: 設定並使用呼叫分析來識別和疑難排解商務用 Skype 和 Microsoft 團隊通話品質問題。
ms.openlocfilehash: 51f28b402fea69f0e5033954018a5f67bf6c90d6
ms.sourcegitcommit: b92b673e718e34b6ebda6de57ad69eb6651faa98
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/24/2019
ms.locfileid: "36183588"
---
# <a name="set-up-call-analytics"></a><span data-ttu-id="e9c45-103">設定通話分析</span><span class="sxs-lookup"><span data-stu-id="e9c45-103">Set up Call Analytics</span></span>

<span data-ttu-id="e9c45-104">在團隊或商務用 Skype Online 系統管理員中, 您可以使用呼叫分析來疑難排解商務用 Skype 和 Microsoft 團隊通話品質與連線問題。</span><span class="sxs-lookup"><span data-stu-id="e9c45-104">As a Teams or Skype for Business Online admin, you can use Call Analytics to troubleshoot Skype for Business and Microsoft Teams call quality and connection problems.</span></span> <span data-ttu-id="e9c45-105">您可能會發現在 [呼叫分析] 中設定下列功能很有用:</span><span class="sxs-lookup"><span data-stu-id="e9c45-105">You may find it useful to set up the following capabilities in Call Analytics:</span></span>
  
- <span data-ttu-id="e9c45-106">設定許可權讓其他人員 (例如支援者的工程師) 使用呼叫分析, 但不能存取 Microsoft 團隊系統管理中心的其餘部分。</span><span class="sxs-lookup"><span data-stu-id="e9c45-106">Set permissions that let other personnel, such as helpdesk agents, use Call Analytics, but prevent them from accessing the rest of the Microsoft Teams admin center.</span></span> 
    
- <span data-ttu-id="e9c45-107">透過上傳 tsv 或 .csv 資料檔案, 將建築物、網站和租使用者資訊新增至呼叫分析。</span><span class="sxs-lookup"><span data-stu-id="e9c45-107">Add building, site, and tenant information to Call Analytics by uploading a .tsv or .csv data file.</span></span>
    
<span data-ttu-id="e9c45-108">**[通話分析] 現已提供給 Microsoft [團隊管理中心**]。</span><span class="sxs-lookup"><span data-stu-id="e9c45-108">**Call Analytics is now available in the Microsoft Teams admin center**.</span></span> <span data-ttu-id="e9c45-109">若要查看使用者的所有通話資訊和資料, 請使用 [**通話記錄**] 索引標籤。您可以透過執行下列其中一項動作來查看使用者的設定檔頁面面:</span><span class="sxs-lookup"><span data-stu-id="e9c45-109">To see all the call information and data for a user, use the **Call History** tab. You can do this by looking on the user's profile page by doing one of the following:</span></span>

- <span data-ttu-id="e9c45-110">從儀表板搜尋使用者。</span><span class="sxs-lookup"><span data-stu-id="e9c45-110">Search for the user from the dashboard.</span></span>
  
   ![儀表板上使用者搜尋的螢幕擷取畫面](media/set-up-call-analytics-image-1.png)

-  <span data-ttu-id="e9c45-112">選取左側導覽中的 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="e9c45-112">Select **Users** in the left navigation.</span></span>

   ![左側導覽的螢幕擷取畫面](media/set-up-call-analytics-image-2.png)
  
## <a name="set-call-analytics-permissions"></a><span data-ttu-id="e9c45-114">設定呼叫分析許可權</span><span class="sxs-lookup"><span data-stu-id="e9c45-114">Set Call Analytics permissions</span></span>
<a name="BKMK_SetCAPerms"></a>

<span data-ttu-id="e9c45-115">就像管理員一樣, 您擁有呼叫分析的所有功能的完整存取權。</span><span class="sxs-lookup"><span data-stu-id="e9c45-115">As the admin, you have full access to all the features of Call Analytics.</span></span> <span data-ttu-id="e9c45-116">此外, 您也可以將 Azure Active Directory 角色指派給支援人員。</span><span class="sxs-lookup"><span data-stu-id="e9c45-116">In addition, you can assign Azure Active Directory roles to support staff.</span></span> <span data-ttu-id="e9c45-117">將團隊通訊支援專家角色指派給應該擁有有限的通話分析視圖的使用者。</span><span class="sxs-lookup"><span data-stu-id="e9c45-117">Assign the Teams communications support specialist role to users who should have a limited view of Call Analytics.</span></span> <span data-ttu-id="e9c45-118">指派團隊通訊支援工程師角色給需要存取呼叫分析完整功能的使用者。</span><span class="sxs-lookup"><span data-stu-id="e9c45-118">Assign the Teams communications support engineer role to users who need access to the full functionality of Call Analytics.</span></span> <span data-ttu-id="e9c45-119">兩個許可權等級都無法存取 Microsoft 團隊系統管理中心的其他部分。</span><span class="sxs-lookup"><span data-stu-id="e9c45-119">Both permission levels prevent access to the rest of the Microsoft Teams admin center.</span></span>

> [!NOTE]
> <span data-ttu-id="e9c45-120">通訊支援專家角色相當於第1層支援, 且溝通支援工程師角色相當於第2層支援。</span><span class="sxs-lookup"><span data-stu-id="e9c45-120">The communications support specialist role is equivalent to tier 1 support and the communications support engineer role is equivalent to tier 2 support.</span></span>

<span data-ttu-id="e9c45-121">如需有關團隊管理員角色的詳細資訊, 請參閱[使用 Microsoft 團隊管理員角色管理團隊](using-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="e9c45-121">For more information about Teams admin roles, see [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md).</span></span> 
  
<span data-ttu-id="e9c45-122">通訊支援專家處理基本的通話品質問題。</span><span class="sxs-lookup"><span data-stu-id="e9c45-122">Communications support specialists handle basic call-quality problems.</span></span> <span data-ttu-id="e9c45-123">他們不會調查會議的問題。</span><span class="sxs-lookup"><span data-stu-id="e9c45-123">They don't investigate issues with meetings.</span></span> <span data-ttu-id="e9c45-124">相反地, 他們會收集相關資訊, 然後升級至通訊支援工程師。</span><span class="sxs-lookup"><span data-stu-id="e9c45-124">Instead, they collect related information and then escalate to a communications support engineer.</span></span> <span data-ttu-id="e9c45-125">通訊支援工程師請參閱與通訊支援專家隱藏的詳細通話記錄中的資訊。</span><span class="sxs-lookup"><span data-stu-id="e9c45-125">Communications support engineers see information in detailed call logs that's hidden from communications support specialists.</span></span> <span data-ttu-id="e9c45-126">下表提供通訊支援專家與通訊支援工程師在使用呼叫分析時所提供資訊的概覽。</span><span class="sxs-lookup"><span data-stu-id="e9c45-126">The following table gives an overview of information available to communications support specialists and communications support engineers when they use Call Analytics.</span></span>

|<span data-ttu-id="e9c45-127">**操作**</span><span class="sxs-lookup"><span data-stu-id="e9c45-127">**Activity**</span></span>|<span data-ttu-id="e9c45-128">**通話分析中的資訊**</span><span class="sxs-lookup"><span data-stu-id="e9c45-128">**Information in Call Analytics**</span></span>|<span data-ttu-id="e9c45-129">**溝通支援專家所能看到的內容**</span><span class="sxs-lookup"><span data-stu-id="e9c45-129">**What the communications support specialist sees**</span></span>|<span data-ttu-id="e9c45-130">**溝通支援工程師所能看到的內容**</span><span class="sxs-lookup"><span data-stu-id="e9c45-130">**What the communications support engineer sees**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e9c45-131">**撥**</span><span class="sxs-lookup"><span data-stu-id="e9c45-131">**Calls**</span></span> <br/> |<span data-ttu-id="e9c45-132">來電者名稱</span><span class="sxs-lookup"><span data-stu-id="e9c45-132">Caller name</span></span>  <br/> |<span data-ttu-id="e9c45-133">僅限代理程式搜尋的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="e9c45-133">Only the name of the user for whom the agent searched.</span></span>  <br/> |<span data-ttu-id="e9c45-134">[使用者名稱]。</span><span class="sxs-lookup"><span data-stu-id="e9c45-134">User name.</span></span>  <br/> |
||<span data-ttu-id="e9c45-135">收件者名稱</span><span class="sxs-lookup"><span data-stu-id="e9c45-135">Recipient name</span></span>  <br/> |<span data-ttu-id="e9c45-136">顯示為內部使用者或外部使用者。</span><span class="sxs-lookup"><span data-stu-id="e9c45-136">Shows as Internal User or External User.</span></span>  <br/> |<span data-ttu-id="e9c45-137">收件者名稱。</span><span class="sxs-lookup"><span data-stu-id="e9c45-137">Recipient name.</span></span>  <br/> |
||<span data-ttu-id="e9c45-138">來電者電話號碼</span><span class="sxs-lookup"><span data-stu-id="e9c45-138">Caller phone number</span></span>  <br/> |<span data-ttu-id="e9c45-139">除後三位數以外的整個電話號碼都會以星號符號加以混淆。</span><span class="sxs-lookup"><span data-stu-id="e9c45-139">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="e9c45-140">例如, 15552823 \* \* \*。</span><span class="sxs-lookup"><span data-stu-id="e9c45-140">For example, 15552823\*\*\*.</span></span>  <br/> |<span data-ttu-id="e9c45-141">除後三位數以外的整個電話號碼都會以星號符號加以混淆。</span><span class="sxs-lookup"><span data-stu-id="e9c45-141">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="e9c45-142">例如, 15552823 \* \* \*。</span><span class="sxs-lookup"><span data-stu-id="e9c45-142">For example, 15552823\*\*\*.</span></span>  <br/> |
||<span data-ttu-id="e9c45-143">收件者電話號碼</span><span class="sxs-lookup"><span data-stu-id="e9c45-143">Recipient phone number</span></span>  <br/> |<span data-ttu-id="e9c45-144">除後三位數以外的整個電話號碼都會以星號符號加以混淆。</span><span class="sxs-lookup"><span data-stu-id="e9c45-144">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="e9c45-145">例如, 15552823 \* \* \*。</span><span class="sxs-lookup"><span data-stu-id="e9c45-145">For example, 15552823\*\*\*.</span></span>  <br/> |<span data-ttu-id="e9c45-146">除後三位數以外的整個電話號碼都會以星號符號加以混淆。</span><span class="sxs-lookup"><span data-stu-id="e9c45-146">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="e9c45-147">例如, 15552823 \* \* \*。</span><span class="sxs-lookup"><span data-stu-id="e9c45-147">For example, 15552823\*\*\*.</span></span>  <br/> |
||<span data-ttu-id="e9c45-148">**[通話詳細資料** >  \*\* \*\* ] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="e9c45-148">**Call Details** > **Advanced** tab</span></span> <br/> |<span data-ttu-id="e9c45-149">未顯示資訊。</span><span class="sxs-lookup"><span data-stu-id="e9c45-149">Information not shown.</span></span>  <br/> |<span data-ttu-id="e9c45-150">顯示所有的詳細資料, 例如裝置名稱、IP 位址、子網對應等。</span><span class="sxs-lookup"><span data-stu-id="e9c45-150">All details shown, such as device names, IP address, subnet mapping, and more.</span></span>  <br/> |
||<span data-ttu-id="e9c45-151">**通話詳細資料** > [**高級** > **調試**] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="e9c45-151">**Call Details** > **Advanced** > **Debug** tab</span></span> <br/> |<span data-ttu-id="e9c45-152">未顯示資訊。</span><span class="sxs-lookup"><span data-stu-id="e9c45-152">Information not shown.</span></span>  <br/> |<span data-ttu-id="e9c45-153">顯示所有的詳細資料, 例如 DNS 尾碼和 SSID。</span><span class="sxs-lookup"><span data-stu-id="e9c45-153">All details shown, such as DNS suffix and SSID.</span></span>  <br/> |
|<span data-ttu-id="e9c45-154">**舉行**</span><span class="sxs-lookup"><span data-stu-id="e9c45-154">**Meetings**</span></span> <br/> |<span data-ttu-id="e9c45-155">參與者名稱</span><span class="sxs-lookup"><span data-stu-id="e9c45-155">Participant names</span></span>  <br/> |<span data-ttu-id="e9c45-156">僅限代理程式搜尋的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="e9c45-156">Only the name of the user for whom the agent searched.</span></span> <span data-ttu-id="e9c45-157">已識別為內部使用者或外部使用者的其他參與者。</span><span class="sxs-lookup"><span data-stu-id="e9c45-157">Other participants identified as Internal User or External User.</span></span>  <br/> |<span data-ttu-id="e9c45-158">顯示所有名稱。</span><span class="sxs-lookup"><span data-stu-id="e9c45-158">All names shown.</span></span>  <br/> |
||<span data-ttu-id="e9c45-159">參與者計數</span><span class="sxs-lookup"><span data-stu-id="e9c45-159">Participant count</span></span>  <br/> |<span data-ttu-id="e9c45-160">參與者數目。</span><span class="sxs-lookup"><span data-stu-id="e9c45-160">Number of participants.</span></span>  <br/> |<span data-ttu-id="e9c45-161">參與者數目。</span><span class="sxs-lookup"><span data-stu-id="e9c45-161">Number of participants.</span></span>  <br/> |
||<span data-ttu-id="e9c45-162">會話詳細資料</span><span class="sxs-lookup"><span data-stu-id="e9c45-162">Session details</span></span>  <br/> |<span data-ttu-id="e9c45-163">顯示的會話詳細資料 (含例外狀況)。</span><span class="sxs-lookup"><span data-stu-id="e9c45-163">Session details shown with exceptions.</span></span> <span data-ttu-id="e9c45-164">只顯示代理程式搜尋的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="e9c45-164">Only the name of the user for whom the agent searched is shown.</span></span> <span data-ttu-id="e9c45-165">已識別為內部使用者或外部使用者的其他參與者。</span><span class="sxs-lookup"><span data-stu-id="e9c45-165">Other participants identified as Internal User or External User.</span></span> <span data-ttu-id="e9c45-166">以星號符號加以混淆之電話號碼的後三位數。</span><span class="sxs-lookup"><span data-stu-id="e9c45-166">Last three digits of telephone number obfuscated with asterisk symbols.</span></span>  <br/> |<span data-ttu-id="e9c45-167">顯示 [會話詳細資料]。</span><span class="sxs-lookup"><span data-stu-id="e9c45-167">Session details shown.</span></span> <span data-ttu-id="e9c45-168">顯示 [使用者名稱] 和 [會話詳細資料]。</span><span class="sxs-lookup"><span data-stu-id="e9c45-168">User names and session details shown.</span></span> <span data-ttu-id="e9c45-169">以星號符號加以混淆之電話號碼的後三位數。</span><span class="sxs-lookup"><span data-stu-id="e9c45-169">Last three digits of telephone number obfuscated with asterisk symbols.</span></span>  <br/> |
||||
   
 ### <a name="set-up-permissions-by-assigning-admin-roles"></a><span data-ttu-id="e9c45-170">指派管理員角色來設定許可權</span><span class="sxs-lookup"><span data-stu-id="e9c45-170">Set up permissions by assigning admin roles</span></span>
<span data-ttu-id="e9c45-171"><a name="BKMK_SetUpTier"> </a></span><span class="sxs-lookup"><span data-stu-id="e9c45-171"></span></span>

<span data-ttu-id="e9c45-172">若要瞭解如何在 Azure Active Directory 中指派系統管理角色, 請參閱[在 Azure Active directory 中查看和指派角色](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-manage-roles-portal)。</span><span class="sxs-lookup"><span data-stu-id="e9c45-172">To learn how to assign administrative roles in Azure Active Directory, see [View and assign roles in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a><span data-ttu-id="e9c45-173">上傳. tsv 或 .csv 檔案, 以新增建築物、網站和租使用者資訊</span><span class="sxs-lookup"><span data-stu-id="e9c45-173">Upload a .tsv or .csv file to add building, site, and tenant information</span></span>
<span data-ttu-id="e9c45-174"><a name="BKMK_UploadFiles"> </a></span><span class="sxs-lookup"><span data-stu-id="e9c45-174"></span></span>

<span data-ttu-id="e9c45-175">您可以透過上傳 .csv 或 tsv 檔案, 將建築物、網站和租使用者資訊新增至呼叫分析。</span><span class="sxs-lookup"><span data-stu-id="e9c45-175">You can add building, site, and tenant information to Call Analytics by uploading a .csv or .tsv file.</span></span> <span data-ttu-id="e9c45-176">在所有這些資訊的情況下, 呼叫分析可以將 IP 位址對應至物理位置。</span><span class="sxs-lookup"><span data-stu-id="e9c45-176">With all this information, Call Analytics can map IP addresses to physical locations.</span></span> <span data-ttu-id="e9c45-177">您或技術支援人員可能會發現此資訊有助於找出通話問題的趨勢。</span><span class="sxs-lookup"><span data-stu-id="e9c45-177">You or helpdesk agents might find this information useful to help spot trends in call problems.</span></span> <span data-ttu-id="e9c45-178">例如, 為什麼同一個建築物中的許多使用者都有類似的通話品質問題？</span><span class="sxs-lookup"><span data-stu-id="e9c45-178">For example, why are many users in the same building having similar call quality issues?</span></span> 

<span data-ttu-id="e9c45-179">如果您是團隊和商務用 Skype 系統管理員, 您可以使用 [團隊] & 商務用 Skype 通話品質儀表板中的現有資料檔案。</span><span class="sxs-lookup"><span data-stu-id="e9c45-179">If you're a Teams and Skype for Business admin, you can use an existing data file from the Teams & Skype for Business Call Quality Dashboard.</span></span> <span data-ttu-id="e9c45-180">首先, 您要從 [通話品質儀表板] 下載檔案, 然後將它上傳到 [呼叫分析]。</span><span class="sxs-lookup"><span data-stu-id="e9c45-180">First, you download the file from Call Quality Dashboard, and then you upload it to Call Analytics.</span></span> 

- <span data-ttu-id="e9c45-181">若要下載現有的資料檔, 請移至**Microsoft 團隊系統管理中心** > **的通話品質儀表板** > **[立即上傳**]。</span><span class="sxs-lookup"><span data-stu-id="e9c45-181">To download an existing data file, go to **Microsoft Teams admin center** > **Call Quality Dashboard** > **Upload now**.</span></span> <span data-ttu-id="e9c45-182">在 [**我**的上傳] 清單中, 按一下您想要的檔案旁的 [**下載**]。</span><span class="sxs-lookup"><span data-stu-id="e9c45-182">In the **My uploads** list, click **Download** next to the file you want.</span></span>

- <span data-ttu-id="e9c45-183">若要上傳新檔案, 請移至**Microsoft 團隊系統管理中心** > **位置**, 然後選取 **[上傳位置資料**] 或 [**取代位置資料**]。</span><span class="sxs-lookup"><span data-stu-id="e9c45-183">To upload the new file, go to **Microsoft Teams admin center** > **Locations**, and then select **Upload location data** or **Replace location data**.</span></span>
  
<span data-ttu-id="e9c45-184">如果您要從頭開始建立 tsv 或 .csv 檔案, 請參閱租使用者[資料檔案格式及建立資料檔案結構](turning-on-and-using-call-quality-dashboard.md#BKMKTenantDataFile)。</span><span class="sxs-lookup"><span data-stu-id="e9c45-184">If you're creating the .tsv or .csv file from scratch, see [Tenant data file format and Building data file structure](turning-on-and-using-call-quality-dashboard.md#BKMKTenantDataFile).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e9c45-185">相關主題</span><span class="sxs-lookup"><span data-stu-id="e9c45-185">Related topics</span></span>
<span data-ttu-id="e9c45-186"><a name="BKMK_UploadFiles"> </a></span><span class="sxs-lookup"><span data-stu-id="e9c45-186"></span></span>

[<span data-ttu-id="e9c45-187">使用呼叫分析來排查不佳的通話品質問題</span><span class="sxs-lookup"><span data-stu-id="e9c45-187">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

<span data-ttu-id="e9c45-188">[[通話分析] 和 [通話品質儀表板]](difference-between-call-analytics-and-call-quality-dashboard.md)</span><span class="sxs-lookup"><span data-stu-id="e9c45-188">[Call Analytics and Call Quality Dashboard](difference-between-call-analytics-and-call-quality-dashboard.md)</span></span>

  
 
