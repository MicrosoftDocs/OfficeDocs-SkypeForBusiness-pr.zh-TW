---
title: Lync Server 2013：準備鎖定的 Active Directory 網域服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing a locked-down Active Directory Domain Services
ms:assetid: 68bde963-3fa3-4102-88d6-ac931c1dd2d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398492(v=OCS.15)
ms:contentKeyID: 48184377
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d589fbc6b7d31b38bc788ba9851edf4386294ea
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747453"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-a-locked-down-active-directory-domain-services-in-lync-server-2013"></a><span data-ttu-id="13cdd-102">在 Lync Server 2013 中準備鎖定的 Active Directory 網域服務</span><span class="sxs-lookup"><span data-stu-id="13cdd-102">Preparing a locked-down Active Directory Domain Services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13cdd-103">_**主題上次修改日期：** 2012-05-14_</span><span class="sxs-lookup"><span data-stu-id="13cdd-103">_**Topic Last Modified:** 2012-05-14_</span></span>

<span data-ttu-id="13cdd-104">組織通常會鎖定 Active Directory 網域服務，以協助減輕安全性風險。</span><span class="sxs-lookup"><span data-stu-id="13cdd-104">Organizations often lock down Active Directory Domain Services to help mitigate security risks.</span></span> <span data-ttu-id="13cdd-105">不過，鎖定的 Active Directory 環境可以限制 Lync Server 2013 所需的許可權。</span><span class="sxs-lookup"><span data-stu-id="13cdd-105">However, a locked-down Active Directory environment can limit the permissions that Lync Server 2013 requires.</span></span> <span data-ttu-id="13cdd-106">針對 Lync Server 2013 正確地準備鎖定的 Active Directory 環境，涉及一些其他的考慮和步驟。</span><span class="sxs-lookup"><span data-stu-id="13cdd-106">Properly preparing a locked-down Active Directory environment for Lync Server 2013 involves some additional considerations and steps.</span></span>

<span data-ttu-id="13cdd-107">在鎖定的 Active Directory 環境中，許可權受到限制的兩種常見方式如下：</span><span class="sxs-lookup"><span data-stu-id="13cdd-107">Two common ways in which permissions are limited in a locked-down Active Directory environment are as follows:</span></span>

  - <span data-ttu-id="13cdd-108">已從容器中移除經過驗證的使用者存取控制專案（Ace）。</span><span class="sxs-lookup"><span data-stu-id="13cdd-108">Authenticated user access control entries (ACEs) are removed from containers.</span></span>

  - <span data-ttu-id="13cdd-109">在使用者、連絡人、InetOrgPerson 或電腦物件的容器上停用許可權繼承。</span><span class="sxs-lookup"><span data-stu-id="13cdd-109">Permissions inheritance is disabled on containers of User, Contact, InetOrgPerson, or Computer objects.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="13cdd-110">本節內容</span><span class="sxs-lookup"><span data-stu-id="13cdd-110">In This Section</span></span>

  - [<span data-ttu-id="13cdd-111">Lync Server 2013 中已移除已驗證使用者權限</span><span class="sxs-lookup"><span data-stu-id="13cdd-111">Authenticated user permissions are removed in Lync Server 2013</span></span>](lync-server-2013-authenticated-user-permissions-are-removed.md)

  - [<span data-ttu-id="13cdd-112">Lync Server 2013 中的 Computers、Users 或 InetOrgPerson 容器已停用權限繼承</span><span class="sxs-lookup"><span data-stu-id="13cdd-112">Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013</span></span>](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

