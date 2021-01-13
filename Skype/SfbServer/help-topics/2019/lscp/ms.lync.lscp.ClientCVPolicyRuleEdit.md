---
title: 用戶端版本規則
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
ROBOTS: NOINDEX, NOFOLLOW
description: 用戶端版本原則是由一組用戶端版本規則所組成。當使用者嘗試以特定用戶端及用戶端版本登入時，這些規則會定義所要採取的動作。
ms.openlocfilehash: 26f37c77886ac9f9fe7fb8d8680fb0dad642a9cf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812373"
---
# <a name="client-version-rule"></a><span data-ttu-id="18bde-104">用戶端版本規則</span><span class="sxs-lookup"><span data-stu-id="18bde-104">Client Version Rule</span></span>

<span data-ttu-id="18bde-p102">用戶端版本原則是由一組用戶端版本規則所組成。當使用者嘗試以特定用戶端及用戶端版本登入時，這些規則會定義所要採取的動作。</span><span class="sxs-lookup"><span data-stu-id="18bde-p102">A client version policy is made up of a set of client version rules. These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="18bde-107">您可以執行的工作</span><span class="sxs-lookup"><span data-stu-id="18bde-107">Tasks you can perform</span></span>

<span data-ttu-id="18bde-108">您可以在「新增用戶端版本設定」或「編輯用戶端版本設定」頁面上執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="18bde-108">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>

- <span data-ttu-id="18bde-109">新增規則至用戶端版本原則。</span><span class="sxs-lookup"><span data-stu-id="18bde-109">Add new rules to a client version policy.</span></span>

- <span data-ttu-id="18bde-110">修改組成現有用戶端版本原則的規則</span><span class="sxs-lookup"><span data-stu-id="18bde-110">Modify the rules that make up an existing client version policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="18bde-111">UI 參考</span><span class="sxs-lookup"><span data-stu-id="18bde-111">UI Reference</span></span>

<span data-ttu-id="18bde-112">下列清單說明頁面上的功能表、命令、欄位及內容。
</span><span class="sxs-lookup"><span data-stu-id="18bde-112">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="18bde-113">**使用者代理程式** 您可以從清單中選取用戶端類型。</span><span class="sxs-lookup"><span data-stu-id="18bde-113">**User agent** You can select a client type from the list.</span></span> <span data-ttu-id="18bde-114">下表定義使用者代理程式碼。</span><span class="sxs-lookup"><span data-stu-id="18bde-114">The following table defines user agent codes.</span></span> <span data-ttu-id="18bde-115">此清單包含舊版用戶端類型，其中一些已不再支援。</span><span class="sxs-lookup"><span data-stu-id="18bde-115">This list includes legacy client types, some of which are no longer supported.</span></span>

