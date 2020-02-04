---
title: Lync Server 2013：針對通訊錄管理進行測試 CsAddressBookWebQuery
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
ms.openlocfilehash: c50497979e8439a60799864376d1f93d36646cec
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746253"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-csaddressbookwebquery-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="42764-102">在 Lync Server 2013 中 CsAddressBookWebQuery 通訊錄管理的測試</span><span class="sxs-lookup"><span data-stu-id="42764-102">Test-CsAddressBookWebQuery for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42764-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="42764-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="42764-104">誰可以執行這個 Cmdlet：根據預設，下列群組的成員有權執行測試 CsAddressBookWebQuery Cmdlet： RTCUniversalServerAdmins。</span><span class="sxs-lookup"><span data-stu-id="42764-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Test-CsAddressBookWebQuery cmdlet: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="42764-105">若要傳回已指派這個 Cmdlet 的所有角色式存取控制（RBAC）角色的清單（包括您自行建立的任何自訂 RBAC 角色），請在 Windows PowerShell 提示中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="42764-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Test-CsAddressBookService"}

<span data-ttu-id="42764-106">與 Test CsAddressBookService 綜合交易類似，Test CsAddressBookWebQuery 會針對通訊錄網頁查詢執行查詢，以確保其正常運作。</span><span class="sxs-lookup"><span data-stu-id="42764-106">Similar to the Test-CsAddressBookService synthetic transaction, Test-CsAddressBookWebQuery performs a query against the Address Book Web Query to ensure that it is operating properly.</span></span> <span data-ttu-id="42764-107">這個 Cmdlet 會連線至 Web 票證驗證，並呈現在-UserCredential 中指定的認證。</span><span class="sxs-lookup"><span data-stu-id="42764-107">The cmdlet will connect to the Web Ticket authentication and present the credentials specified in –UserCredential.</span></span> <span data-ttu-id="42764-108">如果經過驗證，則 Cmdlet 會呈現-TargetSipAddress 資訊。</span><span class="sxs-lookup"><span data-stu-id="42764-108">If authenticated, the cmdlet then present the –TargetSipAddress information.</span></span> <span data-ttu-id="42764-109">如果該 Cmdlet 能夠取得連絡人的相關資訊，就應該報告成功。</span><span class="sxs-lookup"><span data-stu-id="42764-109">The cmdlet should report success if it was able to retrieve the information about the contact.</span></span>

<span data-ttu-id="42764-110">例如：</span><span class="sxs-lookup"><span data-stu-id="42764-110">For example:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn atl-cs-001.contoso.com -UserCredential contoso\bob -UserSipAddress "sip:bob@contoso.com" -TargetSipAddress "sip:bob@contoso.com"

<div>

## <a name="see-also"></a><span data-ttu-id="42764-111">請參閱</span><span class="sxs-lookup"><span data-stu-id="42764-111">See Also</span></span>


[<span data-ttu-id="42764-112">Test-CsAddressBookWebQuery</span><span class="sxs-lookup"><span data-stu-id="42764-112">Test-CsAddressBookWebQuery</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

