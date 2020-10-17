---
title: Lync Server 2013：用於通訊錄管理的 Remove-CsWebServiceConfiguration
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove-CsWebServiceConfiguration for Address Book management
ms:assetid: 91947cad-5cdd-41b9-83e1-650703c55879
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429713(v=OCS.15)
ms:contentKeyID: 48184848
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 62ad914027fc1d406ba66d2dead2b8eab7601ff7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536490"
---
# <a name="remove-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="42be7-102">Lync Server 2013 中用於通訊錄管理的 Remove-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="42be7-102">Remove-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42be7-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="42be7-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="42be7-104">誰可以執行此 Cmdlet：下列群組的成員預設會獲授權可以在本機上執行 Remove-CsWebServiceConfiguration Cmdlet：RTCUniversalServerAdmins。</span><span class="sxs-lookup"><span data-stu-id="42be7-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Remove-CsWebServiceConfiguration cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="42be7-105">若要傳回所有獲指派此 Cmdlet 的角色型存取控制 (RBAC) 角色清單 (包括您自行建立的自訂 RBAC 角色)，請在 Windows PowerShell 命令提示中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="42be7-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Remove-CsWebServiceConfiguration"}

<span data-ttu-id="42be7-106">Remove-CsWebServiceConfiguration Cmdlet 可讓系統管理員移除先前建立的 Web 服務設定。</span><span class="sxs-lookup"><span data-stu-id="42be7-106">The Remove-CsWebServiceConfiguration cmdlet allows an administrator to remove a previously created Web Services configuration.</span></span> <span data-ttu-id="42be7-107">Cmdlet 無法移除全域 Web 服務設定。</span><span class="sxs-lookup"><span data-stu-id="42be7-107">The cmdlet cannot remove the global Web Services configuration.</span></span>

<span data-ttu-id="42be7-108">例如：</span><span class="sxs-lookup"><span data-stu-id="42be7-108">For example:</span></span>

    Remove-CsWebServiceConfiguration -Identity site:Redmond

<div>

## <a name="see-also"></a><span data-ttu-id="42be7-109">請參閱</span><span class="sxs-lookup"><span data-stu-id="42be7-109">See Also</span></span>


[<span data-ttu-id="42be7-110">Remove-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="42be7-110">Remove-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

