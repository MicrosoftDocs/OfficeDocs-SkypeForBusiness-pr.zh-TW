---
title: Lync Server 2013： 網際網路資訊服務 (IIS) 需求
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
ms.openlocfilehash: d2e3914d66576d72d250a96948d45f05aa0a5f41
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145352"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="internet-information-services-iis-requirements-in-lync-server-2013"></a><span data-ttu-id="56804-102">在 [Lync Server 2013 的網際網路資訊服務 (IIS) 需求</span><span class="sxs-lookup"><span data-stu-id="56804-102">Internet Information Services (IIS) requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56804-103">_**主題上次修改日期：** 2012年-06-19_</span><span class="sxs-lookup"><span data-stu-id="56804-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="56804-104">數個 Lync Server 2013 元件需要網際網路資訊服務 (IIS)。</span><span class="sxs-lookup"><span data-stu-id="56804-104">Several Lync Server 2013 components require Internet Information Services (IIS).</span></span> <span data-ttu-id="56804-105">本主題說明支援 Lync Server 所需的特定 IIS 功能。</span><span class="sxs-lookup"><span data-stu-id="56804-105">This topic describes the specific IIS features required to support Lync Server.</span></span> <span data-ttu-id="56804-106">本節中的主題則說明 IIS 特定元件的需求。</span><span class="sxs-lookup"><span data-stu-id="56804-106">The topics in this section describe the requirements of specific components for IIS.</span></span>

<span data-ttu-id="56804-p102">當 Windows Server 2008 上啟用 Web 伺服器 (IIS) 角色時，預設會安裝各種角色服務。下表說明當 Windows Server 2008 上啟用 Web 伺服器 (IIS) 角色時，必須安裝的其他角色服務。</span><span class="sxs-lookup"><span data-stu-id="56804-p102">When the Web Server (IIS) role is enabled on Windows Server 2008, various role services are installed by default. The following table describes the additional role services that must be installed when the Web Server (IIS) role is enabled on Windows Server 2008.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="56804-109">角色服務</span><span class="sxs-lookup"><span data-stu-id="56804-109">Role service</span></span></th>
<th><span data-ttu-id="56804-110">功能</span><span class="sxs-lookup"><span data-stu-id="56804-110">Feature</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="56804-111">一般 HTTP 功能</span><span class="sxs-lookup"><span data-stu-id="56804-111">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="56804-112">HTTP 重新導向</span><span class="sxs-lookup"><span data-stu-id="56804-112">HTTP Redirection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56804-113">應用程式開發</span><span class="sxs-lookup"><span data-stu-id="56804-113">Application Development</span></span></p></td>
<td><p><span data-ttu-id="56804-114">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="56804-114">ASP.NET</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56804-115">應用程式開發</span><span class="sxs-lookup"><span data-stu-id="56804-115">Application Development</span></span></p></td>
<td><p><span data-ttu-id="56804-116">.NET 擴充性</span><span class="sxs-lookup"><span data-stu-id="56804-116">.NET Extensibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56804-117">應用程式開發</span><span class="sxs-lookup"><span data-stu-id="56804-117">Application Development</span></span></p></td>
<td><p><span data-ttu-id="56804-118">ISAPI 擴充程式</span><span class="sxs-lookup"><span data-stu-id="56804-118">ISAPI Extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56804-119">應用程式開發</span><span class="sxs-lookup"><span data-stu-id="56804-119">Application Development</span></span></p></td>
<td><p><span data-ttu-id="56804-120">ISAPI 篩選器</span><span class="sxs-lookup"><span data-stu-id="56804-120">ISAPI Filters</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56804-121">健康情況及診斷</span><span class="sxs-lookup"><span data-stu-id="56804-121">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="56804-122">記錄工具</span><span class="sxs-lookup"><span data-stu-id="56804-122">Logging Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56804-123">健康情況及診斷</span><span class="sxs-lookup"><span data-stu-id="56804-123">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="56804-124">追蹤</span><span class="sxs-lookup"><span data-stu-id="56804-124">Tracing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56804-125">安全性</span><span class="sxs-lookup"><span data-stu-id="56804-125">Security</span></span></p></td>
<td><p><span data-ttu-id="56804-126">基本驗證</span><span class="sxs-lookup"><span data-stu-id="56804-126">Basic Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56804-127">安全性</span><span class="sxs-lookup"><span data-stu-id="56804-127">Security</span></span></p></td>
<td><p><span data-ttu-id="56804-128">Windows 驗證</span><span class="sxs-lookup"><span data-stu-id="56804-128">Windows Authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56804-129">管理工具</span><span class="sxs-lookup"><span data-stu-id="56804-129">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="56804-130">IIS 管理指令碼及工具</span><span class="sxs-lookup"><span data-stu-id="56804-130">IIS Management Scripts and Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56804-131">管理工具</span><span class="sxs-lookup"><span data-stu-id="56804-131">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="56804-132">IIS 6 管理相容性</span><span class="sxs-lookup"><span data-stu-id="56804-132">IIS 6 Management Compatibility</span></span></p></td>
</tr>
</tbody>
</table>


<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="安全性" alt="security" /><span data-ttu-id="56804-134">安全性附註：</span><span class="sxs-lookup"><span data-stu-id="56804-134">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="56804-135">如果您在 Windows Server 2008 作業系統上使用 IIS 7.0，Lync Server 安裝程式會停用 IIS 中的核心模式驗證。</span><span class="sxs-lookup"><span data-stu-id="56804-135">If you are using IIS 7.0 on a Windows Server 2008 operating system, Lync Server Setup disables kernel mode authentication in IIS.</span></span></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="56804-136">本章節內容</span><span class="sxs-lookup"><span data-stu-id="56804-136">In This Section</span></span>

  - [<span data-ttu-id="56804-137">前端集區和 Standard Edition server 在 Lync Server 2013 中的 IIS 需求</span><span class="sxs-lookup"><span data-stu-id="56804-137">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

