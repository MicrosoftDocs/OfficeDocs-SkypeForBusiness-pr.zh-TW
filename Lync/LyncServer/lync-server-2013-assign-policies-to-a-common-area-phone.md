---
title: Lync Server 2013：將原則指派給常見的區域電話
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign policies to a common area phone
ms:assetid: f0554fd1-b237-49b3-9eb4-26f4b91f5604
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994082(v=OCS.15)
ms:contentKeyID: 51803993
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e19e2fccabe4759f8cf4cf5eb55ade7e68e2b560
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734043"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-policies-in-lync-server-2013-to-a-common-area-phone"></a><span data-ttu-id="eb777-102">在 Lync Server 2013 中將原則指派至常見的區域電話</span><span class="sxs-lookup"><span data-stu-id="eb777-102">Assign policies in Lync Server 2013 to a common area phone</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb777-103">_**主題上次修改日期：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="eb777-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="eb777-104">在您為常用的區域手機建立原則之後（如需詳細資訊，請參閱[在 Lync Server 2013 中建立語音原則和設定 PSTN 使用記錄](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)），您可以使用 Windows PowerShell 和適當的**Grant-Cs** Cmdlet，將原則指派給常見的區域電話。</span><span class="sxs-lookup"><span data-stu-id="eb777-104">After you create your policy for common area phones (for details, see [Create a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)), you can assign the policy to a common area phone by using Windows PowerShell and the appropriate **Grant-Cs** cmdlet.</span></span> <span data-ttu-id="eb777-105">這些 Cmdlet 都可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。</span><span class="sxs-lookup"><span data-stu-id="eb777-105">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="eb777-106">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="eb777-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="assigning-a-policy-to-a-single-common-area-phone"></a><span data-ttu-id="eb777-107">將原則指派給單一常見區域電話</span><span class="sxs-lookup"><span data-stu-id="eb777-107">Assigning a Policy to a Single Common Area Phone</span></span>

  - <span data-ttu-id="eb777-108">下列命令會將每個使用者的語音原則 RedmondVoice 指派給具有 [建築物 14] 之身分識別的一般區域手機。</span><span class="sxs-lookup"><span data-stu-id="eb777-108">The following command assigns the per-user voice policy RedmondVoice to the common area phone that has the Identity Building 14 Lobby.</span></span>
    
        Grant-CsVoicePolicy -Identity "Building 14 Lobby" -PolicyName "RedmondVoicePolicy"

</div>

<div>

## <a name="assigning-a-policy-to-multiple-common-area-phones"></a><span data-ttu-id="eb777-109">將原則指派給多個常見的區域手機</span><span class="sxs-lookup"><span data-stu-id="eb777-109">Assigning a Policy to Multiple Common Area Phones</span></span>

  - <span data-ttu-id="eb777-110">在這個範例中，每個使用者的語音原則 RedmondVoice 都指派給所有設定為在組織中使用的通用區域電話。</span><span class="sxs-lookup"><span data-stu-id="eb777-110">In this example, the per-user voice policy RedmondVoice is assigned to all the common area phones configured for use in the organization.</span></span>
    
        Get-CsCommonAreaPhone | Grant-CsVoicePolicy  -PolicyName "RedmondVoicePolicy"

</div>

<span data-ttu-id="eb777-111">如需詳細資訊，請參閱[授權 CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsVoicePolicy)的說明主題。</span><span class="sxs-lookup"><span data-stu-id="eb777-111">For details, see the Help topics for the [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsVoicePolicy).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="eb777-112">請參閱</span><span class="sxs-lookup"><span data-stu-id="eb777-112">See Also</span></span>


[<span data-ttu-id="eb777-113">CsCommonAreaPhone</span><span class="sxs-lookup"><span data-stu-id="eb777-113">Get-CsCommonAreaPhone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

