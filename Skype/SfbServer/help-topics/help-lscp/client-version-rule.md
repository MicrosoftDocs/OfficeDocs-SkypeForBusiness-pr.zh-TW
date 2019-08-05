---
title: 用戶端版本規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
description: 用戶端版本原則是由一組用戶端版本規則所組成。當使用者嘗試以特定用戶端及用戶端版本登入時，這些規則會定義所要採取的動作。
ms.openlocfilehash: 6fa3ca3f59756c8a6fedb9fd8f1f457ca3f2df40
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188053"
---
# <a name="client-version-rule"></a><span data-ttu-id="bfbbe-104">用戶端版本規則</span><span class="sxs-lookup"><span data-stu-id="bfbbe-104">Client Version Rule</span></span>

<span data-ttu-id="bfbbe-p102">用戶端版本原則是由一組用戶端版本規則所組成。當使用者嘗試以特定用戶端及用戶端版本登入時，這些規則會定義所要採取的動作。</span><span class="sxs-lookup"><span data-stu-id="bfbbe-p102">A client version policy is made up of a set of client version rules. These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="bfbbe-107">您可以執行的工作</span><span class="sxs-lookup"><span data-stu-id="bfbbe-107">Tasks you can perform</span></span>

<span data-ttu-id="bfbbe-108">您可以在「新增用戶端版本設定」\*\*\*\* 或「編輯用戶端版本設定」\*\*\*\* 頁面上執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="bfbbe-108">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>

- <span data-ttu-id="bfbbe-109">新增規則至用戶端版本原則。</span><span class="sxs-lookup"><span data-stu-id="bfbbe-109">Add new rules to a client version policy.</span></span>

- <span data-ttu-id="bfbbe-110">修改組成現有用戶端版本原則的規則</span><span class="sxs-lookup"><span data-stu-id="bfbbe-110">Modify the rules that make up an existing client version policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="bfbbe-111">UI 參考</span><span class="sxs-lookup"><span data-stu-id="bfbbe-111">UI Reference</span></span>

<span data-ttu-id="bfbbe-112">下列清單說明頁面上的功能表、命令、欄位及內容。</span><span class="sxs-lookup"><span data-stu-id="bfbbe-112">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="bfbbe-113">**使用者代理程式**您可以從清單中選取用戶端類型。</span><span class="sxs-lookup"><span data-stu-id="bfbbe-113">**User agent** You can select a client type from the list.</span></span> <span data-ttu-id="bfbbe-114">下表定義使用者代理程式碼。</span><span class="sxs-lookup"><span data-stu-id="bfbbe-114">The following table defines user agent codes.</span></span>

