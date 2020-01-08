---
title: Lync Server 2013：針對通訊錄管理的新 CsClientPolicy
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New-CsClientPolicy for Address Book management
ms:assetid: ef4415fc-82c4-4dc8-97d1-37a084553343
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429726(v=OCS.15)
ms:contentKeyID: 48185771
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77cf1f7ebe085fc11d23381db9d1c474c79403d0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974493"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-csclientpolicy-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="0d953-102">Lync Server 2013 中的通訊錄管理的新 CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="0d953-102">New-CsClientPolicy for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d953-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="0d953-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="0d953-104">誰可以執行這個 Cmdlet：根據預設，下列群組的成員有權執行新的 CsClientPolicy Cmdlet： RTCUniversalServerAdmins。</span><span class="sxs-lookup"><span data-stu-id="0d953-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the New-CsClientPolicy cmdlet: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="0d953-105">若要傳回已指派這個 Cmdlet 的所有角色式存取控制（RBAC）角色的清單（包括您自行建立的任何自訂 RBAC 角色），請在 Windows PowerShell 提示中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="0d953-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsClientPolicy"}

<span data-ttu-id="0d953-106">Cmdlet New-CsClientPolicy 會定義大量設定，以便為 Lync Server 2013 中提供的功能提供客戶。</span><span class="sxs-lookup"><span data-stu-id="0d953-106">The cmdlet New-CsClientPolicy defines a large number of settings for provisioning clients for features that are available in Lync Server 2013.</span></span> <span data-ttu-id="0d953-107">針對通訊錄服務，參數 AddressBookAvailability 是有意義的。</span><span class="sxs-lookup"><span data-stu-id="0d953-107">For the Address Book Service, the parameter AddressBookAvailability is of interest.</span></span> <span data-ttu-id="0d953-108">這個參數會直接影響用戶端可用的選項，有三種可能的選項：</span><span class="sxs-lookup"><span data-stu-id="0d953-108">This parameter, which directly impacts the options available to clients, has three possible options:</span></span>

  - <span data-ttu-id="0d953-109">WebSearchAndFileDownload</span><span class="sxs-lookup"><span data-stu-id="0d953-109">WebSearchAndFileDownload</span></span>

  - <span data-ttu-id="0d953-110">WebSearchOnly</span><span class="sxs-lookup"><span data-stu-id="0d953-110">WebSearchOnly</span></span>

  - <span data-ttu-id="0d953-111">FileDownloadOnly</span><span class="sxs-lookup"><span data-stu-id="0d953-111">FileDownloadOnly</span></span>

<span data-ttu-id="0d953-112">定義後，會決定用戶端存取通訊錄的方式。</span><span class="sxs-lookup"><span data-stu-id="0d953-112">When defined, it determines how the Address Book is accessed by clients.</span></span> <span data-ttu-id="0d953-113">如果您定義此參數，您必須定義其中一個選項。</span><span class="sxs-lookup"><span data-stu-id="0d953-113">If you define this parameter, you must define one of the options.</span></span> <span data-ttu-id="0d953-114">如果您不修改此設定，預設 WebSearchAndFileDownload 會保持生效。</span><span class="sxs-lookup"><span data-stu-id="0d953-114">If you do not modify this setting, the default WebSearchAndFileDownload remains in effect.</span></span>

<span data-ttu-id="0d953-115">例如：</span><span class="sxs-lookup"><span data-stu-id="0d953-115">For example:</span></span>

    New-CsClientPolicy -Identity RedmondClientPolicy -DisableCalendarPresence $True -DisablePhonePresence $True -DisplayPhoto "PhotosFromADOnly" -AddressBookAvailability "WebSearchOnly"

<div>

## <a name="see-also"></a><span data-ttu-id="0d953-116">請參閱</span><span class="sxs-lookup"><span data-stu-id="0d953-116">See Also</span></span>


[<span data-ttu-id="0d953-117">New-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="0d953-117">New-CsClientPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

