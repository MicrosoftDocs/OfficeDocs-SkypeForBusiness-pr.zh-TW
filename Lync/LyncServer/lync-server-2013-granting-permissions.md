---
title: Lync Server 2013：授與權限
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting permissions
ms:assetid: d1c9ea66-bd07-480e-99a0-011108f97e42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398901(v=OCS.15)
ms:contentKeyID: 48185446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ccfdf804fc9052ac69b383d0f8cd3321222e79a8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763897"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-permissions-in-lync-server-2013"></a><span data-ttu-id="a276f-102">Lync Server 2013 中的授與權限</span><span class="sxs-lookup"><span data-stu-id="a276f-102">Granting permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a276f-103">_**主題上次修改日期：** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="a276f-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="a276f-104">針對設定，您可以為特定 Active Directory 組織單位（OU）授予 RTCUniversalServerAdmins 通用群組的許可權，讓該 OU 中的 RTCUniversalServerAdmins 群組成員在指定的網域中安裝 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="a276f-104">For setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain.</span></span> <span data-ttu-id="a276f-105">當您授與 OU 的許可權時，系統會授與下列許可權：</span><span class="sxs-lookup"><span data-stu-id="a276f-105">When you grant permissions for an OU, the following permissions are granted:</span></span>

  - <span data-ttu-id="a276f-106">查看</span><span class="sxs-lookup"><span data-stu-id="a276f-106">Read</span></span>

  - <span data-ttu-id="a276f-107">撰寫</span><span class="sxs-lookup"><span data-stu-id="a276f-107">Write</span></span>

  - <span data-ttu-id="a276f-108">ReadSPN</span><span class="sxs-lookup"><span data-stu-id="a276f-108">ReadSPN</span></span>

  - <span data-ttu-id="a276f-109">WriteSPN</span><span class="sxs-lookup"><span data-stu-id="a276f-109">WriteSPN</span></span>

<span data-ttu-id="a276f-110">針對 [管理]，您可以在指定的 Ou 中新增許可權，讓「林準備」所建立的 RTC 通用群組成員無需成為網域系統管理員群組的成員，就能存取 Ou。</span><span class="sxs-lookup"><span data-stu-id="a276f-110">For administration, you can add permissions to specified OUs so that members of the RTC universal groups created by forest preparation can access the OUs without needing to be members of the Domain Admins group.</span></span> <span data-ttu-id="a276f-111">新增至指定 OU 的許可權與**Enable-CsAdDomain** Cmdlet 新增到電腦和使用者 OU 容器的許可權相同。</span><span class="sxs-lookup"><span data-stu-id="a276f-111">The permissions added to the specified OU are the same permissions that the **Enable-CsAdDomain** cmdlet adds to the computers and users OU containers.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a276f-112">本節內容</span><span class="sxs-lookup"><span data-stu-id="a276f-112">In This Section</span></span>

  - [<span data-ttu-id="a276f-113">在 Lync Server 2013 中授與設定權限</span><span class="sxs-lookup"><span data-stu-id="a276f-113">Granting setup permissions in Lync Server 2013</span></span>](lync-server-2013-granting-setup-permissions.md)

  - [<span data-ttu-id="a276f-114">在 Lync Server 2013 中授與組織單位權限</span><span class="sxs-lookup"><span data-stu-id="a276f-114">Granting organizational unit permissions in Lync Server 2013</span></span>](lync-server-2013-granting-organizational-unit-permissions.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

