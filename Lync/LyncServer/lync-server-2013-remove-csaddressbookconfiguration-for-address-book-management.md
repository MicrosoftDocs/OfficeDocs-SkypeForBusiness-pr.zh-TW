---
title: CsAddressBookConfiguration 網址簿管理的 [移除]
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Remove-CsAddressBookConfiguration for Address Book management
ms:assetid: 5d173ebe-ec4d-4640-8432-a25071ea9cc5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429705(v=OCS.15)
ms:contentKeyID: 48184258
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2662ef012c33d173f836bc3a49581653e846b00b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977623"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-csaddressbookconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="ca0b2-102">在 Lync Server 2013 中移除通訊錄管理的 CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="ca0b2-102">Remove-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca0b2-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="ca0b2-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="ca0b2-104">誰可以執行這個 Cmdlet：根據預設，下列群組的成員有權在本機執行移除 CsAddressBookConfiguration Cmdlet： RTCUniversalServerAdmins。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Remove-CsAddressBookConfiguration cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="ca0b2-105">若要傳回已指派這個 Cmdlet 的所有角色式存取控制（RBAC）角色的清單（包括您自行建立的任何自訂 RBAC 角色），請在 Windows PowerShell 提示中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="ca0b2-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Remove-CsAddressBookConfiguration"}

<span data-ttu-id="ca0b2-106">如名稱所示，Remove-CsAddressBookConfiguration 會根據定義的網站身分識別來移除設定。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-106">As the name implies, Remove-CsAddressBookConfiguration will remove the configuration based on the defined Site Identity.</span></span>

<span data-ttu-id="ca0b2-107">例如：</span><span class="sxs-lookup"><span data-stu-id="ca0b2-107">For example:</span></span>

    Remove-CsAddressBookConfiguration -Identity site:Redmond

<div>

## <a name="see-also"></a><span data-ttu-id="ca0b2-108">請參閱</span><span class="sxs-lookup"><span data-stu-id="ca0b2-108">See Also</span></span>


<span data-ttu-id="ca0b2-109">[移除-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398934(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca0b2-109">[Remove-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398934(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

