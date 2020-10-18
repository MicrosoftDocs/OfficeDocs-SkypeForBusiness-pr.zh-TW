---
title: Lync Server 2013：用於通訊錄管理的 New-CsClientPolicy
description: Lync Server 2013：用於通訊錄管理的 New-CsClientPolicy。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New-CsClientPolicy for Address Book management
ms:assetid: ef4415fc-82c4-4dc8-97d1-37a084553343
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429726(v=OCS.15)
ms:contentKeyID: 48185771
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12c14534c7af447f30a01b1bbbd1679a8375c705
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578929"
---
# <a name="new-csclientpolicy-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="24cb5-103">Lync Server 2013 中用於通訊錄管理的 New-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="24cb5-103">New-CsClientPolicy for Address Book management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24cb5-104">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="24cb5-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="24cb5-105">誰可以執行這個 Cmdlet：根據預設，下列群組成員已獲得授權，可執行 New-CsClientPolicy Cmdlet：RTCUniversalServerAdmins。</span><span class="sxs-lookup"><span data-stu-id="24cb5-105">Who can run this cmdlet: By default, members of the following groups are authorized to run the New-CsClientPolicy cmdlet: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="24cb5-106">若要傳回所有獲指派此 Cmdlet 的角色型存取控制 (RBAC) 角色清單 (包括您自行建立的自訂 RBAC 角色)，請在 Windows PowerShell 命令提示中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="24cb5-106">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsClientPolicy"}

<span data-ttu-id="24cb5-107">Cmdlet New-CsClientPolicy 會定義大量設定，以提供 Lync Server 2013 中提供之功能的用戶端。</span><span class="sxs-lookup"><span data-stu-id="24cb5-107">The cmdlet New-CsClientPolicy defines a large number of settings for provisioning clients for features that are available in Lync Server 2013.</span></span> <span data-ttu-id="24cb5-108">在通訊錄服務中，參數 AddressBookAvailability 是有意義的。</span><span class="sxs-lookup"><span data-stu-id="24cb5-108">For the Address Book Service, the parameter AddressBookAvailability is of interest.</span></span> <span data-ttu-id="24cb5-109">此參數會直接影響用戶端可用的選項，有三種可能的選項：</span><span class="sxs-lookup"><span data-stu-id="24cb5-109">This parameter, which directly impacts the options available to clients, has three possible options:</span></span>

  - <span data-ttu-id="24cb5-110">WebSearchAndFileDownload</span><span class="sxs-lookup"><span data-stu-id="24cb5-110">WebSearchAndFileDownload</span></span>

  - <span data-ttu-id="24cb5-111">WebSearchOnly</span><span class="sxs-lookup"><span data-stu-id="24cb5-111">WebSearchOnly</span></span>

  - <span data-ttu-id="24cb5-112">FileDownloadOnly</span><span class="sxs-lookup"><span data-stu-id="24cb5-112">FileDownloadOnly</span></span>

<span data-ttu-id="24cb5-113">定義後，它會決定用戶端存取通訊錄的方式。</span><span class="sxs-lookup"><span data-stu-id="24cb5-113">When defined, it determines how the Address Book is accessed by clients.</span></span> <span data-ttu-id="24cb5-114">如果您定義此參數，則必須定義其中一個選項。</span><span class="sxs-lookup"><span data-stu-id="24cb5-114">If you define this parameter, you must define one of the options.</span></span> <span data-ttu-id="24cb5-115">如果您未修改此設定，則預設 WebSearchAndFileDownload 會保持作用。</span><span class="sxs-lookup"><span data-stu-id="24cb5-115">If you do not modify this setting, the default WebSearchAndFileDownload remains in effect.</span></span>

<span data-ttu-id="24cb5-116">例如：</span><span class="sxs-lookup"><span data-stu-id="24cb5-116">For example:</span></span>

    New-CsClientPolicy -Identity RedmondClientPolicy -DisableCalendarPresence $True -DisablePhonePresence $True -DisplayPhoto "PhotosFromADOnly" -AddressBookAvailability "WebSearchOnly"

<div>

## <a name="see-also"></a><span data-ttu-id="24cb5-117">請參閱</span><span class="sxs-lookup"><span data-stu-id="24cb5-117">See Also</span></span>


[<span data-ttu-id="24cb5-118">New-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="24cb5-118">New-CsClientPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

