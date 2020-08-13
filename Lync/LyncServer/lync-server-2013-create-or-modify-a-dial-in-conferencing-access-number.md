---
title: Lync Server 2013：建立或修改電話撥入式會議存取號碼
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a dial-in conferencing access number
ms:assetid: 06f55c28-57f8-4d4e-8313-9740846796d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398126(v=OCS.15)
ms:contentKeyID: 48183304
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f684166c7a33f092ee9d7a00eb9582cb70e2606
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188336"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-dial-in-conferencing-access-number-in-lync-server-2013"></a><span data-ttu-id="c5885-102">在 Lync Server 2013 中建立或修改電話撥入式會議存取號碼</span><span class="sxs-lookup"><span data-stu-id="c5885-102">Create or modify a dial-in conferencing access number in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5885-103">_**主題上次修改日期：** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="c5885-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="c5885-104">如果您想建立或修改電話撥入式會議存取號碼，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="c5885-104">Follow these steps if you want to create or modify a dial-in conferencing access number.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c5885-p101">您必須先在與新的撥入存取號碼關聯的撥號對應表中設定電話撥入式會議區域，才可建立新的撥入存取號碼。多個撥號對應表可使用相同的區域。</span><span class="sxs-lookup"><span data-stu-id="c5885-p101">Before you create a new dial-in access number, you must set a dial-in conferencing region in the dial plan that is associated with the new dial-in access number. Multiple dial plans can use the same region.</span></span>



</div>

<div>

## <a name="to-create-or-modify-a-dial-in-access-number"></a><span data-ttu-id="c5885-107">若要建立或修改撥入存取號碼</span><span class="sxs-lookup"><span data-stu-id="c5885-107">To create or modify a dial-in access number</span></span>

1.  <span data-ttu-id="c5885-108">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="c5885-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c5885-109">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="c5885-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c5885-110">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="c5885-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c5885-111">在左導覽列中，按一下 **[會議]**，然後按一下 **[撥入存取號碼]**。</span><span class="sxs-lookup"><span data-stu-id="c5885-111">In the left navigation bar, click **Conferencing** and then click **Dial-in Access Number**.</span></span>

4.  <span data-ttu-id="c5885-112">在 **[撥入存取號碼]** 頁面中，執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="c5885-112">On the **Dial-in Access Number** page, do one of the following:</span></span>
    
      - <span data-ttu-id="c5885-113">按一下 **[新增]** 以開啟 **[新增撥入存取號碼]**。</span><span class="sxs-lookup"><span data-stu-id="c5885-113">Click **New** to open **New Dial-in Access Number**.</span></span>
    
      - <span data-ttu-id="c5885-114">按一下清單中的其中一個撥入存取號碼，按一下 **[編輯]**，然後按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="c5885-114">Click one of the dial-in access numbers in the list, click **Edit**, and then click **Show details**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c5885-p103">使用搜尋欄位來搜尋撥入存取號碼清單中可能無法產生預期結果的欄內容。請依照您想要的欄排序此清單，找出您想檢視或變更的撥入存取號碼。</span><span class="sxs-lookup"><span data-stu-id="c5885-p103">Using the search field to search for the contents of a column in the list of dial-in access numbers may not yield the results you expect. Instead, sort the list by the column of interest to identify the dial-in access number you want to view or change.</span></span>

        
        </div>

5.  <span data-ttu-id="c5885-117">在 [**顯示號碼**] 中，輸入公用交換電話網路 (PSTN) 電話使用者撥號以加入會議的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="c5885-117">In **Display number**, type the phone number that public switched telephone network (PSTN) phone users dial to join a conference.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c5885-118">此號碼會顯示在會議邀請中和電話撥入式會議設定網頁上。</span><span class="sxs-lookup"><span data-stu-id="c5885-118">This number is displayed in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>

    
    </div>

6.  <span data-ttu-id="c5885-119">在 [**顯示名稱**] 中，輸入撥入存取號碼的描述。</span><span class="sxs-lookup"><span data-stu-id="c5885-119">In **Display name**, type a description for the dial-in access number.</span></span> <span data-ttu-id="c5885-120">這是與 Lync 搜尋結果中的撥入存取號碼相關聯的名稱。</span><span class="sxs-lookup"><span data-stu-id="c5885-120">This is the name that is associated with the dial-in access number in Lync search results.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c5885-121">當使用者呼叫存取號碼時，此名稱會顯示在用戶端中。</span><span class="sxs-lookup"><span data-stu-id="c5885-121">This name is displayed in the client when a user calls the access number.</span></span>

    
    </div>

7.  <span data-ttu-id="c5885-122">在 [**行 uri**] 中，輸入電話 uri 格式的撥入存取號碼的 e.164 號碼，包含號碼前面的 + 符號，並排除空格。</span><span class="sxs-lookup"><span data-stu-id="c5885-122">In **Line URI**, type the E.164 number of the dial-in access number in TEL URI format, including the + symbol before the number and excluding spaces.</span></span> <span data-ttu-id="c5885-123">例如電話： + 14255550200。</span><span class="sxs-lookup"><span data-stu-id="c5885-123">For example, tel:+14255550200.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c5885-124">其他電話撥入式會議存取號碼無法重複使用相同的列 URI。</span><span class="sxs-lookup"><span data-stu-id="c5885-124">The same Line URI cannot be reused by another dial-in conferencing access number.</span></span>

    
    </div>

