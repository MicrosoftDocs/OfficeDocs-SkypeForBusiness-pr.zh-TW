---
title: 使用 OneDrive 和 SharePoint 進行會議錄製
author: cichur
ms.author: v-cichur
ms.reviewer: hao.moy
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何從 Microsoft 團隊中的 [資料流程] 切換至 [商務用 OneDrive] 和 [SharePoint 會議錄製儲存空間]。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7a42c46cf9592c64676d153e1885357a4ee8ec7b
ms.sourcegitcommit: 48cb3cdd69558ec80f8f25f870b302a65280ce5a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/08/2020
ms.locfileid: "48389931"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a><span data-ttu-id="6c334-103">在會議錄製中使用商務用 OneDrive 和 SharePoint 或串流</span><span class="sxs-lookup"><span data-stu-id="6c334-103">Use OneDrive for Business and SharePoint or Stream for meeting recordings</span></span>

> [!Note]
> <span data-ttu-id="6c334-104">從使用 Microsoft Stream 到變更為使用商務用 OneDrive 和 OneDrive 來進行會議錄製，將會採取階段性的方式。</span><span class="sxs-lookup"><span data-stu-id="6c334-104">The change from using Microsoft Stream to OneDrive for Business and SharePoint for meeting recordings will be a phased approach.</span></span> <span data-ttu-id="6c334-105">在啟動時，租使用者系統管理員可以在10月2020中選擇這個新的工作流程選項，並開始查看錄製自動上傳至商務用 OneDrive 和 SharePoint 的功能。</span><span class="sxs-lookup"><span data-stu-id="6c334-105">At launch, tenant admins can choose this new workflow option today and will start seeing recordings auto-upload to OneDrive for Business and SharePoint in October 2020.</span></span> <span data-ttu-id="6c334-106">在11月，如果您想要繼續使用串流，且在早期的2021中還有一些時間，我們會要求所有客戶使用商務用 OneDrive 和 SharePoint 來進行新的會議錄製。</span><span class="sxs-lookup"><span data-stu-id="6c334-106">In November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

