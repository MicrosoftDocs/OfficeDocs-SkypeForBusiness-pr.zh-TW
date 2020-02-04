---
title: Lync Server 2013：通訊錄服務器 Cmdlet
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
ms.openlocfilehash: 5117b7a17d607ec995df371fd0cd80fd7c05aeab
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737993"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="address-book-server-cmdlets-in-lync-server-2013"></a><span data-ttu-id="3c559-102">Lync Server 2013 中的通訊錄服務器 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="3c559-102">Address Book Server cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c559-103">_**主題上次修改日期：** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="3c559-103">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="3c559-104">[通訊錄服務器] 是 Active Directory 網域服務與 Microsoft Lync Server 2013 之間的媒介。</span><span class="sxs-lookup"><span data-stu-id="3c559-104">Address Book servers are intermediaries between Active Directory Domain Services and Microsoft Lync Server 2013.</span></span> <span data-ttu-id="3c559-105">通訊錄服務器可確保儲存在 Lync Server 2013 的使用者資訊與 Active Directory 中儲存的使用者資訊同步處理。</span><span class="sxs-lookup"><span data-stu-id="3c559-105">The Address Book server ensures that the user information stored in Lync Server 2013 is in synch with the user information stored in Active Directory.</span></span> <span data-ttu-id="3c559-106">這是透過定期使用儲存在使用者資料庫中之資訊來同步處理通訊錄檔案所完成。</span><span class="sxs-lookup"><span data-stu-id="3c559-106">This is done by periodically synching Address Book files with information stored in the User database.</span></span> <span data-ttu-id="3c559-107">接著 Lync Server 包含許多用來管理通訊錄服務器的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3c559-107">In turn, Lync Server includes a number of cmdlets for managing Address Book servers.</span></span>

<div>

## <a name="address-book-server-cmdlets"></a><span data-ttu-id="3c559-108">通訊錄服務器 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="3c559-108">Address Book Server Cmdlets</span></span>

<span data-ttu-id="3c559-109">您無法在 Lync Server [控制台] 中設定通訊錄服務器設定。</span><span class="sxs-lookup"><span data-stu-id="3c559-109">You cannot configure the Address Book Server settings in Lync Server Control Panel.</span></span> <span data-ttu-id="3c559-110">Windows PowerShell 是管理這些設定的主要工具。</span><span class="sxs-lookup"><span data-stu-id="3c559-110">Windows PowerShell is the primary tool for managing these settings.</span></span> <span data-ttu-id="3c559-111">以下是直接與管理通訊錄服務器相關的 Cmdlet 清單：</span><span class="sxs-lookup"><span data-stu-id="3c559-111">The following is a list of cmdlets that relate directly to managing the Address Book Server:</span></span>

<span data-ttu-id="3c559-112">**通訊錄服務器**</span><span class="sxs-lookup"><span data-stu-id="3c559-112">**Address Book Server**</span></span>

  - <span></span>  
    <span data-ttu-id="3c559-113">[CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398132(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3c559-113">[Get-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398132(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3c559-114">[New-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398395(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3c559-114">[New-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398395(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3c559-115">[移除-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398934(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3c559-115">[Remove-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398934(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3c559-116">[Set-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg412784(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3c559-116">[Set-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg412784(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="3c559-117">[更新-CsAddressBook](https://technet.microsoft.com/en-us/library/Gg398194(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3c559-117">[Update-CsAddressBook](https://technet.microsoft.com/en-us/library/Gg398194(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="3c559-118">[Debug-CsAddressBookReplication](https://technet.microsoft.com/en-us/library/JJ205232(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3c559-118">[Debug-CsAddressBookReplication](https://technet.microsoft.com/en-us/library/JJ205232(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="3c559-119">[Test-CsAddressBookService](https://technet.microsoft.com/en-us/library/Gg398661(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3c559-119">[Test-CsAddressBookService](https://technet.microsoft.com/en-us/library/Gg398661(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="3c559-120">[Test-CsAddressBookWebQuery](https://technet.microsoft.com/en-us/library/Gg398773(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3c559-120">[Test-CsAddressBookWebQuery](https://technet.microsoft.com/en-us/library/Gg398773(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3c559-121">請參閱</span><span class="sxs-lookup"><span data-stu-id="3c559-121">See Also</span></span>


[<span data-ttu-id="3c559-122">Lync Server PowerShell 博客</span><span class="sxs-lookup"><span data-stu-id="3c559-122">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

