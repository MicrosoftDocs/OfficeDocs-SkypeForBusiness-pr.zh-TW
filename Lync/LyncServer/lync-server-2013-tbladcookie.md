---
title: Lync Server 2013： tblADCookie
description: Lync Server 2013： tblADCookie。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblADCookie
ms:assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558610(v=OCS.15)
ms:contentKeyID: 48183366
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41c3dde3730ede07b204a473c7fe0a5ab68054d3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573719"
---
# <a name="tbladcookie-in-lync-server-2013"></a><span data-ttu-id="3eb37-103">Lync Server 2013 中的 tblADCookie</span><span class="sxs-lookup"><span data-stu-id="3eb37-103">tblADCookie in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3eb37-104">_**主題上次修改日期：** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="3eb37-104">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="3eb37-105">tblADCookie 包含目前的輕量型目錄存取通訊協定 (LDAP) 同步處理 Cookie。</span><span class="sxs-lookup"><span data-stu-id="3eb37-105">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>

### <a name="columns"></a><span data-ttu-id="3eb37-106">Columns</span><span class="sxs-lookup"><span data-stu-id="3eb37-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3eb37-107">欄</span><span class="sxs-lookup"><span data-stu-id="3eb37-107">Column</span></span></th>
<th><span data-ttu-id="3eb37-108">類型</span><span class="sxs-lookup"><span data-stu-id="3eb37-108">Type</span></span></th>
<th><span data-ttu-id="3eb37-109">描述</span><span class="sxs-lookup"><span data-stu-id="3eb37-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3eb37-110">prinGuid</span><span class="sxs-lookup"><span data-stu-id="3eb37-110">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="3eb37-111">GUID，非 null</span><span class="sxs-lookup"><span data-stu-id="3eb37-111">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="3eb37-112">受監控網域的主體 GUID。</span><span class="sxs-lookup"><span data-stu-id="3eb37-112">Principal GUID of the domain being monitored.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3eb37-113">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="3eb37-113">prinDCHost</span></span></p></td>
<td><p><span data-ttu-id="3eb37-114">nvarchar(255)</span><span class="sxs-lookup"><span data-stu-id="3eb37-114">nvarchar (255)</span></span></p></td>
<td><p><span data-ttu-id="3eb37-115">用於 Active Directory 網域服務同步處理的目前網域控制站 (FQDN) 的完整功能變數名稱。具有資訊性值。</span><span class="sxs-lookup"><span data-stu-id="3eb37-115">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3eb37-116">adcContent</span><span class="sxs-lookup"><span data-stu-id="3eb37-116">adcContent</span></span></p></td>
<td><p><span data-ttu-id="3eb37-117">影像 (二進位)</span><span class="sxs-lookup"><span data-stu-id="3eb37-117">image (binary)</span></span></p></td>
<td><p><span data-ttu-id="3eb37-118">Active Directory 同步處理 Cookie。</span><span class="sxs-lookup"><span data-stu-id="3eb37-118">Active Directory Sync cookie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3eb37-119">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="3eb37-119">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="3eb37-120">datetime</span><span class="sxs-lookup"><span data-stu-id="3eb37-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="3eb37-121">含有列更新時間的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="3eb37-121">Time stamp with the row update time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3eb37-122">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="3eb37-122">lockedUntil</span></span></p></td>
<td><p><span data-ttu-id="3eb37-123">datetime</span><span class="sxs-lookup"><span data-stu-id="3eb37-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="3eb37-p101">鎖定列以進行變更的時間。這是軟體聯鎖機制的一部分，可確保一次僅有一個聊天服務會進行 Active Directory 同步處理。</span><span class="sxs-lookup"><span data-stu-id="3eb37-p101">Time until the row is locked for changes. This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="3eb37-126">索引鍵</span><span class="sxs-lookup"><span data-stu-id="3eb37-126">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3eb37-127">欄 (s) </span><span class="sxs-lookup"><span data-stu-id="3eb37-127">Column(s)</span></span></th>
<th><span data-ttu-id="3eb37-128">描述</span><span class="sxs-lookup"><span data-stu-id="3eb37-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3eb37-129">prinGuid</span><span class="sxs-lookup"><span data-stu-id="3eb37-129">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="3eb37-130">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="3eb37-130">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3eb37-131">prinGuid</span><span class="sxs-lookup"><span data-stu-id="3eb37-131">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="3eb37-132">在 Principal.prinID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="3eb37-132">Foreign key with lookup in Principal.prinGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

