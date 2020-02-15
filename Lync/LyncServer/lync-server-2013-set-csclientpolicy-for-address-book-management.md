---
title: 'Lync Server 2013: Set-CsClientPolicy 適用於通訊錄管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set-CsClientPolicy for Address Book management
ms:assetid: e7788bea-606f-481a-a3a4-1855ac028493
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429723(v=OCS.15)
ms:contentKeyID: 48185726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f726e42d5827c153cac08a11e43d4e4f9423da1d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046546"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-csclientpolicy-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="8bb0d-102">適用於 Lync Server 2013 中的通訊錄管理的 Set-csclientpolicy</span><span class="sxs-lookup"><span data-stu-id="8bb0d-102">Set-CsClientPolicy for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8bb0d-103">_**主題上次修改日期：** 2012年-11-01_</span><span class="sxs-lookup"><span data-stu-id="8bb0d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="8bb0d-104">誰可以執行此 Cmdlet：下列群組的成員預設會獲授權可以在本機上執行 Set-CsClientPolicy Cmdlet：RTCUniversalServerAdmins。</span><span class="sxs-lookup"><span data-stu-id="8bb0d-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Set-CsClientPolicy cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="8bb0d-105">若要傳回所有獲指派此 Cmdlet 的角色型存取控制 (RBAC) 角色清單 (包括您自行建立的自訂 RBAC 角色)，請在 Windows PowerShell 命令提示中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="8bb0d-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClientPolicy"}

<span data-ttu-id="8bb0d-106">類似於 New-csclientpolicy，Set-csclientpolicy cmdlet 可讓您修改已經已備妥的用戶端設定。</span><span class="sxs-lookup"><span data-stu-id="8bb0d-106">Similar to New-CsClientPolicy, the Set-CsClientPolicy cmdlet allows you to modify client settings that are already in place.</span></span>

<span data-ttu-id="8bb0d-107">例如：</span><span class="sxs-lookup"><span data-stu-id="8bb0d-107">For example:</span></span>

    Set-CsClientPolicy -Identity RedmondClientPolicy -WebServicePollInterval "00:15:00" -AddressBookAvailability "WebSearchAndFileDownload"

<div>

## <a name="see-also"></a><span data-ttu-id="8bb0d-108">請參閱</span><span class="sxs-lookup"><span data-stu-id="8bb0d-108">See Also</span></span>


[<span data-ttu-id="8bb0d-109">Set-csclientpolicy</span><span class="sxs-lookup"><span data-stu-id="8bb0d-109">Set-CsClientPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

