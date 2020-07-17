---
title: 將單一使用者移至試驗集區
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move a single user to the pilot pool
ms:assetid: 80d5b365-f153-4c61-a148-f9e18ce6e027
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688109(v=OCS.15)
ms:contentKeyID: 49733708
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 200e929cb7dff4006ffe776504220618e5e7b570
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756472"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="3ada4-102">將單一使用者移至試驗集區</span><span class="sxs-lookup"><span data-stu-id="3ada4-102">Move a single user to the pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ada4-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="3ada4-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="3ada4-104">您可以使用 Lync Server 2013 控制台或 Lync Server 2013 管理命令介面，將使用者從 Office 通訊伺服器 2007 R2 集區移至 Lync Server 2013 試驗集區。</span><span class="sxs-lookup"><span data-stu-id="3ada4-104">You can move a user from your Office Communications Server 2007 R2 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="3ada4-105">在下列範例中，[報名者集區] 欄 **\<Office Communications Server\>** 是 Office 通訊伺服器 2007 R2 集區，而這六個使用者都連接至此集區。</span><span class="sxs-lookup"><span data-stu-id="3ada4-105">In the example below, in the Registrar pool column, **\<Office Communications Server\>** is the Office Communications Server 2007 R2 pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="3ada4-106">使用下列程式，使用 Lync Server 2013 控制台和 Lync Server 管理命令介面，將使用者移至您的 Lync Server 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="3ada4-106">Use the following procedures to move a user to your Lync Server 2013 pool using Lync Server 2013 Control Panel and Lync Server Management Shell.</span></span>

<span data-ttu-id="3ada4-107">![在 Lync Server 控制台中搜尋 OCS 使用者](images/JJ688109.d2008fd6-868b-4f26-84cf-57bb69e073d3(OCS.15).jpg "在 Lync Server 控制台中搜尋 OCS 使用者")</span><span class="sxs-lookup"><span data-stu-id="3ada4-107">![Search for OCS users in Lync Server Control Panel](images/JJ688109.d2008fd6-868b-4f26-84cf-57bb69e073d3(OCS.15).jpg "Search for OCS users in Lync Server Control Panel")</span></span>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="3ada4-108">使用 Lync Server 2013 控制台移動使用者</span><span class="sxs-lookup"><span data-stu-id="3ada4-108">To move a user by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="3ada4-109">使用 RTCUniversalServerAdmins 群組的成員帳戶、CsAdministrator 成員帳戶或 CsUserAdministrator 系統管理角色的成員帳戶，登入前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="3ada4-109">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>

2.  <span data-ttu-id="3ada4-110">開啟 [Lync Server 控制台]。</span><span class="sxs-lookup"><span data-stu-id="3ada4-110">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="3ada4-111">按一下 [使用者]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3ada4-111">Click **Users**.</span></span>

4.  <span data-ttu-id="3ada4-112">從 [使用者搜尋]\*\*\*\* 索引標籤，按一下 [搜尋]\*\*\*\* 按鈕。</span><span class="sxs-lookup"><span data-stu-id="3ada4-112">From the **User Search** tab, click the **Search** button.</span></span>

5.  <span data-ttu-id="3ada4-113">接著，按一下 [新增篩選]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3ada4-113">Next, click **Add Filter**.</span></span>

6.  <span data-ttu-id="3ada4-114">建立篩選，其中的 [Office Communications Server 使用者]\*\*\*\* 等於 [True]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3ada4-114">Create a filter where **Office Communications Server user** is equal to **True**.</span></span>

7.  <span data-ttu-id="3ada4-115">按一下 [**尋找**] 搜尋舊版 Office 通訊伺服器 2007 R2 使用者。</span><span class="sxs-lookup"><span data-stu-id="3ada4-115">Click **Find** to search for legacy Office Communications Server 2007 R2 users.</span></span>
    
    <span data-ttu-id="3ada4-116">![在 Lync Server 控制台中搜尋 OCS 使用者](images/JJ688109.09528349-7915-41e1-91b4-6ab5c12b1b38(OCS.15).jpg "在 Lync Server 控制台中搜尋 OCS 使用者")</span><span class="sxs-lookup"><span data-stu-id="3ada4-116">![Search for OCS users in Lync Server Control Panel](images/JJ688109.09528349-7915-41e1-91b4-6ab5c12b1b38(OCS.15).jpg "Search for OCS users in Lync Server Control Panel")</span></span>  

