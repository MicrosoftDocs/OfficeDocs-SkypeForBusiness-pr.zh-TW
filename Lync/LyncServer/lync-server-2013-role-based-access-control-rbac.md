---
title: 'Lync Server 2013：以角色為基礎的存取控制 (RBAC) '
description: Lync Server 2013：以角色為基礎的存取控制 (RBAC) 。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Role-based access control (RBAC) for Lync Server 2013
ms:assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481134(v=OCS.15)
ms:contentKeyID: 59893872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6586517083ff6cd2c4e20d83e9b8f861edf800c0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576579"
---
# <a name="role-based-access-control-rbac-for-lync-server-2013"></a><span data-ttu-id="10dbe-103">Lync Server 2013 的以角色為基礎的存取控制 (RBAC) </span><span class="sxs-lookup"><span data-stu-id="10dbe-103">Role-based access control (RBAC) for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10dbe-104">_**主題上次修改日期：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="10dbe-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="10dbe-105">Microsoft Lync Server 2013 包括 Role-Based 存取控制 (RBAC) 群組，可讓您委派管理工作，同時維持高安全性標準。</span><span class="sxs-lookup"><span data-stu-id="10dbe-105">Microsoft Lync Server 2013 includes Role-Based Access Control (RBAC) groups to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="10dbe-106">這些群組是在樹系準備期間建立的。</span><span class="sxs-lookup"><span data-stu-id="10dbe-106">These groups are created during forest preparation.</span></span> <span data-ttu-id="10dbe-107">如需樹系準備的詳細資訊，請參閱 [Lync Server 2013 的 Active Directory 網域服務](lync-server-2013-active-directory-domain-services-for-lync-server.md)。</span><span class="sxs-lookup"><span data-stu-id="10dbe-107">For details about forest preparation, see [Active Directory Domain Services for Lync Server 2013](lync-server-2013-active-directory-domain-services-for-lync-server.md).</span></span> <span data-ttu-id="10dbe-108">如需「樹系準備」所建立之特定群組的詳細資訊，請參閱部署檔中的 [Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) 中的「樹系準備」所做的變更。</span><span class="sxs-lookup"><span data-stu-id="10dbe-108">For details about the specific groups created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="10dbe-109">使用 RBAC，可藉由指派使用者給預先定義的系統管理角色，授與系統管理權限，包括 11 個預先定義角色，涵蓋許多常用系統管理工作。</span><span class="sxs-lookup"><span data-stu-id="10dbe-109">With RBAC, administrative privilege is granted by assigning users to pre-defined administrative roles, including the 11 predefined roles that cover many common administrative tasks.</span></span> <span data-ttu-id="10dbe-110">每個角色都與特定清單的 Lync Server 管理命令介面 Cmdlet 相關聯，讓該角色中的使用者能夠執行。</span><span class="sxs-lookup"><span data-stu-id="10dbe-110">Each role is associated with a specific list of Lync Server Management Shell cmdlets that users in that role are allowed to run.</span></span> <span data-ttu-id="10dbe-111">您可以使用 RBAC 遵循「最低權限」的原則，使用者只會授與其工作需要的系統管理能力。</span><span class="sxs-lookup"><span data-stu-id="10dbe-111">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative abilities that their jobs require.</span></span> <span data-ttu-id="10dbe-112">如需詳細資訊，請參閱規劃檔中的 [規劃 Lync Server 2013 中的角色型存取控制](lync-server-2013-planning-for-role-based-access-control.md) 。</span><span class="sxs-lookup"><span data-stu-id="10dbe-112">For details, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

