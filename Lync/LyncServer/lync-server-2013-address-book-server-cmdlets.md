---
title: 'Lync Server 2013: Address Book Server cmdlet'
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
ms.openlocfilehash: e35106634d9ad9dbc8c4a044aad42d50081cd1e7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196406"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="address-book-server-cmdlets-in-lync-server-2013"></a><span data-ttu-id="da5a3-102">處理 Lync Server 2013 中的活頁簿 Server cmdlet</span><span class="sxs-lookup"><span data-stu-id="da5a3-102">Address Book Server cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da5a3-103">_**主題上次修改日期：** 2012年-06-26_</span><span class="sxs-lookup"><span data-stu-id="da5a3-103">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="da5a3-104">Address Book server 是 Active Directory 網域服務和 Microsoft Lync Server 2013 之間的媒介。</span><span class="sxs-lookup"><span data-stu-id="da5a3-104">Address Book servers are intermediaries between Active Directory Domain Services and Microsoft Lync Server 2013.</span></span> <span data-ttu-id="da5a3-105">Address Book server 可確保儲存在 Lync Server 2013 中的使用者資訊的同步處理儲存在 Active Directory 中的使用者資訊。</span><span class="sxs-lookup"><span data-stu-id="da5a3-105">The Address Book server ensures that the user information stored in Lync Server 2013 is in synch with the user information stored in Active Directory.</span></span> <span data-ttu-id="da5a3-106">其作法是定期將 Address Book 檔案與使用者資料庫中儲存的資訊同步化。</span><span class="sxs-lookup"><span data-stu-id="da5a3-106">This is done by periodically synching Address Book files with information stored in the User database.</span></span> <span data-ttu-id="da5a3-107">接著，Lync Server 包含許多管理 Address Book server cmdlet。</span><span class="sxs-lookup"><span data-stu-id="da5a3-107">In turn, Lync Server includes a number of cmdlets for managing Address Book servers.</span></span>

<div>

## <a name="address-book-server-cmdlets"></a><span data-ttu-id="da5a3-108">Address Book Server Cmdlet</span><span class="sxs-lookup"><span data-stu-id="da5a3-108">Address Book Server Cmdlets</span></span>

<span data-ttu-id="da5a3-109">您無法 Address Book Server 中設定 Lync Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="da5a3-109">You cannot configure the Address Book Server settings in Lync Server Control Panel.</span></span> <span data-ttu-id="da5a3-110">Windows PowerShell 為主要工具，以管理這些設定。</span><span class="sxs-lookup"><span data-stu-id="da5a3-110">Windows PowerShell is the primary tool for managing these settings.</span></span> <span data-ttu-id="da5a3-111">下表列出的 Cmdlet 與管理 Address Book Server 直接相關：</span><span class="sxs-lookup"><span data-stu-id="da5a3-111">The following is a list of cmdlets that relate directly to managing the Address Book Server:</span></span>

<span data-ttu-id="da5a3-112">**Address Book Server**</span><span class="sxs-lookup"><span data-stu-id="da5a3-112">**Address Book Server**</span></span>

  - <span></span>  
    <span data-ttu-id="da5a3-113">[Get-csaddressbookconfiguration cmdlet](https://technet.microsoft.com/library/Gg398132(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="da5a3-113">[Get-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398132(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="da5a3-114">[New-csaddressbookconfiguration](https://technet.microsoft.com/library/Gg398395(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="da5a3-114">[New-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398395(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="da5a3-115">[Remove-csaddressbookconfiguration](https://technet.microsoft.com/library/Gg398934(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="da5a3-115">[Remove-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398934(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="da5a3-116">[Set-csaddressbookconfiguration](https://technet.microsoft.com/library/Gg412784(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="da5a3-116">[Set-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg412784(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="da5a3-117">[Update-csaddressbook](https://technet.microsoft.com/library/Gg398194(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="da5a3-117">[Update-CsAddressBook](https://technet.microsoft.com/library/Gg398194(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="da5a3-118">[Debug-csaddressbookreplication](https://technet.microsoft.com/library/JJ205232(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="da5a3-118">[Debug-CsAddressBookReplication](https://technet.microsoft.com/library/JJ205232(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="da5a3-119">[Test-csaddressbookservice](https://technet.microsoft.com/library/Gg398661(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="da5a3-119">[Test-CsAddressBookService](https://technet.microsoft.com/library/Gg398661(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="da5a3-120">[Test-csaddressbookwebquery](https://technet.microsoft.com/library/Gg398773(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="da5a3-120">[Test-CsAddressBookWebQuery](https://technet.microsoft.com/library/Gg398773(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="da5a3-121">另請參閱</span><span class="sxs-lookup"><span data-stu-id="da5a3-121">See Also</span></span>


[<span data-ttu-id="da5a3-122">Lync Server PowerShell 部落格</span><span class="sxs-lookup"><span data-stu-id="da5a3-122">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

