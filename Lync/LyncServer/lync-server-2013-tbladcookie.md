---
title: 'Lync Server 2013: tblADCookie'
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
ms.openlocfilehash: 1f733397483693ad4c18418f3e82b9f99cfa640f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbladcookie-in-lync-server-2013"></a><span data-ttu-id="fee87-102">Lync Server 2013 中的 tblADCookie</span><span class="sxs-lookup"><span data-stu-id="fee87-102">tblADCookie in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fee87-103">_**主題上次修改日期：** 2012年-06-25_</span><span class="sxs-lookup"><span data-stu-id="fee87-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="fee87-104">tblADCookie 包含目前的輕量型目錄存取通訊協定 (LDAP) 同步處理 Cookie。</span><span class="sxs-lookup"><span data-stu-id="fee87-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>

### <a name="columns"></a><span data-ttu-id="fee87-105">Columns</span><span class="sxs-lookup"><span data-stu-id="fee87-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fee87-106">欄</span><span class="sxs-lookup"><span data-stu-id="fee87-106">Column</span></span></th>
<th><span data-ttu-id="fee87-107">類型	</span><span class="sxs-lookup"><span data-stu-id="fee87-107">Type</span></span></th>
<th><span data-ttu-id="fee87-108">描述</span><span class="sxs-lookup"><span data-stu-id="fee87-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fee87-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="fee87-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="fee87-110">GUID，非 null</span><span class="sxs-lookup"><span data-stu-id="fee87-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="fee87-111">受監控網域的主體 GUID。</span><span class="sxs-lookup"><span data-stu-id="fee87-111">Principal GUID of the domain being monitored.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fee87-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="fee87-112">prinDCHost</span></span></p></td>
<td><p><span data-ttu-id="fee87-113">nvarchar(255)</span><span class="sxs-lookup"><span data-stu-id="fee87-113">nvarchar (255)</span></span></p></td>
<td><p><span data-ttu-id="fee87-114">用於 Active Directory 網域服務同步處理的目前網域控制站的完整的網域名稱 (FQDN)。具有資訊性的值。</span><span class="sxs-lookup"><span data-stu-id="fee87-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fee87-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="fee87-115">adcContent</span></span></p></td>
<td><p><span data-ttu-id="fee87-116">影像 (二進位)</span><span class="sxs-lookup"><span data-stu-id="fee87-116">image (binary)</span></span></p></td>
<td><p><span data-ttu-id="fee87-117">Active Directory 同步處理 Cookie。</span><span class="sxs-lookup"><span data-stu-id="fee87-117">Active Directory Sync cookie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fee87-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="fee87-118">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="fee87-119">datetime</span><span class="sxs-lookup"><span data-stu-id="fee87-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="fee87-120">含有列更新時間的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="fee87-120">Time stamp with the row update time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fee87-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="fee87-121">lockedUntil</span></span></p></td>
<td><p><span data-ttu-id="fee87-122">datetime</span><span class="sxs-lookup"><span data-stu-id="fee87-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="fee87-p101">鎖定列以進行變更的時間。這是軟體聯鎖機制的一部分，可確保一次僅有一個聊天服務會進行 Active Directory 同步處理。</span><span class="sxs-lookup"><span data-stu-id="fee87-p101">Time until the row is locked for changes. This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="fee87-125">索引鍵</span><span class="sxs-lookup"><span data-stu-id="fee87-125">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fee87-126">資料欄</span><span class="sxs-lookup"><span data-stu-id="fee87-126">Column(s)</span></span></th>
<th><span data-ttu-id="fee87-127">描述</span><span class="sxs-lookup"><span data-stu-id="fee87-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fee87-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="fee87-128">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="fee87-129">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="fee87-129">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fee87-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="fee87-130">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="fee87-131">在 Principal.prinID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="fee87-131">Foreign key with lookup in Principal.prinGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

