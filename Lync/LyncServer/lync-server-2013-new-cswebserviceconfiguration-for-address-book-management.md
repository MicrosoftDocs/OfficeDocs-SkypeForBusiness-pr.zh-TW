---
title: Lync Server 2013：針對通訊錄管理的新 CsWebServiceConfiguration
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
ms.openlocfilehash: 434c9a7c4ded9516cd930bbaa9bba72873b15a4f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738773"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="2260d-102">Lync Server 2013 中的通訊錄管理的新 CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="2260d-102">New-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2260d-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="2260d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="2260d-104">誰可以執行這個 Cmdlet：根據預設，下列群組的成員有權在本機執行新的 CsWebServiceConfiguration Cmdlet： RTCUniversalServerAdmins。</span><span class="sxs-lookup"><span data-stu-id="2260d-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the New-CsWebServiceConfiguration cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="2260d-105">若要傳回已指派這個 Cmdlet 的所有角色式存取控制（RBAC）角色的清單（包括您自行建立的任何自訂 RBAC 角色），請在 Windows PowerShell 提示中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="2260d-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsWebServiceConfiguration"}

<span data-ttu-id="2260d-106">Cmdlet CsWebServiceConfiguration 為貴組織中的 Web 服務定義新的配置。</span><span class="sxs-lookup"><span data-stu-id="2260d-106">The cmdlet New-CsWebServiceConfiguration defines a new configuration for Web Services in your organization.</span></span> <span data-ttu-id="2260d-107">Web 服務配置的範圍只能位於網站或服務層級。</span><span class="sxs-lookup"><span data-stu-id="2260d-107">The scope for the Web Services configuration can only be at the site or service level.</span></span> <span data-ttu-id="2260d-108">它無法在全域層級建立新的 Web 服務設定。</span><span class="sxs-lookup"><span data-stu-id="2260d-108">It cannot create a new Web Services configuration at the global level.</span></span> <span data-ttu-id="2260d-109">[通訊錄] 的特別興趣是 EnableGroupExansion 屬性。</span><span class="sxs-lookup"><span data-stu-id="2260d-109">Specifically of interest to the Address Book is the EnableGroupExansion attribute.</span></span> <span data-ttu-id="2260d-110">如果設為 True，則 Web 服務可以回應群組延伸的要求。</span><span class="sxs-lookup"><span data-stu-id="2260d-110">If set to True, the Web Services can respond to requests for group expansion.</span></span>

<span data-ttu-id="2260d-111">例如：</span><span class="sxs-lookup"><span data-stu-id="2260d-111">For example:</span></span>

    New-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $False -UseCertificateAuth $True

<div>

## <a name="see-also"></a><span data-ttu-id="2260d-112">請參閱</span><span class="sxs-lookup"><span data-stu-id="2260d-112">See Also</span></span>


[<span data-ttu-id="2260d-113">New-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="2260d-113">New-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

