---
title: 'Lync Server 2013: Test-CsAddressBookService 適用於通訊錄管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test-CsAddressBookService for Address Book management
ms:assetid: b88cea74-41fd-4c0e-9284-7135bff27a27
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429720(v=OCS.15)
ms:contentKeyID: 48185206
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83499d42dee053b7ee26d9ea5302c7b4eaab550c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194656"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-csaddressbookservice-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="d5877-102">適用於通訊錄管理 Lync Server 2013 中的測試 CsAddressBookService</span><span class="sxs-lookup"><span data-stu-id="d5877-102">Test-CsAddressBookService for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5877-103">_**主題上次修改日期：** 2012年-11-01_</span><span class="sxs-lookup"><span data-stu-id="d5877-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="d5877-104">誰可以執行此 Cmdlet：下列群組的成員預設會獲授權可以在本機上執行 Test-CsAddressBookService Cmdlet：RTCUniversalServerAdmins。</span><span class="sxs-lookup"><span data-stu-id="d5877-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Test-CsAddressBookService cmdlet: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="d5877-105">若要傳回所有獲指派此 Cmdlet 的角色型存取控制 (RBAC) 角色清單 (包括您自行建立的自訂 RBAC 角色)，請在 Windows PowerShell 命令提示中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="d5877-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Test-CsAddressBookService"}

<span data-ttu-id="d5877-106">Lync Server 2013 包含許多 cmdlet 可啟動綜合命令，以確認特定功能正常運作。</span><span class="sxs-lookup"><span data-stu-id="d5877-106">Lync Server 2013 contains a number of cmdlets that initiate synthetic commands to confirm that a specific function or feature is working properly.</span></span> <span data-ttu-id="d5877-107">Test-csaddressbookservice 會確認已定義的使用者可以連線並從 Address Book Web 服務要求的本機檔案。</span><span class="sxs-lookup"><span data-stu-id="d5877-107">Test-CsAddressBookService confirms that a defined user can connect and request the local files from the Address Book Web service.</span></span>

<span data-ttu-id="d5877-108">例如：</span><span class="sxs-lookup"><span data-stu-id="d5877-108">For example:</span></span>

    Test-CsAddressBookService -TargetFqdn atl-cs-001.contoso.com -UserCredential contoso\bob -UserSipAddress "sip:bob@contoso.com"

<div>

## <a name="see-also"></a><span data-ttu-id="d5877-109">請參閱</span><span class="sxs-lookup"><span data-stu-id="d5877-109">See Also</span></span>


[<span data-ttu-id="d5877-110">Test-csaddressbookservice</span><span class="sxs-lookup"><span data-stu-id="d5877-110">Test-CsAddressBookService</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

