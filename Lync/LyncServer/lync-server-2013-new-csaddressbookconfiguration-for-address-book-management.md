---
title: Lync Server 2013：用於通訊錄管理的 New-CsAddressBookConfiguration
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New-CsAddressBookConfiguration for Address Book management
ms:assetid: a58ddc8c-ae04-4141-b69e-e45374a67d72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429718(v=OCS.15)
ms:contentKeyID: 48184985
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88c2cbeb3ff4b9f75a0bce77543e8094ba8a7a89
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508830"
---
# <a name="new-csaddressbookconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="67f29-102">Lync Server 2013 中用於通訊錄管理的 New-CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="67f29-102">New-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67f29-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="67f29-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="67f29-104">誰可以執行此 Cmdlet：下列群組的成員預設會獲授權可以在本機上執行 New-CsAddressBookConfiguration Cmdlet：RTCUniversalServerAdmins。</span><span class="sxs-lookup"><span data-stu-id="67f29-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the New-CsAddressBookConfiguration cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="67f29-105">若要傳回所有獲指派此 Cmdlet 的角色型存取控制 (RBAC) 角色清單 (包括您自行建立的自訂 RBAC 角色)，請在 Windows PowerShell 命令提示中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="67f29-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsAddressBookConfiguration"}

<span data-ttu-id="67f29-106">New-CsAddressBookConfiguration Cmdlet 會建立新的設定，以管理通訊錄的行為。</span><span class="sxs-lookup"><span data-stu-id="67f29-106">The New-CsAddressBookConfiguration cmdlet creates a new configuration to manage the behavior of the Address book.</span></span> <span data-ttu-id="67f29-107">在此 Cmdlet 中，您可以定義通訊錄服務是否會建立用戶端下載檔案、如何使用正規化規則，以及如何使用正規化規則、保留增量及壓縮增量檔案的時間長度，以及建立完整檔通訊錄的時間，以及內部的資訊同步處理使用者資料庫中的資訊的時間。</span><span class="sxs-lookup"><span data-stu-id="67f29-107">Specific to this cmdlet is the ability to define if the Address Book Service creates the client download files, how and if normalization rules are used, how long to retain delta and compact delta files, delta file size before incorporating a new full file creation, what time of day the full file Address Book is created, and what the internal should be for synchronization of information in the User database.</span></span>

<span data-ttu-id="67f29-108">例如：</span><span class="sxs-lookup"><span data-stu-id="67f29-108">For example:</span></span>

    New-CsAddressBookConfiguration -Identity site:Redmond -KeepDuration 15 -SynchronizePollingInterval 00:10:00

<div>

## <a name="see-also"></a><span data-ttu-id="67f29-109">請參閱</span><span class="sxs-lookup"><span data-stu-id="67f29-109">See Also</span></span>


[<span data-ttu-id="67f29-110">New-CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="67f29-110">New-CsAddressBookConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAddressBookConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

