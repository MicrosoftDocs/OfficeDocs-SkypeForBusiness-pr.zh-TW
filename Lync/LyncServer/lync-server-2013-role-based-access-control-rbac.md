---
title: Lync Server 2013：以角色為基礎的存取控制（RBAC）
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
ms.openlocfilehash: 2fc2da0c832ded3c0241d3e50197f98f07c2a96a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732983"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="role-based-access-control-rbac-for-lync-server-2013"></a><span data-ttu-id="c0569-102">Lync Server 2013 的角色式存取控制（RBAC）</span><span class="sxs-lookup"><span data-stu-id="c0569-102">Role-based access control (RBAC) for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0569-103">_**主題上次修改日期：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="c0569-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="c0569-104">Microsoft Lync Server 2013 包含以角色為基礎的存取控制（RBAC）群組，可讓您委派管理工作，同時維持高安全性的標準。</span><span class="sxs-lookup"><span data-stu-id="c0569-104">Microsoft Lync Server 2013 includes Role-Based Access Control (RBAC) groups to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="c0569-105">這些群組是在林準備期間建立的。</span><span class="sxs-lookup"><span data-stu-id="c0569-105">These groups are created during forest preparation.</span></span> <span data-ttu-id="c0569-106">如需林準備的詳細資料，請參閱[Lync Server 2013 的 Active Directory 網域服務](lync-server-2013-active-directory-domain-services-for-lync-server.md)。</span><span class="sxs-lookup"><span data-stu-id="c0569-106">For details about forest preparation, see [Active Directory Domain Services for Lync Server 2013](lync-server-2013-active-directory-domain-services-for-lync-server.md).</span></span> <span data-ttu-id="c0569-107">如需有關林準備所建立之特定群組的詳細資訊，請參閱部署檔中的[Lync Server 2013 中的林準備所做的變更](lync-server-2013-changes-made-by-forest-preparation.md)。</span><span class="sxs-lookup"><span data-stu-id="c0569-107">For details about the specific groups created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="c0569-108">使用 RBAC，系統會將使用者指派給預先定義的管理角色，包括11個預先定義的角色，涵蓋許多常見的管理工作，以獲得 [RBAC] 許可權。</span><span class="sxs-lookup"><span data-stu-id="c0569-108">With RBAC, administrative privilege is granted by assigning users to pre-defined administrative roles, including the 11 predefined roles that cover many common administrative tasks.</span></span> <span data-ttu-id="c0569-109">每個角色都與該角色中的使用者允許執行的 Lync Server 管理命令介面指令的特定清單相關聯。</span><span class="sxs-lookup"><span data-stu-id="c0569-109">Each role is associated with a specific list of Lync Server Management Shell cmdlets that users in that role are allowed to run.</span></span> <span data-ttu-id="c0569-110">您可以使用 RBAC 來遵循「最低許可權」的原則，在此原則中，使用者只能得到他們工作所需的管理能力。</span><span class="sxs-lookup"><span data-stu-id="c0569-110">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative abilities that their jobs require.</span></span> <span data-ttu-id="c0569-111">如需詳細資訊，請參閱規劃檔中的[Lync Server 2013 中的角色式存取控制規劃](lync-server-2013-planning-for-role-based-access-control.md)。</span><span class="sxs-lookup"><span data-stu-id="c0569-111">For details, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