|<span data-ttu-id="bfbbe-115">**用戶端名稱**</span><span class="sxs-lookup"><span data-stu-id="bfbbe-115">**Client Name**</span></span>|<span data-ttu-id="bfbbe-116">**使用者代理程式**</span><span class="sxs-lookup"><span data-stu-id="bfbbe-116">**User Agent**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bfbbe-117">Lync 2013、Lync 2010、Office Communicator</span><span class="sxs-lookup"><span data-stu-id="bfbbe-117">Lync 2013, Lync 2010, Office Communicator</span></span>  <br/> |<span data-ttu-id="bfbbe-118">OC</span><span class="sxs-lookup"><span data-stu-id="bfbbe-118">OC</span></span>  <br/> |
|<span data-ttu-id="bfbbe-119">Lync Web App、Communicator Web Access</span><span class="sxs-lookup"><span data-stu-id="bfbbe-119">Lync Web App, Communicator Web Access</span></span>  <br/> |<span data-ttu-id="bfbbe-120">CWA</span><span class="sxs-lookup"><span data-stu-id="bfbbe-120">CWA</span></span>  <br/> |
|<span data-ttu-id="bfbbe-121">Lync Phone Edition、Office Communicator Phone</span><span class="sxs-lookup"><span data-stu-id="bfbbe-121">Lync Phone Edition, Office Communicator Phone</span></span>  <br/> |<span data-ttu-id="bfbbe-122">OCPhone</span><span class="sxs-lookup"><span data-stu-id="bfbbe-122">OCPhone</span></span>  <br/> |
|<span data-ttu-id="bfbbe-123">Communicator Phone Edition 平台</span><span class="sxs-lookup"><span data-stu-id="bfbbe-123">Communicator Phone Edition Platform</span></span>  <br/> |<span data-ttu-id="bfbbe-124">CPE</span><span class="sxs-lookup"><span data-stu-id="bfbbe-124">CPE</span></span>  <br/> |
|<span data-ttu-id="bfbbe-125">整合通訊平台</span><span class="sxs-lookup"><span data-stu-id="bfbbe-125">Unified Communications Platform</span></span>  <br/> |<span data-ttu-id="bfbbe-126">UCCP</span><span class="sxs-lookup"><span data-stu-id="bfbbe-126">UCCP</span></span>  <br/> |
|<span data-ttu-id="bfbbe-127">Lync 2010 出席者</span><span class="sxs-lookup"><span data-stu-id="bfbbe-127">Lync 2010 Attendee</span></span>  <br/> |<span data-ttu-id="bfbbe-128">AOC</span><span class="sxs-lookup"><span data-stu-id="bfbbe-128">AOC</span></span>  <br/> |
|<span data-ttu-id="bfbbe-129">Live Meeting 增益集</span><span class="sxs-lookup"><span data-stu-id="bfbbe-129">Live Meeting Add-In</span></span>  <br/> |<span data-ttu-id="bfbbe-130">LiveMeetingAddins</span><span class="sxs-lookup"><span data-stu-id="bfbbe-130">LiveMeetingAddins</span></span>  <br/> |
|<span data-ttu-id="bfbbe-131">Office Live Meeting</span><span class="sxs-lookup"><span data-stu-id="bfbbe-131">Office Live Meeting</span></span>  <br/> |<span data-ttu-id="bfbbe-132">LMC</span><span class="sxs-lookup"><span data-stu-id="bfbbe-132">LMC</span></span>  <br/> |
|<span data-ttu-id="bfbbe-133">Windows Messenger</span><span class="sxs-lookup"><span data-stu-id="bfbbe-133">Windows Messenger</span></span>  <br/> |<span data-ttu-id="bfbbe-134">WM</span><span class="sxs-lookup"><span data-stu-id="bfbbe-134">WM</span></span>  <br/> |
|<span data-ttu-id="bfbbe-135">即時通訊用戶端</span><span class="sxs-lookup"><span data-stu-id="bfbbe-135">Real-time Communications Client</span></span>  <br/> |<span data-ttu-id="bfbbe-136">RTC</span><span class="sxs-lookup"><span data-stu-id="bfbbe-136">RTC</span></span>  <br/> |
|<span data-ttu-id="bfbbe-137">IPad 版 Lync 2010</span><span class="sxs-lookup"><span data-stu-id="bfbbe-137">Lync 2010 for iPad</span></span>  <br/> |<span data-ttu-id="bfbbe-138">iPadLync</span><span class="sxs-lookup"><span data-stu-id="bfbbe-138">iPadLync</span></span>  <br/> |
|<span data-ttu-id="bfbbe-139">IPhone 版 Lync 2010</span><span class="sxs-lookup"><span data-stu-id="bfbbe-139">Lync 2010 for iPhone</span></span>  <br/> |<span data-ttu-id="bfbbe-140">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="bfbbe-140">iPhoneLync</span></span>  <br/> |
|<span data-ttu-id="bfbbe-141">Windows Phone 版 Lync 2010</span><span class="sxs-lookup"><span data-stu-id="bfbbe-141">Lync 2010 for Windows Phone</span></span>  <br/> |<span data-ttu-id="bfbbe-142">WPLync</span><span class="sxs-lookup"><span data-stu-id="bfbbe-142">WPLync</span></span>  <br/> |
|<span data-ttu-id="bfbbe-143">適用于 Nokia 的 Lync 2010</span><span class="sxs-lookup"><span data-stu-id="bfbbe-143">Lync 2010 for Nokia</span></span>  <br/> |<span data-ttu-id="bfbbe-144">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="bfbbe-144">NokiaLync</span></span>  <br/> |
|<span data-ttu-id="bfbbe-145">Android 版 Lync 2010</span><span class="sxs-lookup"><span data-stu-id="bfbbe-145">Lync 2010 for Android</span></span>  <br/> |<span data-ttu-id="bfbbe-146">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="bfbbe-146">AndroidLync</span></span>  <br/> |
|<span data-ttu-id="bfbbe-147">行動性服務</span><span class="sxs-lookup"><span data-stu-id="bfbbe-147">Mobility service</span></span>  <br/> |<span data-ttu-id="bfbbe-148">McxService</span><span class="sxs-lookup"><span data-stu-id="bfbbe-148">McxService</span></span>  <br/> |

