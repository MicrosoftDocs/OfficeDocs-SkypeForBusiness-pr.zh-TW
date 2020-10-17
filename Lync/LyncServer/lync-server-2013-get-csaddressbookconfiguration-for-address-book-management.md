---
title: Lync Server 2013：用於通訊錄管理的 Get-CsAddressBookConfiguration
description: Lync Server 2013：用於通訊錄管理的 Get-CsAddressBookConfiguration。
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
ms.openlocfilehash: 91b96aead7b7038464f3166691a5952b9ff850dc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566999"
---
# <a name="get-csaddressbookconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="9f443-103">Lync Server 2013 中用於通訊錄管理的 Get-CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="9f443-103">Get-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f443-104">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="9f443-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="9f443-105">誰可以執行此 Cmdlet：根據預設，會授權下列群組的成員在本機執行 Get-CsAddressBookConfiguration Cmdlet： RTCUniversalServerAdmins。</span><span class="sxs-lookup"><span data-stu-id="9f443-105">Who can run this cmdlet: By default, members of the following groups are authorized to run the Get-CsAddressBookConfiguration cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="9f443-106">若要傳回所有獲指派此 Cmdlet 的角色型存取控制 (RBAC) 角色清單 (包括您自行建立的自訂 RBAC 角色)，請在 Windows PowerShell 命令提示中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="9f443-106">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsAddressBookConfiguration"}

<span data-ttu-id="9f443-107">Cmdlet Get-CsAddressBookConfiguration 會傳回已存在之設定的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="9f443-107">The cmdlet Get-CsAddressBookConfiguration returns information about a configuration that already exists.</span></span>

<span data-ttu-id="9f443-108">例如：</span><span class="sxs-lookup"><span data-stu-id="9f443-108">For example:</span></span>

    Get-CsAddressBookConfiguration -Identity site:Redmond

<span data-ttu-id="9f443-109">結合 Get-CsAddressBookConfiguration 和 Set-CsAddressBookConfiguration 的功能可讓系統管理員定義要修改的設定，然後套用修改。</span><span class="sxs-lookup"><span data-stu-id="9f443-109">Combining the functionality of Get-CsAddressBookConfiguration and Set-CsAddressBookConfiguration allows the administrator to define which configurations to modify and then apply the modifications.</span></span> <span data-ttu-id="9f443-110">例如，這會結合下列專案：</span><span class="sxs-lookup"><span data-stu-id="9f443-110">For example, this combined:</span></span>

    Get-CsAddressBookConfiguration -Filter site:* | Set-CsAddressBookConfiguration -RunTimeOfDay 23:00

<span data-ttu-id="9f443-111">會傳回所有網站中的所有設定，並將23:00 小時的 RunTimeOfDay 套用至設定。</span><span class="sxs-lookup"><span data-stu-id="9f443-111">Returns all configurations in all sites and applies the RunTimeOfDay of 23:00 hours to the configurations.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="9f443-112">另請參閱</span><span class="sxs-lookup"><span data-stu-id="9f443-112">See Also</span></span>


[<span data-ttu-id="9f443-113">Get-CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="9f443-113">Get-CsAddressBookConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAddressBookConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