8.  <span data-ttu-id="3ada4-117">選取您要移至 Lync Server 2013 集區的使用者。</span><span class="sxs-lookup"><span data-stu-id="3ada4-117">Select a user that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="3ada4-118">在這個範例中，將移動使用者 Sara Davis。</span><span class="sxs-lookup"><span data-stu-id="3ada4-118">In this example, we will move user Sara Davis.</span></span>

9.  <span data-ttu-id="3ada4-119">在 [執行]\*\*\*\* 功能表上，選取 [將選取的使用者移至集區]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3ada4-119">On the **Action** menu, select **Move selected users to pool**.</span></span>

10. <span data-ttu-id="3ada4-120">從下拉式清單中，選取 [Lync Server 2013 集區]。</span><span class="sxs-lookup"><span data-stu-id="3ada4-120">From the drop-down list, select the Lync Server 2013 pool.</span></span>

11. <span data-ttu-id="3ada4-121">按一下 [動作]\*\*\*\*，然後按一下 [將選取的使用者移至集區]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3ada4-121">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="3ada4-122">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3ada4-122">Click **OK**.</span></span>
    
    <span data-ttu-id="3ada4-123">![在 [移動使用者] 對話方塊中設定目的地集區](images/JJ688109.d7dc0759-87c5-4c23-938f-361576621504(OCS.15).jpg "在 [移動使用者] 對話方塊中設定目的地集區")</span><span class="sxs-lookup"><span data-stu-id="3ada4-123">![Setting the Destination pool in Move Users dialog](images/JJ688109.d7dc0759-87c5-4c23-938f-361576621504(OCS.15).jpg "Setting the Destination pool in Move Users dialog")</span></span>  

12. <span data-ttu-id="3ada4-124">確認使用者的 [**報名者集**區] 欄現在包含 Lync Server 2013 集區，這表示使用者已成功移動</span><span class="sxs-lookup"><span data-stu-id="3ada4-124">Verify that the **Registrar pool** column for the user now contains the Lync Server 2013 pool, which indicates that the user has been successfully moved</span></span>

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="3ada4-125">使用 Lync Server 2013 管理命令介面移動使用者</span><span class="sxs-lookup"><span data-stu-id="3ada4-125">To move a user by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="3ada4-126">開啟 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="3ada4-126">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="3ada4-127">在命令列輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="3ada4-127">At the command line, type the following:</span></span>
    
        Move-CsLegacyUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  <span data-ttu-id="3ada4-128">接著，在命令列輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="3ada4-128">Next, at the command line, type the following:</span></span>
    
        Get-CsUser -Identity "David Pelton"

4.  <span data-ttu-id="3ada4-129">**RegistrarPool**身分識別現在會指向 Lync Server 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="3ada4-129">The **RegistrarPool** identity now points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="3ada4-130">這個身分識別的出現表示已成功移動使用者。</span><span class="sxs-lookup"><span data-stu-id="3ada4-130">The presence of this identity confirms that the user has been successfully moved.</span></span>
    
    <span data-ttu-id="3ada4-131">![具有身分識別篩選的 Get-CsUser Cmdlet 的輸出](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "具有身分識別篩選的 Get-CsUser Cmdlet 的輸出")</span><span class="sxs-lookup"><span data-stu-id="3ada4-131">![Output from Get-CsUser cmdlet with Identity filter](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Output from Get-CsUser cmdlet with Identity filter")</span></span>  
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3ada4-132">如需關於 <STRONG>Get-CsUser</STRONG> Cmdlet 的詳細資訊，請執行：<STRONG>Get-Help Get-CsUser –Detailed</STRONG></span><span class="sxs-lookup"><span data-stu-id="3ada4-132">For details about the <STRONG>Get-CsUser</STRONG> cmdlet, run: <STRONG>Get-Help Get-CsUser –Detailed</STRONG></span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