- <span data-ttu-id="bfbbe-149">**版本號碼**您可以指定下欄欄位的版本號碼, 或使用萬用字元來表示用戶端的版本號碼。</span><span class="sxs-lookup"><span data-stu-id="bfbbe-149">**Version number** You can specify the version numbers for the following fields, or use wildcards to indicate the client version number.</span></span>

  - <span data-ttu-id="bfbbe-150">**主要版本**指定與用戶端主要版本相對應的數位。</span><span class="sxs-lookup"><span data-stu-id="bfbbe-150">**Major version** Specifies the number that corresponds to the major release of the client.</span></span>

  - <span data-ttu-id="bfbbe-151">**次要版本**指定與用戶端次要發行版本相對應的數位。</span><span class="sxs-lookup"><span data-stu-id="bfbbe-151">**Minor version** Specifies the number that corresponds to the minor release of the client.</span></span>

  - <span data-ttu-id="bfbbe-152">**組建**指定與用戶端主要和次要版本相對應的組建編號。</span><span class="sxs-lookup"><span data-stu-id="bfbbe-152">**Build** Specifies the build number that corresponds to the major and minor release of the client.</span></span>

  - <span data-ttu-id="bfbbe-153">**更新**指定與用戶端更新版本相對應的數位。</span><span class="sxs-lookup"><span data-stu-id="bfbbe-153">**Update** Specifies the number that corresponds to the updated release of the client.</span></span>

- <span data-ttu-id="bfbbe-154">**比較運算**您可以針對您在上述步驟中所指定的用戶端版本, 指定相符的操作。</span><span class="sxs-lookup"><span data-stu-id="bfbbe-154">**Comparison operation** You can specify the matching operation for the client version you specified in the preceding steps.</span></span> <span data-ttu-id="bfbbe-155">下列作業可供使用:</span><span class="sxs-lookup"><span data-stu-id="bfbbe-155">The following operations are available:</span></span>

  - <span data-ttu-id="bfbbe-156">**相同**</span><span class="sxs-lookup"><span data-stu-id="bfbbe-156">**Same as**</span></span>

  - <span data-ttu-id="bfbbe-157">**不相同**</span><span class="sxs-lookup"><span data-stu-id="bfbbe-157">**Is not**</span></span>

  - <span data-ttu-id="bfbbe-158">**新於**</span><span class="sxs-lookup"><span data-stu-id="bfbbe-158">**Newer than**</span></span>

  - <span data-ttu-id="bfbbe-159">**新於或相同**</span><span class="sxs-lookup"><span data-stu-id="bfbbe-159">**Newer than or same as**</span></span>

  - <span data-ttu-id="bfbbe-160">**舊於**</span><span class="sxs-lookup"><span data-stu-id="bfbbe-160">**Older than**</span></span>

  - <span data-ttu-id="bfbbe-161">**舊於或相同**</span><span class="sxs-lookup"><span data-stu-id="bfbbe-161">**Older than or same as**</span></span>

