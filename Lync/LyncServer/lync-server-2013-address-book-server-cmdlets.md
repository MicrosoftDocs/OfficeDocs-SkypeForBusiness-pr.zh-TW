---
title: Lync Server 2013： Address Book Server Cmdlet
description: Lync Server 2013： Address Book Server Cmdlet。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Address Book Server cmdlets
ms:assetid: 33da45da-3c57-4d04-9679-f0e5a0cfd37e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415643(v=OCS.15)
ms:contentKeyID: 48183793
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4fef903d25f0d2707410e017f4eb280282bbdab
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553029"
---
# <a name="address-book-server-cmdlets-in-lync-server-2013"></a><span data-ttu-id="ee016-103">Lync Server 2013 中的通訊錄服務器 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="ee016-103">Address Book Server cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee016-104">_**主題上次修改日期：** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="ee016-104">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="ee016-105">Address Book servers 是 Active Directory 網域服務和 Microsoft Lync Server 2013 之間的仲介。</span><span class="sxs-lookup"><span data-stu-id="ee016-105">Address Book servers are intermediaries between Active Directory Domain Services and Microsoft Lync Server 2013.</span></span> <span data-ttu-id="ee016-106">Address Book server 會確保儲存在 Lync Server 2013 中的使用者資訊，與儲存在 Active Directory 中的使用者資訊同步。</span><span class="sxs-lookup"><span data-stu-id="ee016-106">The Address Book server ensures that the user information stored in Lync Server 2013 is in synch with the user information stored in Active Directory.</span></span> <span data-ttu-id="ee016-107">其作法是定期將 Address Book 檔案與使用者資料庫中儲存的資訊同步化。</span><span class="sxs-lookup"><span data-stu-id="ee016-107">This is done by periodically synching Address Book files with information stored in the User database.</span></span> <span data-ttu-id="ee016-108">然後，Lync Server 會包含許多 Cmdlet 來管理通訊錄服務器。</span><span class="sxs-lookup"><span data-stu-id="ee016-108">In turn, Lync Server includes a number of cmdlets for managing Address Book servers.</span></span>

<div>

## <a name="address-book-server-cmdlets"></a><span data-ttu-id="ee016-109">Address Book Server Cmdlet</span><span class="sxs-lookup"><span data-stu-id="ee016-109">Address Book Server Cmdlets</span></span>

<span data-ttu-id="ee016-110">您無法在 Lync Server 控制台中設定通訊錄服務器設定。</span><span class="sxs-lookup"><span data-stu-id="ee016-110">You cannot configure the Address Book Server settings in Lync Server Control Panel.</span></span> <span data-ttu-id="ee016-111">Windows PowerShell 是用來管理這些設定的主要工具。</span><span class="sxs-lookup"><span data-stu-id="ee016-111">Windows PowerShell is the primary tool for managing these settings.</span></span> <span data-ttu-id="ee016-112">下表列出的 Cmdlet 與管理 Address Book Server 直接相關：</span><span class="sxs-lookup"><span data-stu-id="ee016-112">The following is a list of cmdlets that relate directly to managing the Address Book Server:</span></span>

<span data-ttu-id="ee016-113">**Address Book Server**</span><span class="sxs-lookup"><span data-stu-id="ee016-113">**Address Book Server**</span></span>

  - <span></span>  
    <span data-ttu-id="ee016-114">[Get-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398132(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ee016-114">[Get-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398132(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ee016-115">[New-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398395(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ee016-115">[New-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398395(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ee016-116">[Remove-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398934(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ee016-116">[Remove-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398934(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ee016-117">[Set-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg412784(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ee016-117">[Set-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg412784(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ee016-118">[Update-CsAddressBook](https://technet.microsoft.com/library/Gg398194(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ee016-118">[Update-CsAddressBook](https://technet.microsoft.com/library/Gg398194(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ee016-119">[Debug-CsAddressBookReplication](https://technet.microsoft.com/library/JJ205232(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ee016-119">[Debug-CsAddressBookReplication](https://technet.microsoft.com/library/JJ205232(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ee016-120">[Test-CsAddressBookService](https://technet.microsoft.com/library/Gg398661(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ee016-120">[Test-CsAddressBookService](https://technet.microsoft.com/library/Gg398661(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ee016-121">[Test-CsAddressBookWebQuery](https://technet.microsoft.com/library/Gg398773(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ee016-121">[Test-CsAddressBookWebQuery](https://technet.microsoft.com/library/Gg398773(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ee016-122">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ee016-122">See Also</span></span>


[<span data-ttu-id="ee016-123">Lync Server PowerShell 的博客</span><span class="sxs-lookup"><span data-stu-id="ee016-123">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

