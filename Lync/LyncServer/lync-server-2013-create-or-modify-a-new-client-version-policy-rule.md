---
title: Lync Server 2013： 建立或修改新的用戶端版本原則規則
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
ms.openlocfilehash: b4fec7930b8ebd7aa6bb7f50c71a1f163cdb83f2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207909"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-new-client-version-policy-rule-in-lync-server-2013"></a><span data-ttu-id="55ff4-102">建立或修改 Lync Server 2013 中新的用戶端版本原則規則</span><span class="sxs-lookup"><span data-stu-id="55ff4-102">Create or modify a new client version policy rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55ff4-103">_**上次修改主題：** 2013年-01-21_</span><span class="sxs-lookup"><span data-stu-id="55ff4-103">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="55ff4-104">用戶端版本原則規則定義當使用者嘗試登入特定的用戶端與用戶端版本時應該採取的動作。</span><span class="sxs-lookup"><span data-stu-id="55ff4-104">Client version policy rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span> <span data-ttu-id="55ff4-105">您可以建立或修改 Lync Server 2013 控制台從用戶端版本原則的個別規則。</span><span class="sxs-lookup"><span data-stu-id="55ff4-105">You can create or modify individual rules for a client version policy from Lync Server 2013 Control Panel.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="55ff4-106">規則會列在的優先順序。</span><span class="sxs-lookup"><span data-stu-id="55ff4-106">Rules are listed in order of precedence.</span></span> <span data-ttu-id="55ff4-107">比方說，如果您有一個規則，可讓用戶端執行連線 1.5 版，後面接著會封鎖用戶端規則執行更早版本的版本比 2.0 中，第一個規則的優先順序，和允許執行 1.5 版用戶端連接。</span><span class="sxs-lookup"><span data-stu-id="55ff4-107">For example, if you have a rule that allows clients running version 1.5 to connect, followed by a rule that blocks clients running a version earlier than 2.0, the first rule takes precedence, and clients running version 1.5 are allowed to connect.</span></span>



</div>

<div>

## <a name="to-create-or-modify-client-version-policy-rules-with-lync-server-control-panel"></a><span data-ttu-id="55ff4-108">若要建立或修改用戶端版本原則規則與 Lync Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="55ff4-108">To create or modify client version policy rules with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="55ff4-109">[建立或修改 Lync Server 2013 中的新用戶端版本原則](lync-server-2013-create-or-modify-a-new-client-version-policy.md)與 Lync Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="55ff4-109">[Create or modify a new client version policy in Lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy.md) with Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="55ff4-110">在 [**編輯用戶端版本原則**] 頁面上，執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="55ff4-110">On the **Edit Client Version Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="55ff4-111">按一下 [**新增**]，以建立新的用戶端版本規則。</span><span class="sxs-lookup"><span data-stu-id="55ff4-111">Click **New** to create a new client version rule.</span></span>
    
      - <span data-ttu-id="55ff4-112">按一下其中一個已定義的用戶端類型的清單中，，然後按一下 [**顯示詳細資料**。</span><span class="sxs-lookup"><span data-stu-id="55ff4-112">Click one of the defined client types in the list, and then click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="55ff4-113">您可以使用萬用字元表示用戶端類型。</span><span class="sxs-lookup"><span data-stu-id="55ff4-113">You can use wildcards to indicate the client type.</span></span>

    
    </div>

3.  <span data-ttu-id="55ff4-114">**使用者代理程式**] 中選取的用戶端類型。</span><span class="sxs-lookup"><span data-stu-id="55ff4-114">In **User agent**, select a client type.</span></span>