8.  <span data-ttu-id="c5885-125">在 [ **SIP URI**] 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="c5885-125">In **SIP URI**, do the following:</span></span>
    
      - <span data-ttu-id="c5885-126">在文字方塊中，輸入此撥入式會議存取號碼的唯一 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="c5885-126">In the text box, type a unique SIP URI for this dial-in conferencing access number.</span></span> <span data-ttu-id="c5885-127">這種 SIP URI 會顯示在不同的位置，包括（但不限於）來電通知訊息和舊版的 Communicator 用戶端。</span><span class="sxs-lookup"><span data-stu-id="c5885-127">This SIP URI is displayed in various locations including, but not limited to, call notification messages and previous versions of Communicator clients.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c5885-128">其他電話撥入式會議存取號碼無法重複使用相同的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="c5885-128">The same SIP URI cannot be reused by another dial-in conferencing access number.</span></span> <span data-ttu-id="c5885-129">建立存取號碼之後，便無法修改 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="c5885-129">The SIP URI cannot be modified after the access number is created.</span></span> <span data-ttu-id="c5885-130">變更 SIP URI 的唯一方法是刪除並重新建立存取號碼。</span><span class="sxs-lookup"><span data-stu-id="c5885-130">The only way to change the SIP URI is to delete and recreate the access number.</span></span>

        
        </div>
    
      - <span data-ttu-id="c5885-131">在下拉式清單方塊中，按一下支援此撥入存取號碼之會議應答應用程式的網域。</span><span class="sxs-lookup"><span data-stu-id="c5885-131">In the drop-down list box, click the domain of the Conferencing Attendant application that supports this dial-in access number.</span></span>

9.  <span data-ttu-id="c5885-132">在 [**集**區] 中，按一下執行支援此撥入存取號碼之會議助理實例的集區。</span><span class="sxs-lookup"><span data-stu-id="c5885-132">In **Pool**, click the pool that is running the instance of Conferencing Attendant that supports this dial-in access number.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c5885-133">如果您在建立存取號碼之後需要變更集區，則必須使用<STRONG>Move-CsApplicationEndpoint</STRONG> Cmdlet，或刪除並重新建立存取號碼。</span><span class="sxs-lookup"><span data-stu-id="c5885-133">If you need to change the pool after you create the access number, you must use the <STRONG>Move-CsApplicationEndpoint</STRONG> cmdlet or delete and recreate the access number.</span></span>

    
    </div>

10. <span data-ttu-id="c5885-134">在 [**主要語言**] 中，按一下為此撥入存取號碼播放提示時所使用的語言。</span><span class="sxs-lookup"><span data-stu-id="c5885-134">In **Primary language**, click the language in which prompts are played for this dial-in access number.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c5885-135">主要語言是會議助理用來接聽通話的語言。</span><span class="sxs-lookup"><span data-stu-id="c5885-135">The primary language is the language that the Conferencing Attendant uses to answer the call.</span></span> <span data-ttu-id="c5885-136">在 [電話撥入式會議設定] 網頁上的每一個存取電話號碼旁會顯示支援的語言。</span><span class="sxs-lookup"><span data-stu-id="c5885-136">Supported languages are displayed alongside each access phone number on the Dial-in Conferencing Settings webpage.</span></span>

    
    </div>

11. <span data-ttu-id="c5885-137"> (選用) 在**次要語言中 (最多四個) **，請按一下 [**新增**]，選取您要支援的來電者撥打此撥入存取號碼的一或多個其他語言，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="c5885-137">(Optional) In **Secondary languages (maximum of four)**, click **Add**, select one or more additional languages that you want to support for callers to this dial-in access number, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c5885-138">您最多可以為每個撥入存取號碼選擇四種次要語言。</span><span class="sxs-lookup"><span data-stu-id="c5885-138">You can choose up to four secondary languages for each dial-in access number.</span></span> <span data-ttu-id="c5885-139">使用者在撥入會議時，可以先選取次要語言，再進入會議識別碼。</span><span class="sxs-lookup"><span data-stu-id="c5885-139">Users can select a secondary language before entering the conference ID when they dial in to a conference.</span></span>

    
    </div>

12. <span data-ttu-id="c5885-140">若要新增撥入存取號碼的地區，請在 [**關聯的地區**] 下，按一下 [**新增**]，然後按一下與此撥入存取號碼的撥號對應表相關聯的一個或多個地區，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="c5885-140">To add a region for the dial-in access number, under **Associated regions**, click **Add**, click one or more regions that are associated with the dial plans for this dial-in access number, and then click **OK**.</span></span>

13. <span data-ttu-id="c5885-141">若要從撥入存取號碼中刪除地區，請在 [**關聯的地區**] 下，按一下您要刪除的地區，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="c5885-141">To delete a region from the dial-in access number, under **Associated regions**, click the region you want to delete, and then click **Remove**.</span></span>

14. <span data-ttu-id="c5885-142">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="c5885-142">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

