---
title: 'Lync Server 2013: New-CsClientPolicy 適用於通訊錄管理'
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
ms.openlocfilehash: 30ee2dff06f2881906793043f1dc039f57919a67
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216959"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-csclientpolicy-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="2b47d-102">適用於通訊錄管理 Lync Server 2013 中的新 CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="2b47d-102">New-CsClientPolicy for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b47d-103">_**主題上次修改日期：** 2012年-11-01_</span><span class="sxs-lookup"><span data-stu-id="2b47d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="2b47d-104">誰可以執行這個 Cmdlet：根據預設，下列群組成員已獲得授權，可執行 New-CsClientPolicy Cmdlet：RTCUniversalServerAdmins。</span><span class="sxs-lookup"><span data-stu-id="2b47d-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the New-CsClientPolicy cmdlet: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="2b47d-105">若要傳回所有獲指派此 Cmdlet 的角色型存取控制 (RBAC) 角色清單 (包括您自行建立的自訂 RBAC 角色)，請在 Windows PowerShell 命令提示中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="2b47d-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsClientPolicy"}

<span data-ttu-id="2b47d-106">此 cmdlet New-csclientpolicy 定義大量設定如佈建 Lync Server 2013 中可用的功能的用戶端。</span><span class="sxs-lookup"><span data-stu-id="2b47d-106">The cmdlet New-CsClientPolicy defines a large number of settings for provisioning clients for features that are available in Lync Server 2013.</span></span> <span data-ttu-id="2b47d-107">若為通訊錄服務，參數 AddressBookAvailability 是感興趣。</span><span class="sxs-lookup"><span data-stu-id="2b47d-107">For the Address Book Service, the parameter AddressBookAvailability is of interest.</span></span> <span data-ttu-id="2b47d-108">此參數，直接影響用戶端可用的選項，有三個可能的選項：</span><span class="sxs-lookup"><span data-stu-id="2b47d-108">This parameter, which directly impacts the options available to clients, has three possible options:</span></span>

  - <span data-ttu-id="2b47d-109">WebSearchAndFileDownload</span><span class="sxs-lookup"><span data-stu-id="2b47d-109">WebSearchAndFileDownload</span></span>

  - <span data-ttu-id="2b47d-110">WebSearchOnly</span><span class="sxs-lookup"><span data-stu-id="2b47d-110">WebSearchOnly</span></span>

  - <span data-ttu-id="2b47d-111">FileDownloadOnly</span><span class="sxs-lookup"><span data-stu-id="2b47d-111">FileDownloadOnly</span></span>

<span data-ttu-id="2b47d-112">定義時，它會決定用戶端存取通訊錄的方式。</span><span class="sxs-lookup"><span data-stu-id="2b47d-112">When defined, it determines how the Address Book is accessed by clients.</span></span> <span data-ttu-id="2b47d-113">如果您定義此參數，您必須定義其中一個選項。</span><span class="sxs-lookup"><span data-stu-id="2b47d-113">If you define this parameter, you must define one of the options.</span></span> <span data-ttu-id="2b47d-114">如果您不要修改此設定，預設 WebSearchAndFileDownload 仍然有效。</span><span class="sxs-lookup"><span data-stu-id="2b47d-114">If you do not modify this setting, the default WebSearchAndFileDownload remains in effect.</span></span>

<span data-ttu-id="2b47d-115">例如：</span><span class="sxs-lookup"><span data-stu-id="2b47d-115">For example:</span></span>

    New-CsClientPolicy -Identity RedmondClientPolicy -DisableCalendarPresence $True -DisablePhonePresence $True -DisplayPhoto "PhotosFromADOnly" -AddressBookAvailability "WebSearchOnly"

<div>

## <a name="see-also"></a><span data-ttu-id="2b47d-116">請參閱</span><span class="sxs-lookup"><span data-stu-id="2b47d-116">See Also</span></span>


[<span data-ttu-id="2b47d-117">New-csclientpolicy</span><span class="sxs-lookup"><span data-stu-id="2b47d-117">New-CsClientPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

