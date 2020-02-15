---
title: 'Lync Server 2013: New-CsWebServiceConfiguration 適用於通訊錄管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New-CsWebServiceConfiguration for Address Book management
ms:assetid: 49e4ecc5-aa3e-4dd4-a32c-b0dea3758fab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429703(v=OCS.15)
ms:contentKeyID: 48184067
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ccc4eafd9fd7db6173b14c17b44218c122ad01b8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051381"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="8c0f4-102">適用於通訊錄管理 Lync Server 2013 中的新 CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="8c0f4-102">New-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c0f4-103">_**主題上次修改日期：** 2012年-11-01_</span><span class="sxs-lookup"><span data-stu-id="8c0f4-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="8c0f4-p101">誰可以執行這個 Cmdlet：根據預設，會授權下列群組的成員在本機執行 New-CsWebServiceConfiguration Cmdlet：RTCUniversalServerAdmins。若要傳回指派給該 Cmdlet 的所有角色型存取控制 (RBAC) 角色清單 (包括您自己建立的任何自訂 RBAC 角色)，請在 Windows PowerShell 提示中輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="8c0f4-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the New-CsWebServiceConfiguration cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsWebServiceConfiguration"}

<span data-ttu-id="8c0f4-p102">New-CsWebServiceConfiguration 這個 Cmdlet 會為組織中的 Web 服務定義新的組態。Web 服務組態的範圍只能在網站或服務層級。無法在全域層級建立新的 Web 服務組態。對電話簿而言特別重要的是 EnableGroupExansion 屬性。如果設為 True，則 Web 服務可以回應群組擴充的要求。</span><span class="sxs-lookup"><span data-stu-id="8c0f4-p102">The cmdlet New-CsWebServiceConfiguration defines a new configuration for Web Services in your organization. The scope for the Web Services configuration can only be at the site or service level. It cannot create a new Web Services configuration at the global level. Specifically of interest to the Address Book is the EnableGroupExansion attribute. If set to True, the Web Services can respond to requests for group expansion.</span></span>

<span data-ttu-id="8c0f4-111">例如：</span><span class="sxs-lookup"><span data-stu-id="8c0f4-111">For example:</span></span>

    New-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $False -UseCertificateAuth $True

<div>

## <a name="see-also"></a><span data-ttu-id="8c0f4-112">請參閱</span><span class="sxs-lookup"><span data-stu-id="8c0f4-112">See Also</span></span>


[<span data-ttu-id="8c0f4-113">New-cswebserviceconfiguration</span><span class="sxs-lookup"><span data-stu-id="8c0f4-113">New-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

