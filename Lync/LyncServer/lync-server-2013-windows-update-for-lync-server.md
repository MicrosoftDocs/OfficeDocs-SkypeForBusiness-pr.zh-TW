---
title: 'Lync Server 2013: Lync server 的 Windows 更新'
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
ms.openlocfilehash: e70ac17e27508a7922d8353e6142b3b5f05b34e9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041142"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="windows-update-for-lync-server-2013"></a><span data-ttu-id="d8d79-102">Lync Server 2013 的 Windows 更新</span><span class="sxs-lookup"><span data-stu-id="d8d79-102">Windows Update for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8d79-103">_**上次修改主題：** 2013年-12-05_</span><span class="sxs-lookup"><span data-stu-id="d8d79-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="d8d79-104">經常使用 Windows Update Services 檢查並套用更新和安全性修補程式。</span><span class="sxs-lookup"><span data-stu-id="d8d79-104">Frequently check for and apply updates and security updates using Windows Update Services.</span></span> <span data-ttu-id="d8d79-105">這樣才能協助避免可能導致攻擊者能夠存取系統管理員權限執行 Microsoft Lync Server 2013 的伺服器，進而危害 Lync Server 2013 的其他系統元件的弱點。</span><span class="sxs-lookup"><span data-stu-id="d8d79-105">Doing so helps prevents vulnerabilities in other system components that might lead to attackers being able to gain access to servers running Microsoft Lync Server 2013 with administrator rights and thereby compromise Lync Server 2013.</span></span>

<span data-ttu-id="d8d79-106">Microsoft SQL Server 2008 Express （64 位元版本） 的更新在執行每個 Lync Server 2013 Standard Edition （後端資料庫伺服器），在其他所有 Lync Server 2013 伺服器角色 （適用於本機設定存放區），除非您已升級這些SQL Server 2008 R2 express 資料庫。</span><span class="sxs-lookup"><span data-stu-id="d8d79-106">Updates for Microsoft SQL Server 2008 Express (64-bit edition) runs on each Lync Server 2013 Standard Edition server (for the back-end database) and on all other Lync Server 2013 server roles (for the Local Configuration Store), unless you have upgraded these databases to SQL Server 2008 R2 Express.</span></span> <span data-ttu-id="d8d79-107">您應將這些資料庫，包括前端集區之後端資料庫上的 SQL Server、監控資料庫以及封存資料庫，都視為例行安全性更新維護的一部分。</span><span class="sxs-lookup"><span data-stu-id="d8d79-107">You should consider these databases as part of routine security update maintenance, as should SQL Server on the back-end database of a Front End pool, the Monitoring database, and the Archiving database.</span></span>

<div>

## <a name="best-practice"></a><span data-ttu-id="d8d79-108">最佳作法</span><span class="sxs-lookup"><span data-stu-id="d8d79-108">Best Practice</span></span>

  - <span data-ttu-id="d8d79-109">使用 Windows Update 維持最新狀態。</span><span class="sxs-lookup"><span data-stu-id="d8d79-109">Keep current with Windows Update.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