<span data-ttu-id="6c334-107">Microsoft 團隊有一個儲存會議錄製的新方法。</span><span class="sxs-lookup"><span data-stu-id="6c334-107">Microsoft Teams has a new method for saving meeting recordings.</span></span> <span data-ttu-id="6c334-108">作為從傳統 Microsoft Stream 轉換到 [新串流](https://docs.microsoft.com/stream/streamnew/new-stream)的第一個階段，此方法會將錄製儲存在 microsoft 365 中的 microsoft OneDrive 和 SharePoint，並提供許多好處。</span><span class="sxs-lookup"><span data-stu-id="6c334-108">As the first phase of a transition from classic Microsoft Stream to the [new Stream](https://docs.microsoft.com/stream/streamnew/new-stream), this method stores recordings on Microsoft OneDrive and SharePoint in Microsoft 365 and offers many benefits.</span></span>

<span data-ttu-id="6c334-109">使用商務用 OneDrive 和 SharePoint 儲存錄製的好處包括：</span><span class="sxs-lookup"><span data-stu-id="6c334-109">The benefits of using OneDrive for Business and SharePoint for storing recordings include:</span></span>

- <span data-ttu-id="6c334-110">團隊會議錄製 (TMR)  (S + C E5 autoretention 標籤的保留原則) </span><span class="sxs-lookup"><span data-stu-id="6c334-110">Retention policies for Teams meeting recording (TMR) (S+C E5 autoretention labels)</span></span>
- <span data-ttu-id="6c334-111">從商務用 OneDrive 和 SharePoint 資訊管理獲益</span><span class="sxs-lookup"><span data-stu-id="6c334-111">Benefit from OneDrive for Business and SharePoint information governance</span></span>
- <span data-ttu-id="6c334-112">輕鬆設定許可權和共用</span><span class="sxs-lookup"><span data-stu-id="6c334-112">Easy to set permissions and sharing</span></span>
- <span data-ttu-id="6c334-113">在只有明確共用的情況 (外部使用者) 與來賓共用錄製</span><span class="sxs-lookup"><span data-stu-id="6c334-113">Share recordings with guests (external users) with explicit share only</span></span>
- <span data-ttu-id="6c334-114">要求存取流程</span><span class="sxs-lookup"><span data-stu-id="6c334-114">Request access flow</span></span>
- <span data-ttu-id="6c334-115">供應商務用 OneDrive 和 SharePoint 共用連結</span><span class="sxs-lookup"><span data-stu-id="6c334-115">Provide OneDrive for Business and SharePoint shared links</span></span>
- <span data-ttu-id="6c334-116">增加配額</span><span class="sxs-lookup"><span data-stu-id="6c334-116">Increased quota</span></span>
- <span data-ttu-id="6c334-117">更快速地提供會議錄製</span><span class="sxs-lookup"><span data-stu-id="6c334-117">Meeting  recordings are available faster</span></span>
- <span data-ttu-id="6c334-118">**開始提供本機** 租使用者支援</span><span class="sxs-lookup"><span data-stu-id="6c334-118">**Go local** tenant support</span></span>
- <span data-ttu-id="6c334-119">多地區支援–錄製會儲存在該使用者專用的區域中</span><span class="sxs-lookup"><span data-stu-id="6c334-119">Multi-geo support – recordings are stored in a region specific to that user</span></span>
- <span data-ttu-id="6c334-120">提供您自己的金鑰 (BYOK) 支援</span><span class="sxs-lookup"><span data-stu-id="6c334-120">Bring your own key (BYOK) support</span></span>
- <span data-ttu-id="6c334-121">改良的記錄品質與演講者歸屬</span><span class="sxs-lookup"><span data-stu-id="6c334-121">Improved Transcript quality and speaker attribution</span></span>

<span data-ttu-id="6c334-122">以下是一些需要考慮的限制：</span><span class="sxs-lookup"><span data-stu-id="6c334-122">There are some limitations to consider:</span></span>

- <span data-ttu-id="6c334-123">系統會提供英文版隱藏式輔助字幕和記錄。</span><span class="sxs-lookup"><span data-stu-id="6c334-123">There will be English-only closed captions and transcripts.</span></span>
- <span data-ttu-id="6c334-124">您將無法搜尋 [腳本] 或其內容。</span><span class="sxs-lookup"><span data-stu-id="6c334-124">You won't be able to search transcripts or their content.</span></span>
- <span data-ttu-id="6c334-125">您無法編輯這些記錄，但您可以開啟/關閉 [標題]。</span><span class="sxs-lookup"><span data-stu-id="6c334-125">You won’t be able to edit the transcripts, but you'll be able to toggle captions off/on.</span></span>
- <span data-ttu-id="6c334-126">您可以控制您共用錄製的物件，但無法封鎖有共用存取權的人員下載錄製。</span><span class="sxs-lookup"><span data-stu-id="6c334-126">You can control with whom you share the recording, but you won't be able to block people with shared access from downloading the recording.</span></span>
- <span data-ttu-id="6c334-127">錄製完成後，您將不會收到電子郵件，但錄製會在會議完成後出現在會議聊天中。</span><span class="sxs-lookup"><span data-stu-id="6c334-127">You'll not get an email when the recording finishes saving, but the recording will appear in the meeting chat once it’s finished.</span></span> <span data-ttu-id="6c334-128">這將會比先前在資料流程中的速度更快</span><span class="sxs-lookup"><span data-stu-id="6c334-128">This will happen much quicker than it did in Stream previously</span></span>

<span data-ttu-id="6c334-129">如需詳細資訊，請觀看「會議錄製」。</span><span class="sxs-lookup"><span data-stu-id="6c334-129">Watch "Meeting Recording" for more information.</span></span>

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a><span data-ttu-id="6c334-130">設定商務用 OneDrive 和 SharePoint 的會議錄製選項</span><span class="sxs-lookup"><span data-stu-id="6c334-130">Set up the meeting recording option for OneDrive for Business and SharePoint</span></span>

1. <span data-ttu-id="6c334-131">安裝商務用 Skype Online PowerShell 管理主控台。</span><span class="sxs-lookup"><span data-stu-id="6c334-131">Install the Skype For Business Online PowerShell admin console.</span></span>

    <span data-ttu-id="6c334-132">a.</span><span class="sxs-lookup"><span data-stu-id="6c334-132">a.</span></span> <span data-ttu-id="6c334-133">下載 [商務用 Skype Online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="6c334-133">Download [Skype for Business Online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide).</span></span>

    <span data-ttu-id="6c334-134">b.</span><span class="sxs-lookup"><span data-stu-id="6c334-134">b.</span></span> <span data-ttu-id="6c334-135">依照提示進行安裝。</span><span class="sxs-lookup"><span data-stu-id="6c334-135">Follow the prompts to install it.</span></span>

    <span data-ttu-id="6c334-136">c-clip.</span><span class="sxs-lookup"><span data-stu-id="6c334-136">c.</span></span> <span data-ttu-id="6c334-137">重新開機您的電腦。</span><span class="sxs-lookup"><span data-stu-id="6c334-137">Restart your machine.</span></span>

2. <span data-ttu-id="6c334-138">以系統管理員身分啟動 PowerShell</span><span class="sxs-lookup"><span data-stu-id="6c334-138">Launch PowerShell as an admin</span></span>

3. <span data-ttu-id="6c334-139">匯入 SkypeOnline 連接器，然後以團隊管理員身分登入。</span><span class="sxs-lookup"><span data-stu-id="6c334-139">Import the SkypeOnline Connector and log in as a Teams admin.</span></span>

```PowerShell
  Import-Module SkypeOnlineConnector
  $sfbSession = New-CsOnlineSession
  Import-PSSession $sfbSession
```

4. <span data-ttu-id="6c334-140">使用 [ [設定] csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) ，將 [團隊會議原則] 轉換為 [從資料流程儲存轉換為 ODSP]。</span><span class="sxs-lookup"><span data-stu-id="6c334-140">Use [set-csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) to set a Teams Meeting Policy to transition from the Stream storage to ODSP.</span></span>

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
```

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a><span data-ttu-id="6c334-141">退出商務用 OneDrive 和 SharePoint 以繼續使用資料流程</span><span class="sxs-lookup"><span data-stu-id="6c334-141">Opt out of OneDrive for Business and SharePoint to continue using Stream</span></span>

<span data-ttu-id="6c334-142">即使原則將它設定為 [ **資料流程**]，也可能不會設定。</span><span class="sxs-lookup"><span data-stu-id="6c334-142">Even if a policy says it's set to **Stream**, it might not be set.</span></span> <span data-ttu-id="6c334-143">通常，如果原則沒有設定，則預設設定為 [ **資料流程**]。</span><span class="sxs-lookup"><span data-stu-id="6c334-143">Typically, if the policy isn't set, then the default setting is **Stream**.</span></span> <span data-ttu-id="6c334-144">不過，如果您想要選擇不使用 SharePoint 或 OneDrive，請使用這項新的變更，您必須將原則重設為 **串流** ，以確保它是預設值。</span><span class="sxs-lookup"><span data-stu-id="6c334-144">However, with this new change, if you want to opt-out of using SharePoint or OneDrive, then you must reset the policy to **Stream** to ensure that it's the default.</span></span>

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="frequently-asked-questions"></a><span data-ttu-id="6c334-145">常見問題集</span><span class="sxs-lookup"><span data-stu-id="6c334-145">Frequently asked questions</span></span>

<span data-ttu-id="6c334-146">**會議錄製將儲存在哪裡？**</span><span class="sxs-lookup"><span data-stu-id="6c334-146">**Where will the meeting recording be stored?**</span></span>

- <span data-ttu-id="6c334-147">對於非頻道會議，錄製會儲存在 OneDrive 中名為 [ **錄製** ] 的資料夾中，該資料夾屬於開始會議錄製的人員。</span><span class="sxs-lookup"><span data-stu-id="6c334-147">For non-Channel meetings, the recording is stored in a folder named **Recordings** that is at the top level of the OneDrive that belongs to the person who started the meeting recording.</span></span> <span data-ttu-id="6c334-148">範例</span><span class="sxs-lookup"><span data-stu-id="6c334-148">Example:</span></span>

  <span data-ttu-id="6c334-149"><i>錄影機的商務</i> / 用 OneDrive**錄製**</span><span class="sxs-lookup"><span data-stu-id="6c334-149"><i>recorder's OneDrive for Business</i>/**Recordings**</span></span>

- <span data-ttu-id="6c334-150">對於頻道會議，錄製會儲存在名為 [ **錄製**] 資料夾的 [小組網站] 文件庫中。</span><span class="sxs-lookup"><span data-stu-id="6c334-150">For Channel meetings, the recording is stored in the Teams site documentation library in a folder named **Recordings**.</span></span> <span data-ttu-id="6c334-151">範例</span><span class="sxs-lookup"><span data-stu-id="6c334-151">Example:</span></span>

  <span data-ttu-id="6c334-152"><i>團隊名稱-頻道名稱</i> /**檔** /**錄製**</span><span class="sxs-lookup"><span data-stu-id="6c334-152"><i>Teams name - Channel name</i>/**Documents**/**Recordings**</span></span>

<span data-ttu-id="6c334-153">**我要如何處理來自離職員工的錄製？**</span><span class="sxs-lookup"><span data-stu-id="6c334-153">**How do I handle recordings from former employees?**</span></span>

<span data-ttu-id="6c334-154">因為影片與 OneDrive 和 SharePoint 中的任何其他檔案一樣，所以在員工離職之後，處理擁有權及保留期將遵循正常的 [OneDrive 和 sharepoint]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process)程式。</span><span class="sxs-lookup"><span data-stu-id="6c334-154">Since videos are just like any other file in OneDrive and SharePoint, handling ownership and retention after an employee leaves will follow the normal [OneDrive and SharePoint process]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process).</span></span>

<span data-ttu-id="6c334-155">**誰有權查看會議錄製？**</span><span class="sxs-lookup"><span data-stu-id="6c334-155">**Who has the permissions to view the meeting recording?**</span></span>

- <span data-ttu-id="6c334-156">如果是非頻道會議，除了外部使用者以外的所有會議受邀者，都將自動取得個人共用的連結。</span><span class="sxs-lookup"><span data-stu-id="6c334-156">For non-Channel meetings, all meeting invitees, except for external users, will automatically get a personally shared link.</span></span> <span data-ttu-id="6c334-157">外部使用者必須透過會議召集人或開始會議錄製的人員，將其明確新增至共用清單中。</span><span class="sxs-lookup"><span data-stu-id="6c334-157">External users will need to be explicitly added to the shared list by the meeting organizer or the person who started the meeting recording.</span></span>

- <span data-ttu-id="6c334-158">對於頻道會議，許可權是從頻道中的 [擁有人] 和 [成員] 清單繼承而來。</span><span class="sxs-lookup"><span data-stu-id="6c334-158">For Channel meetings, permissions are inherited from the owners and members list in the channel.</span></span>

<span data-ttu-id="6c334-159">**我要如何管理腳本？**</span><span class="sxs-lookup"><span data-stu-id="6c334-159">**How can I manage transcripts?**</span></span>

<span data-ttu-id="6c334-160">客戶加入宣告此預覽並不會在其小組會議錄製中提供隱藏式輔助字幕，且已遷移至 OneDrive 和 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="6c334-160">Customers opting in to this preview will not have closed captions available on their Teams Meeting Recordings that are migrated to OneDrive and SharePoint.</span></span><span data-ttu-id="6c334-161">我們正致力於將隱藏式輔助字幕從英文新增至2020年10月的會議錄製。</span><span class="sxs-lookup"><span data-stu-id="6c334-161">  We're working to add captioning, beginning with closed captions in English, to meeting recordings in October 2020.</span></span>

<span data-ttu-id="6c334-162">小組會議錄製會提供隱藏式輔助字幕，供已自願加入在[小組雲端錄製](cloud-recording.md)中描述的客戶使用。</span><span class="sxs-lookup"><span data-stu-id="6c334-162">Closed captions will be available on Teams Meeting Recordings for customers who have opted in to allow transcripts as described in [Teams cloud recordings](cloud-recording.md)</span></span>

<span data-ttu-id="6c334-163">[標題] 可協助為所有功能的檢視器建立包含內容。</span><span class="sxs-lookup"><span data-stu-id="6c334-163">Captions help create inclusive content for viewers of all abilities.</span></span> <span data-ttu-id="6c334-164">在擁有者中，您可以隱藏標題，但除非您刪除小組中的標題，否則仍可在團隊中使用這些記錄。</span><span class="sxs-lookup"><span data-stu-id="6c334-164">As an owner, you can hide captions, although the transcript will still be available on Teams unless you delete the captions from Teams.</span></span> <span data-ttu-id="6c334-165">瞭解 [如何開啟或關閉會議錄製](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)</span><span class="sxs-lookup"><span data-stu-id="6c334-165">See [how to turn on or off meeting recordings](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)</span></span>

<span data-ttu-id="6c334-166">錄製會議時，小組會議錄製支援的60天是隱藏式輔助字幕。</span><span class="sxs-lookup"><span data-stu-id="6c334-166">Closed captions are supported for Teams meeting recordings for 60 days from when the meeting is recorded.</span></span>

<span data-ttu-id="6c334-167">**我的儲存空間配額受影響的方式**</span><span class="sxs-lookup"><span data-stu-id="6c334-167">**How will my storage quota be impacted**</span></span>

<span data-ttu-id="6c334-168">小組會議會在商務用 OneDrive 和 SharePoint 中即時錄製檔案，並包含在這些服務的配額中。</span><span class="sxs-lookup"><span data-stu-id="6c334-168">Teams meeting recording files live in OneDrive for Business and SharePoint and are included in your quota for those services.</span></span> <span data-ttu-id="6c334-169">請參閱 [SharePoint 配額](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) 和 [商務用 OneDrive 配額] (https://docs.microsoft.com/onedrive/set-default-storage-space) 。</span><span class="sxs-lookup"><span data-stu-id="6c334-169">See [SharePoint quota](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) and [OneDrive for Business quota] (https://docs.microsoft.com/onedrive/set-default-storage-space).</span></span>

<span data-ttu-id="6c334-170">**如何播放團隊會議錄製？**</span><span class="sxs-lookup"><span data-stu-id="6c334-170">**How can I play a Teams meeting recording?**</span></span>

<span data-ttu-id="6c334-171">您的影片將會在商務用 OneDrive 或 SharePoint 的影片播放機上播放，視您存取該檔案的位置而定。</span><span class="sxs-lookup"><span data-stu-id="6c334-171">Your video will play on the video player of OneDrive for Business or SharePoint depending on where you access the file.</span></span>

<span data-ttu-id="6c334-172">**如果您打算 deprecating 新增至串流，現有的影片會持續保持不變嗎？**</span><span class="sxs-lookup"><span data-stu-id="6c334-172">**If you plan on deprecating adding to Stream, will existing videos stay as is and for how long?**</span></span>

<span data-ttu-id="6c334-173">在不久的將來，不會棄用作為平臺的資料流程。</span><span class="sxs-lookup"><span data-stu-id="6c334-173">Stream as a platform won't be deprecated in the near future.</span></span> <span data-ttu-id="6c334-174">目前在資料流程中的影片會一直留在這裡，直到我們開始進行遷移為止。</span><span class="sxs-lookup"><span data-stu-id="6c334-174">The videos that currently live in Stream will stay there until we start migrating.</span></span> <span data-ttu-id="6c334-175">遷移時，這些影片也會同時遷移至 ODSP。</span><span class="sxs-lookup"><span data-stu-id="6c334-175">Upon migration, those videos will be migrated to ODSP as well.</span></span> <span data-ttu-id="6c334-176">若要瞭解詳細資訊，請參閱 [這裡](https://docs.microsoft.com/stream/streamnew/classic-migration) 。</span><span class="sxs-lookup"><span data-stu-id="6c334-176">Check [here](https://docs.microsoft.com/stream/streamnew/classic-migration) for more information.</span></span>
