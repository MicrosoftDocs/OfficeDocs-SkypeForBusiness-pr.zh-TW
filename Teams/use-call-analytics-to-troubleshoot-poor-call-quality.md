---
title: 使用通話分析來疑難排解不良通話品質
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 03/08/2019
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
- Reporting
description: 使用裝置、網路和連線的呼叫分析詳細資料，來針對 Microsoft 團隊及商務用 Skype 通話和會議的使用者問題進行疑難排解。
ms.openlocfilehash: 71a1e1c339c502da5cbbf998c75e758f2bbe3be2
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2020
ms.locfileid: "44665245"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a><span data-ttu-id="c3632-103">使用通話分析來疑難排解不良通話品質</span><span class="sxs-lookup"><span data-stu-id="c3632-103">Use Call Analytics to troubleshoot poor call quality</span></span>

<span data-ttu-id="c3632-104">[通話分析] 可協助您排查 Microsoft 團隊和商務用 Skype 的通話或連線問題。</span><span class="sxs-lookup"><span data-stu-id="c3632-104">Call Analytics helps you troubleshoot call or connection problems with Microsoft Teams and Skype for Business.</span></span> <span data-ttu-id="c3632-105">[通話分析] 會顯示適用于 Microsoft 365 或 Office 365 帳戶中每位使用者的通話與會議的詳細資訊，以及有關裝置、網路及連線的連線能力。</span><span class="sxs-lookup"><span data-stu-id="c3632-105">Call Analytics shows detailed information about the devices, networks, and connectivity for the calls and meetings of each user in your Microsoft 365 or Office 365 account.</span></span> <span data-ttu-id="c3632-106">如果已將組建、網站和租使用者資訊新增至呼叫分析，也會針對每個通話和會話顯示該資訊。</span><span class="sxs-lookup"><span data-stu-id="c3632-106">If building, site, and tenant information has been added to Call Analytics, it will also be shown for each call and session.</span></span> <span data-ttu-id="c3632-107">透過 [呼叫分析] 提供的資訊可協助您瞭解使用者為何通話或會議感覺不佳的原因。</span><span class="sxs-lookup"><span data-stu-id="c3632-107">Information available via Call Analytics can help you figure out why a user had a poor call or meeting experience.</span></span> 
  
## <a name="call-analytics-permissions"></a><span data-ttu-id="c3632-108">呼叫分析許可權</span><span class="sxs-lookup"><span data-stu-id="c3632-108">Call Analytics permissions</span></span>

<span data-ttu-id="c3632-109">就像管理員一樣，您就能完全存取通話分析的所有功能。</span><span class="sxs-lookup"><span data-stu-id="c3632-109">As the admin, you get full access to all the features of Call Analytics.</span></span> <span data-ttu-id="c3632-110">此外，您也可以將 Azure Active Directory 角色指派給支援人員。</span><span class="sxs-lookup"><span data-stu-id="c3632-110">In addition, you can assign Azure Active Directory roles to support staff.</span></span> <span data-ttu-id="c3632-111">將團隊通訊支援專家角色指派給應該擁有有限的通話分析視圖的使用者。</span><span class="sxs-lookup"><span data-stu-id="c3632-111">Assign the Teams communications support specialist role to users who should have a limited view of Call Analytics.</span></span> <span data-ttu-id="c3632-112">指派團隊通訊支援工程師角色給需要存取呼叫分析完整功能的使用者。</span><span class="sxs-lookup"><span data-stu-id="c3632-112">Assign the Teams communications support engineer role to users who need access to the full functionality of Call Analytics.</span></span> <span data-ttu-id="c3632-113">兩個許可權等級都無法存取 Microsoft 團隊系統管理中心的其他部分。</span><span class="sxs-lookup"><span data-stu-id="c3632-113">Both permission levels prevent access to the rest of the Microsoft Teams admin center.</span></span>