|<span data-ttu-id="18bde-116">**用戶端名稱**</span><span class="sxs-lookup"><span data-stu-id="18bde-116">**Client Name**</span></span>|<span data-ttu-id="18bde-117">**使用者代理程式**</span><span class="sxs-lookup"><span data-stu-id="18bde-117">**User Agent**</span></span>|
|:-----|:-----|
|<span data-ttu-id="18bde-118">Lync 2013、Lync 2010、Office Communicator</span><span class="sxs-lookup"><span data-stu-id="18bde-118">Lync 2013, Lync 2010, Office Communicator</span></span>  <br/> |<span data-ttu-id="18bde-119">Oc</span><span class="sxs-lookup"><span data-stu-id="18bde-119">OC</span></span>  <br/> |
|<span data-ttu-id="18bde-120">Lync Web App、Communicator Web Access</span><span class="sxs-lookup"><span data-stu-id="18bde-120">Lync Web App, Communicator Web Access</span></span>  <br/> |<span data-ttu-id="18bde-121">NM-CWA-13-NO-VERSION</span><span class="sxs-lookup"><span data-stu-id="18bde-121">CWA</span></span>  <br/> |
|<span data-ttu-id="18bde-122">Lync Phone Edition、Office Communicator Phone</span><span class="sxs-lookup"><span data-stu-id="18bde-122">Lync Phone Edition, Office Communicator Phone</span></span>  <br/> |<span data-ttu-id="18bde-123">OCPhone</span><span class="sxs-lookup"><span data-stu-id="18bde-123">OCPhone</span></span>  <br/> |
|<span data-ttu-id="18bde-124">Communicator Phone Edition 平台</span><span class="sxs-lookup"><span data-stu-id="18bde-124">Communicator Phone Edition Platform</span></span>  <br/> |<span data-ttu-id="18bde-125">Cpe</span><span class="sxs-lookup"><span data-stu-id="18bde-125">CPE</span></span>  <br/> |
|<span data-ttu-id="18bde-126">Unified Communications 平台</span><span class="sxs-lookup"><span data-stu-id="18bde-126">Unified Communications Platform</span></span>  <br/> |<span data-ttu-id="18bde-127">UCCP</span><span class="sxs-lookup"><span data-stu-id="18bde-127">UCCP</span></span>  <br/> |
|<span data-ttu-id="18bde-128">Lync 2010 Attendee</span><span class="sxs-lookup"><span data-stu-id="18bde-128">Lync 2010 Attendee</span></span>  <br/> |<span data-ttu-id="18bde-129">Aoc</span><span class="sxs-lookup"><span data-stu-id="18bde-129">AOC</span></span>  <br/> |
|<span data-ttu-id="18bde-130">Live Meeting 增益集</span><span class="sxs-lookup"><span data-stu-id="18bde-130">Live Meeting Add-In</span></span>  <br/> |<span data-ttu-id="18bde-131">LiveMeetingAddins</span><span class="sxs-lookup"><span data-stu-id="18bde-131">LiveMeetingAddins</span></span>  <br/> |
|<span data-ttu-id="18bde-132">Office Live Meeting</span><span class="sxs-lookup"><span data-stu-id="18bde-132">Office Live Meeting</span></span>  <br/> |<span data-ttu-id="18bde-133">LMC</span><span class="sxs-lookup"><span data-stu-id="18bde-133">LMC</span></span>  <br/> |
|<span data-ttu-id="18bde-134">Windows Messenger</span><span class="sxs-lookup"><span data-stu-id="18bde-134">Windows Messenger</span></span>  <br/> |<span data-ttu-id="18bde-135">Wm</span><span class="sxs-lookup"><span data-stu-id="18bde-135">WM</span></span>  <br/> |
|<span data-ttu-id="18bde-136">即時通訊用戶端</span><span class="sxs-lookup"><span data-stu-id="18bde-136">Real-time Communications Client</span></span>  <br/> |<span data-ttu-id="18bde-137">Rtc</span><span class="sxs-lookup"><span data-stu-id="18bde-137">RTC</span></span>  <br/> |
|<span data-ttu-id="18bde-138">Lync 2010 for iPad</span><span class="sxs-lookup"><span data-stu-id="18bde-138">Lync 2010 for iPad</span></span>  <br/> |<span data-ttu-id="18bde-139">iPadLync</span><span class="sxs-lookup"><span data-stu-id="18bde-139">iPadLync</span></span>  <br/> |
|<span data-ttu-id="18bde-140">適用于 iPhone 的 Lync 2010</span><span class="sxs-lookup"><span data-stu-id="18bde-140">Lync 2010 for iPhone</span></span>  <br/> |<span data-ttu-id="18bde-141">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="18bde-141">iPhoneLync</span></span>  <br/> |
|<span data-ttu-id="18bde-142">適用于 Windows Phone 的 Lync 2010</span><span class="sxs-lookup"><span data-stu-id="18bde-142">Lync 2010 for Windows Phone</span></span>  <br/> |<span data-ttu-id="18bde-143">WPLync</span><span class="sxs-lookup"><span data-stu-id="18bde-143">WPLync</span></span>  <br/> |
|<span data-ttu-id="18bde-144">Lync 2010 for Nokia</span><span class="sxs-lookup"><span data-stu-id="18bde-144">Lync 2010 for Nokia</span></span>  <br/> |<span data-ttu-id="18bde-145">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="18bde-145">NokiaLync</span></span>  <br/> |
|<span data-ttu-id="18bde-146">適用于 Android 的 Lync 2010</span><span class="sxs-lookup"><span data-stu-id="18bde-146">Lync 2010 for Android</span></span>  <br/> |<span data-ttu-id="18bde-147">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="18bde-147">AndroidLync</span></span>  <br/> |
|<span data-ttu-id="18bde-148">行動性服務</span><span class="sxs-lookup"><span data-stu-id="18bde-148">Mobility service</span></span>  <br/> |<span data-ttu-id="18bde-149">McxService</span><span class="sxs-lookup"><span data-stu-id="18bde-149">McxService</span></span>  <br/> |

