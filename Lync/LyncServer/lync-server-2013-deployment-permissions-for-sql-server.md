---
title: Lync Server 2013： SQL Server 的部署許可權
description: Lync Server 2013： SQL Server 的部署許可權。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment permissions for SQL Server
ms:assetid: 56ea0c02-bcf5-4d45-aa13-570531c29074
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398375(v=OCS.15)
ms:contentKeyID: 48184197
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be5985bc8f3173b03d8969d3dd58cfbf8daf85f8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575719"
---
# <a name="deployment-permissions-for-sql-server-in-lync-server-2013"></a><span data-ttu-id="125ad-103">Lync Server 2013 中 SQL Server 的部署許可權</span><span class="sxs-lookup"><span data-stu-id="125ad-103">Deployment permissions for SQL Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="125ad-104">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="125ad-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="125ad-105">Microsoft SQL Server 2012 在安裝及部署 Lync Server 2013 時有特定的需求。</span><span class="sxs-lookup"><span data-stu-id="125ad-105">Microsoft SQL Server 2012 has specific requirements when installing and deploying Lync Server 2013.</span></span> <span data-ttu-id="125ad-106">由於 Windows 和 SQL Server 會以不同的方式定義安全性，所以以 Active Directory 網域中的系統管理員身分登入 SQL Server 的許可權。</span><span class="sxs-lookup"><span data-stu-id="125ad-106">Because Windows and SQL Server define their security differently, logging in as an administrator in the Active Directory domain does not implicitly grant permissions for SQL Server.</span></span> <span data-ttu-id="125ad-107">您同時必須是所要設定之 SQL Server 伺服器上的 sysadmin 實體成員。</span><span class="sxs-lookup"><span data-stu-id="125ad-107">You must also be a member of the sysadmin entity on the SQL Server-based server you are configuring.</span></span>

<div>

## <a name="permissions-required-for-database-and-lync-server-installation"></a><span data-ttu-id="125ad-108">資料庫與 Lync Server 安裝所需的權限</span><span class="sxs-lookup"><span data-stu-id="125ad-108">Permissions Required for Database and Lync Server Installation</span></span>

<span data-ttu-id="125ad-109">下列選項詳述安裝 Lync Server 2013 檔案和 SQL Server 資料庫的三個許可權和群組成員資格關聯。</span><span class="sxs-lookup"><span data-stu-id="125ad-109">The following options detail three permissions and group membership associations for installation of Lync Server 2013 files and SQL Server databases.</span></span> <span data-ttu-id="125ad-110">請針對組織需求選擇最適合的案例。</span><span class="sxs-lookup"><span data-stu-id="125ad-110">Choose the scenario that best meets the requirements of your organization.</span></span>

