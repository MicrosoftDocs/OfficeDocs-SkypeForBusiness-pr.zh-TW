---
title: Lync Server 2013：用於通訊錄管理的 Test-CsAddressBookWebQuery
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
ms.openlocfilehash: 8c4112f34eb35bcf45991e6744327487afe9a2a7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519240"
---
# <a name="test-csaddressbookwebquery-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="aadab-102">Lync Server 2013 中用於通訊錄管理的 Test-CsAddressBookWebQuery</span><span class="sxs-lookup"><span data-stu-id="aadab-102">Test-CsAddressBookWebQuery for Address Book management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aadab-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="aadab-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="aadab-104">誰可以執行這個 Cmdlet：根據預設，會授權下列群組的成員執行 Test-CsAddressBookWebQuery Cmdlet： RTCUniversalServerAdmins。</span><span class="sxs-lookup"><span data-stu-id="aadab-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Test-CsAddressBookWebQuery cmdlet: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="aadab-105">若要傳回所有獲指派此 Cmdlet 的角色型存取控制 (RBAC) 角色清單 (包括您自行建立的自訂 RBAC 角色)，請在 Windows PowerShell 命令提示中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="aadab-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Test-CsAddressBookService"}

<span data-ttu-id="aadab-106">與 Test-CsAddressBookService 綜合交易類似，Test-CsAddressBookWebQuery 會針對通訊錄 Web 查詢執行查詢，以確保其運作正常。</span><span class="sxs-lookup"><span data-stu-id="aadab-106">Similar to the Test-CsAddressBookService synthetic transaction, Test-CsAddressBookWebQuery performs a query against the Address Book Web Query to ensure that it is operating properly.</span></span> <span data-ttu-id="aadab-107">Cmdlet 會連線至 Web 票證驗證，並顯示– UserCredential 中指定的認證。</span><span class="sxs-lookup"><span data-stu-id="aadab-107">The cmdlet will connect to the Web Ticket authentication and present the credentials specified in –UserCredential.</span></span> <span data-ttu-id="aadab-108">若驗證，Cmdlet 會呈現– TargetSipAddress 資訊。</span><span class="sxs-lookup"><span data-stu-id="aadab-108">If authenticated, the cmdlet then present the –TargetSipAddress information.</span></span> <span data-ttu-id="aadab-109">如果能夠取得連絡人的相關資訊，指令程式就應報告成功。</span><span class="sxs-lookup"><span data-stu-id="aadab-109">The cmdlet should report success if it was able to retrieve the information about the contact.</span></span>

<span data-ttu-id="aadab-110">例如：</span><span class="sxs-lookup"><span data-stu-id="aadab-110">For example:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn atl-cs-001.contoso.com -UserCredential contoso\bob -UserSipAddress "sip:bob@contoso.com" -TargetSipAddress "sip:bob@contoso.com"

<div>

## <a name="see-also"></a><span data-ttu-id="aadab-111">請參閱</span><span class="sxs-lookup"><span data-stu-id="aadab-111">See Also</span></span>


[<span data-ttu-id="aadab-112">Test-CsAddressBookWebQuery</span><span class="sxs-lookup"><span data-stu-id="aadab-112">Test-CsAddressBookWebQuery</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

