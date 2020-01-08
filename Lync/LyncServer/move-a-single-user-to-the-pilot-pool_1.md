---
title: 將單一使用者移至 [試驗] 池
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move a single user to the pilot pool
ms:assetid: 80d5b365-f153-4c61-a148-f9e18ce6e027
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688109(v=OCS.15)
ms:contentKeyID: 49733708
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 086af622644f8d8285ef5f7be8e17f75ff436000
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976817"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="92d20-102">將單一使用者移至 [試驗] 池</span><span class="sxs-lookup"><span data-stu-id="92d20-102">Move a single user to the pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92d20-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="92d20-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="92d20-104">您可以使用 Lync Server 2013 [控制台] 或 [Lync Server 2013 管理命令介面]，將使用者從您的 Office 通訊伺服器 2007 R2 池移至您的 Lync Server 2013 試驗區。</span><span class="sxs-lookup"><span data-stu-id="92d20-104">You can move a user from your Office Communications Server 2007 R2 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="92d20-105">在下列範例中，在 [註冊機構池] 欄中， \*\* \<[office 通訊伺服器\> \*\* ] 是 office 通訊伺服器 2007 R2 池，且所有六個使用者都已連線到此池。</span><span class="sxs-lookup"><span data-stu-id="92d20-105">In the example below, in the Registrar pool column, **\<Office Communications Server\>** is the Office Communications Server 2007 R2 pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="92d20-106">使用下列程式將使用者移至 Lync Server 2013 池（使用 Lync Server 2013 控制台和 Lync Server 管理命令介面）。</span><span class="sxs-lookup"><span data-stu-id="92d20-106">Use the following procedures to move a user to your Lync Server 2013 pool using Lync Server 2013 Control Panel and Lync Server Management Shell.</span></span>

<span data-ttu-id="92d20-107">在 Lync server [控制台]![中搜尋 ocs]使用者(images/JJ688109.d2008fd6-868b-4f26-84cf-57bb69e073d3(OCS.15).jpg "在 Lync server [控制台] 中搜尋 ocs 使用者")</span><span class="sxs-lookup"><span data-stu-id="92d20-107">![Search for OCS users in Lync Server Control Panel](images/JJ688109.d2008fd6-868b-4f26-84cf-57bb69e073d3(OCS.15).jpg "Search for OCS users in Lync Server Control Panel")</span></span>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="92d20-108">使用 Lync Server 2013 [控制台] 移動使用者</span><span class="sxs-lookup"><span data-stu-id="92d20-108">To move a user by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="92d20-109">使用 RTCUniversalServerAdmins 群組成員的帳戶或 CsAdministrator 或 CsUserAdministrator 系統管理角色的成員登入前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="92d20-109">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>

2.  <span data-ttu-id="92d20-110">開啟 [Lync Server 控制台]。</span><span class="sxs-lookup"><span data-stu-id="92d20-110">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="92d20-111">按一下 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="92d20-111">Click **Users**.</span></span>

