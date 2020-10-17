---
title: Lync Server 2013： tblADCookie
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
ms.openlocfilehash: bf372f3dfc39f3ca90cbe0019af09e8d9dd33d26
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509510"
---
# <a name="tbladcookie-in-lync-server-2013"></a><span data-ttu-id="bd61b-102">Lync Server 2013 中的 tblADCookie</span><span class="sxs-lookup"><span data-stu-id="bd61b-102">tblADCookie in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd61b-103">_**主題上次修改日期：** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="bd61b-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="bd61b-104">tblADCookie 包含目前的輕量型目錄存取通訊協定 (LDAP) 同步處理 Cookie。</span><span class="sxs-lookup"><span data-stu-id="bd61b-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>

### <a name="columns"></a><span data-ttu-id="bd61b-105">Columns</span><span class="sxs-lookup"><span data-stu-id="bd61b-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bd61b-106">欄</span><span class="sxs-lookup"><span data-stu-id="bd61b-106">Column</span></span></th>
<th><span data-ttu-id="bd61b-107">類型</span><span class="sxs-lookup"><span data-stu-id="bd61b-107">Type</span></span></th>
<th><span data-ttu-id="bd61b-108">描述</span><span class="sxs-lookup"><span data-stu-id="bd61b-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bd61b-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="bd61b-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="bd61b-110">GUID，非 null</span><span class="sxs-lookup"><span data-stu-id="bd61b-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="bd61b-111">受監控網域的主體 GUID。</span><span class="sxs-lookup"><span data-stu-id="bd61b-111">Principal GUID of the domain being monitored.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd61b-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="bd61b-112">prinDCHost</span></span></p></td>
<td><p><span data-ttu-id="bd61b-113">nvarchar(255)</span><span class="sxs-lookup"><span data-stu-id="bd61b-113">nvarchar (255)</span></span></p></td>
<td><p><span data-ttu-id="bd61b-114">用於 Active Directory 網域服務同步處理的目前網域控制站 (FQDN) 的完整功能變數名稱。具有資訊性值。</span><span class="sxs-lookup"><span data-stu-id="bd61b-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd61b-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="bd61b-115">adcContent</span></span></p></td>
<td><p><span data-ttu-id="bd61b-116">影像 (二進位)</span><span class="sxs-lookup"><span data-stu-id="bd61b-116">image (binary)</span></span></p></td>
<td><p><span data-ttu-id="bd61b-117">Active Directory 同步處理 Cookie。</span><span class="sxs-lookup"><span data-stu-id="bd61b-117">Active Directory Sync cookie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd61b-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="bd61b-118">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="bd61b-119">datetime</span><span class="sxs-lookup"><span data-stu-id="bd61b-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="bd61b-120">含有列更新時間的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="bd61b-120">Time stamp with the row update time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd61b-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="bd61b-121">lockedUntil</span></span></p></td>
<td><p><span data-ttu-id="bd61b-122">datetime</span><span class="sxs-lookup"><span data-stu-id="bd61b-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="bd61b-p101">鎖定列以進行變更的時間。這是軟體聯鎖機制的一部分，可確保一次僅有一個聊天服務會進行 Active Directory 同步處理。</span><span class="sxs-lookup"><span data-stu-id="bd61b-p101">Time until the row is locked for changes. This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="bd61b-125">索引鍵</span><span class="sxs-lookup"><span data-stu-id="bd61b-125">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bd61b-126">欄 (s) </span><span class="sxs-lookup"><span data-stu-id="bd61b-126">Column(s)</span></span></th>
<th><span data-ttu-id="bd61b-127">描述</span><span class="sxs-lookup"><span data-stu-id="bd61b-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bd61b-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="bd61b-128">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="bd61b-129">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="bd61b-129">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd61b-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="bd61b-130">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="bd61b-131">在 Principal.prinID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="bd61b-131">Foreign key with lookup in Principal.prinGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

