---
title: Lync Server 2013：授與許可權
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
ms.openlocfilehash: 3e69cb3c8638cb11ababac73d0f8fe4025bbda24
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498880"
---
# <a name="granting-permissions-in-lync-server-2013"></a><span data-ttu-id="f8e5a-102">在 Lync Server 2013 中授與許可權</span><span class="sxs-lookup"><span data-stu-id="f8e5a-102">Granting permissions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8e5a-103">_**主題上次修改日期：** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="f8e5a-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="f8e5a-104">針對安裝程式，您可以將許可權授與特定 Active Directory 組織單位 (OU) 的 RTCUniversalServerAdmins 通用群組，啟用該 OU 中 RTCUniversalServerAdmins 群組的成員，以在指定的網域中安裝 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="f8e5a-104">For setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain.</span></span> <span data-ttu-id="f8e5a-105">當您授與 OU 的許可權時，會授與下列許可權：</span><span class="sxs-lookup"><span data-stu-id="f8e5a-105">When you grant permissions for an OU, the following permissions are granted:</span></span>

  - <span data-ttu-id="f8e5a-106">讀取</span><span class="sxs-lookup"><span data-stu-id="f8e5a-106">Read</span></span>

  - <span data-ttu-id="f8e5a-107">寫入</span><span class="sxs-lookup"><span data-stu-id="f8e5a-107">Write</span></span>

  - <span data-ttu-id="f8e5a-108">ReadSPN</span><span class="sxs-lookup"><span data-stu-id="f8e5a-108">ReadSPN</span></span>

  - <span data-ttu-id="f8e5a-109">WriteSPN</span><span class="sxs-lookup"><span data-stu-id="f8e5a-109">WriteSPN</span></span>

<span data-ttu-id="f8e5a-110">為了進行管理，您可以將許可權新增至指定的 Ou，使樹系準備建立的 RTC 通用群組成員可以存取 Ou，而不需要是 Domain Admins 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="f8e5a-110">For administration, you can add permissions to specified OUs so that members of the RTC universal groups created by forest preparation can access the OUs without needing to be members of the Domain Admins group.</span></span> <span data-ttu-id="f8e5a-111">新增至指定 OU 的許可權，與 **Enable-CsAdDomain** Cmdlet 新增至電腦和使用者 OU 容器的許可權相同。</span><span class="sxs-lookup"><span data-stu-id="f8e5a-111">The permissions added to the specified OU are the same permissions that the **Enable-CsAdDomain** cmdlet adds to the computers and users OU containers.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f8e5a-112">本章節內容</span><span class="sxs-lookup"><span data-stu-id="f8e5a-112">In This Section</span></span>

  - [<span data-ttu-id="f8e5a-113">在 Lync Server 2013 中授與設定許可權</span><span class="sxs-lookup"><span data-stu-id="f8e5a-113">Granting setup permissions in Lync Server 2013</span></span>](lync-server-2013-granting-setup-permissions.md)

  - [<span data-ttu-id="f8e5a-114">在 Lync Server 2013 中授與組織單位許可權</span><span class="sxs-lookup"><span data-stu-id="f8e5a-114">Granting organizational unit permissions in Lync Server 2013</span></span>](lync-server-2013-granting-organizational-unit-permissions.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

