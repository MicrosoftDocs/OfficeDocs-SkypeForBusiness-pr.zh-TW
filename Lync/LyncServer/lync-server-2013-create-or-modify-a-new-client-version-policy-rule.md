---
title: Lync Server 2013：建立或修改新的用戶端版本原則規則
description: Lync Server 2013：建立或修改新的用戶端版本原則規則。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a new client version policy rule
ms:assetid: 6f879d99-8401-41e0-a562-195c890d63ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898478(v=OCS.15)
ms:contentKeyID: 50873758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11ebcf17d5cb14fd519fba8ad36be10894fabdb9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574619"
---
# <a name="create-or-modify-a-new-client-version-policy-rule-in-lync-server-2013"></a><span data-ttu-id="d752c-103">在 Lync Server 2013 中建立或修改新的用戶端版本原則規則</span><span class="sxs-lookup"><span data-stu-id="d752c-103">Create or modify a new client version policy rule in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d752c-104">_**主題上次修改日期：** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="d752c-104">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="d752c-105">用戶端版本原則規則定義當使用者嘗試以特定用戶端和用戶端版本登入時應該採取的動作。</span><span class="sxs-lookup"><span data-stu-id="d752c-105">Client version policy rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span> <span data-ttu-id="d752c-106">您可以從 Lync Server 2013 控制台建立或修改用戶端版本原則的個別規則。</span><span class="sxs-lookup"><span data-stu-id="d752c-106">You can create or modify individual rules for a client version policy from Lync Server 2013 Control Panel.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d752c-107">規則會依優先權順序列出。</span><span class="sxs-lookup"><span data-stu-id="d752c-107">Rules are listed in order of precedence.</span></span> <span data-ttu-id="d752c-108">例如，如果您有允許執行版本1.5 之用戶端進行連線的規則，接著會封鎖執行高於2.0 之版本之用戶端的規則，第一個規則優先，而且執行版本1.5 的用戶端可以進行連線。</span><span class="sxs-lookup"><span data-stu-id="d752c-108">For example, if you have a rule that allows clients running version 1.5 to connect, followed by a rule that blocks clients running a version earlier than 2.0, the first rule takes precedence, and clients running version 1.5 are allowed to connect.</span></span>



</div>

<div>

