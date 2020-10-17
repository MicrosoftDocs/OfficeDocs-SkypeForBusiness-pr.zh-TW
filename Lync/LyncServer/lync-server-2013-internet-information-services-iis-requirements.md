---
title: Lync Server 2013： Internet Information Services (IIS) 需求
description: Lync Server 2013： Internet Information Services (IIS) 需求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Internet Information Services (IIS) requirements
ms:assetid: 4f57a605-a8a9-4c5a-9a18-05ecb3d9ab6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398321(v=OCS.15)
ms:contentKeyID: 48184128
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd8de55fa4611c3ab29eac7d7c28c522b418e77d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543989"
---
# <a name="internet-information-services-iis-requirements-in-lync-server-2013"></a><span data-ttu-id="891c5-103">Lync Server 2013 中的網際網路資訊服務 (IIS) 需求</span><span class="sxs-lookup"><span data-stu-id="891c5-103">Internet Information Services (IIS) requirements in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="891c5-104">_**主題上次修改日期：** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="891c5-104">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="891c5-105">有些 Lync Server 2013 元件需要 Internet Information Services (IIS) 。</span><span class="sxs-lookup"><span data-stu-id="891c5-105">Several Lync Server 2013 components require Internet Information Services (IIS).</span></span> <span data-ttu-id="891c5-106">本主題說明支援 Lync Server 所需的特定 IIS 功能。</span><span class="sxs-lookup"><span data-stu-id="891c5-106">This topic describes the specific IIS features required to support Lync Server.</span></span> <span data-ttu-id="891c5-107">本節中的主題則說明 IIS 特定元件的需求。</span><span class="sxs-lookup"><span data-stu-id="891c5-107">The topics in this section describe the requirements of specific components for IIS.</span></span>

<span data-ttu-id="891c5-p102">當 Windows Server 2008 上啟用 Web 伺服器 (IIS) 角色時，預設會安裝各種角色服務。下表說明當 Windows Server 2008 上啟用 Web 伺服器 (IIS) 角色時，必須安裝的其他角色服務。</span><span class="sxs-lookup"><span data-stu-id="891c5-p102">When the Web Server (IIS) role is enabled on Windows Server 2008, various role services are installed by default. The following table describes the additional role services that must be installed when the Web Server (IIS) role is enabled on Windows Server 2008.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="891c5-110">角色服務</span><span class="sxs-lookup"><span data-stu-id="891c5-110">Role service</span></span></th>
<th><span data-ttu-id="891c5-111">功能</span><span class="sxs-lookup"><span data-stu-id="891c5-111">Feature</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="891c5-112">一般 HTTP 功能</span><span class="sxs-lookup"><span data-stu-id="891c5-112">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="891c5-113">HTTP 重新導向</span><span class="sxs-lookup"><span data-stu-id="891c5-113">HTTP Redirection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="891c5-114">應用程式開發</span><span class="sxs-lookup"><span data-stu-id="891c5-114">Application Development</span></span></p></td>
<td><p><span data-ttu-id="891c5-115">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="891c5-115">ASP.NET</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="891c5-116">應用程式開發</span><span class="sxs-lookup"><span data-stu-id="891c5-116">Application Development</span></span></p></td>
<td><p><span data-ttu-id="891c5-117">.NET 擴充性</span><span class="sxs-lookup"><span data-stu-id="891c5-117">.NET Extensibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="891c5-118">應用程式開發</span><span class="sxs-lookup"><span data-stu-id="891c5-118">Application Development</span></span></p></td>
<td><p><span data-ttu-id="891c5-119">ISAPI 擴充程式</span><span class="sxs-lookup"><span data-stu-id="891c5-119">ISAPI Extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="891c5-120">應用程式開發</span><span class="sxs-lookup"><span data-stu-id="891c5-120">Application Development</span></span></p></td>
<td><p><span data-ttu-id="891c5-121">ISAPI 篩選器</span><span class="sxs-lookup"><span data-stu-id="891c5-121">ISAPI Filters</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="891c5-122">健康情況及診斷</span><span class="sxs-lookup"><span data-stu-id="891c5-122">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="891c5-123">記錄工具</span><span class="sxs-lookup"><span data-stu-id="891c5-123">Logging Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="891c5-124">健康情況及診斷</span><span class="sxs-lookup"><span data-stu-id="891c5-124">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="891c5-125">跟蹤</span><span class="sxs-lookup"><span data-stu-id="891c5-125">Tracing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="891c5-126">安全性</span><span class="sxs-lookup"><span data-stu-id="891c5-126">Security</span></span></p></td>
<td><p><span data-ttu-id="891c5-127">基本驗證</span><span class="sxs-lookup"><span data-stu-id="891c5-127">Basic Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="891c5-128">安全性</span><span class="sxs-lookup"><span data-stu-id="891c5-128">Security</span></span></p></td>
<td><p><span data-ttu-id="891c5-129">Windows 驗證</span><span class="sxs-lookup"><span data-stu-id="891c5-129">Windows Authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="891c5-130">管理工具</span><span class="sxs-lookup"><span data-stu-id="891c5-130">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="891c5-131">IIS 管理指令碼及工具</span><span class="sxs-lookup"><span data-stu-id="891c5-131">IIS Management Scripts and Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="891c5-132">管理工具</span><span class="sxs-lookup"><span data-stu-id="891c5-132">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="891c5-133">IIS 6 管理相容性</span><span class="sxs-lookup"><span data-stu-id="891c5-133">IIS 6 Management Compatibility</span></span></p></td>
</tr>
</tbody>
</table>


<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="安全" alt="security" /><span data-ttu-id="891c5-135">安全性附注：</span><span class="sxs-lookup"><span data-stu-id="891c5-135">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="891c5-136">如果您在 Windows Server 2008 作業系統上使用 IIS 7.0，Lync Server 安裝程式會在 IIS 中停用核心模式驗證。</span><span class="sxs-lookup"><span data-stu-id="891c5-136">If you are using IIS 7.0 on a Windows Server 2008 operating system, Lync Server Setup disables kernel mode authentication in IIS.</span></span></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="891c5-137">本章節內容</span><span class="sxs-lookup"><span data-stu-id="891c5-137">In This Section</span></span>

  - [<span data-ttu-id="891c5-138">Lync Server 2013 中前端集區與 Standard Edition server 的 IIS 需求</span><span class="sxs-lookup"><span data-stu-id="891c5-138">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