### <a name="permissions-and-group-membership-associations"></a><span data-ttu-id="125ad-111">權限與群組成員資格關聯</span><span class="sxs-lookup"><span data-stu-id="125ad-111">Permissions and Group Membership Associations</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="125ad-112">SQL Server 或 Lync Server 2013 角色</span><span class="sxs-lookup"><span data-stu-id="125ad-112">SQL Server or Lync Server 2013 role</span></span></th>
<th><span data-ttu-id="125ad-113">角色典型的 SQL Server 權限與群組成員資格</span><span class="sxs-lookup"><span data-stu-id="125ad-113">Role-Typical SQL Server permissions and group membership</span></span></th>
<th><span data-ttu-id="125ad-114">角色-一般的 Lync Server 2013 許可權和群組成員資格</span><span class="sxs-lookup"><span data-stu-id="125ad-114">Role-typical Lync Server 2013 permissions and group membership</span></span></th>
<th><span data-ttu-id="125ad-115">權限結果</span><span class="sxs-lookup"><span data-stu-id="125ad-115">Permissions outcome</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="125ad-116">Lync Server 2013 系統管理員</span><span class="sxs-lookup"><span data-stu-id="125ad-116">Lync Server 2013 administrator</span></span></p></td>
<td><p><span data-ttu-id="125ad-117">必須賦予 sysadmins SQL Server 安全性群組與 SQL Server 本機 Administrators 群組成員資格</span><span class="sxs-lookup"><span data-stu-id="125ad-117">Must be granted membership of sysadmins SQL Server security group and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="125ad-118">必須是 RTCUniversalServerAdmins 群組成員</span><span class="sxs-lookup"><span data-stu-id="125ad-118">Must be a member of the RTCUniversalServerAdmins group</span></span></p></td>
<td><p><span data-ttu-id="125ad-119">Lync Server 2013 系統管理員具備安裝 Lync Server 2013 和 SQL Server 資料庫的適當許可權。</span><span class="sxs-lookup"><span data-stu-id="125ad-119">Lync Server 2013 administrator has the proper permissions to install both Lync Server 2013 and SQL Server databases.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="125ad-120">SQL Server 系統管理員</span><span class="sxs-lookup"><span data-stu-id="125ad-120">SQL Server administrator</span></span></p></td>
<td><p><span data-ttu-id="125ad-121">SQL Server sysadmin 群組成員 (或相等地位的成員) 及 SQL Server 本機 Administrators 群組成員</span><span class="sxs-lookup"><span data-stu-id="125ad-121">SQL Server sysadmin group member (or equivalent) and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="125ad-122">必須是 RTCUniversalServerReadOnly 群組成員</span><span class="sxs-lookup"><span data-stu-id="125ad-122">Must be a member of the RTCUniversalServerReadOnly group</span></span></p></td>
<td><p><span data-ttu-id="125ad-123">SQL Server 系統管理員具備安裝 Lync Server 2013 和 SQL Server 資料庫的適當許可權。</span><span class="sxs-lookup"><span data-stu-id="125ad-123">SQL Server administrator has the proper permissions to install both Lync Server 2013 and SQL Server databases.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="125ad-124">這兩位系統管理員共同分攤安裝責任</span><span class="sxs-lookup"><span data-stu-id="125ad-124">Both administrators sharing installation duties</span></span></p></td>
<td><p><span data-ttu-id="125ad-125">SQL Server 系統管理員是 sysadmins 群組成員 (或相等地位的成員) 及 SQL Server 本機 Administrators 群組的成員</span><span class="sxs-lookup"><span data-stu-id="125ad-125">SQL Server administrator is member of sysadmins group (or equivalent) and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="125ad-126">Lync Server 2013 系統管理員是 RTCUniversalServerAdmins 的成員</span><span class="sxs-lookup"><span data-stu-id="125ad-126">Lync Server 2013 administrator is member of RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="125ad-127">Lync Server 2013 管理員可以安裝 Lync Server 2013，但無法安裝資料庫。</span><span class="sxs-lookup"><span data-stu-id="125ad-127">The Lync Server 2013 administrator can install Lync Server 2013, but cannot install the databases.</span></span> <span data-ttu-id="125ad-128">SQL Server 系統管理員會使用 lync server 管理命令介面和 Windows PowerShell 的 Cmdlet，由 Lync Server 2013 系統管理員提供，以安裝資料庫。</span><span class="sxs-lookup"><span data-stu-id="125ad-128">The SQL Server administrator uses the Lync Server Management Shell and Windows PowerShell cmdlets provided by the Lync Server 2013 administrator to install the databases.</span></span> <span data-ttu-id="125ad-129">SQL Server 系統管理員所用的 Lync Server 2013 管理命令介面已安裝在前端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="125ad-129">The Lync Server 2013 Management Shell used by the SQL Server administrator is installed on the Front End Server.</span></span> <span data-ttu-id="125ad-130">這樣就不需要在以 SQL Server 為基礎的伺服器上安裝 Lync Server 2013 系統管理工具。</span><span class="sxs-lookup"><span data-stu-id="125ad-130">This eliminates the need to install the Lync Server 2013 administrative tools on the SQL Server-based server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

