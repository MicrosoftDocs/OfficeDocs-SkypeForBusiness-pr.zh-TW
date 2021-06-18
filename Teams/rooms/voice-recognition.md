---
title: 租使用者系統管理中語音 (語音設定檔) 控制項Teams 會議室
author: cichur
ms.author: v-cichur
ms.reviewer: parisataheri
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解租使用者系統管理在會議室 (語音) 語音Teams控制項。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6b4a8a5d0b866a3eb278ffdba575966f97c549d6
ms.sourcegitcommit: 35ee6946b6f560a268d1313bf51c3cc94d8d52f1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2021
ms.locfileid: "52997746"
---
# <a name="manage-voice-recognition-technology-controls-for-an-intelligent-speaker"></a><span data-ttu-id="4b984-103">管理智慧型喇叭的語音辨識技術控制項</span><span class="sxs-lookup"><span data-stu-id="4b984-103">Manage voice recognition technology controls for an Intelligent Speaker</span></span>

<span data-ttu-id="4b984-104">智慧型喇叭會使用語音設定檔資訊來識別誰在即時抄寫中表達內容。</span><span class="sxs-lookup"><span data-stu-id="4b984-104">An Intelligent Speaker uses voice profile information to recognize who said what in live transcription.</span></span> <span data-ttu-id="4b984-105">當Microsoft Teams 會議室會議室Windows配備智慧型演講者時，可在會議期間使用即時抄寫。</span><span class="sxs-lookup"><span data-stu-id="4b984-105">When a Microsoft Teams Rooms for Windows meeting room is equipped with an Intelligent Speaker, live transcription can be used during the meeting.</span></span> <span data-ttu-id="4b984-106">本文說明租使用者系統管理員如何控制用於語音辨識的語音分析，以產生即時抄寫。</span><span class="sxs-lookup"><span data-stu-id="4b984-106">This article explains how you, a tenant admin, control the voice profiling that's used for voice recognition to generate live transcription.</span></span> <span data-ttu-id="4b984-107">您可以控制組織使用語音辨識的程度，以及下列功能：</span><span class="sxs-lookup"><span data-stu-id="4b984-107">You can control to what degree the organization is using voice recognition and the following features:</span></span>

- <span data-ttu-id="4b984-108">在文字記錄中編輯演講者的名稱。</span><span class="sxs-lookup"><span data-stu-id="4b984-108">Edit the speaker's name in transcripts.</span></span>
- <span data-ttu-id="4b984-109">變更文字記錄中單字的演講者，或變更文字記錄中所有片語中的演講者 (但不要變更) 。</span><span class="sxs-lookup"><span data-stu-id="4b984-109">Change the speaker of a single utterance in the transcript or change the speaker in all the utterances in the transcript (but not on future transcripts).</span></span>
- <span data-ttu-id="4b984-110">變更會議中列出的人員之喇叭識別。</span><span class="sxs-lookup"><span data-stu-id="4b984-110">Change the speaker identification for the people who are listed in the meeting.</span></span>
- <span data-ttu-id="4b984-111">移除每個文字記錄上識別為該演講者的一或多個片語識別。</span><span class="sxs-lookup"><span data-stu-id="4b984-111">Remove the identification of one or more utterances identified as that speaker, on every transcript.</span></span>

## <a name="review-intelligent-speaker-requirements"></a><span data-ttu-id="4b984-112">審查智慧型喇叭需求</span><span class="sxs-lookup"><span data-stu-id="4b984-112">Review Intelligent Speaker requirements</span></span>

<span data-ttu-id="4b984-113">智慧型喇叭包含特殊的七麥克風陣列。</span><span class="sxs-lookup"><span data-stu-id="4b984-113">An Intelligent Speaker includes a special seven-microphone array.</span></span> <span data-ttu-id="4b984-114">系統使用語音設定檔資訊來識別會議室中最多 10 個人的聲音。</span><span class="sxs-lookup"><span data-stu-id="4b984-114">The system uses voice profile information to identify voices of up to 10 people in meeting rooms.</span></span>