<span data-ttu-id="c3632-114">通訊支援專家處理基本的通話品質問題。</span><span class="sxs-lookup"><span data-stu-id="c3632-114">Communications support specialists handle basic call-quality problems.</span></span> <span data-ttu-id="c3632-115">他們不會調查會議的問題。</span><span class="sxs-lookup"><span data-stu-id="c3632-115">They don't investigate issues with meetings.</span></span> <span data-ttu-id="c3632-116">相反地，他們會收集相關資訊，然後升級至通訊支援工程師。</span><span class="sxs-lookup"><span data-stu-id="c3632-116">Instead, they collect related information and then escalate to a communications support engineer.</span></span> <span data-ttu-id="c3632-117">通訊支援工程師請參閱與通訊支援專家隱藏的詳細通話記錄中的資訊。</span><span class="sxs-lookup"><span data-stu-id="c3632-117">Communications support engineers see information in detailed call logs that's hidden from communications support specialists.</span></span> <span data-ttu-id="c3632-118">下表提供通訊支援專家與通訊支援工程師在使用呼叫分析時所提供資訊的概覽。</span><span class="sxs-lookup"><span data-stu-id="c3632-118">The following table gives an overview of information available to communications support specialists and communications support engineers when they use Call Analytics.</span></span>

<span data-ttu-id="c3632-119">指派給您的許可權等級決定了在通話分析中您有權存取哪些類型的資訊：</span><span class="sxs-lookup"><span data-stu-id="c3632-119">The permissions level assigned to you determines what type of information you have access to in Call Analytics:</span></span>
  
- <span data-ttu-id="c3632-120">**團隊服務管理員或團隊溝通系統管理員**：您可以存取通話分析及 Microsoft 團隊管理中心中的所有資訊。</span><span class="sxs-lookup"><span data-stu-id="c3632-120">**Teams service administrator or Teams communications administrator**: You have access to all the information in Call Analytics and in the Microsoft Teams admin center.</span></span>
    
- <span data-ttu-id="c3632-121">**團隊溝通支援專家**：您會在 [呼叫分析] 中看到一組有限的資料。</span><span class="sxs-lookup"><span data-stu-id="c3632-121">**Teams communications support specialist**: You see a limited set of data in Call Analytics.</span></span> <span data-ttu-id="c3632-122">您可以對通話進行疑難排解，但您會將會議問題移交給小組通訊支援工程師。</span><span class="sxs-lookup"><span data-stu-id="c3632-122">You can troubleshoot calls, but you'll hand off problems with meetings to a Teams communications support engineer.</span></span> <span data-ttu-id="c3632-123">您無法存取其他 Microsoft 團隊系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="c3632-123">You don't have access to the rest of the Microsoft Teams admin center.</span></span>
    
- <span data-ttu-id="c3632-124">**團隊溝通支援工程師**：您可以在通話分析中查看所有可用的資料，並協助疑難排解通話與會議的問題。</span><span class="sxs-lookup"><span data-stu-id="c3632-124">**Teams communications support engineer**: You see all available data in Call Analytics and can help troubleshoot problems with both calls and meetings.</span></span> <span data-ttu-id="c3632-125">您無法存取其他 Microsoft 團隊系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="c3632-125">You don't have access to the rest of the Microsoft Teams admin center.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c3632-126">通訊支援專家角色相當於第1層支援，且溝通支援工程師角色相當於第2層支援。</span><span class="sxs-lookup"><span data-stu-id="c3632-126">The communications support specialist role is equivalent to tier 1 support and the communications support engineer role is equivalent to tier 2 support.</span></span>