- <span data-ttu-id="18bde-150">**版本號碼** 您可以指定下欄欄位的版本號碼，或使用萬用字元表示用戶端版本號碼。</span><span class="sxs-lookup"><span data-stu-id="18bde-150">**Version number** You can specify the version numbers for the following fields, or use wildcards to indicate the client version number.</span></span>

  - <span data-ttu-id="18bde-151">**主要版本** 指定對應至用戶端主要版本的號碼。</span><span class="sxs-lookup"><span data-stu-id="18bde-151">**Major version** Specifies the number that corresponds to the major release of the client.</span></span>

  - <span data-ttu-id="18bde-152">**次要版本** 指定對應至用戶端次要版本的號碼。</span><span class="sxs-lookup"><span data-stu-id="18bde-152">**Minor version** Specifies the number that corresponds to the minor release of the client.</span></span>

  - <span data-ttu-id="18bde-153">**組建** 指定對應至用戶端主要和次要版本的組建編號。</span><span class="sxs-lookup"><span data-stu-id="18bde-153">**Build** Specifies the build number that corresponds to the major and minor release of the client.</span></span>

  - <span data-ttu-id="18bde-154">**更新** 指定對應至用戶端更新版本的號碼。</span><span class="sxs-lookup"><span data-stu-id="18bde-154">**Update** Specifies the number that corresponds to the updated release of the client.</span></span>

- <span data-ttu-id="18bde-155">**比較運算** 您可以指定您在上述步驟中指定之用戶端版本的對應作業。</span><span class="sxs-lookup"><span data-stu-id="18bde-155">**Comparison operation** You can specify the matching operation for the client version you specified in the preceding steps.</span></span> <span data-ttu-id="18bde-156">可供使用的作業如下：</span><span class="sxs-lookup"><span data-stu-id="18bde-156">The following operations are available:</span></span>

  - <span data-ttu-id="18bde-157">**相同**</span><span class="sxs-lookup"><span data-stu-id="18bde-157">**Same as**</span></span>

  - <span data-ttu-id="18bde-158">**不相同**</span><span class="sxs-lookup"><span data-stu-id="18bde-158">**Is not**</span></span>

  - <span data-ttu-id="18bde-159">**新於**</span><span class="sxs-lookup"><span data-stu-id="18bde-159">**Newer than**</span></span>

  - <span data-ttu-id="18bde-160">**新於或相同**</span><span class="sxs-lookup"><span data-stu-id="18bde-160">**Newer than or same as**</span></span>

  - <span data-ttu-id="18bde-161">**舊於**</span><span class="sxs-lookup"><span data-stu-id="18bde-161">**Older than**</span></span>

  - <span data-ttu-id="18bde-162">**舊於或相同**</span><span class="sxs-lookup"><span data-stu-id="18bde-162">**Older than or same as**</span></span>