<span data-ttu-id="4b984-115">下列專案為智慧型喇叭需求：</span><span class="sxs-lookup"><span data-stu-id="4b984-115">The following items are Intelligent Speaker requirements:</span></span>

- <span data-ttu-id="4b984-116">客戶租使用者必須位於美國 (北美) 。<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4b984-116">The customer tenant must be located in the U.S. (North America).<sup>1</sup></span></span>
- <span data-ttu-id="4b984-117">會議室最多應有 10 個人出席。</span><span class="sxs-lookup"><span data-stu-id="4b984-117">The meeting room should have a maximum of 10 people present in person.</span></span>
- <span data-ttu-id="4b984-118">會議室的上傳連結至少為 7Mbps。</span><span class="sxs-lookup"><span data-stu-id="4b984-118">The meeting room has an upload link of minimum 7 Mbps.</span></span>

 <span data-ttu-id="4b984-119"><sup>1</sup> 智慧型喇叭和相關語音設定檔及使用方式僅適用于 EN-US 語言，且適用于美國 NA-US 地區 (租) 使用。</span><span class="sxs-lookup"><span data-stu-id="4b984-119"><sup>1</sup> An Intelligent Speaker and associated voice profile and usage will only be available in EN-US language and for US (NA-US region) tenants.</span></span> <span data-ttu-id="4b984-120">租使用者使用者註冊並使用智慧型喇叭進行屬性化抄寫時，這兩個條件都必須正確。</span><span class="sxs-lookup"><span data-stu-id="4b984-120">Both conditions must be true for a tenant user to enroll and use an Intelligent Speaker for attributed transcription.</span></span>

## <a name="set-up-an-intelligent-speaker"></a><span data-ttu-id="4b984-121">設定智慧型喇叭</span><span class="sxs-lookup"><span data-stu-id="4b984-121">Set up an Intelligent Speaker</span></span>

<span data-ttu-id="4b984-122">智慧型喇叭會使用 USB 直接連接到Teams 會議室主機。</span><span class="sxs-lookup"><span data-stu-id="4b984-122">An Intelligent Speaker connects directly using USB to the Teams Rooms console.</span></span> <span data-ttu-id="4b984-123">為了獲得最佳結果，Yealink 品牌智慧型喇叭應該與 Yealink 品牌主機一起使用。</span><span class="sxs-lookup"><span data-stu-id="4b984-123">For best results, a Yealink brand Intelligent Speaker should be used with a Yealink brand console.</span></span>

> [!NOTE]
> <span data-ttu-id="4b984-124">Yealink 智慧喇叭 **必須與** Yealink 主機一起使用。</span><span class="sxs-lookup"><span data-stu-id="4b984-124">A Yealink Intelligent Speaker **must** be used with a Yealink console.</span></span>

> [!NOTE]
> <span data-ttu-id="4b984-125">我們不支援連接到 Logitech Surface Pro Microsoft Teams 會議室。</span><span class="sxs-lookup"><span data-stu-id="4b984-125">We don't support an Intelligent Speaker connected to Logitech Surface Pro Microsoft Teams Rooms.</span></span> <span data-ttu-id="4b984-126">有一個已知Teams 會議室無法透過基座識別智慧型喇叭。</span><span class="sxs-lookup"><span data-stu-id="4b984-126">There is a known issue that Teams Rooms can't recognize the Intelligent Speaker through the dock.</span></span>

<span data-ttu-id="4b984-127">智慧型喇叭應置於至少 8 (20 公) ，遠離牆面和大型物件 ，例如膝上型電腦。</span><span class="sxs-lookup"><span data-stu-id="4b984-127">An Intelligent Speaker should be placed at least 8 inches (20 cm) away from walls and large objects, such as laptops.</span></span> <span data-ttu-id="4b984-128">如果智慧型喇叭 USB 纜線不夠長，無法用於您的設定，請使用纜線延伸器。</span><span class="sxs-lookup"><span data-stu-id="4b984-128">If the Intelligent Speaker USB cable isn't long enough for your setup, use cable extenders.</span></span>