- <span data-ttu-id="bfbbe-162">**動作**您可以指定在滿足上述步驟中的準則時要執行的動作。</span><span class="sxs-lookup"><span data-stu-id="bfbbe-162">**Action** You can specify the action to perform when the criteria in the preceding steps are met.</span></span> <span data-ttu-id="bfbbe-163">下列動作可供使用:</span><span class="sxs-lookup"><span data-stu-id="bfbbe-163">The following actions are available:</span></span>

  - <span data-ttu-id="bfbbe-164">**允許**允許用戶端登入。</span><span class="sxs-lookup"><span data-stu-id="bfbbe-164">**Allow** Allows the client to log on.</span></span>

  - <span data-ttu-id="bfbbe-165">**允許和升級**允許用戶端登入, 並從 Windows Server Update Services 或 Microsoft Update 接收更新。</span><span class="sxs-lookup"><span data-stu-id="bfbbe-165">**Allow and Upgrade** Allows the client to log on and receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="bfbbe-166">只有在選取 [使用者代理**OC** ] 時, 才能使用此動作。</span><span class="sxs-lookup"><span data-stu-id="bfbbe-166">This action is available only when user agent **OC** is selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bfbbe-167">選取此動作會在使用者下次登入商務用 Skype 時, 顯示通知。</span><span class="sxs-lookup"><span data-stu-id="bfbbe-167">Selecting this action causes a notification to appear the next time users sign in to Skype for Business.</span></span> <span data-ttu-id="bfbbe-168">通知指出有可用的更新，即使更新還沒有發佈至 Windows Server Update Service 或 Microsoft Update。</span><span class="sxs-lookup"><span data-stu-id="bfbbe-168">The notification states that an update is available, even if updates have not yet been released to Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="bfbbe-169">為避免混淆，您應該僅在有可用更新時選擇此動作。</span><span class="sxs-lookup"><span data-stu-id="bfbbe-169">To avoid confusion, you should choose this action only after updates become available.</span></span>

  - <span data-ttu-id="bfbbe-170">**允許 URL**允許用戶端登入, 並顯示有關下載其他用戶端版本之位置的訊息。</span><span class="sxs-lookup"><span data-stu-id="bfbbe-170">**Allow with URL** Allows the client to log on and displays a message about where to download another client version.</span></span> <span data-ttu-id="bfbbe-171">您要在 [URL]\*\*\*\* 欄位中指定 URL。</span><span class="sxs-lookup"><span data-stu-id="bfbbe-171">You specify the URL in the **URL** field.</span></span>

  - <span data-ttu-id="bfbbe-172">**封鎖**防止用戶端登入。</span><span class="sxs-lookup"><span data-stu-id="bfbbe-172">**Block** Prevents the client from logging on.</span></span>

  - <span data-ttu-id="bfbbe-173">**封鎖和升級**防止用戶端登入, 並允許用戶端從 Windows Server Update Services 或 Microsoft Update 接收更新。</span><span class="sxs-lookup"><span data-stu-id="bfbbe-173">**Block and Upgrade** Prevents the client from logging on and allows the client to receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="bfbbe-174">只有在選取 [使用者代理**OC** ] 時, 才能使用此動作。</span><span class="sxs-lookup"><span data-stu-id="bfbbe-174">This action is available only when user agent **OC** is selected.</span></span>

  - <span data-ttu-id="bfbbe-p110">**以 URL 封鎖** 禁止用戶端登入並且顯示哪裡可以下載其他用戶端版本的訊息。您要在 [URL]\*\*\*\* 欄位中指定 URL。</span><span class="sxs-lookup"><span data-stu-id="bfbbe-p110">**Block with URL** prevents the client from logging on and displays a message about where to download another client version. You specify the URL in the **URL** field.</span></span>

<span data-ttu-id="bfbbe-p111">如需用戶端和用戶端版本間互通性的詳細資訊，請參閱規劃文件中的〈[Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)〉。如需使用用戶端版本設定的詳細資訊，請參閱作業文件中的〈[Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx)〉。</span><span class="sxs-lookup"><span data-stu-id="bfbbe-p111">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation. For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

