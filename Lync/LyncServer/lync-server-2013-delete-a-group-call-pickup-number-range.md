---
title: Lync Server 2013：刪除群組呼叫收取號碼範圍
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a Group Call Pickup number range
ms:assetid: 521891f3-7a5d-45de-92dc-d57025453159
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945629(v=OCS.15)
ms:contentKeyID: 51541475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de031dd73f5fe74ba6d343cdea5414fa15988f2a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525650"
---
# <a name="delete-a-group-call-pickup-number-range-in-lync-server-2013"></a><span data-ttu-id="b88c8-102">在 Lync Server 2013 中刪除群組呼叫收取號碼範圍</span><span class="sxs-lookup"><span data-stu-id="b88c8-102">Delete a Group Call Pickup number range in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b88c8-103">_**主題上次修改日期：** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="b88c8-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="b88c8-104">使用下列程式可刪除群組呼叫收取號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="b88c8-104">Use the following procedure to delete a Group Call Pickup number range.</span></span>

<div>

## <a name="to-delete-a-call-pickup-group-number-range"></a><span data-ttu-id="b88c8-105">若要刪除呼叫收取群組號碼範圍</span><span class="sxs-lookup"><span data-stu-id="b88c8-105">To delete a call pickup group number range</span></span>

1.  <span data-ttu-id="b88c8-106">以 [Lync server 2013 的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)中所述，登入安裝了 Lync Server 管理命令介面的電腦，以作為 RTCUniversalServerAdmins 群組的成員或必要的使用者權限。</span><span class="sxs-lookup"><span data-stu-id="b88c8-106">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="b88c8-107">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="b88c8-107">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="b88c8-108">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="b88c8-108">At the command line, type:</span></span>
    
        Remove-CsCallParkOrbit -Identity "<group number range name>" 
    
    <span data-ttu-id="b88c8-109">例如：</span><span class="sxs-lookup"><span data-stu-id="b88c8-109">For example:</span></span>
    
        Remove-CsCallParkOrbit -Identity "Redmond call pickup"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b88c8-110">如需更多選項的詳細資訊，請參閱 <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</A>。</span><span class="sxs-lookup"><span data-stu-id="b88c8-110">For details about more options, see <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b88c8-111">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b88c8-111">See Also</span></span>


[<span data-ttu-id="b88c8-112">在 Lync Server 2013 中建立或修改通話駐留軌道範圍</span><span class="sxs-lookup"><span data-stu-id="b88c8-112">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)  


[<span data-ttu-id="b88c8-113">Remove-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="b88c8-113">Remove-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit)  
[<span data-ttu-id="b88c8-114">Get-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="b88c8-114">Get-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

