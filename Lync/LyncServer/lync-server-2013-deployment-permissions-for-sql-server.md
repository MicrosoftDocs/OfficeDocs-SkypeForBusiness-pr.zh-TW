---
title: 'Lync Server 2013: SQL Server 的部署權限'
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
ms.openlocfilehash: 2a6697fdb4910b16592ace53e08dcc754cdb2446
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135460"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-permissions-for-sql-server-in-lync-server-2013"></a><span data-ttu-id="c2b0a-102">Lync Server 2013 中的 SQL Server 的部署權限</span><span class="sxs-lookup"><span data-stu-id="c2b0a-102">Deployment permissions for SQL Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2b0a-103">_**主題上次修改日期：** 2012年-10-01_</span><span class="sxs-lookup"><span data-stu-id="c2b0a-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="c2b0a-104">Microsoft SQL Server 2012 具有安裝及部署 Lync Server 2013 時的特定需求。</span><span class="sxs-lookup"><span data-stu-id="c2b0a-104">Microsoft SQL Server 2012 has specific requirements when installing and deploying Lync Server 2013.</span></span> <span data-ttu-id="c2b0a-105">Windows 和 SQL Server 以不同方式定義其安全性，因為在 Active Directory 系統管理員身分登入網域不會以隱含方式授與 SQL Server 的權限。</span><span class="sxs-lookup"><span data-stu-id="c2b0a-105">Because Windows and SQL Server define their security differently, logging in as an administrator in the Active Directory domain does not implicitly grant permissions for SQL Server.</span></span> <span data-ttu-id="c2b0a-106">您同時必須是所要設定之 SQL Server 伺服器上的 sysadmin 實體成員。</span><span class="sxs-lookup"><span data-stu-id="c2b0a-106">You must also be a member of the sysadmin entity on the SQL Server-based server you are configuring.</span></span>

<div>

## <a name="permissions-required-for-database-and-lync-server-installation"></a><span data-ttu-id="c2b0a-107">資料庫與 Lync Server 安裝所需的權限</span><span class="sxs-lookup"><span data-stu-id="c2b0a-107">Permissions Required for Database and Lync Server Installation</span></span>

<span data-ttu-id="c2b0a-108">三個權限和群組成員資格關聯安裝 Lync Server 2013 檔案和 SQL Server 資料庫的詳細說明下列選項。</span><span class="sxs-lookup"><span data-stu-id="c2b0a-108">The following options detail three permissions and group membership associations for installation of Lync Server 2013 files and SQL Server databases.</span></span> <span data-ttu-id="c2b0a-109">請針對組織需求選擇最適合的案例。</span><span class="sxs-lookup"><span data-stu-id="c2b0a-109">Choose the scenario that best meets the requirements of your organization.</span></span>

