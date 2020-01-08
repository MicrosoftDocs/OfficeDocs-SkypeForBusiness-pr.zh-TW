---
title: Lync Server 2013：tblADCookie
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblADCookie
ms:assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558610(v=OCS.15)
ms:contentKeyID: 48183366
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2eef65e18de609f7e10fed4aaad9283612778070
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978262"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbladcookie-in-lync-server-2013"></a><span data-ttu-id="8d9ea-102">Lync Server 2013 中的 tblADCookie</span><span class="sxs-lookup"><span data-stu-id="8d9ea-102">tblADCookie in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d9ea-103">_**主題上次修改日期：** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="8d9ea-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="8d9ea-104">tblADCookie 包含目前的輕型目錄存取通訊協定（LDAP）同步處理 cookie。</span><span class="sxs-lookup"><span data-stu-id="8d9ea-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>

### <a name="columns"></a><span data-ttu-id="8d9ea-105">分欄</span><span class="sxs-lookup"><span data-stu-id="8d9ea-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8d9ea-106">左欄</span><span class="sxs-lookup"><span data-stu-id="8d9ea-106">Column</span></span></th>
<th><span data-ttu-id="8d9ea-107">類型</span><span class="sxs-lookup"><span data-stu-id="8d9ea-107">Type</span></span></th>
<th><span data-ttu-id="8d9ea-108">描述</span><span class="sxs-lookup"><span data-stu-id="8d9ea-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8d9ea-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="8d9ea-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="8d9ea-110">GUID，不是 null</span><span class="sxs-lookup"><span data-stu-id="8d9ea-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="8d9ea-111">受監視之網域的主要 GUID。</span><span class="sxs-lookup"><span data-stu-id="8d9ea-111">Principal GUID of the domain being monitored.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d9ea-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="8d9ea-112">prinDCHost</span></span></p></td>
<td><p><span data-ttu-id="8d9ea-113">Nvarchar （255）</span><span class="sxs-lookup"><span data-stu-id="8d9ea-113">nvarchar (255)</span></span></p></td>
<td><p><span data-ttu-id="8d9ea-114">用於 Active Directory 網域服務同步處理之目前網網域控制站的完整功能變數名稱（FQDN）。有資訊值。</span><span class="sxs-lookup"><span data-stu-id="8d9ea-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d9ea-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="8d9ea-115">adcContent</span></span></p></td>
<td><p><span data-ttu-id="8d9ea-116">image （二進位）</span><span class="sxs-lookup"><span data-stu-id="8d9ea-116">image (binary)</span></span></p></td>
<td><p><span data-ttu-id="8d9ea-117">Active Directory 同步處理 cookie。</span><span class="sxs-lookup"><span data-stu-id="8d9ea-117">Active Directory Sync cookie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d9ea-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="8d9ea-118">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="8d9ea-119">datetime</span><span class="sxs-lookup"><span data-stu-id="8d9ea-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="8d9ea-120">含有資料列更新時間的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="8d9ea-120">Time stamp with the row update time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d9ea-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="8d9ea-121">lockedUntil</span></span></p></td>
<td><p><span data-ttu-id="8d9ea-122">datetime</span><span class="sxs-lookup"><span data-stu-id="8d9ea-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="8d9ea-123">[時間]，直到列鎖定變更為止。</span><span class="sxs-lookup"><span data-stu-id="8d9ea-123">Time until the row is locked for changes.</span></span> <span data-ttu-id="8d9ea-124">這是軟體互鎖機制的一部分，可確保一次只有其中一個聊天服務進行 Active Directory 同步處理。</span><span class="sxs-lookup"><span data-stu-id="8d9ea-124">This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="8d9ea-125">鍵</span><span class="sxs-lookup"><span data-stu-id="8d9ea-125">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8d9ea-126">欄（s）</span><span class="sxs-lookup"><span data-stu-id="8d9ea-126">Column(s)</span></span></th>
<th><span data-ttu-id="8d9ea-127">描述</span><span class="sxs-lookup"><span data-stu-id="8d9ea-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8d9ea-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="8d9ea-128">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="8d9ea-129">主鍵。</span><span class="sxs-lookup"><span data-stu-id="8d9ea-129">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d9ea-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="8d9ea-130">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="8d9ea-131">PrinGuid 表格中的 [查閱] 外鍵。</span><span class="sxs-lookup"><span data-stu-id="8d9ea-131">Foreign key with lookup in Principal.prinGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

