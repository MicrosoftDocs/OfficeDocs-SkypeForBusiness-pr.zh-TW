---
title: 將單一使用者移至 [試驗] 池
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move a single user to the pilot pool
ms:assetid: e9de81a8-40dd-4446-81e7-a2b810eaea50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205401(v=OCS.15)
ms:contentKeyID: 48185905
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e9ee58a49afaa9c1e57689b6a3a87fac1a6a4502
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976094"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="d37da-102">將單一使用者移至 [試驗] 池</span><span class="sxs-lookup"><span data-stu-id="d37da-102">Move a single user to the pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d37da-103">_**主題上次修改日期：** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="d37da-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="d37da-104">您可以使用 Lync Server 2013 [控制台] 或 [Lync Server 2013 管理命令介面]，將使用者從 Lync Server 2010 池中移至您的 Lync Server 2013 試驗區。</span><span class="sxs-lookup"><span data-stu-id="d37da-104">You can move a user from your Lync Server 2010 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="d37da-105">在下列範例中，在 [註冊機構池] 欄中， **pool01.contoso.net**是 [Lync Server 2010] 池，且所有六個使用者都已連線到此池。</span><span class="sxs-lookup"><span data-stu-id="d37da-105">In the example below, in the Registrar pool column, **pool01.contoso.net** is the Lync Server 2010 pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="d37da-106">使用下列程式將使用者移至 Lync Server 2013 池（使用 Lync Server 2013 控制台和 Lync Server 管理命令介面）。</span><span class="sxs-lookup"><span data-stu-id="d37da-106">Use the following procedures to move a user to your Lync Server 2013 pool using Lync Server 2013 Control Panel and Lync Server Management Shell.</span></span>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="d37da-107">使用 Lync Server 2013 [控制台] 移動使用者</span><span class="sxs-lookup"><span data-stu-id="d37da-107">To move a user by using the Lync Server 2013 Control Panel</span></span>

<span data-ttu-id="d37da-108">**Lync Server 2013 [控制台] 中的使用者清單**</span><span class="sxs-lookup"><span data-stu-id="d37da-108">**List of users in the Lync Server 2013 Control Panel**</span></span>

<span data-ttu-id="d37da-109">![Lync server [控制台]、[移動使用者] 對話方塊][(images/JJ721870.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Lync server] 控制台、[移動使用者] 對話方塊")</span><span class="sxs-lookup"><span data-stu-id="d37da-109">![Lync Server Control Panel, Move User dialog](images/JJ721870.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Lync Server Control Panel, Move User dialog")</span></span>

1.  <span data-ttu-id="d37da-110">使用 RTCUniversalServerAdmins 群組成員的帳戶或 CsAdministrator 或 CsUserAdministrator 系統管理角色的成員登入前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="d37da-110">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>

2.  <span data-ttu-id="d37da-111">開啟 [ **Lync Server 控制台**]。</span><span class="sxs-lookup"><span data-stu-id="d37da-111">Open **Lync Server Control Panel**.</span></span>

3.  <span data-ttu-id="d37da-112">按一下 [**使用者**]，按一下 [搜尋]，然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="d37da-112">Click **Users**, click Search, and then click **Find**.</span></span>

4.  <span data-ttu-id="d37da-113">選取您要移至 Lync Server 2013 池的使用者。</span><span class="sxs-lookup"><span data-stu-id="d37da-113">Select a user that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="d37da-114">在這個範例中，我們將移動 [使用者 Sara Davis]。</span><span class="sxs-lookup"><span data-stu-id="d37da-114">In this example, we will move user Sara Davis.</span></span>

5.  <span data-ttu-id="d37da-115">在 [**動作**] 功能表上，選取 [**將選取的使用者移至資源庫**]。</span><span class="sxs-lookup"><span data-stu-id="d37da-115">On the **Action** menu, select **Move selected users to pool**.</span></span>

6.  <span data-ttu-id="d37da-116">從下拉式清單中，選取 [Lync Server 2013] 池。</span><span class="sxs-lookup"><span data-stu-id="d37da-116">From the drop-down list, select the Lync Server 2013 pool.</span></span>

7.  <span data-ttu-id="d37da-117">按一下 [**動作**]，然後按一下 [**將選取的使用者移至資源庫**]。</span><span class="sxs-lookup"><span data-stu-id="d37da-117">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="d37da-118">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d37da-118">Click **OK**.</span></span>
    
    <span data-ttu-id="d37da-119">[![移動使用者]、[目的地註冊機構池] 對話方塊][(images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "移動使用者]、[目的地註冊員池] 對話方塊")</span><span class="sxs-lookup"><span data-stu-id="d37da-119">![Move Users, destination registrar pool dialog box](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Move Users, destination registrar pool dialog box")</span></span>  

8.  <span data-ttu-id="d37da-120">確認使用者的 [**註冊機構池**] 欄現在包含 Lync Server 2013 池，這表示使用者已順利移動。</span><span class="sxs-lookup"><span data-stu-id="d37da-120">Verify that the **Registrar pool** column for the user now contains the Lync Server 2013 pool, which indicates that the user has been successfully moved.</span></span>

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="d37da-121">使用 Lync Server 2013 管理命令介面來移動使用者</span><span class="sxs-lookup"><span data-stu-id="d37da-121">To move a user by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="d37da-122">開啟 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="d37da-122">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="d37da-123">在命令列中，輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="d37da-123">At the command line, type the following:</span></span>
    
        Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  <span data-ttu-id="d37da-124">接著，在命令列中輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="d37da-124">Next, at the command line, type the following:</span></span>
    
        Get-CsUser -Identity "David Pelton"

4.  <span data-ttu-id="d37da-125">**RegistrarPool**身分識別現在會指向 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="d37da-125">The **RegistrarPool** identity now points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="d37da-126">此身分識別的狀態會確認使用者已順利移動。</span><span class="sxs-lookup"><span data-stu-id="d37da-126">The presence of this identity confirms that the user has been successfully moved.</span></span>
    
    <span data-ttu-id="d37da-127">![Move-csuser Cmdlet 的輸出與](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "含身分識別的 move-csuser Cmdlet")的身分識別篩選器輸出</span><span class="sxs-lookup"><span data-stu-id="d37da-127">![Output from Get-CsUser cmdlet with Identity filter](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Output from Get-CsUser cmdlet with Identity filter")</span></span>  
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d37da-128">如需<STRONG>move-csuser</STRONG> Cmdlet 的詳細資料，請執行： <STRONG>Get-help move-csuser-詳細</STRONG>資訊</span><span class="sxs-lookup"><span data-stu-id="d37da-128">For details about the <STRONG>Get-CsUser</STRONG> cmdlet, run: <STRONG>Get-Help Get-CsUser –Detailed</STRONG></span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

