---
title: Lync Server 2013：針對通訊錄管理進行測試 CsAddressBookService
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test-CsAddressBookService for Address Book management
ms:assetid: b88cea74-41fd-4c0e-9284-7135bff27a27
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429720(v=OCS.15)
ms:contentKeyID: 48185206
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 120a61ff03957a25cb7e6e0d09b8d3bccb11343c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980311"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-csaddressbookservice-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="48f7f-102">在 Lync Server 2013 中 CsAddressBookService 通訊錄管理的測試</span><span class="sxs-lookup"><span data-stu-id="48f7f-102">Test-CsAddressBookService for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48f7f-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="48f7f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="48f7f-104">誰可以執行這個 Cmdlet：根據預設，下列群組的成員有權執行測試 CsAddressBookService Cmdlet： RTCUniversalServerAdmins。</span><span class="sxs-lookup"><span data-stu-id="48f7f-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Test-CsAddressBookService cmdlet: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="48f7f-105">若要傳回已指派這個 Cmdlet 的所有角色式存取控制（RBAC）角色的清單（包括您自行建立的任何自訂 RBAC 角色），請在 Windows PowerShell 提示中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="48f7f-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Test-CsAddressBookService"}

<span data-ttu-id="48f7f-106">Lync Server 2013 包含可啟動綜合命令以確認特定函數或功能正常運作的幾個 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="48f7f-106">Lync Server 2013 contains a number of cmdlets that initiate synthetic commands to confirm that a specific function or feature is working properly.</span></span> <span data-ttu-id="48f7f-107">測試-CsAddressBookService 會確認已定義的使用者可以從通訊錄 Web 服務連線並要求本機檔案。</span><span class="sxs-lookup"><span data-stu-id="48f7f-107">Test-CsAddressBookService confirms that a defined user can connect and request the local files from the Address Book Web service.</span></span>

<span data-ttu-id="48f7f-108">例如：</span><span class="sxs-lookup"><span data-stu-id="48f7f-108">For example:</span></span>

    Test-CsAddressBookService -TargetFqdn atl-cs-001.contoso.com -UserCredential contoso\bob -UserSipAddress "sip:bob@contoso.com"

<div>

## <a name="see-also"></a><span data-ttu-id="48f7f-109">請參閱</span><span class="sxs-lookup"><span data-stu-id="48f7f-109">See Also</span></span>


[<span data-ttu-id="48f7f-110">Test-CsAddressBookService</span><span class="sxs-lookup"><span data-stu-id="48f7f-110">Test-CsAddressBookService</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