## <a name="to-create-or-modify-client-version-policy-rules-with-lync-server-control-panel"></a><span data-ttu-id="d752c-109">使用 Lync Server 控制台建立或修改用戶端版本原則規則</span><span class="sxs-lookup"><span data-stu-id="d752c-109">To create or modify client version policy rules with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="d752c-110">使用 Lync Server 控制台，[在 Lync server 2013 中建立或修改新的用戶端版本原則](lync-server-2013-create-or-modify-a-new-client-version-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="d752c-110">[Create or modify a new client version policy in Lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy.md) with Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="d752c-111">在 [ **編輯用戶端版本原則** ] 頁面上，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="d752c-111">On the **Edit Client Version Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="d752c-112">按一下 [ **新增** ] 建立新的用戶端版本規則。</span><span class="sxs-lookup"><span data-stu-id="d752c-112">Click **New** to create a new client version rule.</span></span>
    
      - <span data-ttu-id="d752c-113">按一下清單中已定義的其中一個用戶端類型，然後按一下 [ **顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="d752c-113">Click one of the defined client types in the list, and then click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d752c-114">您可以使用萬用字元來表示用戶端類型。</span><span class="sxs-lookup"><span data-stu-id="d752c-114">You can use wildcards to indicate the client type.</span></span>

    
    </div>

3.  <span data-ttu-id="d752c-115">在 [ **使用者代理程式**] 中，選取用戶端類型。</span><span class="sxs-lookup"><span data-stu-id="d752c-115">In **User agent**, select a client type.</span></span>

4.  <span data-ttu-id="d752c-116">在 [ **版本編號**] 底下，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="d752c-116">Under **Version number**, do the following:</span></span>
    
      - <span data-ttu-id="d752c-117">在 [ **主要版本**] 中，輸入對應至用戶端主要版本的號碼。</span><span class="sxs-lookup"><span data-stu-id="d752c-117">In **Major version**, type the number that corresponds to the major release of the client.</span></span>
    
      - <span data-ttu-id="d752c-118">在 [ **次要版本**] 中，輸入對應至用戶端次要版本的號碼。</span><span class="sxs-lookup"><span data-stu-id="d752c-118">In **Minor version**, type the number that corresponds to the minor release of the client.</span></span>
    
      - <span data-ttu-id="d752c-119">在 [ **組建**] 中，輸入對應至用戶端主要和次要版本的號碼。</span><span class="sxs-lookup"><span data-stu-id="d752c-119">In **Build**, type the number that corresponds to the major and minor release of the client.</span></span>
    
      - <span data-ttu-id="d752c-120">在 [ **更新**] 中，輸入對應至用戶端更新版本的號碼。</span><span class="sxs-lookup"><span data-stu-id="d752c-120">In **Update**, type the number that corresponds to the updated release of the client.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d752c-121">您可以使用萬用字元表示用戶端版本號碼。</span><span class="sxs-lookup"><span data-stu-id="d752c-121">You can use wildcards to indicate the client version number.</span></span>

    
    </div>

5.  <span data-ttu-id="d752c-122">若要為您在上述步驟中指定的用戶端版本指定對應作業，請在 [ **比較**作業] 中，按一下下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="d752c-122">To specify the matching operation for the client version you specified in the preceding steps, in **Comparison operation**, click one of the following:</span></span>
    
      - <span data-ttu-id="d752c-123">**相同**</span><span class="sxs-lookup"><span data-stu-id="d752c-123">**Same as**</span></span>
    
      - <span data-ttu-id="d752c-124">**不相同**</span><span class="sxs-lookup"><span data-stu-id="d752c-124">**Is not**</span></span>
    
      - <span data-ttu-id="d752c-125">**新於**</span><span class="sxs-lookup"><span data-stu-id="d752c-125">**Newer than**</span></span>
    
      - <span data-ttu-id="d752c-126">**新於或相同**</span><span class="sxs-lookup"><span data-stu-id="d752c-126">**Newer than or same as**</span></span>
    
      - <span data-ttu-id="d752c-127">**舊於**</span><span class="sxs-lookup"><span data-stu-id="d752c-127">**Older than**</span></span>
    
      - <span data-ttu-id="d752c-128">**舊於或相同**</span><span class="sxs-lookup"><span data-stu-id="d752c-128">**Older than or same as**</span></span>

6.  <span data-ttu-id="d752c-129">若要指定在上述步驟中符合準則時所要執行的動作，請按一下下列其中一個 **動作**：</span><span class="sxs-lookup"><span data-stu-id="d752c-129">To specify the action to perform when the criteria in the preceding steps are met, click one of the following in **Action**:</span></span>
    
      - <span data-ttu-id="d752c-130">若要允許用戶端登入，請按一下 [ **允許**]。</span><span class="sxs-lookup"><span data-stu-id="d752c-130">To allow the client to log on, click **Allow**.</span></span>
    
      - <span data-ttu-id="d752c-131">若要允許用戶端登入並接收 Windows Server Update Service 或 Microsoft Update 的更新，請按一下 [ **允許和升級**]。</span><span class="sxs-lookup"><span data-stu-id="d752c-131">To allow the client to log on and receive updates from Windows Server Update Service or Microsoft Update, click **Allow and Upgrade**.</span></span> <span data-ttu-id="d752c-132">只有在選取 [使用者代理 **OC** ] 時，才可使用此動作。</span><span class="sxs-lookup"><span data-stu-id="d752c-132">This action is available only when user agent **OC** is selected.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="d752c-133">選取此動作會在使用者下一次登入 Lync 2013 時顯示通知。</span><span class="sxs-lookup"><span data-stu-id="d752c-133">Selecting this action causes a notification to appear the next time users sign in to Lync 2013.</span></span> <span data-ttu-id="d752c-134">通知指出有可用的更新，即使更新還沒有發佈至 Windows Server Update Service 或 Microsoft Update。</span><span class="sxs-lookup"><span data-stu-id="d752c-134">The notification states that an update is available, even if updates have not yet been released to Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="d752c-135">若要避免混淆，您應該僅在更新可用時選擇此動作。</span><span class="sxs-lookup"><span data-stu-id="d752c-135">To avoid confusion, you should choose this action only after updates become available.</span></span>

        
        </div>
    
      - <span data-ttu-id="d752c-136">若要允許用戶端登入並顯示從何處下載其他用戶端版本的訊息，請按一下 [以 **URL 允許**]。</span><span class="sxs-lookup"><span data-stu-id="d752c-136">To allow the client to log on and display a message about where to download another client version, click **Allow with URL**.</span></span> <span data-ttu-id="d752c-137">您可以在此程式稍後指定 URL。</span><span class="sxs-lookup"><span data-stu-id="d752c-137">You specify the URL later in this procedure.</span></span>
    
      - <span data-ttu-id="d752c-138">若要防止用戶端登入，請按一下 [ **封鎖**]。</span><span class="sxs-lookup"><span data-stu-id="d752c-138">To prevent the client from logging on, click **Block**.</span></span>
    
      - <span data-ttu-id="d752c-139">若要防止用戶端登入，並允許用戶端從 Windows Server Update Service 或 Microsoft Update 接收更新，請按一下 [ **封鎖和升級**]。</span><span class="sxs-lookup"><span data-stu-id="d752c-139">To prevent the client from logging on and allow the client to receive updates from Windows Server Update Service or Microsoft Update, click **Block and Upgrade**.</span></span> <span data-ttu-id="d752c-140">只有在選取 [使用者代理 **OC** ] 時，才可使用此動作。</span><span class="sxs-lookup"><span data-stu-id="d752c-140">This action is available only when user agent **OC** is selected.</span></span>
    
      - <span data-ttu-id="d752c-141">若要防止用戶端登入並顯示要從何處下載其他用戶端版本的訊息，請按一下 [以 **URL 封鎖**]。</span><span class="sxs-lookup"><span data-stu-id="d752c-141">To prevent the client from logging on and display a message about where to download another client version, click **Block with URL**.</span></span> <span data-ttu-id="d752c-142">您可以在此程式稍後指定 URL。</span><span class="sxs-lookup"><span data-stu-id="d752c-142">You specify the URL later in this procedure.</span></span>

7.  <span data-ttu-id="d752c-143"> (選用) 如果您在上一個步驟中按下 [ **允許 url** ] 或 [ **以 url 封鎖** ]，請輸入 **url**中要包含的用戶端下載 URL。</span><span class="sxs-lookup"><span data-stu-id="d752c-143">(Optional) If you clicked **Allow with URL** or **Block with URL** in the previous step, type the client download URL to include in the message in **URL**.</span></span>

8.  <span data-ttu-id="d752c-144">按一下 **[確定]**，然後按一下 [ **認可**]。</span><span class="sxs-lookup"><span data-stu-id="d752c-144">Click **OK**, and then click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

