---
title: 簡介
description: 介紹。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Introduction
ms:assetid: 276395be-93df-4a16-97e2-cb468cd0f2e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945588(v=OCS.15)
ms:contentKeyID: 51541414
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8eb847c499bde077ccaf2aa050de801ceeedcc6f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565279"
---
# <a name="introduction"></a><span data-ttu-id="c276a-103">簡介</span><span class="sxs-lookup"><span data-stu-id="c276a-103">Introduction</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c276a-104">_**主題上次修改日期：** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="c276a-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="c276a-105">Lync Server 2013 應力和效能工具 (稱為 LyncPerfTool) 可以模擬下列類型的使用者負載：</span><span class="sxs-lookup"><span data-stu-id="c276a-105">The Lync Server 2013 Stress and Performance Tool (referred to as LyncPerfTool) can simulate user load of the following types:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c276a-106">立即訊息 (IM) 和目前狀態</span><span class="sxs-lookup"><span data-stu-id="c276a-106">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="c276a-107">音訊會議</span><span class="sxs-lookup"><span data-stu-id="c276a-107">Audio conferencing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c276a-108">應用程式共用</span><span class="sxs-lookup"><span data-stu-id="c276a-108">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="c276a-109">Voice over IP (VoIP) ，包括公用交換電話網路 (PSTN) 模擬</span><span class="sxs-lookup"><span data-stu-id="c276a-109">Voice over IP (VoIP), including public switched telephone network (PSTN) simulation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c276a-110">Web Access 用戶端會議</span><span class="sxs-lookup"><span data-stu-id="c276a-110">Web Access Client conferencing</span></span></p></td>
<td><p><span data-ttu-id="c276a-111">Microsoft Lync 2013 語音應答</span><span class="sxs-lookup"><span data-stu-id="c276a-111">Microsoft Lync 2013 Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c276a-112">回應群組</span><span class="sxs-lookup"><span data-stu-id="c276a-112">Response Groups</span></span></p></td>
<td><p><span data-ttu-id="c276a-113">通訊群組清單延伸</span><span class="sxs-lookup"><span data-stu-id="c276a-113">Distribution list expansion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c276a-114">通訊錄下載和通訊錄查詢</span><span class="sxs-lookup"><span data-stu-id="c276a-114">Address book download and address book query</span></span></p></td>
<td><p><span data-ttu-id="c276a-115">增強型 9-1-1 (E9-1-1) 通話和位置設定檔 (撥號對應表) </span><span class="sxs-lookup"><span data-stu-id="c276a-115">Enhanced 9-1-1 (E9-1-1) calls and location profile (dial plan)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c276a-116">重視</span><span class="sxs-lookup"><span data-stu-id="c276a-116">MultiView</span></span></p></td>
<td><p><span data-ttu-id="c276a-117">從會議中查看多個資料流程</span><span class="sxs-lookup"><span data-stu-id="c276a-117">Viewing multiple streams from a conference</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c276a-118">Lync Server 2013 應力和效能工具僅支援透過高級設定進行跨集區的負載產生及同盟。</span><span class="sxs-lookup"><span data-stu-id="c276a-118">The Lync Server 2013 Stress and Performance Tool supports cross-pool load generation and federation through advanced configuration only.</span></span>

<span data-ttu-id="c276a-119">工具也不會為下列用戶端模擬使用者負載：</span><span class="sxs-lookup"><span data-stu-id="c276a-119">The tool also does not simulate user load for the following clients:</span></span>

  - <span data-ttu-id="c276a-120">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="c276a-120">Office Live Meeting 2007</span></span>

  - <span data-ttu-id="c276a-121">Lync 2013 持續聊天</span><span class="sxs-lookup"><span data-stu-id="c276a-121">Lync 2013 Persistent Chat</span></span>