### <a name="permissions-and-group-membership-associations"></a><span data-ttu-id="c2b0a-110">權限與群組成員資格關聯</span><span class="sxs-lookup"><span data-stu-id="c2b0a-110">Permissions and Group Membership Associations</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c2b0a-111">SQL Server 或 Lync Server 2013 的角色</span><span class="sxs-lookup"><span data-stu-id="c2b0a-111">SQL Server or Lync Server 2013 role</span></span></th>
<th><span data-ttu-id="c2b0a-112">角色典型的 SQL Server 權限與群組成員資格</span><span class="sxs-lookup"><span data-stu-id="c2b0a-112">Role-Typical SQL Server permissions and group membership</span></span></th>
<th><span data-ttu-id="c2b0a-113">角色典型的 Lync Server 2013 權限和群組成員資格</span><span class="sxs-lookup"><span data-stu-id="c2b0a-113">Role-typical Lync Server 2013 permissions and group membership</span></span></th>
<th><span data-ttu-id="c2b0a-114">權限結果</span><span class="sxs-lookup"><span data-stu-id="c2b0a-114">Permissions outcome</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c2b0a-115">Lync Server 2013 系統管理員</span><span class="sxs-lookup"><span data-stu-id="c2b0a-115">Lync Server 2013 administrator</span></span></p></td>
<td><p><span data-ttu-id="c2b0a-116">必須賦予 sysadmins SQL Server 安全性群組與 SQL Server 本機 Administrators 群組成員資格</span><span class="sxs-lookup"><span data-stu-id="c2b0a-116">Must be granted membership of sysadmins SQL Server security group and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="c2b0a-117">必須是 RTCUniversalServerAdmins 群組成員</span><span class="sxs-lookup"><span data-stu-id="c2b0a-117">Must be a member of the RTCUniversalServerAdmins group</span></span></p></td>
<td><p><span data-ttu-id="c2b0a-118">Lync Server 2013 系統管理員具有安裝 Lync Server 2013 和 SQL Server 資料庫的適當權限。</span><span class="sxs-lookup"><span data-stu-id="c2b0a-118">Lync Server 2013 administrator has the proper permissions to install both Lync Server 2013 and SQL Server databases.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2b0a-119">SQL Server 系統管理員</span><span class="sxs-lookup"><span data-stu-id="c2b0a-119">SQL Server administrator</span></span></p></td>
<td><p><span data-ttu-id="c2b0a-120">SQL Server sysadmin 群組成員 (或相等地位的成員) 及 SQL Server 本機 Administrators 群組成員</span><span class="sxs-lookup"><span data-stu-id="c2b0a-120">SQL Server sysadmin group member (or equivalent) and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="c2b0a-121">必須是 RTCUniversalServerReadOnly 群組成員</span><span class="sxs-lookup"><span data-stu-id="c2b0a-121">Must be a member of the RTCUniversalServerReadOnly group</span></span></p></td>
<td><p><span data-ttu-id="c2b0a-122">SQL Server 系統管理員具有安裝 Lync Server 2013 和 SQL Server 資料庫的適當權限。</span><span class="sxs-lookup"><span data-stu-id="c2b0a-122">SQL Server administrator has the proper permissions to install both Lync Server 2013 and SQL Server databases.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2b0a-123">這兩位系統管理員共同分攤安裝責任</span><span class="sxs-lookup"><span data-stu-id="c2b0a-123">Both administrators sharing installation duties</span></span></p></td>
<td><p><span data-ttu-id="c2b0a-124">SQL Server 系統管理員是 sysadmins 群組成員 (或相等地位的成員) 及 SQL Server 本機 Administrators 群組的成員</span><span class="sxs-lookup"><span data-stu-id="c2b0a-124">SQL Server administrator is member of sysadmins group (or equivalent) and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="c2b0a-125">Lync Server 2013 系統管理員是 RTCUniversalServerAdmins 成員</span><span class="sxs-lookup"><span data-stu-id="c2b0a-125">Lync Server 2013 administrator is member of RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="c2b0a-126">Lync Server 2013 系統管理員可以安裝 Lync Server 2013 中，但不能安裝資料庫。</span><span class="sxs-lookup"><span data-stu-id="c2b0a-126">The Lync Server 2013 administrator can install Lync Server 2013, but cannot install the databases.</span></span> <span data-ttu-id="c2b0a-127">SQL Server 系統管理員使用 Lync Server 2013 管理員所提供的 Lync Server 管理命令介面和 Windows PowerShell cmdlet 來安裝資料庫。</span><span class="sxs-lookup"><span data-stu-id="c2b0a-127">The SQL Server administrator uses the Lync Server Management Shell and Windows PowerShell cmdlets provided by the Lync Server 2013 administrator to install the databases.</span></span> <span data-ttu-id="c2b0a-128">在前端伺服器上安裝 Lync Server 2013 管理命令介面使用 SQL Server 系統管理員。</span><span class="sxs-lookup"><span data-stu-id="c2b0a-128">The Lync Server 2013 Management Shell used by the SQL Server administrator is installed on the Front End Server.</span></span> <span data-ttu-id="c2b0a-129">這就不需要 SQL Server 型伺服器上安裝 Lync Server 2013 系統管理工具。</span><span class="sxs-lookup"><span data-stu-id="c2b0a-129">This eliminates the need to install the Lync Server 2013 administrative tools on the SQL Server-based server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

