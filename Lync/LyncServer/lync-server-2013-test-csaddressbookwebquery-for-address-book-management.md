---
title: 'Lync Server 2013: Test-CsAddressBookWebQuery 適用於通訊錄管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test-CsAddressBookWebQuery for Address Book management
ms:assetid: 977a9c1f-5f4e-4539-9a26-8748b61a57d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429716(v=OCS.15)
ms:contentKeyID: 48184865
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5f03ead82f4ec5ebcb09c3bbfa1bba6206b8333
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194589"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-csaddressbookwebquery-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="07848-102">適用於通訊錄管理 Lync Server 2013 中的測試 CsAddressBookWebQuery</span><span class="sxs-lookup"><span data-stu-id="07848-102">Test-CsAddressBookWebQuery for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07848-103">_**主題上次修改日期：** 2012年-11-01_</span><span class="sxs-lookup"><span data-stu-id="07848-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="07848-104">誰可以執行此 cmdlet： 根據預設，下列群組的成員會獲授權可執行 Test-csaddressbookwebquery cmdlet: RTCUniversalServerAdmins。</span><span class="sxs-lookup"><span data-stu-id="07848-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Test-CsAddressBookWebQuery cmdlet: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="07848-105">若要傳回所有獲指派此 Cmdlet 的角色型存取控制 (RBAC) 角色清單 (包括您自行建立的自訂 RBAC 角色)，請在 Windows PowerShell 命令提示中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="07848-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Test-CsAddressBookService"}

<span data-ttu-id="07848-106">類似於 Test-csaddressbookservice 綜合交易，Test-csaddressbookwebquery 執行查詢，以針對通訊錄 Web 查詢以確保其運作正常。</span><span class="sxs-lookup"><span data-stu-id="07848-106">Similar to the Test-CsAddressBookService synthetic transaction, Test-CsAddressBookWebQuery performs a query against the Address Book Web Query to ensure that it is operating properly.</span></span> <span data-ttu-id="07848-107">指令程式會連線至 Web 票證驗證，並呈現 – UserCredential 中指定的認證。</span><span class="sxs-lookup"><span data-stu-id="07848-107">The cmdlet will connect to the Web Ticket authentication and present the credentials specified in –UserCredential.</span></span> <span data-ttu-id="07848-108">如果通過驗證，指令程式接著會呈現 – TargetSipAddress 資訊。</span><span class="sxs-lookup"><span data-stu-id="07848-108">If authenticated, the cmdlet then present the –TargetSipAddress information.</span></span> <span data-ttu-id="07848-109">指令程式應報告成功，如果它能夠擷取連絡人資訊。</span><span class="sxs-lookup"><span data-stu-id="07848-109">The cmdlet should report success if it was able to retrieve the information about the contact.</span></span>

<span data-ttu-id="07848-110">例如：</span><span class="sxs-lookup"><span data-stu-id="07848-110">For example:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn atl-cs-001.contoso.com -UserCredential contoso\bob -UserSipAddress "sip:bob@contoso.com" -TargetSipAddress "sip:bob@contoso.com"

<div>

## <a name="see-also"></a><span data-ttu-id="07848-111">請參閱</span><span class="sxs-lookup"><span data-stu-id="07848-111">See Also</span></span>


[<span data-ttu-id="07848-112">Test-csaddressbookwebquery</span><span class="sxs-lookup"><span data-stu-id="07848-112">Test-CsAddressBookWebQuery</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

