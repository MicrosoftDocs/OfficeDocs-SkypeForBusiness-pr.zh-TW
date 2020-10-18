---
title: 將單一使用者移至試驗集區
description: 將單一使用者移至試驗集區。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move a single user to the pilot pool
ms:assetid: e9de81a8-40dd-4446-81e7-a2b810eaea50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205401(v=OCS.15)
ms:contentKeyID: 48185905
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5f7396ed2d92c7015f01ff6cd6e90fd3998219d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574729"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="e2b49-103">將單一使用者移至試驗集區</span><span class="sxs-lookup"><span data-stu-id="e2b49-103">Move a single user to the pilot pool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2b49-104">_**主題上次修改日期：** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="e2b49-104">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="e2b49-105">您可以使用 Lync Server 2013 控制台或 Lync Server 2013 管理命令介面，將您的 Lync Server 2010 集區中的使用者移至 Lync Server 2013 試驗集區。</span><span class="sxs-lookup"><span data-stu-id="e2b49-105">You can move a user from your Lync Server 2010 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="e2b49-106">在下列範例中，在 [報名者集區] 欄中， **pool01.contoso.net** 是 Lync Server 2010 集區，而這六個使用者都連接至此集區。</span><span class="sxs-lookup"><span data-stu-id="e2b49-106">In the example below, in the Registrar pool column, **pool01.contoso.net** is the Lync Server 2010 pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="e2b49-107">使用下列程式，使用 Lync Server 2013 控制台和 Lync Server 管理命令介面，將使用者移至您的 Lync Server 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="e2b49-107">Use the following procedures to move a user to your Lync Server 2013 pool using Lync Server 2013 Control Panel and Lync Server Management Shell.</span></span>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="e2b49-108">使用 Lync Server 2013 控制台移動使用者</span><span class="sxs-lookup"><span data-stu-id="e2b49-108">To move a user by using the Lync Server 2013 Control Panel</span></span>

<span data-ttu-id="e2b49-109">**Lync Server 2013 控制台中的使用者清單**</span><span class="sxs-lookup"><span data-stu-id="e2b49-109">**List of users in the Lync Server 2013 Control Panel**</span></span>

<span data-ttu-id="e2b49-110">![Lync Server 控制台，移動使用者對話方塊](images/JJ721870.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Lync Server 控制台，移動使用者對話方塊")</span><span class="sxs-lookup"><span data-stu-id="e2b49-110">![Lync Server Control Panel, Move User dialog](images/JJ721870.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Lync Server Control Panel, Move User dialog")</span></span>

1.  <span data-ttu-id="e2b49-111">使用 RTCUniversalServerAdmins 群組的成員帳戶、CsAdministrator 成員帳戶或 CsUserAdministrator 系統管理角色的成員帳戶，登入前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="e2b49-111">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>

2.  <span data-ttu-id="e2b49-112">開啟 [ **Lync Server 控制台**]。</span><span class="sxs-lookup"><span data-stu-id="e2b49-112">Open **Lync Server Control Panel**.</span></span>

3.  <span data-ttu-id="e2b49-113">按一下 [ **使用者**]，按一下 [搜尋]，然後按一下 [ **尋找**]。</span><span class="sxs-lookup"><span data-stu-id="e2b49-113">Click **Users**, click Search, and then click **Find**.</span></span>

4.  <span data-ttu-id="e2b49-114">選取您要移至 Lync Server 2013 集區的使用者。</span><span class="sxs-lookup"><span data-stu-id="e2b49-114">Select a user that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="e2b49-115">在這個範例中，將移動使用者 Sara Davis。</span><span class="sxs-lookup"><span data-stu-id="e2b49-115">In this example, we will move user Sara Davis.</span></span>

5.  <span data-ttu-id="e2b49-116">在 [執行]\*\*\*\* 功能表上，選取 [將選取的使用者移至集區]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e2b49-116">On the **Action** menu, select **Move selected users to pool**.</span></span>

6.  <span data-ttu-id="e2b49-117">從下拉式清單中，選取 [Lync Server 2013 集區]。</span><span class="sxs-lookup"><span data-stu-id="e2b49-117">From the drop-down list, select the Lync Server 2013 pool.</span></span>

7.  <span data-ttu-id="e2b49-118">按一下 [動作]\*\*\*\*，然後按一下 [將選取的使用者移至集區]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e2b49-118">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="e2b49-119">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e2b49-119">Click **OK**.</span></span>
    
    <span data-ttu-id="e2b49-120">![移動使用者、目的地註冊集區] 對話方塊](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "移動使用者、目的地註冊集區] 對話方塊")</span><span class="sxs-lookup"><span data-stu-id="e2b49-120">![Move Users, destination registrar pool dialog box](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Move Users, destination registrar pool dialog box")</span></span>  

8.  <span data-ttu-id="e2b49-121">確認使用者的 [ **報名者集** 區] 欄現在包含 Lync Server 2013 集區，這表示使用者已順利移動。</span><span class="sxs-lookup"><span data-stu-id="e2b49-121">Verify that the **Registrar pool** column for the user now contains the Lync Server 2013 pool, which indicates that the user has been successfully moved.</span></span>

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="e2b49-122">使用 Lync Server 2013 管理命令介面移動使用者</span><span class="sxs-lookup"><span data-stu-id="e2b49-122">To move a user by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="e2b49-123">開啟 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="e2b49-123">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="e2b49-124">在命令列輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="e2b49-124">At the command line, type the following:</span></span>
    
        Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  <span data-ttu-id="e2b49-125">接著，在命令列輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="e2b49-125">Next, at the command line, type the following:</span></span>
    
        Get-CsUser -Identity "David Pelton"

4.  <span data-ttu-id="e2b49-126">**RegistrarPool**身分識別現在會指向 Lync Server 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="e2b49-126">The **RegistrarPool** identity now points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="e2b49-127">這個身分識別的出現表示已成功移動使用者。</span><span class="sxs-lookup"><span data-stu-id="e2b49-127">The presence of this identity confirms that the user has been successfully moved.</span></span>
    
    <span data-ttu-id="e2b49-128">![具有身分識別篩選的 Get-CsUser Cmdlet 的輸出](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "具有身分識別篩選的 Get-CsUser Cmdlet 的輸出")</span><span class="sxs-lookup"><span data-stu-id="e2b49-128">![Output from Get-CsUser cmdlet with Identity filter](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Output from Get-CsUser cmdlet with Identity filter")</span></span>  
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e2b49-129">如需關於 <STRONG>Get-CsUser</STRONG> Cmdlet 的詳細資訊，請執行：<STRONG>Get-Help Get-CsUser –Detailed</STRONG></span><span class="sxs-lookup"><span data-stu-id="e2b49-129">For details about the <STRONG>Get-CsUser</STRONG> cmdlet, run: <STRONG>Get-Help Get-CsUser –Detailed</STRONG></span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

