---
title: Lync Server 2013：設定封存的許可權
description: Lync Server 2013：設定封存的許可權。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up permissions for Archiving
ms:assetid: 67f97c94-52f5-4a83-a35c-8c307d5de9a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204961(v=OCS.15)
ms:contentKeyID: 48184364
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f06c4fb48772a41621ece765dcc90555f0cd2d5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574829"
---
# <a name="setting-up-permissions-for-archiving-in-lync-server-2013"></a><span data-ttu-id="c52f6-103">在 Lync Server 2013 中設定封存的許可權</span><span class="sxs-lookup"><span data-stu-id="c52f6-103">Setting up permissions for Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c52f6-104">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="c52f6-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="c52f6-105">在 Lync Server 2013 中，特定的任務仍然要求執行這些工作的使用者屬於一或多個特定群組的成員。</span><span class="sxs-lookup"><span data-stu-id="c52f6-105">In Lync Server 2013, specific tasks still require that users who perform those tasks be members of one or more specific groups.</span></span> <span data-ttu-id="c52f6-106">不過，您也可以透過指派使用者至預先定義的 Lync Server 系統管理角色，使用以角色為基礎的存取控制 (RBAC) 授與許可權。在您部署封存之前，請確定適當的使用者權限與許可權已存在，且您想要指派給特定 RBAC 角色的任何使用者已獲指派給該角色。</span><span class="sxs-lookup"><span data-stu-id="c52f6-106">However, you can also use role-based access control (RBAC) to grant privileges by assigning users to predefined Lync Server administrative roles.Before you deploy Archiving, be sure that the appropriate user rights and permissions are in place, and that any users who you want to assign to a specific RBAC role have been assigned to that role.</span></span> <span data-ttu-id="c52f6-107">如需有關部署支援封存的使用者權限、許可權及角色的詳細資訊，請參閱在 [Lync Server 2013 中封存的部署檢查清單](lync-server-2013-deployment-checklist-for-archiving.md)，可在規劃檔和部署檔中取得。</span><span class="sxs-lookup"><span data-stu-id="c52f6-107">For details about the user rights, permissions, and roles for deploying support for Archiving, see [Deployment checklist for Archiving in Lync Server 2013](lync-server-2013-deployment-checklist-for-archiving.md), which is available in the Planning documentation and the Deployment documentation.</span></span> <span data-ttu-id="c52f6-108">如需 RBAC 的詳細資訊，請參閱規劃檔中的 [規劃 Lync Server 2013 中的角色型存取控制](lync-server-2013-planning-for-role-based-access-control.md) 。</span><span class="sxs-lookup"><span data-stu-id="c52f6-108">For details about RBAC, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

