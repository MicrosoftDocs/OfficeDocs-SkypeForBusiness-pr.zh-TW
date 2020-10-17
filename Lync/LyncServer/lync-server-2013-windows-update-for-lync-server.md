---
title: Lync Server 2013： Lync Server 的 Windows 更新
description: Lync Server 2013： Lync Server 的 Windows 更新。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Windows Update for Lync Server 2013
ms:assetid: fe26ab32-b1a9-421d-9227-506703d4b834
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518337(v=OCS.15)
ms:contentKeyID: 62625495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe4b6d201a35584fceae5628b91631b48b30faae
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546059"
---
# <a name="windows-update-for-lync-server-2013"></a><span data-ttu-id="fe25d-103">Lync Server 2013 的 Windows 更新</span><span class="sxs-lookup"><span data-stu-id="fe25d-103">Windows Update for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe25d-104">_**主題上次修改日期：** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="fe25d-104">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="fe25d-105">經常使用 Windows Update Services 檢查並套用更新和安全性修補程式。</span><span class="sxs-lookup"><span data-stu-id="fe25d-105">Frequently check for and apply updates and security updates using Windows Update Services.</span></span> <span data-ttu-id="fe25d-106">這樣做可協助避免其他系統元件中的漏洞，這可能會導致攻擊者能夠透過系統管理員許可權取得執行 Microsoft Lync Server 2013 之伺服器的存取權，進而危及 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="fe25d-106">Doing so helps prevents vulnerabilities in other system components that might lead to attackers being able to gain access to servers running Microsoft Lync Server 2013 with administrator rights and thereby compromise Lync Server 2013.</span></span>

<span data-ttu-id="fe25d-107">在每個 Lync Server 2013 Standard Edition server (上的後端資料庫) 和所有其他 Lync Server 2013 server (role 上，如果您已將這些資料庫升級至 SQL Server 2008 R2 Express，則 Microsoft SQL Server 2008 Express (64-bit edition) 會在每個 Lync Server Standard Edition server 上執行的更新。</span><span class="sxs-lookup"><span data-stu-id="fe25d-107">Updates for Microsoft SQL Server 2008 Express (64-bit edition) runs on each Lync Server 2013 Standard Edition server (for the back-end database) and on all other Lync Server 2013 server roles (for the Local Configuration Store), unless you have upgraded these databases to SQL Server 2008 R2 Express.</span></span> <span data-ttu-id="fe25d-108">您應將這些資料庫，包括前端集區之後端資料庫上的 SQL Server、監控資料庫以及封存資料庫，都視為例行安全性更新維護的一部分。</span><span class="sxs-lookup"><span data-stu-id="fe25d-108">You should consider these databases as part of routine security update maintenance, as should SQL Server on the back-end database of a Front End pool, the Monitoring database, and the Archiving database.</span></span>

<div>

## <a name="best-practice"></a><span data-ttu-id="fe25d-109">最佳作法</span><span class="sxs-lookup"><span data-stu-id="fe25d-109">Best Practice</span></span>

  - <span data-ttu-id="fe25d-110">使用 Windows Update 維持最新狀態。</span><span class="sxs-lookup"><span data-stu-id="fe25d-110">Keep current with Windows Update.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

