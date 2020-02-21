---
title: 'Lync Server 2013: Update-CsAddressBook 適用於通訊錄管理'
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
ms.openlocfilehash: 745e636cc4bac682beaf2ea308cd465c3d194df7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193136"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="update-csaddressbook-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="56fc4-102">適用於 Lync Server 2013 中的通訊錄管理的 Update-csaddressbook</span><span class="sxs-lookup"><span data-stu-id="56fc4-102">Update-CsAddressBook for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56fc4-103">_**主題上次修改日期：** 2012年-11-01_</span><span class="sxs-lookup"><span data-stu-id="56fc4-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="56fc4-p101">誰可以執行這個 Cmdlet：根據預設，下列群組成員已獲得授權，可在本機執行 Update-CsAddressBook Cmdlet：RTCUniversalUserAdmins、RTCUniversalServerAdmins。若要傳回指派給該 Cmdlet 的所有角色型存取控制 (RBAC) 角色清單 (包括您自己建立的任何自訂 RBAC 角色)，請在 Windows PowerShell 提示中輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="56fc4-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Update-CsAddressBook cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Update-CsAddressBook"}

<span data-ttu-id="56fc4-p102">Update-CsAddressBook Cmdlet 會取代 Office Communications Server 中的 **abserver.exe –syncNow** 命令。此 Cmdlet 的目的在於立即啟動同步處理，而非等待排程的時間。第一個範例命令會更新組織中的所有通訊錄。第二個範例命令只會更新與所定義伺服器關聯的通訊錄。</span><span class="sxs-lookup"><span data-stu-id="56fc4-p102">The Update-CsAddressBook cmdlet replaces the **abserver.exe –syncNow** command from Office Communications Server. The cmdlet’s purpose is to initiate a synchronization immediately rather than waiting for the scheduled time. The first example command updates all Address Books in the organization. The second updates only the Address Book associated with the defined server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="56fc4-110">在 Lync Server 2013 中，Lync Server 使用者複寫器會挑選來自 Active Directory 所做的變更，並更新 Lync Server 使用者資料庫，根據設定的間隔。</span><span class="sxs-lookup"><span data-stu-id="56fc4-110">In Lync Server 2013, Lync Server User Replicator will pick up the changes from Active Directory and update the Lync Server user database based on a configured interval.</span></span> <span data-ttu-id="56fc4-111">Lync Server 使用者複寫器會也將變更傳播到 RTCab 資料庫快速而不必執行 Update-csaddressbook 系統管理員。</span><span class="sxs-lookup"><span data-stu-id="56fc4-111">Lync Server User Replicator will also propagate the changes to the RTCab database quickly without the administrator having to run Update-CSAddressBook.</span></span> <span data-ttu-id="56fc4-112">系統管理員只將必須重新執行 Update-csaddressbook，如果已啟用 Address Book 檔案下載。</span><span class="sxs-lookup"><span data-stu-id="56fc4-112">Administrators will only need to run Update -CSAddressBook if the Address Book file download is enabled.</span></span>



</div>

<span data-ttu-id="56fc4-113">例如：</span><span class="sxs-lookup"><span data-stu-id="56fc4-113">For example:</span></span>

   ```PowerShell
    Update-CsAddressBook
   ```

   ```PowerShell
    Update-CsAddressBook -Fqdn atl-abs-001.contoso.com
   ```

<div>

## <a name="see-also"></a><span data-ttu-id="56fc4-114">請參閱</span><span class="sxs-lookup"><span data-stu-id="56fc4-114">See Also</span></span>


[<span data-ttu-id="56fc4-115">Update-csaddressbook</span><span class="sxs-lookup"><span data-stu-id="56fc4-115">Update-CsAddressBook</span></span>](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