1. <span data-ttu-id="4b984-129">以系統管理員的登錄主機。</span><span class="sxs-lookup"><span data-stu-id="4b984-129">Sign in to the console as administrator.</span></span>
2. <span data-ttu-id="4b984-130">設定Teams設定，以配合智慧型喇叭麥克風和喇叭。</span><span class="sxs-lookup"><span data-stu-id="4b984-130">Set the Teams device settings to match the Intelligent Speaker microphone and speaker.</span></span>
   <span data-ttu-id="4b984-131">您也可以透過 TAC 入口網站而非會議室主控台執行此操作。</span><span class="sxs-lookup"><span data-stu-id="4b984-131">You can also do this through the TAC portal instead of at the room console.</span></span>

   <span data-ttu-id="4b984-132">圖表顯示智慧型喇叭如何連接到裝置 ，如果裝置包含資料方塊。</span><span class="sxs-lookup"><span data-stu-id="4b984-132">The diagram shows how the Intelligent Speaker is connected to the device if the device includes a data box.</span></span>

   ![<span data-ttu-id="4b984-133">智慧型喇叭設定與喇叭、電源和資料方塊。</span><span class="sxs-lookup"><span data-stu-id="4b984-133">The Intelligent Speaker setup with the speaker, the power and data box.</span></span> <span data-ttu-id="4b984-134">一條線會進入主機的 USB 埠，另一條線則進入電源。</span><span class="sxs-lookup"><span data-stu-id="4b984-134">One line goes to the USB port of the console, and the other line goes to power.</span></span> ](../media/intelligent-speakers1.png)

   <span data-ttu-id="4b984-135">圖表顯示如果裝置不包含資料方塊，智慧型喇叭如何連接到裝置。</span><span class="sxs-lookup"><span data-stu-id="4b984-135">The diagram shows how the Intelligent Speaker is connected to the device if the device doesn't include a data box.</span></span>

   ![<span data-ttu-id="4b984-136">智慧型喇叭設定，讓喇叭直接連接到主機。</span><span class="sxs-lookup"><span data-stu-id="4b984-136">The Intelligent Speaker setup with the speaker connecting directly to the console.</span></span> ](../media/intelligent-speakers2.png)

> [!Note]
> <span data-ttu-id="4b984-137">EPOS 和 Yealink 裝置應具有 "EPOS" 或 "Yealink" 首碼，且在喇叭名稱中包含 「UAC2_RENDER」，而麥克風名稱中則包含 「UAC2_TEAMS」。</span><span class="sxs-lookup"><span data-stu-id="4b984-137">EPOS and Yealink devices should have "EPOS" or "Yealink" prefix and contain "UAC2_RENDER" in the speaker name and "UAC2_TEAMS" in the microphone name.</span></span> <span data-ttu-id="4b984-138">如果您在下拉式功能表中找不到這些麥克風和喇叭名稱，請重新開機智慧喇叭裝置。</span><span class="sxs-lookup"><span data-stu-id="4b984-138">If you don't find these microphone and speaker names in the dropdown menu, restart the Intelligent Speaker device.</span></span>

## <a name="enable-an-intelligent-speaker-user-recognition"></a><span data-ttu-id="4b984-139">啟用智慧型喇叭使用者識別</span><span class="sxs-lookup"><span data-stu-id="4b984-139">Enable an Intelligent Speaker user recognition</span></span>

