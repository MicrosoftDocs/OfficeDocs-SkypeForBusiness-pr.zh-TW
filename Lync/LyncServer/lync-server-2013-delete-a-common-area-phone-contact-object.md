---
title: Lync Server 2013：刪除公共區域電話連絡人物件
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
ms.openlocfilehash: 2e0bd9d635cc745c10836c58a331d2e36380e446
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190796"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-a-common-area-phone-contact-object-in-lync-server-2013"></a><span data-ttu-id="e791b-102">在 Lync Server 2013 中刪除公共區域電話連絡人物件</span><span class="sxs-lookup"><span data-stu-id="e791b-102">Delete a common area phone Contact object in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e791b-103">_**主題上次修改日期：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="e791b-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="e791b-104">您可能想要刪除與公共區域電話相關聯的連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="e791b-104">You might want to delete the contact object associated with a common area phone.</span></span> <span data-ttu-id="e791b-105">例如，如果您移除員工前往中的電話，則不需要有與該電話相關聯的 contact 物件。</span><span class="sxs-lookup"><span data-stu-id="e791b-105">For example, if you remove the phone from an employee lounge, there’s no need to have a contact object associated with that phone.</span></span> <span data-ttu-id="e791b-106">**Remove-CsCommonAreaPhone** Cmdlet 提供一種方法，讓您刪除公用區域電話帳戶。</span><span class="sxs-lookup"><span data-stu-id="e791b-106">The **Remove-CsCommonAreaPhone** cmdlet provides a way for you to delete common area phone accounts.</span></span> <span data-ttu-id="e791b-107">當您執行此 Cmdlet 時，系統會從**Get-CsCommonAreaPhone**傳回的常見區域電話清單中刪除電話。</span><span class="sxs-lookup"><span data-stu-id="e791b-107">When you run this cmdlet, the phone is deleted from the list of common area phones returned by **Get-CsCommonAreaPhone**.</span></span> <span data-ttu-id="e791b-108">此外，會從 Active Directory 網域服務中刪除與該電話相關聯的連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="e791b-108">In addition, the contact object associated with that phone is deleted from Active Directory Domain Services.</span></span>

<span data-ttu-id="e791b-109">使用**Remove-CsCommonAreaPhone**來移除一個共同區域電話或所有具有共同元素的公共區域電話，例如顯示名稱或國家/地區碼和區號。</span><span class="sxs-lookup"><span data-stu-id="e791b-109">Use **Remove-CsCommonAreaPhone** to remove one common area phone or all common area phones that have a common element, such as a display name or country and area code.</span></span> <span data-ttu-id="e791b-110">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e791b-110">You can run this cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e791b-111">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="e791b-111">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="removing-a-specified-common-area-phone"></a><span data-ttu-id="e791b-112">移除指定的公共區域電話</span><span class="sxs-lookup"><span data-stu-id="e791b-112">Removing a Specified Common Area Phone</span></span>

  - <span data-ttu-id="e791b-113">下列命令會移除帶有 SIP 位址 sip:mainlobby@litwareinc.com 的公共區域電話：</span><span class="sxs-lookup"><span data-stu-id="e791b-113">The following command removes the common area phone with the SIP address sip:mainlobby@litwareinc.com:</span></span>
    
        Remove-CsCommonAreaPhone -Identity "sip:mainlobby@litwareinc.com"

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-display-name"></a><span data-ttu-id="e791b-114">根據顯示名稱移除公共區域電話</span><span class="sxs-lookup"><span data-stu-id="e791b-114">Removing Common Area Phones Based on Their Display Name</span></span>

  - <span data-ttu-id="e791b-115">此命令會移除顯示名稱包含字串值 "組建 14" 的所有公共區域電話：</span><span class="sxs-lookup"><span data-stu-id="e791b-115">This command removes all the common area phones where the display name includes the string value "Building 14":</span></span>
    
        Get-CsCommonAreaPhone | Where-Object {$_.DisplayName -match "Building 14"} | Remove-CsCommonAreaPhone

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-country-and-area-codes"></a><span data-ttu-id="e791b-116">根據國家/地區碼移除公共區域電話</span><span class="sxs-lookup"><span data-stu-id="e791b-116">Removing Common Area Phones Based on Their Country and Area Codes</span></span>

  - <span data-ttu-id="e791b-117">此命令會移除美國 (國家碼 1) 和區號425的所有通用區域電話：</span><span class="sxs-lookup"><span data-stu-id="e791b-117">This command removes all the common area phones for the United States (country code 1) and the area code 425:</span></span>
    
        Get-CsCommonAreaPhone | Where-Object {$_.LineUri  -match "^tel:\+1425"} | Remove-CsCommonAreaPhone

</div>

<span data-ttu-id="e791b-118">如需詳細資訊，請參閱[Remove-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Remove-CsCommonAreaPhone) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="e791b-118">For details, see the Help topic for the [Remove-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Remove-CsCommonAreaPhone) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e791b-119">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e791b-119">See Also</span></span>


[<span data-ttu-id="e791b-120">Get-CsCommonAreaPhone</span><span class="sxs-lookup"><span data-stu-id="e791b-120">Get-CsCommonAreaPhone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

