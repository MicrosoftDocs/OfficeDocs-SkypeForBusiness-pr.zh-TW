---
title: Lync Server 2013：針對通訊錄管理取得 CsAddressBookConfiguration
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Get-CsAddressBookConfiguration for Address Book management
ms:assetid: bd62f916-caf3-4e10-ada4-631bbb331ef1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429721(v=OCS.15)
ms:contentKeyID: 48185264
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30a9f29ee4842b11c503e913d1e80e97e2dab274
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756937"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="get-csaddressbookconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="d756d-102">在 Lync Server 2013 中取得通訊錄管理的 CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="d756d-102">Get-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d756d-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="d756d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="d756d-104">誰可以執行這個 Cmdlet：根據預設，下列群組的成員有權在本機執行 CsAddressBookConfiguration Cmdlet： RTCUniversalServerAdmins。</span><span class="sxs-lookup"><span data-stu-id="d756d-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Get-CsAddressBookConfiguration cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="d756d-105">若要傳回已指派這個 Cmdlet 的所有角色式存取控制（RBAC）角色的清單（包括您自行建立的任何自訂 RBAC 角色），請在 Windows PowerShell 提示中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="d756d-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsAddressBookConfiguration"}

<span data-ttu-id="d756d-106">Cmdlet CsAddressBookConfiguration 會傳回已存在之設定的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="d756d-106">The cmdlet Get-CsAddressBookConfiguration returns information about a configuration that already exists.</span></span>

<span data-ttu-id="d756d-107">例如：</span><span class="sxs-lookup"><span data-stu-id="d756d-107">For example:</span></span>

    Get-CsAddressBookConfiguration -Identity site:Redmond

<span data-ttu-id="d756d-108">結合 CsAddressBookConfiguration 和 Set CsAddressBookConfiguration 的功能，管理員可以定義要修改的設定，然後套用修改。</span><span class="sxs-lookup"><span data-stu-id="d756d-108">Combining the functionality of Get-CsAddressBookConfiguration and Set-CsAddressBookConfiguration allows the administrator to define which configurations to modify and then apply the modifications.</span></span> <span data-ttu-id="d756d-109">例如，以下是其中一種組合：</span><span class="sxs-lookup"><span data-stu-id="d756d-109">For example, this combined:</span></span>

    Get-CsAddressBookConfiguration -Filter site:* | Set-CsAddressBookConfiguration -RunTimeOfDay 23:00

<span data-ttu-id="d756d-110">會傳回所有網站中的所有設定，並將23:00 小時的 RunTimeOfDay 套用至設定。</span><span class="sxs-lookup"><span data-stu-id="d756d-110">Returns all configurations in all sites and applies the RunTimeOfDay of 23:00 hours to the configurations.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="d756d-111">請參閱</span><span class="sxs-lookup"><span data-stu-id="d756d-111">See Also</span></span>


[<span data-ttu-id="d756d-112">CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="d756d-112">Get-CsAddressBookConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAddressBookConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

