---
title: Lync Server 2013：SQL Server 的部署權限
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment permissions for SQL Server
ms:assetid: 56ea0c02-bcf5-4d45-aa13-570531c29074
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398375(v=OCS.15)
ms:contentKeyID: 48184197
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea0334c7070ae3aadb3191da4bf036a978878688
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978409"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-permissions-for-sql-server-in-lync-server-2013"></a><span data-ttu-id="62908-102">Lync Server 2013 中 SQL Server 的部署權限</span><span class="sxs-lookup"><span data-stu-id="62908-102">Deployment permissions for SQL Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62908-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="62908-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="62908-104">Microsoft SQL Server 2012 在安裝和部署 Lync Server 2013 時有特定的需求。</span><span class="sxs-lookup"><span data-stu-id="62908-104">Microsoft SQL Server 2012 has specific requirements when installing and deploying Lync Server 2013.</span></span> <span data-ttu-id="62908-105">因為 Windows 與 SQL Server 定義其安全性的方式不同，所以以 Active Directory 網域中的管理員身分登入，並不會針對 SQL Server 隱式授與許可權。</span><span class="sxs-lookup"><span data-stu-id="62908-105">Because Windows and SQL Server define their security differently, logging in as an administrator in the Active Directory domain does not implicitly grant permissions for SQL Server.</span></span> <span data-ttu-id="62908-106">您也必須是您正在設定的 SQL Server 基礎伺服器上 sysadmin 實體的成員。</span><span class="sxs-lookup"><span data-stu-id="62908-106">You must also be a member of the sysadmin entity on the SQL Server-based server you are configuring.</span></span>

<div>

## <a name="permissions-required-for-database-and-lync-server-installation"></a><span data-ttu-id="62908-107">資料庫和 Lync Server 安裝所需的許可權</span><span class="sxs-lookup"><span data-stu-id="62908-107">Permissions Required for Database and Lync Server Installation</span></span>

<span data-ttu-id="62908-108">下列選項詳細說明安裝 Lync Server 2013 檔案與 SQL Server 資料庫所需的三種許可權和群組成員資格關聯。</span><span class="sxs-lookup"><span data-stu-id="62908-108">The following options detail three permissions and group membership associations for installation of Lync Server 2013 files and SQL Server databases.</span></span> <span data-ttu-id="62908-109">選擇最符合貴組織需求的案例。</span><span class="sxs-lookup"><span data-stu-id="62908-109">Choose the scenario that best meets the requirements of your organization.</span></span>

### <a name="permissions-and-group-membership-associations"></a><span data-ttu-id="62908-110">許可權與群組成員資格關聯</span><span class="sxs-lookup"><span data-stu-id="62908-110">Permissions and Group Membership Associations</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="62908-111">SQL Server 或 Lync Server 2013 角色</span><span class="sxs-lookup"><span data-stu-id="62908-111">SQL Server or Lync Server 2013 role</span></span></th>
<th><span data-ttu-id="62908-112">角色-一般 SQL Server 許可權與群組成員資格</span><span class="sxs-lookup"><span data-stu-id="62908-112">Role-Typical SQL Server permissions and group membership</span></span></th>
<th><span data-ttu-id="62908-113">角色-一般的 Lync Server 2013 許可權與群組成員資格</span><span class="sxs-lookup"><span data-stu-id="62908-113">Role-typical Lync Server 2013 permissions and group membership</span></span></th>
<th><span data-ttu-id="62908-114">許可權結果</span><span class="sxs-lookup"><span data-stu-id="62908-114">Permissions outcome</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="62908-115">Lync Server 2013 系統管理員</span><span class="sxs-lookup"><span data-stu-id="62908-115">Lync Server 2013 administrator</span></span></p></td>
<td><p><span data-ttu-id="62908-116">必須授與 sysadmin SQL Server 安全性群組的成員資格，以及 SQL Server 本機管理員群組的成員</span><span class="sxs-lookup"><span data-stu-id="62908-116">Must be granted membership of sysadmins SQL Server security group and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="62908-117">必須是 RTCUniversalServerAdmins 群組的成員</span><span class="sxs-lookup"><span data-stu-id="62908-117">Must be a member of the RTCUniversalServerAdmins group</span></span></p></td>
<td><p><span data-ttu-id="62908-118">Lync Server 2013 系統管理員擁有安裝 Lync Server 2013 與 SQL Server 資料庫的適當許可權。</span><span class="sxs-lookup"><span data-stu-id="62908-118">Lync Server 2013 administrator has the proper permissions to install both Lync Server 2013 and SQL Server databases.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62908-119">SQL Server 系統管理員</span><span class="sxs-lookup"><span data-stu-id="62908-119">SQL Server administrator</span></span></p></td>
<td><p><span data-ttu-id="62908-120">SQL Server sysadmin 群組成員（或對等）與 SQL Server 本機管理員群組的成員</span><span class="sxs-lookup"><span data-stu-id="62908-120">SQL Server sysadmin group member (or equivalent) and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="62908-121">必須是 RTCUniversalServerReadOnly 群組的成員</span><span class="sxs-lookup"><span data-stu-id="62908-121">Must be a member of the RTCUniversalServerReadOnly group</span></span></p></td>
<td><p><span data-ttu-id="62908-122">SQL Server 系統管理員擁有安裝 Lync Server 2013 與 SQL Server 資料庫的適當許可權。</span><span class="sxs-lookup"><span data-stu-id="62908-122">SQL Server administrator has the proper permissions to install both Lync Server 2013 and SQL Server databases.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62908-123">兩個管理員都在共用安裝職責</span><span class="sxs-lookup"><span data-stu-id="62908-123">Both administrators sharing installation duties</span></span></p></td>
<td><p><span data-ttu-id="62908-124">SQL Server 系統管理員是 sysadmin 群組的成員（或同等），以及 SQL Server 本機管理員群組的成員</span><span class="sxs-lookup"><span data-stu-id="62908-124">SQL Server administrator is member of sysadmins group (or equivalent) and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="62908-125">Lync Server 2013 系統管理員是 RTCUniversalServerAdmins 的成員</span><span class="sxs-lookup"><span data-stu-id="62908-125">Lync Server 2013 administrator is member of RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="62908-126">Lync Server 2013 系統管理員可以安裝 Lync Server 2013，但無法安裝資料庫。</span><span class="sxs-lookup"><span data-stu-id="62908-126">The Lync Server 2013 administrator can install Lync Server 2013, but cannot install the databases.</span></span> <span data-ttu-id="62908-127">SQL Server 系統管理員使用由 Lync Server 2013 系統管理員提供的 Lync Server 管理命令介面和 Windows PowerShell Cmdlet 來安裝資料庫。</span><span class="sxs-lookup"><span data-stu-id="62908-127">The SQL Server administrator uses the Lync Server Management Shell and Windows PowerShell cmdlets provided by the Lync Server 2013 administrator to install the databases.</span></span> <span data-ttu-id="62908-128">SQL Server 系統管理員使用的 Lync Server 2013 管理命令介面已安裝在前端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="62908-128">The Lync Server 2013 Management Shell used by the SQL Server administrator is installed on the Front End Server.</span></span> <span data-ttu-id="62908-129">這樣就不需要在 SQL Server 的伺服器上安裝 Lync Server 2013 系統管理工具。</span><span class="sxs-lookup"><span data-stu-id="62908-129">This eliminates the need to install the Lync Server 2013 administrative tools on the SQL Server-based server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

