---
title: Lync Server 2013：刪除組呼叫提貨號碼範圍
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete a Group Call Pickup number range
ms:assetid: 521891f3-7a5d-45de-92dc-d57025453159
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945629(v=OCS.15)
ms:contentKeyID: 51541475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7429543c48018eb8fef45e372a4788968396f256
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974081"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-group-call-pickup-number-range-in-lync-server-2013"></a><span data-ttu-id="99daf-102">刪除 Lync Server 2013 中的群組呼叫挑選號碼範圍</span><span class="sxs-lookup"><span data-stu-id="99daf-102">Delete a Group Call Pickup number range in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99daf-103">_**主題上次修改日期：** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="99daf-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="99daf-104">使用下列程式刪除群組通話編號範圍。</span><span class="sxs-lookup"><span data-stu-id="99daf-104">Use the following procedure to delete a Group Call Pickup number range.</span></span>

<div>

## <a name="to-delete-a-call-pickup-group-number-range"></a><span data-ttu-id="99daf-105">刪除呼叫挑選群組的數位範圍</span><span class="sxs-lookup"><span data-stu-id="99daf-105">To delete a call pickup group number range</span></span>

1.  <span data-ttu-id="99daf-106">登入 Lync Server 管理命令介面安裝為 RTCUniversalServerAdmins 群組的成員的電腦，或使用[Lync server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)中所述的必要使用者許可權。</span><span class="sxs-lookup"><span data-stu-id="99daf-106">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="99daf-107">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="99daf-107">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="99daf-108">在命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="99daf-108">At the command line, type:</span></span>
    
        Remove-CsCallParkOrbit -Identity "<group number range name>" 
    
    <span data-ttu-id="99daf-109">例如：</span><span class="sxs-lookup"><span data-stu-id="99daf-109">For example:</span></span>
    
        Remove-CsCallParkOrbit -Identity "Redmond call pickup"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="99daf-110">如需更多選項的詳細資訊，請參閱<A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">移除-CsCallParkOrbit</A>。</span><span class="sxs-lookup"><span data-stu-id="99daf-110">For details about more options, see <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="99daf-111">請參閱</span><span class="sxs-lookup"><span data-stu-id="99daf-111">See Also</span></span>


[<span data-ttu-id="99daf-112">在 Lync Server 2013 中建立或修改通話駐留軌道的範圍</span><span class="sxs-lookup"><span data-stu-id="99daf-112">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)  


[<span data-ttu-id="99daf-113">移除-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="99daf-113">Remove-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit)  
[<span data-ttu-id="99daf-114">CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="99daf-114">Get-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