<span data-ttu-id="c276a-122">因此，Lync Server 2013 的壓力和效能工具不支援測試下列元件：</span><span class="sxs-lookup"><span data-stu-id="c276a-122">As a result, the Lync Server 2013 Stress and Performance Tool will not support testing the following components:</span></span>

  - <span data-ttu-id="c276a-123">Lync 2013 持續聊天</span><span class="sxs-lookup"><span data-stu-id="c276a-123">Lync 2013 Persistent Chat</span></span>

  - <span data-ttu-id="c276a-124">Exchange 整合案例</span><span class="sxs-lookup"><span data-stu-id="c276a-124">Exchange integration scenarios</span></span>

<div>

## <a name="applications-and-files-included-with-the-lync-server-2013-stress-and-performance-tool"></a><span data-ttu-id="c276a-125">Lync Server 2013 壓力和效能工具隨附的應用程式和檔案</span><span class="sxs-lookup"><span data-stu-id="c276a-125">Applications and Files Included with the Lync Server 2013 Stress and Performance Tool</span></span>

<span data-ttu-id="c276a-126">Lync Server 2013 應力和效能工具組含下列應用程式：</span><span class="sxs-lookup"><span data-stu-id="c276a-126">The following applications are included in the Lync Server 2013 Stress and Performance Tool:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c276a-127">工具</span><span class="sxs-lookup"><span data-stu-id="c276a-127">Tool</span></span></th>
<th><span data-ttu-id="c276a-128">描述</span><span class="sxs-lookup"><span data-stu-id="c276a-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c276a-129">UserProvisioningTool.exe</span><span class="sxs-lookup"><span data-stu-id="c276a-129">UserProvisioningTool.exe</span></span></p></td>
<td><p><span data-ttu-id="c276a-130">Lync Server 2013 使用者布建工具。</span><span class="sxs-lookup"><span data-stu-id="c276a-130">The Lync Server 2013 User Provisioning tool.</span></span> <span data-ttu-id="c276a-131">此工具用來建立使用者和連絡人。</span><span class="sxs-lookup"><span data-stu-id="c276a-131">This tool is used to create users and contacts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c276a-132">UserProfileGenerator.exe</span><span class="sxs-lookup"><span data-stu-id="c276a-132">UserProfileGenerator.exe</span></span></p></td>
<td><p><span data-ttu-id="c276a-133">Lync Server 2013 載入設定工具。</span><span class="sxs-lookup"><span data-stu-id="c276a-133">The Lync Server 2013 Load Configuration Tool.</span></span> <span data-ttu-id="c276a-134">此工具用來設定要模擬之使用者負載的特性。</span><span class="sxs-lookup"><span data-stu-id="c276a-134">This tool is used to configure the characteristics of the user load to simulate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c276a-135">LyncPerfTool.exe</span><span class="sxs-lookup"><span data-stu-id="c276a-135">LyncPerfTool.exe</span></span></p></td>
<td><p><span data-ttu-id="c276a-136">Lync Server 2013 壓力和效能工具。</span><span class="sxs-lookup"><span data-stu-id="c276a-136">The Lync Server 2013 Stress and Performance Tool.</span></span> <span data-ttu-id="c276a-137">LyncPerfTool 是一種模擬使用者負載的工具。</span><span class="sxs-lookup"><span data-stu-id="c276a-137">LyncPerfTool is the tool that simulates the user load.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c276a-138">預設的 tmx</span><span class="sxs-lookup"><span data-stu-id="c276a-138">Default.tmx</span></span></p></td>
<td><p><span data-ttu-id="c276a-139">使用 Lync Server 2013 記錄工具時，必須使用預設 tmx。</span><span class="sxs-lookup"><span data-stu-id="c276a-139">Default.tmx is required to use the Lync Server 2013 Logging Tool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c276a-140">範例布建腳本</span><span class="sxs-lookup"><span data-stu-id="c276a-140">Example provisioning scripts</span></span></p></td>
<td><p><span data-ttu-id="c276a-141">這些範例是根據特定案例，用來設定執行負載測試的拓撲</span><span class="sxs-lookup"><span data-stu-id="c276a-141">These examples are used to configure the topology for running load tests, based on specific scenarios</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