<span data-ttu-id="c3632-127">如需有關團隊管理員角色的詳細資訊，請參閱[使用 Microsoft 團隊管理員角色管理團隊](using-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="c3632-127">For more information about Teams admin roles, see [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md).</span></span> <span data-ttu-id="c3632-128">如需團隊溝通支援專家與團隊溝通支援工程師角色的詳細比較，請參閱[設定呼叫分析](set-up-call-analytics.md#set-call-analytics-permissions)</span><span class="sxs-lookup"><span data-stu-id="c3632-128">For a detailed comparison of the Teams communications support specialist and Teams communications support engineer roles, see [Set up Call Analytics](set-up-call-analytics.md#set-call-analytics-permissions)</span></span> 
  
<span data-ttu-id="c3632-129">如果您需要許可權的協助，請參閱您的小組和商務用 Skype 系統管理員。</span><span class="sxs-lookup"><span data-stu-id="c3632-129">See your Teams and Skype for Business admin if you need help with permissions.</span></span>
  
## <a name="troubleshoot-call-quality-problems-using-call-analytics"></a><span data-ttu-id="c3632-130">使用通話分析進行通話品質問題的疑難排解</span><span class="sxs-lookup"><span data-stu-id="c3632-130">Troubleshoot call quality problems using Call Analytics</span></span>

1. <span data-ttu-id="c3632-131">使用您的小組通訊支援或團隊管理員認證登入。</span><span class="sxs-lookup"><span data-stu-id="c3632-131">Sign in with your Teams communications support or Teams admin credentials.</span></span>

2. <span data-ttu-id="c3632-132">在您的網頁瀏覽器中，移至 *https://admin.teams.microsoft.com* 。</span><span class="sxs-lookup"><span data-stu-id="c3632-132">In your web browser go to *https://admin.teams.microsoft.com*.</span></span>
    
3. <span data-ttu-id="c3632-133">在**儀表板**上的 [**使用者搜尋**] 中，開始輸入您要排除其來電之使用者的名稱或 sip 位址，或選取 [**查看使用者**] 來查看使用者清單。</span><span class="sxs-lookup"><span data-stu-id="c3632-133">On the **Dashboard**, in **User Search**, start typing either the name or sip address of the user whose calls you want to troubleshoot or select **View users** to see a list of users.</span></span>
    
    ![[通話分析] 使用者搜尋方塊的螢幕擷取畫面](media/use-call-analytics-to-troubleshoot-image-1.png)
  
4. <span data-ttu-id="c3632-135">從清單中選取使用者。</span><span class="sxs-lookup"><span data-stu-id="c3632-135">Select the user from the list.</span></span>

5. <span data-ttu-id="c3632-136">選取 [**通話記錄**]，然後選取您想要疑難排解的通話或會議。</span><span class="sxs-lookup"><span data-stu-id="c3632-136">Select **Call history**, and then select the call or meeting that you want to troubleshoot.</span></span>  <span data-ttu-id="c3632-137">最多可傳回500筆記錄。</span><span class="sxs-lookup"><span data-stu-id="c3632-137">A maximum of 500 records will be returned.</span></span>
    
    ![使用者 [通話記錄] 頁面的螢幕擷取畫面。](media/use-call-analytics-to-troubleshoot-image-2.png)
  
6. <span data-ttu-id="c3632-139">選取 [**高級**] 索引標籤，然後尋找黃色和紅色專案，指出通話品質或連線問題不佳。</span><span class="sxs-lookup"><span data-stu-id="c3632-139">Select the **Advanced** tab, and then look for yellow and red items which indicate poor call quality or connection problems.</span></span>
    
    <span data-ttu-id="c3632-140">在每個通話或會議的 [會話詳細資料] 中，次要問題會以黃色顯示。</span><span class="sxs-lookup"><span data-stu-id="c3632-140">In the session details for each call or meeting, minor issues appear in yellow.</span></span> <span data-ttu-id="c3632-141">（例如，在下列螢幕擷取畫面中，對於平均抖動、最大抖動及平均資料包遺失率而言，這些值都是黃色。）如果有黃色，則它不在正常範圍之內，可能會造成問題，但不太可能是問題的主要原因。</span><span class="sxs-lookup"><span data-stu-id="c3632-141">(For example, in the following screenshot, the values are in yellow for Average jitter, Max jitter, and Average packet loss rate.) If something is yellow, it's outside of normal range, and it may be contributing to the problem, but it's unlikely to be the main cause of the problem.</span></span> <span data-ttu-id="c3632-142">如果有紅色，這是一個很重要的問題，這可能是這個會話的通話品質不佳的主要原因。</span><span class="sxs-lookup"><span data-stu-id="c3632-142">If something is red, it's a significant problem, and it's likely the main cause of the poor call quality for this session.</span></span> 
    
    ![<span data-ttu-id="c3632-143">使用者通話記錄的 [高級] 索引標籤的螢幕擷取畫面</span><span class="sxs-lookup"><span data-stu-id="c3632-143">Screenshot of the Advanced tab of a user's Call history</span></span> ](media/use-call-analytics-to-troubleshoot-image-3.png)
  
<span data-ttu-id="c3632-144">在少數情況下，音訊會話的體驗資料品質不會收到。</span><span class="sxs-lookup"><span data-stu-id="c3632-144">In rare cases, quality of experience data isn't received for audio sessions.</span></span> <span data-ttu-id="c3632-145">這通常是由呼叫斷開並與用戶端端接所造成。</span><span class="sxs-lookup"><span data-stu-id="c3632-145">Often this is caused by the call dropping and connection with the client terminating.</span></span> <span data-ttu-id="c3632-146">發生這種情況時，**無法使用**[會議評等]。</span><span class="sxs-lookup"><span data-stu-id="c3632-146">When this occurs, the session rating is **unavailable**.</span></span>
  
<span data-ttu-id="c3632-147">對於有經驗品質（QoE）資料的音訊會話，下表說明將會話限制為**不良**的主要問題。</span><span class="sxs-lookup"><span data-stu-id="c3632-147">For audio sessions that do have quality of experience (QoE) data, the following table describes major issues that qualify a session as **poor**.</span></span>
  
|<span data-ttu-id="c3632-148">**問題**</span><span class="sxs-lookup"><span data-stu-id="c3632-148">**Issue**</span></span>|<span data-ttu-id="c3632-149">**圖**</span><span class="sxs-lookup"><span data-stu-id="c3632-149">**Area**</span></span>|<span data-ttu-id="c3632-150">**描述**</span><span class="sxs-lookup"><span data-stu-id="c3632-150">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c3632-151">撥號設定</span><span class="sxs-lookup"><span data-stu-id="c3632-151">Call setup</span></span>  <br/> |<span data-ttu-id="c3632-152">工作階段</span><span class="sxs-lookup"><span data-stu-id="c3632-152">Session</span></span>  <br/> |<span data-ttu-id="c3632-153">錯誤碼 Ms-診斷程式20-29 指出通話設定失敗。</span><span class="sxs-lookup"><span data-stu-id="c3632-153">The error code Ms-diag 20-29 indicates the call setup failed.</span></span> <span data-ttu-id="c3632-154">使用者無法加入通話或會議。</span><span class="sxs-lookup"><span data-stu-id="c3632-154">The user couldn't join the call or meeting.</span></span>  <br/> |
|<span data-ttu-id="c3632-155">音訊網路分類不佳通話</span><span class="sxs-lookup"><span data-stu-id="c3632-155">Audio network classified poor call</span></span>  <br/> |<span data-ttu-id="c3632-156">工作階段</span><span class="sxs-lookup"><span data-stu-id="c3632-156">Session</span></span>  <br/> |<span data-ttu-id="c3632-157">遇到網路品質問題（例如資料包遺失、抖動、NMOS 下降、RTT 或隱藏比率）。</span><span class="sxs-lookup"><span data-stu-id="c3632-157">Network quality issues (such as packet loss, jitter, NMOS degradation, RTT, or concealed ratio) were encountered.</span></span> <span data-ttu-id="c3632-158">如需有關用來將不佳通話分類之條件的詳細資訊，請參閱這篇[Microsoft 博客文章](https://go.microsoft.com/fwlink/p/?linkid=852133)。</span><span class="sxs-lookup"><span data-stu-id="c3632-158">For more information about the conditions used to classify poor calls, see this [Microsoft blog post](https://go.microsoft.com/fwlink/p/?linkid=852133).</span></span>  <br/> |
|<span data-ttu-id="c3632-159">裝置無法運作</span><span class="sxs-lookup"><span data-stu-id="c3632-159">Device not functioning</span></span>  <br/> |<span data-ttu-id="c3632-160">裝置</span><span class="sxs-lookup"><span data-stu-id="c3632-160">Device</span></span>  <br/> | <span data-ttu-id="c3632-161">裝置無法正常運作。</span><span class="sxs-lookup"><span data-stu-id="c3632-161">A device isn't functioning correctly.</span></span> <span data-ttu-id="c3632-162">裝置的運作比例如下：</span><span class="sxs-lookup"><span data-stu-id="c3632-162">Device not functioning ratios are :</span></span> <br/>  <span data-ttu-id="c3632-163">DeviceRenderNotFunctioningEventRatio >= 0.005</span><span class="sxs-lookup"><span data-stu-id="c3632-163">DeviceRenderNotFunctioningEventRatio >= 0.005</span></span> <br/>  <span data-ttu-id="c3632-164">DeviceCaptureNotFunctioningEventRatio >= 0.005</span><span class="sxs-lookup"><span data-stu-id="c3632-164">DeviceCaptureNotFunctioningEventRatio >= 0.005</span></span> <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="c3632-165">相關主題</span><span class="sxs-lookup"><span data-stu-id="c3632-165">Related topics</span></span>
[<span data-ttu-id="c3632-166">設定通話分析</span><span class="sxs-lookup"><span data-stu-id="c3632-166">Set up Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="c3632-167">通話分析和通話品質儀表板</span><span class="sxs-lookup"><span data-stu-id="c3632-167">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
