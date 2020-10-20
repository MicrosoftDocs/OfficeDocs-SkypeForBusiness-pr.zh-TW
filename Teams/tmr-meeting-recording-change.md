---
title: 使用商務用 OneDrive 和 SharePoint 進行會議錄製
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
ms.openlocfilehash: dc024491ee289717b9028969544ae179a72e3d0e
ms.sourcegitcommit: 96febfae562d604d9affc60028975881f5d6fb7c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/20/2020
ms.locfileid: "48599558"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a><span data-ttu-id="cb073-103">在會議錄製中使用商務用 OneDrive 和 SharePoint 或串流</span><span class="sxs-lookup"><span data-stu-id="cb073-103">Use OneDrive for Business and SharePoint or Stream for meeting recordings</span></span>

> [!Note]
> <span data-ttu-id="cb073-104">使用 Microsoft Stream to 商務用 OneDrive 和 Microsoft SharePoint for meeting 錄製所做的變更將是一種分階段的方法。</span><span class="sxs-lookup"><span data-stu-id="cb073-104">The change from using Microsoft Stream to OneDrive for Business and Microsoft SharePoint for meeting recordings will be a phased approach.</span></span>


|<span data-ttu-id="cb073-105">為止</span><span class="sxs-lookup"><span data-stu-id="cb073-105">Date</span></span>|<span data-ttu-id="cb073-106">引發</span><span class="sxs-lookup"><span data-stu-id="cb073-106">Event</span></span>|
|---|-----------------|
|<span data-ttu-id="cb073-107">CY20 年4月初</span><span class="sxs-lookup"><span data-stu-id="cb073-107">Early Q4 CY20</span></span>|<span data-ttu-id="cb073-108">**商務用 OneDrive 和 SharePoint 上的小組會議錄製可供自願加入或退出宣告。**</span><span class="sxs-lookup"><span data-stu-id="cb073-108">**Teams meeting recording on OneDrive for Business and SharePoint available for opt in or opt out.**</span></span><br> <span data-ttu-id="cb073-109">租使用者管理員可以加入宣告或退出宣告商務用 OneDrive 和 SharePoint 設定 PowerShell 中的團隊原則</span><span class="sxs-lookup"><span data-stu-id="cb073-109">Tenant admins can opt in  or opt out of OneDrive for Business and SharePoint setting the Teams policy in PowerShell</span></span>|
|<span data-ttu-id="cb073-110">第4季度中旬 CY20</span><span class="sxs-lookup"><span data-stu-id="cb073-110">Mid Q4 CY20</span></span>|<span data-ttu-id="cb073-111">**在商務用 OneDrive 上的小組會議錄製，以及 SharePoint 設定為未選擇的租使用者的預設值**</span><span class="sxs-lookup"><span data-stu-id="cb073-111">**Teams meeting recording on OneDrive for Business and SharePoint set as default for tenants who don't opt out**</span></span><br> <span data-ttu-id="cb073-112">這是大多數客戶的建議路徑</span><span class="sxs-lookup"><span data-stu-id="cb073-112">This is the  recommended path for most customers</span></span>|
|<span data-ttu-id="cb073-113">Q1 CY21</span><span class="sxs-lookup"><span data-stu-id="cb073-113">Q1 CY21</span></span>|<span data-ttu-id="cb073-114">**已不再允許將團隊會議錄製儲存至傳統資料流程**</span><span class="sxs-lookup"><span data-stu-id="cb073-114">**Saving Teams meeting recording to Classic Stream no longer allowed**</span></span><br><span data-ttu-id="cb073-115">所有承租人都會將團隊會議記錄儲存至商務用 OneDrive 和 SharePoint</span><span class="sxs-lookup"><span data-stu-id="cb073-115">All tenants will save Teams meeting recording to OneDrive for Business and SharePoint</span></span>|