4.  <span data-ttu-id="55ff4-115">[**版本號碼**] 下方執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="55ff4-115">Under **Version number**, do the following:</span></span>
    
      - <span data-ttu-id="55ff4-116">在 [**主要版本**中，輸入對應至用戶端主要版本號碼。</span><span class="sxs-lookup"><span data-stu-id="55ff4-116">In **Major version**, type the number that corresponds to the major release of the client.</span></span>
    
      - <span data-ttu-id="55ff4-117">在 [**次要版本**中，輸入對應至用戶端次要版本號碼。</span><span class="sxs-lookup"><span data-stu-id="55ff4-117">In **Minor version**, type the number that corresponds to the minor release of the client.</span></span>
    
      - <span data-ttu-id="55ff4-118">在**建立**時，輸入對應至用戶端主要和次要版本號碼。</span><span class="sxs-lookup"><span data-stu-id="55ff4-118">In **Build**, type the number that corresponds to the major and minor release of the client.</span></span>
    
      - <span data-ttu-id="55ff4-119">在**更新**時，輸入對應至用戶端更新版本的號碼。</span><span class="sxs-lookup"><span data-stu-id="55ff4-119">In **Update**, type the number that corresponds to the updated release of the client.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="55ff4-120">您可以使用萬用字元表示用戶端版本號碼。</span><span class="sxs-lookup"><span data-stu-id="55ff4-120">You can use wildcards to indicate the client version number.</span></span>

    
    </div>

5.  <span data-ttu-id="55ff4-121">若要指定您在先前步驟中，在**比較作業**中，指定用戶端版本比對作業按一下下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="55ff4-121">To specify the matching operation for the client version you specified in the preceding steps, in **Comparison operation**, click one of the following:</span></span>
    
      - <span data-ttu-id="55ff4-122">**相同**</span><span class="sxs-lookup"><span data-stu-id="55ff4-122">**Same as**</span></span>
    
      - <span data-ttu-id="55ff4-123">**不相同**</span><span class="sxs-lookup"><span data-stu-id="55ff4-123">**Is not**</span></span>
    
      - <span data-ttu-id="55ff4-124">**新於**</span><span class="sxs-lookup"><span data-stu-id="55ff4-124">**Newer than**</span></span>
    
      - <span data-ttu-id="55ff4-125">**新於或相同**</span><span class="sxs-lookup"><span data-stu-id="55ff4-125">**Newer than or same as**</span></span>
    
      - <span data-ttu-id="55ff4-126">**舊於**</span><span class="sxs-lookup"><span data-stu-id="55ff4-126">**Older than**</span></span>
    
      - <span data-ttu-id="55ff4-127">**舊於或相同**</span><span class="sxs-lookup"><span data-stu-id="55ff4-127">**Older than or same as**</span></span>

6.  <span data-ttu-id="55ff4-128">若要指定的巨集指令來執行前述步驟中的條件符合時，按一下 [**巨集指令**中下列其中之一：</span><span class="sxs-lookup"><span data-stu-id="55ff4-128">To specify the action to perform when the criteria in the preceding steps are met, click one of the following in **Action**:</span></span>
    
      - <span data-ttu-id="55ff4-129">若要允許用戶端登入，請按一下 [**允許**]。</span><span class="sxs-lookup"><span data-stu-id="55ff4-129">To allow the client to log on, click **Allow**.</span></span>
    
      - <span data-ttu-id="55ff4-130">若要允許用戶端登入，並從 Windows Server Update Service 或 Microsoft Update 」 接收更新，請按一下 [**允許並升級**。</span><span class="sxs-lookup"><span data-stu-id="55ff4-130">To allow the client to log on and receive updates from Windows Server Update Service or Microsoft Update, click **Allow and Upgrade**.</span></span> <span data-ttu-id="55ff4-131">選取 [使用者代理程式**OC**時才使用此巨集指令。</span><span class="sxs-lookup"><span data-stu-id="55ff4-131">This action is available only when user agent **OC** is selected.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="55ff4-132">選取此巨集指令會顯示 [下一次使用者登入 Lync 2013 的通知。</span><span class="sxs-lookup"><span data-stu-id="55ff4-132">Selecting this action causes a notification to appear the next time users sign in to Lync 2013.</span></span> <span data-ttu-id="55ff4-133">通知指出有可用的更新，即使更新還沒有發佈至 Windows Server Update Service 或 Microsoft Update。</span><span class="sxs-lookup"><span data-stu-id="55ff4-133">The notification states that an update is available, even if updates have not yet been released to Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="55ff4-134">若要避免混淆，您應該僅在更新可用時選擇此動作。</span><span class="sxs-lookup"><span data-stu-id="55ff4-134">To avoid confusion, you should choose this action only after updates become available.</span></span>

        
        </div>
    
      - <span data-ttu-id="55ff4-135">若要允許用戶端登入並顯示一則訊息關於到哪裡下載另一個用戶端版本，請按一下 [**以 URL 允許**]。</span><span class="sxs-lookup"><span data-stu-id="55ff4-135">To allow the client to log on and display a message about where to download another client version, click **Allow with URL**.</span></span> <span data-ttu-id="55ff4-136">您稍後在此程序中指定的 URL。</span><span class="sxs-lookup"><span data-stu-id="55ff4-136">You specify the URL later in this procedure.</span></span>
    
      - <span data-ttu-id="55ff4-137">若要防止用戶端登入，請按一下 [**封鎖**]。</span><span class="sxs-lookup"><span data-stu-id="55ff4-137">To prevent the client from logging on, click **Block**.</span></span>
    
      - <span data-ttu-id="55ff4-138">若要防止用戶端登入，並允許用戶端以從 Windows Server Update Service 或 Microsoft Update 」 接收更新，請按一下 [**封鎖並升級**。</span><span class="sxs-lookup"><span data-stu-id="55ff4-138">To prevent the client from logging on and allow the client to receive updates from Windows Server Update Service or Microsoft Update, click **Block and Upgrade**.</span></span> <span data-ttu-id="55ff4-139">選取 [使用者代理程式**OC**時才使用此巨集指令。</span><span class="sxs-lookup"><span data-stu-id="55ff4-139">This action is available only when user agent **OC** is selected.</span></span>
    
      - <span data-ttu-id="55ff4-140">若要防止用戶端登入並顯示一則訊息關於到哪裡下載另一個用戶端版本，按一下 [**以 URL 封鎖**]。</span><span class="sxs-lookup"><span data-stu-id="55ff4-140">To prevent the client from logging on and display a message about where to download another client version, click **Block with URL**.</span></span> <span data-ttu-id="55ff4-141">您稍後在此程序中指定的 URL。</span><span class="sxs-lookup"><span data-stu-id="55ff4-141">You specify the URL later in this procedure.</span></span>

7.  <span data-ttu-id="55ff4-142">（選用）如果您在先前步驟中，按一下**以 URL 允許**] 或 [**以 URL 封鎖**]，類型用戶端下載**URL**] 中的訊息中包含的 URL。</span><span class="sxs-lookup"><span data-stu-id="55ff4-142">(Optional) If you clicked **Allow with URL** or **Block with URL** in the previous step, type the client download URL to include in the message in **URL**.</span></span>

8.  <span data-ttu-id="55ff4-143">按一下 [**確定**]，然後按一下 [**認可]**。</span><span class="sxs-lookup"><span data-stu-id="55ff4-143">Click **OK**, and then click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

