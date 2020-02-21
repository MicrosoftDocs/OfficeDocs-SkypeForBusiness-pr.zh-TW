---
title: Lync Server 2013： 授與權限
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
ms.openlocfilehash: 20679f910ead1f1b7cab45fde658b38233c644f3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="granting-permissions-in-lync-server-2013"></a><span data-ttu-id="f6cca-102">授與 Lync Server 2013 中的權限</span><span class="sxs-lookup"><span data-stu-id="f6cca-102">Granting permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6cca-103">_**主題上次修改日期：** 2012 年 10 月 15_</span><span class="sxs-lookup"><span data-stu-id="f6cca-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="f6cca-104">安裝程式，您可以授與權限的 RTCUniversalServerAdmins 萬用群組特定 Active Directory 組織單位 (OU)，讓該 OU 中指定的網域安裝 Lync Server 2013 中的 RTCUniversalServerAdmins 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="f6cca-104">For setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain.</span></span> <span data-ttu-id="f6cca-105">當您授與 OU 權限時，會授與下列權限：</span><span class="sxs-lookup"><span data-stu-id="f6cca-105">When you grant permissions for an OU, the following permissions are granted:</span></span>

  - <span data-ttu-id="f6cca-106">讀取</span><span class="sxs-lookup"><span data-stu-id="f6cca-106">Read</span></span>

  - <span data-ttu-id="f6cca-107">寫入</span><span class="sxs-lookup"><span data-stu-id="f6cca-107">Write</span></span>

  - <span data-ttu-id="f6cca-108">ReadSPN</span><span class="sxs-lookup"><span data-stu-id="f6cca-108">ReadSPN</span></span>

  - <span data-ttu-id="f6cca-109">WriteSPN</span><span class="sxs-lookup"><span data-stu-id="f6cca-109">WriteSPN</span></span>

<span data-ttu-id="f6cca-110">管理，您可以指定 ou 新增權限，使樹系準備所建立的 RTC 萬用群組的成員能夠存取 Ou，而不需要成為 Domain Admins 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="f6cca-110">For administration, you can add permissions to specified OUs so that members of the RTC universal groups created by forest preparation can access the OUs without needing to be members of the Domain Admins group.</span></span> <span data-ttu-id="f6cca-111">新增至所指定 OU 權限是相同的權限**Enable-csaddomain** cmdlet 新增至電腦和使用者的 OU 容器。</span><span class="sxs-lookup"><span data-stu-id="f6cca-111">The permissions added to the specified OU are the same permissions that the **Enable-CsAdDomain** cmdlet adds to the computers and users OU containers.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f6cca-112">本章節內容</span><span class="sxs-lookup"><span data-stu-id="f6cca-112">In This Section</span></span>

  - [<span data-ttu-id="f6cca-113">授與 Lync Server 2013 中的設定權限</span><span class="sxs-lookup"><span data-stu-id="f6cca-113">Granting setup permissions in Lync Server 2013</span></span>](lync-server-2013-granting-setup-permissions.md)

  - [<span data-ttu-id="f6cca-114">授與 Lync Server 2013 中的組織單位權限</span><span class="sxs-lookup"><span data-stu-id="f6cca-114">Granting organizational unit permissions in Lync Server 2013</span></span>](lync-server-2013-granting-organizational-unit-permissions.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