<span data-ttu-id="cb073-116">Microsoft 團隊有一個儲存會議錄製的新方法。</span><span class="sxs-lookup"><span data-stu-id="cb073-116">Microsoft Teams has a new method for saving meeting recordings.</span></span> <span data-ttu-id="cb073-117">作為從傳統 Microsoft Stream 轉換到 [新串流](https://docs.microsoft.com/stream/streamnew/new-stream)的第一個階段，此方法會將錄製儲存在 microsoft 365 的商務用 OneDrive 和 SharePoint 中，並提供許多好處。</span><span class="sxs-lookup"><span data-stu-id="cb073-117">As the first phase of a transition from classic Microsoft Stream to the [new Stream](https://docs.microsoft.com/stream/streamnew/new-stream), this method stores recordings on Microsoft OneDrive for Business and SharePoint in Microsoft 365 and offers many benefits.</span></span>

<span data-ttu-id="cb073-118">使用商務用 OneDrive 和 SharePoint 儲存錄製的好處包括：</span><span class="sxs-lookup"><span data-stu-id="cb073-118">The benefits of using OneDrive for Business and SharePoint for storing recordings include:</span></span>

- <span data-ttu-id="cb073-119">團隊會議錄製 (TMR)  (S + C E5 autoretention 標籤的保留原則) </span><span class="sxs-lookup"><span data-stu-id="cb073-119">Retention policies for Teams meeting recording (TMR) (S+C E5 autoretention labels)</span></span>
- <span data-ttu-id="cb073-120">從商務用 OneDrive 和 SharePoint 資訊管理獲益</span><span class="sxs-lookup"><span data-stu-id="cb073-120">Benefit from OneDrive for Business and SharePoint information governance</span></span>
- <span data-ttu-id="cb073-121">輕鬆設定許可權和共用</span><span class="sxs-lookup"><span data-stu-id="cb073-121">Easy to set permissions and sharing</span></span>
- <span data-ttu-id="cb073-122">在只有明確共用的情況 (外部使用者) 與來賓共用錄製</span><span class="sxs-lookup"><span data-stu-id="cb073-122">Share recordings with guests (external users) with explicit share only</span></span>
- <span data-ttu-id="cb073-123">要求存取流程</span><span class="sxs-lookup"><span data-stu-id="cb073-123">Request access flow</span></span>
- <span data-ttu-id="cb073-124">供應商務用 OneDrive 和 SharePoint 共用連結</span><span class="sxs-lookup"><span data-stu-id="cb073-124">Provide OneDrive for Business and SharePoint shared links</span></span>
- <span data-ttu-id="cb073-125">增加配額</span><span class="sxs-lookup"><span data-stu-id="cb073-125">Increased quota</span></span>
- <span data-ttu-id="cb073-126">更快速地提供會議錄製</span><span class="sxs-lookup"><span data-stu-id="cb073-126">Meeting  recordings are available faster</span></span>
- <span data-ttu-id="cb073-127">**開始提供本機** 租使用者支援</span><span class="sxs-lookup"><span data-stu-id="cb073-127">**Go local** tenant support</span></span>
- <span data-ttu-id="cb073-128">多地區支援–錄製會儲存在該使用者專用的區域中</span><span class="sxs-lookup"><span data-stu-id="cb073-128">Multi-geo support – recordings are stored in a region specific to that user</span></span>
- <span data-ttu-id="cb073-129">提供您自己的金鑰 (BYOK) 支援</span><span class="sxs-lookup"><span data-stu-id="cb073-129">Bring your own key (BYOK) support</span></span>
- <span data-ttu-id="cb073-130">改良的記錄品質與演講者歸屬</span><span class="sxs-lookup"><span data-stu-id="cb073-130">Improved Transcript quality and speaker attribution</span></span>

<span data-ttu-id="cb073-131">以下是一些需要考慮的限制：</span><span class="sxs-lookup"><span data-stu-id="cb073-131">There are some limitations to consider:</span></span>

- <span data-ttu-id="cb073-132">系統會提供英文版隱藏式輔助字幕和記錄。</span><span class="sxs-lookup"><span data-stu-id="cb073-132">There will be English-only closed captions and transcripts.</span></span>
- <span data-ttu-id="cb073-133">您將無法搜尋 [腳本] 或其內容。</span><span class="sxs-lookup"><span data-stu-id="cb073-133">You won't be able to search transcripts or their content.</span></span>
- <span data-ttu-id="cb073-134">您無法編輯這些記錄，但您可以開啟/關閉 [標題]。</span><span class="sxs-lookup"><span data-stu-id="cb073-134">You won’t be able to edit the transcripts, but you'll be able to toggle captions off/on.</span></span>
- <span data-ttu-id="cb073-135">您可以控制您共用錄製的物件，但無法封鎖有共用存取權的人員下載錄製。</span><span class="sxs-lookup"><span data-stu-id="cb073-135">You can control with whom you share the recording, but you won't be able to block people with shared access from downloading the recording.</span></span>
- <span data-ttu-id="cb073-136">錄製完成後，您將不會收到電子郵件，但錄製會在會議完成後出現在會議聊天中。</span><span class="sxs-lookup"><span data-stu-id="cb073-136">You'll not get an email when the recording finishes saving, but the recording will appear in the meeting chat once it’s finished.</span></span> <span data-ttu-id="cb073-137">這將會比先前在資料流程中的速度更快</span><span class="sxs-lookup"><span data-stu-id="cb073-137">This will happen much quicker than it did in Stream previously</span></span>

<span data-ttu-id="cb073-138">如需詳細資訊，請觀看「會議錄製」。</span><span class="sxs-lookup"><span data-stu-id="cb073-138">Watch "Meeting Recording" for more information.</span></span>

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a><span data-ttu-id="cb073-139">設定商務用 OneDrive 和 SharePoint 的會議錄製選項</span><span class="sxs-lookup"><span data-stu-id="cb073-139">Set up the meeting recording option for OneDrive for Business and SharePoint</span></span>

1. <span data-ttu-id="cb073-140">安裝商務用 Skype Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="cb073-140">Install Skype For Business Online PowerShell.</span></span> 
<span data-ttu-id="cb073-141">**注意**：商務用 Skype Online 連接器目前是最新團隊 PowerShell 模組的一部分。</span><span class="sxs-lookup"><span data-stu-id="cb073-141">**Note**: Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="cb073-142">如果您使用的是最新的團隊 PowerShell 公開發行，就不需要安裝商務用 Skype Online 連接器。</span><span class="sxs-lookup"><span data-stu-id="cb073-142">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span> <span data-ttu-id="cb073-143">請參閱 [使用 PowerShell 管理商務用 Skype Online](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true)。</span><span class="sxs-lookup"><span data-stu-id="cb073-143">See [Manage Skype for Business Online with PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true).</span></span>

    <span data-ttu-id="cb073-144">a.</span><span class="sxs-lookup"><span data-stu-id="cb073-144">a.</span></span> <span data-ttu-id="cb073-145">下載 [商務用 Skype Online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true)。</span><span class="sxs-lookup"><span data-stu-id="cb073-145">Download [Skype for Business Online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true).</span></span> 

    <span data-ttu-id="cb073-146">b.</span><span class="sxs-lookup"><span data-stu-id="cb073-146">b.</span></span> <span data-ttu-id="cb073-147">依照提示進行安裝。</span><span class="sxs-lookup"><span data-stu-id="cb073-147">Follow the prompts to install it.</span></span>

    <span data-ttu-id="cb073-148">c-clip.</span><span class="sxs-lookup"><span data-stu-id="cb073-148">c.</span></span> <span data-ttu-id="cb073-149">重新開機您的電腦。</span><span class="sxs-lookup"><span data-stu-id="cb073-149">Restart your machine.</span></span>

2. <span data-ttu-id="cb073-150">以系統管理員身分啟動 PowerShell</span><span class="sxs-lookup"><span data-stu-id="cb073-150">Launch PowerShell as an admin</span></span>

3. <span data-ttu-id="cb073-151">匯入 SkypeOnline 連接器，然後以團隊管理員身分登入。</span><span class="sxs-lookup"><span data-stu-id="cb073-151">Import the SkypeOnline Connector and log in as a Teams admin.</span></span>

   ```powershell
   Import-Module SkypeOnlineConnector
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

4. <span data-ttu-id="cb073-152">使用 [ [設定 csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps&preserve-view=true) ] 將 [團隊會議原則] 設定為從資料流程儲存轉換為商務用 OneDrive 和 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="cb073-152">Use [set-csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps&preserve-view=true) to set a Teams Meeting Policy to transition from the Stream storage to OneDrive for Business and SharePoint.</span></span>

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a><span data-ttu-id="cb073-153">退出商務用 OneDrive 和 SharePoint 以繼續使用資料流程</span><span class="sxs-lookup"><span data-stu-id="cb073-153">Opt out of OneDrive for Business and SharePoint to continue using Stream</span></span>

<span data-ttu-id="cb073-154">即使原則將它設定為 [ **資料流程**]，也可能不會設定。</span><span class="sxs-lookup"><span data-stu-id="cb073-154">Even if a policy says it's set to **Stream**, it might not be set.</span></span> <span data-ttu-id="cb073-155">通常，如果原則沒有設定，則預設設定為 [ **資料流程**]。</span><span class="sxs-lookup"><span data-stu-id="cb073-155">Typically, if the policy isn't set, then the default setting is **Stream**.</span></span> <span data-ttu-id="cb073-156">不過，如果您想要選擇不使用 SharePoint 或 OneDrive，請使用這項新的變更，您必須將原則重設為 **串流** ，以確保它是預設值。</span><span class="sxs-lookup"><span data-stu-id="cb073-156">However, with this new change, if you want to opt-out of using SharePoint or OneDrive, then you must reset the policy to **Stream** to ensure that it's the default.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="permissions-or-role-based-access"></a><span data-ttu-id="cb073-157">許可權或以角色為基礎的存取權</span><span class="sxs-lookup"><span data-stu-id="cb073-157">Permissions or role-based access</span></span>


|<span data-ttu-id="cb073-158">會議類型</span><span class="sxs-lookup"><span data-stu-id="cb073-158">Meeting type</span></span>                               | <span data-ttu-id="cb073-159">按一下 [記錄] 的人員</span><span class="sxs-lookup"><span data-stu-id="cb073-159">Who clicked on Record?</span></span>| <span data-ttu-id="cb073-160">錄製的土地在哪裡？</span><span class="sxs-lookup"><span data-stu-id="cb073-160">Where does the recording land?</span></span>                               |<span data-ttu-id="cb073-161">誰有存取權？</span><span class="sxs-lookup"><span data-stu-id="cb073-161">Who has access?</span></span> <span data-ttu-id="cb073-162">R/W、R 或共用</span><span class="sxs-lookup"><span data-stu-id="cb073-162">R/W, R or sharing</span></span>                                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|<span data-ttu-id="cb073-163">與內部合作夥伴的1:1 通話</span><span class="sxs-lookup"><span data-stu-id="cb073-163">1:1 call with internal parties</span></span>             |<span data-ttu-id="cb073-164">呼叫</span><span class="sxs-lookup"><span data-stu-id="cb073-164">Caller</span></span>                 |<span data-ttu-id="cb073-165">來電者的商務用 OneDrive 帳戶</span><span class="sxs-lookup"><span data-stu-id="cb073-165">Caller’s OneDrive for Business account</span></span>                        |<span data-ttu-id="cb073-166">-來電者為擁有者，擁有完全許可權被叫方 (if) 具有唯讀存取權，但如果在不同的租使用者中) 沒有存取權，就不會有共用存取被叫用的 (。</span><span class="sxs-lookup"><span data-stu-id="cb073-166">- Caller is owner, has full rights  - Callee (if in the same tenant) has read only access, no sharing access -  Callee (if in different tenant) has no access.</span></span> <span data-ttu-id="cb073-167">來電者必須將它共用給被叫方</span><span class="sxs-lookup"><span data-stu-id="cb073-167">Caller must share it to the Callee</span></span>|
|<span data-ttu-id="cb073-168">與內部合作夥伴的1:1 通話</span><span class="sxs-lookup"><span data-stu-id="cb073-168">1:1 call with internal parties</span></span>             |<span data-ttu-id="cb073-169">方</span><span class="sxs-lookup"><span data-stu-id="cb073-169">Callee</span></span>                 |<span data-ttu-id="cb073-170">被呼叫者的商務用 OneDrive 帳戶</span><span class="sxs-lookup"><span data-stu-id="cb073-170">Callee’s OneDrive for Business account</span></span>                        |<span data-ttu-id="cb073-171">被叫人為擁有者、擁有完全許可權的呼叫者 (如果在同一個租使用者中有唯讀存取權，則在不同的租使用者中，就不會 (共用存取-呼叫者) 沒有存取權。</span><span class="sxs-lookup"><span data-stu-id="cb073-171">- Callee is owner, has full rights - Caller (if in the same tenant has read only access, no sharing access - Caller (if in different tenant) has no access.</span></span> <span data-ttu-id="cb073-172">被呼叫方必須將它共用給被呼叫者</span><span class="sxs-lookup"><span data-stu-id="cb073-172">Callee must share it to the Callee</span></span>|
|<span data-ttu-id="cb073-173">使用外部通話的1:1 通話</span><span class="sxs-lookup"><span data-stu-id="cb073-173">1:1 call with an external call</span></span>             |<span data-ttu-id="cb073-174">呼叫</span><span class="sxs-lookup"><span data-stu-id="cb073-174">Caller</span></span>                 |<span data-ttu-id="cb073-175">來電者的商務用 OneDrive 帳戶</span><span class="sxs-lookup"><span data-stu-id="cb073-175">Caller’s OneDrive for Business account</span></span>                        |<span data-ttu-id="cb073-176">-呼叫者為擁有者，擁有完全許可權被叫方沒有存取權。</span><span class="sxs-lookup"><span data-stu-id="cb073-176">- Caller is owner, has full rights - Callee has no access.</span></span> <span data-ttu-id="cb073-177">來電者必須將它共用給被叫方</span><span class="sxs-lookup"><span data-stu-id="cb073-177">Caller must share it to the Callee</span></span>|
|<span data-ttu-id="cb073-178">使用外部通話的1:1 通話</span><span class="sxs-lookup"><span data-stu-id="cb073-178">1:1 call with an external call</span></span>             |<span data-ttu-id="cb073-179">方</span><span class="sxs-lookup"><span data-stu-id="cb073-179">Callee</span></span>                 |<span data-ttu-id="cb073-180">來電者的商務用 OneDrive 帳戶</span><span class="sxs-lookup"><span data-stu-id="cb073-180">Caller’s OneDrive for Business account</span></span>                        |<span data-ttu-id="cb073-181">被叫方為擁有者，擁有完整許可權-來電者沒有存取權。</span><span class="sxs-lookup"><span data-stu-id="cb073-181">- Callee is owner, has full rights - Caller has no access.</span></span> <span data-ttu-id="cb073-182">被叫方必須將它共用給來電者</span><span class="sxs-lookup"><span data-stu-id="cb073-182">Callee must share it to the Caller</span></span>|
|<span data-ttu-id="cb073-183">群組通話</span><span class="sxs-lookup"><span data-stu-id="cb073-183">Group call</span></span>                                 |<span data-ttu-id="cb073-184">通話的任何成員</span><span class="sxs-lookup"><span data-stu-id="cb073-184">Any member of the call</span></span> |<span data-ttu-id="cb073-185">按一下記錄的商務用 OneDrive 帳戶的成員</span><span class="sxs-lookup"><span data-stu-id="cb073-185">Member who clicked on Record’s OneDrive for Business account</span></span>  |<span data-ttu-id="cb073-186">-按一下記錄的成員具有完整的許可權-來自相同租使用者的其他成員都有讀取權限-來自不同租使用者的其他成員都沒有許可權。</span><span class="sxs-lookup"><span data-stu-id="cb073-186">- Member who clicked on Record has full rights - Other members from the same tenant have Read rights - Other members from different tenant have no rights to it.</span></span>|
|<span data-ttu-id="cb073-187">即席/排程會議</span><span class="sxs-lookup"><span data-stu-id="cb073-187">Adhoc/Scheduled meeting</span></span>                    |<span data-ttu-id="cb073-188">召集人</span><span class="sxs-lookup"><span data-stu-id="cb073-188">Organizer</span></span>              |<span data-ttu-id="cb073-189">召集人的商務用 OneDrive 帳戶</span><span class="sxs-lookup"><span data-stu-id="cb073-189">Organizer’s OneDrive for Business account</span></span>                     |<span data-ttu-id="cb073-190">-召集人擁有錄製的完整許可權，會議的所有其他成員都有讀取權限</span><span class="sxs-lookup"><span data-stu-id="cb073-190">- Organizer has full rights to the recording - All other members of the meeting have read access</span></span>|
|<span data-ttu-id="cb073-191">即席/排程會議</span><span class="sxs-lookup"><span data-stu-id="cb073-191">Adhoc/Scheduled meeting</span></span>                    |<span data-ttu-id="cb073-192">其他會議成員</span><span class="sxs-lookup"><span data-stu-id="cb073-192">Other meeting member</span></span>   |<span data-ttu-id="cb073-193">按一下 [記錄] 的成員</span><span class="sxs-lookup"><span data-stu-id="cb073-193">Member who clicked on Record</span></span>                                  |<span data-ttu-id="cb073-194">-按一下記錄的成員對錄製有完整的許可權，且可以共用-所有其他成員都有讀取權限</span><span class="sxs-lookup"><span data-stu-id="cb073-194">- Member who clicked on Record has full rights to the recording - Organizer has edit rights and can share - All other members have read access</span></span>|
|<span data-ttu-id="cb073-195">與外部使用者進行即席/排程的會議</span><span class="sxs-lookup"><span data-stu-id="cb073-195">Adhoc/Scheduled meeting with external users</span></span>|<span data-ttu-id="cb073-196">召集人</span><span class="sxs-lookup"><span data-stu-id="cb073-196">Organizer</span></span>              |<span data-ttu-id="cb073-197">召集人的商務用 OneDrive 帳戶</span><span class="sxs-lookup"><span data-stu-id="cb073-197">Organizer’s OneDrive for Business account</span></span>                     |<span data-ttu-id="cb073-198">-召集人對錄製有完整的許可權，與召集人相同的租使用者中的所有其他成員都有讀取存取權，且召集人必須將其共用給他們</span><span class="sxs-lookup"><span data-stu-id="cb073-198">- Organizer has full rights to the recording - All other members of the meeting from the same tenant as the organizer have read access - All other external members have no access and the Organizer must share it to them</span></span>|
|<span data-ttu-id="cb073-199">與外部使用者進行即席/排程的會議</span><span class="sxs-lookup"><span data-stu-id="cb073-199">Adhoc/Scheduled meeting with external users</span></span>|<span data-ttu-id="cb073-200">其他會議成員</span><span class="sxs-lookup"><span data-stu-id="cb073-200">Other meeting member</span></span>   |<span data-ttu-id="cb073-201">按一下 [記錄] 的成員</span><span class="sxs-lookup"><span data-stu-id="cb073-201">Member who clicked on Record</span></span>                                  |<span data-ttu-id="cb073-202">-按一下 [記錄] 的成員對錄製擁有完整的許可權，且可以與召集人相同的租使用者擁有 [讀取存取權]，而且所有其他外部成員都無法存取，且召集人必須將其共用給他們</span><span class="sxs-lookup"><span data-stu-id="cb073-202">- Member who clicked on Record has full rights to the recording - Organizer has edit rights and can share - All other members of the meeting from the same tenant as the organizer have read access - All other external members have no access and the Organizer must share it to them</span></span>|
|<span data-ttu-id="cb073-203">頻道會議</span><span class="sxs-lookup"><span data-stu-id="cb073-203">Channel meeting</span></span>                            |<span data-ttu-id="cb073-204">頻道成員</span><span class="sxs-lookup"><span data-stu-id="cb073-204">Channel Member</span></span>         |<span data-ttu-id="cb073-205">團隊在該頻道中的 SharePoint 位置</span><span class="sxs-lookup"><span data-stu-id="cb073-205">Teams' SharePoint location for that channel</span></span>                   |<span data-ttu-id="cb073-206">-按一下記錄的成員擁有錄製的編輯許可權，而其他成員的許可權都是以頻道 SharePoint 許可權為基礎。</span><span class="sxs-lookup"><span data-stu-id="cb073-206">- Member who clicked on Record has edit rights to the recording  - Every other member’s permissions are based off of the Channel SharePoint permissions</span></span>|


## <a name="frequently-asked-questions"></a><span data-ttu-id="cb073-207">常見問題集</span><span class="sxs-lookup"><span data-stu-id="cb073-207">Frequently asked questions</span></span>

<span data-ttu-id="cb073-208">**會議錄製將儲存在哪裡？**</span><span class="sxs-lookup"><span data-stu-id="cb073-208">**Where will the meeting recording be stored?**</span></span>

- <span data-ttu-id="cb073-209">對於非頻道會議，錄製會儲存在屬於開始會議錄製之**Recordings**人員之商務用 OneDrive 的最上層的資料夾中。</span><span class="sxs-lookup"><span data-stu-id="cb073-209">For non-Channel meetings, the recording is stored in a folder named **Recordings** that is at the top level of the OneDrive for Business that belongs to the person who started the meeting recording.</span></span> <span data-ttu-id="cb073-210">範例</span><span class="sxs-lookup"><span data-stu-id="cb073-210">Example:</span></span>

  <span data-ttu-id="cb073-211"><i>錄影機的商務</i> / 用 OneDrive**錄製**</span><span class="sxs-lookup"><span data-stu-id="cb073-211"><i>recorder's OneDrive for Business</i>/**Recordings**</span></span>

- <span data-ttu-id="cb073-212">對於頻道會議，錄製會儲存在名為 [ **錄製**] 資料夾的 [小組網站] 文件庫中。</span><span class="sxs-lookup"><span data-stu-id="cb073-212">For Channel meetings, the recording is stored in the Teams site documentation library in a folder named **Recordings**.</span></span> <span data-ttu-id="cb073-213">範例</span><span class="sxs-lookup"><span data-stu-id="cb073-213">Example:</span></span>

  <span data-ttu-id="cb073-214"><i>團隊名稱-頻道名稱</i> /**檔** /**錄製**</span><span class="sxs-lookup"><span data-stu-id="cb073-214"><i>Teams name - Channel name</i>/**Documents**/**Recordings**</span></span>

<span data-ttu-id="cb073-215">**我要如何處理來自離職員工的錄製？**</span><span class="sxs-lookup"><span data-stu-id="cb073-215">**How do I handle recordings from former employees?**</span></span>

<span data-ttu-id="cb073-216">因為影片與商務用 OneDrive 和 SharePoint 中的任何其他檔案一樣，所以在員工離職之後，處理擁有權及保留期將遵循正常的 [商務用 OneDrive 和 SharePoint 程式]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process)。</span><span class="sxs-lookup"><span data-stu-id="cb073-216">Since videos are just like any other file in OneDrive for Business and SharePoint, handling ownership and retention after an employee leaves will follow the normal [OneDrive for Business and SharePoint process]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process).</span></span>

<span data-ttu-id="cb073-217">**誰有權查看會議錄製？**</span><span class="sxs-lookup"><span data-stu-id="cb073-217">**Who has the permissions to view the meeting recording?**</span></span>

- <span data-ttu-id="cb073-218">如果是非頻道會議，除了外部使用者以外的所有會議受邀者，都將自動取得個人共用的連結。</span><span class="sxs-lookup"><span data-stu-id="cb073-218">For non-Channel meetings, all meeting invitees, except for external users, will automatically get a personally shared link.</span></span> <span data-ttu-id="cb073-219">外部使用者必須透過會議召集人或開始會議錄製的人員，將其明確新增至共用清單中。</span><span class="sxs-lookup"><span data-stu-id="cb073-219">External users will need to be explicitly added to the shared list by the meeting organizer or the person who started the meeting recording.</span></span>

- <span data-ttu-id="cb073-220">對於頻道會議，許可權是從頻道中的 [擁有人] 和 [成員] 清單繼承而來。</span><span class="sxs-lookup"><span data-stu-id="cb073-220">For Channel meetings, permissions are inherited from the owners and members list in the channel.</span></span>

<span data-ttu-id="cb073-221">**我要如何管理腳本？**</span><span class="sxs-lookup"><span data-stu-id="cb073-221">**How can I manage transcripts?**</span></span>

<span data-ttu-id="cb073-222">如果客戶加入宣告此預覽，小組會議錄製將不會提供隱藏式輔助字幕，且已遷移至商務用 OneDrive 和 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="cb073-222">Customers opting in to this preview will not have closed captions available on their Teams Meeting Recordings that are migrated to OneDrive for Business and SharePoint.</span></span><span data-ttu-id="cb073-223">我們正致力於將隱藏式輔助字幕從英文新增至2020年10月的會議錄製。</span><span class="sxs-lookup"><span data-stu-id="cb073-223">  We're working to add captioning, beginning with closed captions in English, to meeting recordings in October 2020.</span></span>

<span data-ttu-id="cb073-224">小組會議錄製會提供隱藏式輔助字幕，供已自願加入在[小組雲端錄製](cloud-recording.md)中描述的客戶使用。</span><span class="sxs-lookup"><span data-stu-id="cb073-224">Closed captions will be available on Teams Meeting Recordings for customers who have opted in to allow transcripts as described in [Teams cloud recordings](cloud-recording.md)</span></span>

<span data-ttu-id="cb073-225">[標題] 可協助為所有功能的檢視器建立包含內容。</span><span class="sxs-lookup"><span data-stu-id="cb073-225">Captions help create inclusive content for viewers of all abilities.</span></span> <span data-ttu-id="cb073-226">在擁有者中，您可以隱藏標題，但除非您刪除小組中的標題，否則仍可在團隊中使用這些記錄。</span><span class="sxs-lookup"><span data-stu-id="cb073-226">As an owner, you can hide captions, although the transcript will still be available on Teams unless you delete the captions from Teams.</span></span> <span data-ttu-id="cb073-227">瞭解 [如何開啟或關閉會議錄製](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)</span><span class="sxs-lookup"><span data-stu-id="cb073-227">See [how to turn on or off meeting recordings](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)</span></span>

<span data-ttu-id="cb073-228">錄製會議時，小組會議錄製支援的60天是隱藏式輔助字幕。</span><span class="sxs-lookup"><span data-stu-id="cb073-228">Closed captions are supported for Teams meeting recordings for 60 days from when the meeting is recorded.</span></span>

<span data-ttu-id="cb073-229">如果將小組會議錄製從其在 OneDrive 或 SharePoint 上的原始位置移動或複製，就不會完全支援隱藏式輔助字幕。</span><span class="sxs-lookup"><span data-stu-id="cb073-229">Closed captions are not fully supported if the Teams Meeting Recording is moved or copied from its original location on OneDrive or SharePoint.</span></span>

<span data-ttu-id="cb073-230">**我的儲存空間配額受影響的方式**</span><span class="sxs-lookup"><span data-stu-id="cb073-230">**How will my storage quota be impacted**</span></span>

<span data-ttu-id="cb073-231">小組會議會在商務用 OneDrive 和 SharePoint 中即時錄製檔案，並包含在這些服務的配額中。</span><span class="sxs-lookup"><span data-stu-id="cb073-231">Teams meeting recording files live in OneDrive for Business and SharePoint and are included in your quota for those services.</span></span> <span data-ttu-id="cb073-232">請參閱 [SharePoint 配額](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) 和 [商務用 OneDrive 配額] (https://docs.microsoft.com/onedrive/set-default-storage-space) 。</span><span class="sxs-lookup"><span data-stu-id="cb073-232">See [SharePoint quota](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) and [OneDrive for Business quota] (https://docs.microsoft.com/onedrive/set-default-storage-space).</span></span>

<span data-ttu-id="cb073-233">**如何播放團隊會議錄製？**</span><span class="sxs-lookup"><span data-stu-id="cb073-233">**How can I play a Teams meeting recording?**</span></span>

<span data-ttu-id="cb073-234">您的影片將會在商務用 OneDrive 或 SharePoint 的影片播放機上播放，視您存取該檔案的位置而定。</span><span class="sxs-lookup"><span data-stu-id="cb073-234">Your video will play on the video player of OneDrive for Business or SharePoint depending on where you access the file.</span></span>

<span data-ttu-id="cb073-235">**如果您打算 deprecating 新增至串流，現有的影片會持續保持不變嗎？**</span><span class="sxs-lookup"><span data-stu-id="cb073-235">**If you plan on deprecating adding to Stream, will existing videos stay as is and for how long?**</span></span>

<span data-ttu-id="cb073-236">在不久的將來，不會棄用作為平臺的資料流程。</span><span class="sxs-lookup"><span data-stu-id="cb073-236">Stream as a platform won't be deprecated in the near future.</span></span> <span data-ttu-id="cb073-237">目前在資料流程中的影片會一直留在這裡，直到我們開始進行遷移為止。</span><span class="sxs-lookup"><span data-stu-id="cb073-237">The videos that currently live in Stream will stay there until we start migrating.</span></span> <span data-ttu-id="cb073-238">遷移時，這些影片也會同時遷移至 ODSP。</span><span class="sxs-lookup"><span data-stu-id="cb073-238">Upon migration, those videos will be migrated to ODSP as well.</span></span> <span data-ttu-id="cb073-239">若要瞭解詳細資訊，請參閱 [這裡](https://docs.microsoft.com/stream/streamnew/classic-migration) 。</span><span class="sxs-lookup"><span data-stu-id="cb073-239">Check [here](https://docs.microsoft.com/stream/streamnew/classic-migration) for more information.</span></span>
