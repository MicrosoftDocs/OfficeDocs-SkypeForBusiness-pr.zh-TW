---
title: Lync Server 2013：設定通訊錄管理的 CsClientPolicy
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set-CsClientPolicy for Address Book management
ms:assetid: e7788bea-606f-481a-a3a4-1855ac028493
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429723(v=OCS.15)
ms:contentKeyID: 48185726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 248a04692327d93293e5bc5d37e650322b415ccb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975490"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-csclientpolicy-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="644a8-102">在 Lync Server 2013 中設定通訊錄管理 CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="644a8-102">Set-CsClientPolicy for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="644a8-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="644a8-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="644a8-104">誰可以執行這個 Cmdlet：根據預設，下列群組的成員有權在本機執行 CsClientPolicy Cmdlet： RTCUniversalServerAdmins。</span><span class="sxs-lookup"><span data-stu-id="644a8-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Set-CsClientPolicy cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="644a8-105">若要傳回已指派這個 Cmdlet 的所有角色式存取控制（RBAC）角色的清單（包括您自行建立的任何自訂 RBAC 角色），請在 Windows PowerShell 提示中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="644a8-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClientPolicy"}

<span data-ttu-id="644a8-106">與 New-CsClientPolicy 類似，CsClientPolicy Cmdlet 可讓您修改現有的用戶端設定。</span><span class="sxs-lookup"><span data-stu-id="644a8-106">Similar to New-CsClientPolicy, the Set-CsClientPolicy cmdlet allows you to modify client settings that are already in place.</span></span>

<span data-ttu-id="644a8-107">例如：</span><span class="sxs-lookup"><span data-stu-id="644a8-107">For example:</span></span>

    Set-CsClientPolicy -Identity RedmondClientPolicy -WebServicePollInterval "00:15:00" -AddressBookAvailability "WebSearchAndFileDownload"

<div>

## <a name="see-also"></a><span data-ttu-id="644a8-108">請參閱</span><span class="sxs-lookup"><span data-stu-id="644a8-108">See Also</span></span>


[<span data-ttu-id="644a8-109">Set-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="644a8-109">Set-CsClientPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

