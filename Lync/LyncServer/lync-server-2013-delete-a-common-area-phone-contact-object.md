---
title: Lync Server 2013：刪除公共區域電話連絡人物件
description: Lync Server 2013：刪除公共區域電話連絡人物件。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a common area phone Contact object
ms:assetid: f4c139dc-f07c-4c75-9345-e291aea41173
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994087(v=OCS.15)
ms:contentKeyID: 51803999
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e918f7a46269f70577f28b2c3e55297959430721
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566599"
---
# <a name="delete-a-common-area-phone-contact-object-in-lync-server-2013"></a><span data-ttu-id="2f446-103">在 Lync Server 2013 中刪除公共區域電話連絡人物件</span><span class="sxs-lookup"><span data-stu-id="2f446-103">Delete a common area phone Contact object in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f446-104">_**主題上次修改日期：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="2f446-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="2f446-105">您可能想要刪除與公共區域電話相關聯的連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="2f446-105">You might want to delete the contact object associated with a common area phone.</span></span> <span data-ttu-id="2f446-106">例如，如果您移除員工前往中的電話，則不需要有與該電話相關聯的 contact 物件。</span><span class="sxs-lookup"><span data-stu-id="2f446-106">For example, if you remove the phone from an employee lounge, there’s no need to have a contact object associated with that phone.</span></span> <span data-ttu-id="2f446-107">**Remove-CsCommonAreaPhone** Cmdlet 提供一種方法，讓您刪除公用區域電話帳戶。</span><span class="sxs-lookup"><span data-stu-id="2f446-107">The **Remove-CsCommonAreaPhone** cmdlet provides a way for you to delete common area phone accounts.</span></span> <span data-ttu-id="2f446-108">當您執行此 Cmdlet 時，系統會從 **Get-CsCommonAreaPhone**傳回的常見區域電話清單中刪除電話。</span><span class="sxs-lookup"><span data-stu-id="2f446-108">When you run this cmdlet, the phone is deleted from the list of common area phones returned by **Get-CsCommonAreaPhone**.</span></span> <span data-ttu-id="2f446-109">此外，會從 Active Directory 網域服務中刪除與該電話相關聯的連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="2f446-109">In addition, the contact object associated with that phone is deleted from Active Directory Domain Services.</span></span>

<span data-ttu-id="2f446-110">使用 **Remove-CsCommonAreaPhone** 來移除一個共同區域電話或所有具有共同元素的公共區域電話，例如顯示名稱或國家/地區碼和區號。</span><span class="sxs-lookup"><span data-stu-id="2f446-110">Use **Remove-CsCommonAreaPhone** to remove one common area phone or all common area phones that have a common element, such as a display name or country and area code.</span></span> <span data-ttu-id="2f446-111">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2f446-111">You can run this cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="2f446-112">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="2f446-112">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="removing-a-specified-common-area-phone"></a><span data-ttu-id="2f446-113">移除指定的公共區域電話</span><span class="sxs-lookup"><span data-stu-id="2f446-113">Removing a Specified Common Area Phone</span></span>

  - <span data-ttu-id="2f446-114">下列命令會移除帶有 SIP 位址 sip:mainlobby@litwareinc.com 的公共區域電話：</span><span class="sxs-lookup"><span data-stu-id="2f446-114">The following command removes the common area phone with the SIP address sip:mainlobby@litwareinc.com:</span></span>
    
        Remove-CsCommonAreaPhone -Identity "sip:mainlobby@litwareinc.com"

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-display-name"></a><span data-ttu-id="2f446-115">根據顯示名稱移除公共區域電話</span><span class="sxs-lookup"><span data-stu-id="2f446-115">Removing Common Area Phones Based on Their Display Name</span></span>

  - <span data-ttu-id="2f446-116">此命令會移除顯示名稱包含字串值 "組建 14" 的所有公共區域電話：</span><span class="sxs-lookup"><span data-stu-id="2f446-116">This command removes all the common area phones where the display name includes the string value "Building 14":</span></span>
    
        Get-CsCommonAreaPhone | Where-Object {$_.DisplayName -match "Building 14"} | Remove-CsCommonAreaPhone

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-country-and-area-codes"></a><span data-ttu-id="2f446-117">根據國家/地區碼移除公共區域電話</span><span class="sxs-lookup"><span data-stu-id="2f446-117">Removing Common Area Phones Based on Their Country and Area Codes</span></span>

  - <span data-ttu-id="2f446-118">此命令會移除美國 (國家碼 1) 和區號425的所有通用區域電話：</span><span class="sxs-lookup"><span data-stu-id="2f446-118">This command removes all the common area phones for the United States (country code 1) and the area code 425:</span></span>
    
        Get-CsCommonAreaPhone | Where-Object {$_.LineUri  -match "^tel:\+1425"} | Remove-CsCommonAreaPhone

</div>

<span data-ttu-id="2f446-119">如需詳細資訊，請參閱 [Remove-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Remove-CsCommonAreaPhone) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="2f446-119">For details, see the Help topic for the [Remove-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Remove-CsCommonAreaPhone) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2f446-120">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2f446-120">See Also</span></span>


[<span data-ttu-id="2f446-121">Get-CsCommonAreaPhone</span><span class="sxs-lookup"><span data-stu-id="2f446-121">Get-CsCommonAreaPhone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