<span data-ttu-id="4b984-140">語音設定檔資料可用於使用智慧型喇叭的任何會議。</span><span class="sxs-lookup"><span data-stu-id="4b984-140">Voice profile data can be used in any meeting with an Intelligent Speaker.</span></span> <span data-ttu-id="4b984-141">請參閱[Teams和](../meeting-policies-in-teams.md#allow-transcription) [PowerShell 會議 Cmdlet，](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)以瞭解會議設定的資訊。</span><span class="sxs-lookup"><span data-stu-id="4b984-141">See [Teams meetings policies](../meeting-policies-in-teams.md#allow-transcription) and the [PowerShell meeting cmdlets](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) for information on the meeting settings.</span></span>

<span data-ttu-id="4b984-142">當策略設定為區分時，或非會議受邀者在會議期間逐步加入時，即會建立使用者的語音設定檔資料。</span><span class="sxs-lookup"><span data-stu-id="4b984-142">The voice profile data of the user is created when the policy is set to distinguish or a non-meeting invitee walks in during the meeting.</span></span> <span data-ttu-id="4b984-143">語音設定檔資料在會議結束時會關閉。</span><span class="sxs-lookup"><span data-stu-id="4b984-143">The voice profile data is dismissed at the end of the meeting.</span></span>

<span data-ttu-id="4b984-144">以下是設定智慧型喇叭和使用者識別所需的策略。</span><span class="sxs-lookup"><span data-stu-id="4b984-144">The following are the required policies to set an Intelligent Speaker and user recognition.</span></span>

|<span data-ttu-id="4b984-145">政策</span><span class="sxs-lookup"><span data-stu-id="4b984-145">Policy</span></span>|<span data-ttu-id="4b984-146">說明</span><span class="sxs-lookup"><span data-stu-id="4b984-146">Description</span></span>|<span data-ttu-id="4b984-147">值與行為</span><span class="sxs-lookup"><span data-stu-id="4b984-147">Values and Behavior</span></span>|
|-|-|-|
|<span data-ttu-id="4b984-148">註冊UserOverride</span><span class="sxs-lookup"><span data-stu-id="4b984-148">enrollUserOverride</span></span>|<span data-ttu-id="4b984-149">用於設定租使用者Teams的語音設定檔捕獲或註冊。</span><span class="sxs-lookup"><span data-stu-id="4b984-149">Use to set voice profile capture, or enrollment, in Teams settings for a tenant.</span></span> |<span data-ttu-id="4b984-150">**已停用**</span><span class="sxs-lookup"><span data-stu-id="4b984-150">**Disabled**</span></span><br><ul><li> <span data-ttu-id="4b984-151">從未註冊的使用者無法查看、註冊或重新註冊。</span><span class="sxs-lookup"><span data-stu-id="4b984-151">Users who have never enrolled can't view, enroll, or re-enroll.</span></span><li><span data-ttu-id="4b984-152">註冊流程的進入點將會隱藏。</span><span class="sxs-lookup"><span data-stu-id="4b984-152">The entry point to the enrollment flow will be hidden.</span></span><li><span data-ttu-id="4b984-153">如果使用者選取註冊頁面的連結，就會看到一則訊息，指出其組織未啟用此功能。</span><span class="sxs-lookup"><span data-stu-id="4b984-153">If users select a link to the enrollment page, they'll see a message that states this feature isn't enabled for their organization.</span></span>  <li><span data-ttu-id="4b984-154">已註冊的使用者可以在設定中查看和移除Teams設定檔。</span><span class="sxs-lookup"><span data-stu-id="4b984-154">Users who have enrolled can view and remove their voice profile in the Teams settings.</span></span> <span data-ttu-id="4b984-155">移除語音設定檔後，他們將無法查看、存取或完成註冊流程。</span><span class="sxs-lookup"><span data-stu-id="4b984-155">Once they remove their voice profile, they won't be able to view, access, or complete the enrollment flow.</span></span></li></ul><br><span data-ttu-id="4b984-156">**啟用**</span><span class="sxs-lookup"><span data-stu-id="4b984-156">**Enabled**</span></span><br><ul><li> <span data-ttu-id="4b984-157">使用者可以查看、存取及完成註冊流程。</span><span class="sxs-lookup"><span data-stu-id="4b984-157">Users can view, access, and complete the enrollment flow.</span></span><li><span data-ttu-id="4b984-158">進入點會顯示在Teams的設定 **頁面上**。</span><span class="sxs-lookup"><span data-stu-id="4b984-158">The entry point will show on Teams settings page under the **Recognition** tab.</span></span></li></ul>|
|<span data-ttu-id="4b984-159">roomAttributeUserOverride</span><span class="sxs-lookup"><span data-stu-id="4b984-159">roomAttributeUserOverride</span></span>|<span data-ttu-id="4b984-160">控制會議室中的語音使用者識別。</span><span class="sxs-lookup"><span data-stu-id="4b984-160">Control the voice-based user identification in meeting rooms.</span></span> <span data-ttu-id="4b984-161">此設定適用于Teams 會議室帳戶。</span><span class="sxs-lookup"><span data-stu-id="4b984-161">This setting is required for Teams Rooms accounts.</span></span>| <span data-ttu-id="4b984-162">**關閉**</span><span class="sxs-lookup"><span data-stu-id="4b984-162">**Off**</span></span><br><ul><li><span data-ttu-id="4b984-163">Teams 會議室裝置不會從會議室傳送音訊串流節省頻寬。</span><span class="sxs-lookup"><span data-stu-id="4b984-163">The Teams Rooms device won't send audio stream-saving bandwidth from the room.</span></span> <li><span data-ttu-id="4b984-164">會議室使用者不會被屬性或區分，而且他們的語音簽名也不會被取回或使用。</span><span class="sxs-lookup"><span data-stu-id="4b984-164">Meeting room users won't be attributed or distinguished, and their voice signatures won't be retrieved or used at all.</span></span><li><span data-ttu-id="4b984-165">會議室使用者不明。</span><span class="sxs-lookup"><span data-stu-id="4b984-165">Meeting room users are unknown.</span></span></li></ul> <br><span data-ttu-id="4b984-166">**屬性**</span><span class="sxs-lookup"><span data-stu-id="4b984-166">**Attribute**</span></span><br><ul><li><span data-ttu-id="4b984-167">會議室使用者會依據他們的註冊狀態來屬性。</span><span class="sxs-lookup"><span data-stu-id="4b984-167">Rooms users will be attributed based on their enrollment status.</span></span><li><span data-ttu-id="4b984-168">註冊的使用者在文字翻譯中會顯示其名稱。</span><span class="sxs-lookup"><span data-stu-id="4b984-168">Users who are enrolled are shown with their name in the transcription.</span></span>  <li><span data-ttu-id="4b984-169">未註冊的使用者會顯示為演講者 n。</span><span class="sxs-lookup"><span data-stu-id="4b984-169">Users who aren't enrolled show as Speaker n.</span></span><li><span data-ttu-id="4b984-170">Teams 會議室裝置會從會議室傳送七個音訊資料流程。</span><span class="sxs-lookup"><span data-stu-id="4b984-170">The Teams Rooms device will send seven audio streams from the room.</span></span></ul> <br><span data-ttu-id="4b984-171">**區分**</span><span class="sxs-lookup"><span data-stu-id="4b984-171">**Distinguish**</span></span><br> <span data-ttu-id="4b984-172">*這項設定將在日後提供。*</span><span class="sxs-lookup"><span data-stu-id="4b984-172">*This setting will be available at a later date.*</span></span>|
|<span data-ttu-id="4b984-173">enabletranscription</span><span class="sxs-lookup"><span data-stu-id="4b984-173">enabletranscription</span></span>|<span data-ttu-id="4b984-174">使用者和會議室帳戶Teams必填專案。</span><span class="sxs-lookup"><span data-stu-id="4b984-174">Required for user and Teams rooms accounts.</span></span>|<span data-ttu-id="4b984-175">**True** 和 **False**</span><span class="sxs-lookup"><span data-stu-id="4b984-175">**True** and **False**</span></span>|
||||

<span data-ttu-id="4b984-176">在系統管理Teams中，設定 **允許抄寫** 政策。</span><span class="sxs-lookup"><span data-stu-id="4b984-176">In the Teams admin center, set the **Allow transcription** policy.</span></span> <span data-ttu-id="4b984-177">設定預設 **為關閉**。</span><span class="sxs-lookup"><span data-stu-id="4b984-177">Settings are **Off** by default.</span></span>

![系統管理中心，系統已強調會議政策，且已選取允許抄寫](../media/allow-transcription1.png)

## <a name="frequently-asked-questions-faq"></a><span data-ttu-id="4b984-179">常見問題集 (FAQ)</span><span class="sxs-lookup"><span data-stu-id="4b984-179">Frequently asked questions (FAQ)</span></span>

<span data-ttu-id="4b984-180">**語音設定檔資料儲存在哪裡？**</span><span class="sxs-lookup"><span data-stu-id="4b984-180">**Where is the voice profile data stored?**</span></span>

<span data-ttu-id="4b984-181">語音設定檔資料會儲存在雲端Office 365包含使用者內容。</span><span class="sxs-lookup"><span data-stu-id="4b984-181">Voice profile data is stored in Office 365 cloud with user content.</span></span>

<span data-ttu-id="4b984-182">**什麼是保留時間表和策略？**</span><span class="sxs-lookup"><span data-stu-id="4b984-182">**What is the retention timeline and policy?**</span></span>

<span data-ttu-id="4b984-183">資料保留概觀中會說明一 [般保留政策](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview)。</span><span class="sxs-lookup"><span data-stu-id="4b984-183">General retention policy is stated in the [Data retention overview](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview).</span></span> <span data-ttu-id="4b984-184">此外，如果使用者未在 3 年內受邀參加智慧型喇叭的任何會議，使用者的語音設定檔資料將在 3 年後刪除。</span><span class="sxs-lookup"><span data-stu-id="4b984-184">In addition, a user's voice profile data will be deleted after 3 years  if the user isn't invited to any meetings with an Intelligent Speaker within that 3-year period.</span></span> <span data-ttu-id="4b984-185">資料不會用於現有員工的任何會議。</span><span class="sxs-lookup"><span data-stu-id="4b984-185">Data isn't used in any meetings for existing employees.</span></span> <span data-ttu-id="4b984-186">如果員工離職，語音設定檔資料會視為使用者內容，並且根據資料保留概觀所述Office 365資料保留政策視為[使用者內容](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview)。</span><span class="sxs-lookup"><span data-stu-id="4b984-186">If an employee has left the company, voice profile data is considered user content and is treated as such per Office 365 data retention policy described in the [Data retention overview](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview).</span></span>

<span data-ttu-id="4b984-187">**語音設定檔資料是否用於Microsoft 服務？**</span><span class="sxs-lookup"><span data-stu-id="4b984-187">**Is voice profile data used across Microsoft services?**</span></span>

<span data-ttu-id="4b984-188">否，語音設定檔資料只會用於使用者提供同意的目的。</span><span class="sxs-lookup"><span data-stu-id="4b984-188">No, voice profile data is only used for the purpose for which the user has provided consent.</span></span> <span data-ttu-id="4b984-189">Microsoft 不會使用語音設定檔資料，除非Teams語音辨識案例。</span><span class="sxs-lookup"><span data-stu-id="4b984-189">Microsoft will not use the voice profile data except within Teams voice recognition scenarios.</span></span>

<span data-ttu-id="4b984-190">例如，Microsoft 不會在下列情況下使用資料：</span><span class="sxs-lookup"><span data-stu-id="4b984-190">For example, Microsoft won't use the data in the following situations:</span></span>

<span data-ttu-id="4b984-191">**當我加入另一個組織的會議時，是否使用我的語音設定檔資料？**</span><span class="sxs-lookup"><span data-stu-id="4b984-191">**Is my voice profile data used when I join a meeting in another organization?**</span></span>

<span data-ttu-id="4b984-192">只有貴組織中使用者所組織的會議才不一樣。</span><span class="sxs-lookup"><span data-stu-id="4b984-192">No only in meetings organized by a user in your organization.</span></span>

<span data-ttu-id="4b984-193">**如何匯出語音設定檔？**</span><span class="sxs-lookup"><span data-stu-id="4b984-193">**How can I export my voice profile?**</span></span>

<span data-ttu-id="4b984-194">您的 IT 系統管理員隨時都可以匯出您的音訊資料。</span><span class="sxs-lookup"><span data-stu-id="4b984-194">Your IT admin can export your audio data at any time.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4b984-195">相關主題</span><span class="sxs-lookup"><span data-stu-id="4b984-195">Related topics</span></span>

[<span data-ttu-id="4b984-196">支援文章：使用智慧型喇叭識別會議室參與者 </span><span class="sxs-lookup"><span data-stu-id="4b984-196">Support article: Use Intelligent Speakers to Identify in-room participants </span></span>](https://support.microsoft.com/office/use-teams-intelligent-speakers-to-identify-in-room-participants-in-meeting-transcription-a075d6c0-30b3-44b9-b218-556a87fadc00)