4.  <span data-ttu-id="92d20-112">從 [**使用者搜尋] 索引**標籤上，按一下 [**搜尋**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="92d20-112">From the **User Search** tab, click the **Search** button.</span></span>

5.  <span data-ttu-id="92d20-113">接著，按一下 [**新增篩選**]。</span><span class="sxs-lookup"><span data-stu-id="92d20-113">Next, click **Add Filter**.</span></span>

6.  <span data-ttu-id="92d20-114">建立 [ **Office 通訊伺服器] 使用者**等於 [ **True**] 的篩選器。</span><span class="sxs-lookup"><span data-stu-id="92d20-114">Create a filter where **Office Communications Server user** is equal to **True**.</span></span>

7.  <span data-ttu-id="92d20-115">按一下 [**尋找**]，搜尋舊版 Office 通訊伺服器 2007 R2 使用者。</span><span class="sxs-lookup"><span data-stu-id="92d20-115">Click **Find** to search for legacy Office Communications Server 2007 R2 users.</span></span>
    
    <span data-ttu-id="92d20-116">在 Lync server [控制台]![中搜尋 ocs]使用者(images/JJ688109.09528349-7915-41e1-91b4-6ab5c12b1b38(OCS.15).jpg "在 Lync server [控制台] 中搜尋 ocs 使用者")</span><span class="sxs-lookup"><span data-stu-id="92d20-116">![Search for OCS users in Lync Server Control Panel](images/JJ688109.09528349-7915-41e1-91b4-6ab5c12b1b38(OCS.15).jpg "Search for OCS users in Lync Server Control Panel")</span></span>  

8.  <span data-ttu-id="92d20-117">選取您要移至 Lync Server 2013 池的使用者。</span><span class="sxs-lookup"><span data-stu-id="92d20-117">Select a user that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="92d20-118">在這個範例中，我們將移動 [使用者 Sara Davis]。</span><span class="sxs-lookup"><span data-stu-id="92d20-118">In this example, we will move user Sara Davis.</span></span>

9.  <span data-ttu-id="92d20-119">在 [**動作**] 功能表上，選取 [**將選取的使用者移至資源庫**]。</span><span class="sxs-lookup"><span data-stu-id="92d20-119">On the **Action** menu, select **Move selected users to pool**.</span></span>

10. <span data-ttu-id="92d20-120">從下拉式清單中，選取 [Lync Server 2013] 池。</span><span class="sxs-lookup"><span data-stu-id="92d20-120">From the drop-down list, select the Lync Server 2013 pool.</span></span>

11. <span data-ttu-id="92d20-121">按一下 [**動作**]，然後按一下 [**將選取的使用者移至資源庫**]。</span><span class="sxs-lookup"><span data-stu-id="92d20-121">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="92d20-122">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="92d20-122">Click **OK**.</span></span>
    
    <span data-ttu-id="92d20-123">![在 [移動使用者] 對話方塊中設定目的地池](images/JJ688109.d7dc0759-87c5-4c23-938f-361576621504(OCS.15).jpg "設定 [移動使用者] 對話方塊中的 [目標] 池")</span><span class="sxs-lookup"><span data-stu-id="92d20-123">![Setting the Destination pool in Move Users dialog](images/JJ688109.d7dc0759-87c5-4c23-938f-361576621504(OCS.15).jpg "Setting the Destination pool in Move Users dialog")</span></span>  

12. <span data-ttu-id="92d20-124">確認使用者的 [**註冊機構池**] 欄現在包含 Lync Server 2013 池，這表示使用者已順利移動</span><span class="sxs-lookup"><span data-stu-id="92d20-124">Verify that the **Registrar pool** column for the user now contains the Lync Server 2013 pool, which indicates that the user has been successfully moved</span></span>

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="92d20-125">使用 Lync Server 2013 管理命令介面來移動使用者</span><span class="sxs-lookup"><span data-stu-id="92d20-125">To move a user by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="92d20-126">開啟 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="92d20-126">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="92d20-127">在命令列中，輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="92d20-127">At the command line, type the following:</span></span>
    
        Move-CsLegacyUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  <span data-ttu-id="92d20-128">接著，在命令列中輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="92d20-128">Next, at the command line, type the following:</span></span>
    
        Get-CsUser -Identity "David Pelton"

4.  <span data-ttu-id="92d20-129">**RegistrarPool**身分識別現在會指向 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="92d20-129">The **RegistrarPool** identity now points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="92d20-130">此身分識別的狀態會確認使用者已順利移動。</span><span class="sxs-lookup"><span data-stu-id="92d20-130">The presence of this identity confirms that the user has been successfully moved.</span></span>
    
    <span data-ttu-id="92d20-131">![Move-csuser Cmdlet 的輸出與](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "含身分識別的 move-csuser Cmdlet")的身分識別篩選器輸出</span><span class="sxs-lookup"><span data-stu-id="92d20-131">![Output from Get-CsUser cmdlet with Identity filter](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Output from Get-CsUser cmdlet with Identity filter")</span></span>  
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="92d20-132">如需<STRONG>move-csuser</STRONG> Cmdlet 的詳細資料，請執行： <STRONG>Get-help move-csuser-詳細</STRONG>資訊</span><span class="sxs-lookup"><span data-stu-id="92d20-132">For details about the <STRONG>Get-CsUser</STRONG> cmdlet, run: <STRONG>Get-Help Get-CsUser –Detailed</STRONG></span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

