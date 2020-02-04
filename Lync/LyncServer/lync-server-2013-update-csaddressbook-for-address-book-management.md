---
title: Lync Server 2013：更新-通訊錄管理的 CsAddressBook
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Update-CsAddressBook for Address Book management
ms:assetid: 0ffd2ef8-201c-44aa-8c64-1c7b0eaa7d48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429695(v=OCS.15)
ms:contentKeyID: 48183428
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f03fe225b2eae508870220e278d7bfc3373dad22
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744783"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="update-csaddressbook-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="b9552-102">CsAddressBook 在 Lync Server 2013 中的通訊錄管理的更新</span><span class="sxs-lookup"><span data-stu-id="b9552-102">Update-CsAddressBook for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9552-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="b9552-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="b9552-104">誰可以執行這個 Cmdlet：根據預設，下列群組的成員有權在本機執行更新-CsAddressBook Cmdlet： RTCUniversalUserAdmins、RTCUniversalServerAdmins。</span><span class="sxs-lookup"><span data-stu-id="b9552-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Update-CsAddressBook cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span></span> <span data-ttu-id="b9552-105">若要傳回已指派這個 Cmdlet 的所有角色式存取控制（RBAC）角色的清單（包括您自行建立的任何自訂 RBAC 角色），請在 Windows PowerShell 提示中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="b9552-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Update-CsAddressBook"}

<span data-ttu-id="b9552-106">CsAddressBook Cmdlet 會從 Office 通訊伺服器取代**abserver-syncNow**命令。</span><span class="sxs-lookup"><span data-stu-id="b9552-106">The Update-CsAddressBook cmdlet replaces the **abserver.exe –syncNow** command from Office Communications Server.</span></span> <span data-ttu-id="b9552-107">這個 Cmdlet 的目的是立即啟動同步處理，而不是等待排程的時間。</span><span class="sxs-lookup"><span data-stu-id="b9552-107">The cmdlet’s purpose is to initiate a synchronization immediately rather than waiting for the scheduled time.</span></span> <span data-ttu-id="b9552-108">第一個範例命令會更新組織中的所有通訊錄。</span><span class="sxs-lookup"><span data-stu-id="b9552-108">The first example command updates all Address Books in the organization.</span></span> <span data-ttu-id="b9552-109">第二個只會更新與已定義的伺服器相關聯的通訊錄。</span><span class="sxs-lookup"><span data-stu-id="b9552-109">The second updates only the Address Book associated with the defined server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b9552-110">在 Lync Server 2013 中，Lync Server 使用者複製程式會從 Active Directory 中挑選變更，並根據設定的間隔更新 Lync Server 使用者資料庫。</span><span class="sxs-lookup"><span data-stu-id="b9552-110">In Lync Server 2013, Lync Server User Replicator will pick up the changes from Active Directory and update the Lync Server user database based on a configured interval.</span></span> <span data-ttu-id="b9552-111">Lync Server 使用者複製程式也會快速傳播 RTCab 資料庫的變更，而不需管理員必須執行更新-CSAddressBook。</span><span class="sxs-lookup"><span data-stu-id="b9552-111">Lync Server User Replicator will also propagate the changes to the RTCab database quickly without the administrator having to run Update-CSAddressBook.</span></span> <span data-ttu-id="b9552-112">如果已啟用通訊錄檔案下載，系統管理員將只需要執行更新 CSAddressBook。</span><span class="sxs-lookup"><span data-stu-id="b9552-112">Administrators will only need to run Update -CSAddressBook if the Address Book file download is enabled.</span></span>



</div>

<span data-ttu-id="b9552-113">例如：</span><span class="sxs-lookup"><span data-stu-id="b9552-113">For example:</span></span>

   ```PowerShell
    Update-CsAddressBook
   ```

   ```PowerShell
    Update-CsAddressBook -Fqdn atl-abs-001.contoso.com
   ```

<div>

## <a name="see-also"></a><span data-ttu-id="b9552-114">請參閱</span><span class="sxs-lookup"><span data-stu-id="b9552-114">See Also</span></span>


[<span data-ttu-id="b9552-115">更新-CsAddressBook</span><span class="sxs-lookup"><span data-stu-id="b9552-115">Update-CsAddressBook</span></span>](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