- <span data-ttu-id="18bde-163">**動作** 您可以指定在上述步驟中符合準則時所要執行的動作。</span><span class="sxs-lookup"><span data-stu-id="18bde-163">**Action** You can specify the action to perform when the criteria in the preceding steps are met.</span></span> <span data-ttu-id="18bde-164">可供使用的動作如下：</span><span class="sxs-lookup"><span data-stu-id="18bde-164">The following actions are available:</span></span>

  - <span data-ttu-id="18bde-165">**允許** 允許用戶端登入。</span><span class="sxs-lookup"><span data-stu-id="18bde-165">**Allow** Allows the client to log on.</span></span>

  - <span data-ttu-id="18bde-166">**允許和升級** 允許用戶端登入和接收來自 Windows Server Update Service 或 Microsoft Update 的更新。</span><span class="sxs-lookup"><span data-stu-id="18bde-166">**Allow and Upgrade** Allows the client to log on and receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="18bde-167">只有在選取 [使用者代理 **OC** ] 時，才可使用此動作。</span><span class="sxs-lookup"><span data-stu-id="18bde-167">This action is available only when user agent **OC** is selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="18bde-168">選取此動作會在使用者下一次登入商務用 Skype 時顯示通知。</span><span class="sxs-lookup"><span data-stu-id="18bde-168">Selecting this action causes a notification to appear the next time users sign in to Skype for Business.</span></span> <span data-ttu-id="18bde-169">通知指出有可用的更新，即使更新還沒有發佈至 Windows Server Update Service 或 Microsoft Update。</span><span class="sxs-lookup"><span data-stu-id="18bde-169">The notification states that an update is available, even if updates have not yet been released to Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="18bde-170">若要避免混淆，您應該僅在更新可用時選擇此動作。</span><span class="sxs-lookup"><span data-stu-id="18bde-170">To avoid confusion, you should choose this action only after updates become available.</span></span>

  - <span data-ttu-id="18bde-171">**允許搭配 URL** 允許用戶端登入並顯示從何處下載其他用戶端版本的訊息。</span><span class="sxs-lookup"><span data-stu-id="18bde-171">**Allow with URL** Allows the client to log on and displays a message about where to download another client version.</span></span> <span data-ttu-id="18bde-172">您要在 [URL] 欄位中指定 URL。</span><span class="sxs-lookup"><span data-stu-id="18bde-172">You specify the URL in the **URL** field.</span></span>

  - <span data-ttu-id="18bde-173">**封鎖** 禁止用戶端登入。</span><span class="sxs-lookup"><span data-stu-id="18bde-173">**Block** Prevents the client from logging on.</span></span>

  - <span data-ttu-id="18bde-174">**封鎖和升級** 防止用戶端登入，並且允許用戶端從 Windows Server Update Service 或 Microsoft Update 接收更新。</span><span class="sxs-lookup"><span data-stu-id="18bde-174">**Block and Upgrade** Prevents the client from logging on and allows the client to receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="18bde-175">只有在選取 [使用者代理 **OC** ] 時，才可使用此動作。</span><span class="sxs-lookup"><span data-stu-id="18bde-175">This action is available only when user agent **OC** is selected.</span></span>

  - <span data-ttu-id="18bde-p110">**以 URL 封鎖** 禁止用戶端登入並且顯示哪裡可以下載其他用戶端版本的訊息。您要在 [URL] 欄位中指定 URL。</span><span class="sxs-lookup"><span data-stu-id="18bde-p110">**Block with URL** prevents the client from logging on and displays a message about where to download another client version. You specify the URL in the **URL** field.</span></span>

<span data-ttu-id="18bde-178">如需用戶端與用戶端版本之間的互用性相關詳細資訊，請參閱規劃檔中的 [用戶端互通性](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="18bde-178">For details about interoperability among clients and client versions, see [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="18bde-179">如需使用用戶端版本設定的詳細資訊，請參閱作業文件中的＜[Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx)＞。</span><span class="sxs-lookup"><span data-stu-id="18bde-179">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

