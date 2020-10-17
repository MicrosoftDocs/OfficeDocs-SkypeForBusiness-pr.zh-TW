---
title: 簡介
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
ms.openlocfilehash: f217ec7d39134dcb8d6000de33b3d0c17aeb033d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527150"
---
# <a name="introduction"></a><span data-ttu-id="29164-102">簡介</span><span class="sxs-lookup"><span data-stu-id="29164-102">Introduction</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29164-103">_**主題上次修改日期：** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="29164-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="29164-104">Lync Server 2013 應力和效能工具 (稱為 LyncPerfTool) 可以模擬下列類型的使用者負載：</span><span class="sxs-lookup"><span data-stu-id="29164-104">The Lync Server 2013 Stress and Performance Tool (referred to as LyncPerfTool) can simulate user load of the following types:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29164-105">立即訊息 (IM) 和目前狀態</span><span class="sxs-lookup"><span data-stu-id="29164-105">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="29164-106">音訊會議</span><span class="sxs-lookup"><span data-stu-id="29164-106">Audio conferencing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29164-107">應用程式共用</span><span class="sxs-lookup"><span data-stu-id="29164-107">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="29164-108">Voice over IP (VoIP) ，包括公用交換電話網路 (PSTN) 模擬</span><span class="sxs-lookup"><span data-stu-id="29164-108">Voice over IP (VoIP), including public switched telephone network (PSTN) simulation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29164-109">Web Access 用戶端會議</span><span class="sxs-lookup"><span data-stu-id="29164-109">Web Access Client conferencing</span></span></p></td>
<td><p><span data-ttu-id="29164-110">Microsoft Lync 2013 語音應答</span><span class="sxs-lookup"><span data-stu-id="29164-110">Microsoft Lync 2013 Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29164-111">回應群組</span><span class="sxs-lookup"><span data-stu-id="29164-111">Response Groups</span></span></p></td>
<td><p><span data-ttu-id="29164-112">通訊群組清單延伸</span><span class="sxs-lookup"><span data-stu-id="29164-112">Distribution list expansion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29164-113">通訊錄下載和通訊錄查詢</span><span class="sxs-lookup"><span data-stu-id="29164-113">Address book download and address book query</span></span></p></td>
<td><p><span data-ttu-id="29164-114">增強型 9-1-1 (E9-1-1) 通話和位置設定檔 (撥號對應表) </span><span class="sxs-lookup"><span data-stu-id="29164-114">Enhanced 9-1-1 (E9-1-1) calls and location profile (dial plan)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29164-115">重視</span><span class="sxs-lookup"><span data-stu-id="29164-115">MultiView</span></span></p></td>
<td><p><span data-ttu-id="29164-116">從會議中查看多個資料流程</span><span class="sxs-lookup"><span data-stu-id="29164-116">Viewing multiple streams from a conference</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="29164-117">Lync Server 2013 應力和效能工具僅支援透過高級設定進行跨集區的負載產生及同盟。</span><span class="sxs-lookup"><span data-stu-id="29164-117">The Lync Server 2013 Stress and Performance Tool supports cross-pool load generation and federation through advanced configuration only.</span></span>

<span data-ttu-id="29164-118">工具也不會為下列用戶端模擬使用者負載：</span><span class="sxs-lookup"><span data-stu-id="29164-118">The tool also does not simulate user load for the following clients:</span></span>

  - <span data-ttu-id="29164-119">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="29164-119">Office Live Meeting 2007</span></span>

  - <span data-ttu-id="29164-120">Lync 2013 持續聊天</span><span class="sxs-lookup"><span data-stu-id="29164-120">Lync 2013 Persistent Chat</span></span>

<span data-ttu-id="29164-121">因此，Lync Server 2013 的壓力和效能工具不支援測試下列元件：</span><span class="sxs-lookup"><span data-stu-id="29164-121">As a result, the Lync Server 2013 Stress and Performance Tool will not support testing the following components:</span></span>

  - <span data-ttu-id="29164-122">Lync 2013 持續聊天</span><span class="sxs-lookup"><span data-stu-id="29164-122">Lync 2013 Persistent Chat</span></span>

  - <span data-ttu-id="29164-123">Exchange 整合案例</span><span class="sxs-lookup"><span data-stu-id="29164-123">Exchange integration scenarios</span></span>

<div>

## <a name="applications-and-files-included-with-the-lync-server-2013-stress-and-performance-tool"></a><span data-ttu-id="29164-124">Lync Server 2013 壓力和效能工具隨附的應用程式和檔案</span><span class="sxs-lookup"><span data-stu-id="29164-124">Applications and Files Included with the Lync Server 2013 Stress and Performance Tool</span></span>

<span data-ttu-id="29164-125">Lync Server 2013 應力和效能工具組含下列應用程式：</span><span class="sxs-lookup"><span data-stu-id="29164-125">The following applications are included in the Lync Server 2013 Stress and Performance Tool:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="29164-126">工具</span><span class="sxs-lookup"><span data-stu-id="29164-126">Tool</span></span></th>
<th><span data-ttu-id="29164-127">描述</span><span class="sxs-lookup"><span data-stu-id="29164-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29164-128">UserProvisioningTool.exe</span><span class="sxs-lookup"><span data-stu-id="29164-128">UserProvisioningTool.exe</span></span></p></td>
<td><p><span data-ttu-id="29164-129">Lync Server 2013 使用者布建工具。</span><span class="sxs-lookup"><span data-stu-id="29164-129">The Lync Server 2013 User Provisioning tool.</span></span> <span data-ttu-id="29164-130">此工具用來建立使用者和連絡人。</span><span class="sxs-lookup"><span data-stu-id="29164-130">This tool is used to create users and contacts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29164-131">UserProfileGenerator.exe</span><span class="sxs-lookup"><span data-stu-id="29164-131">UserProfileGenerator.exe</span></span></p></td>
<td><p><span data-ttu-id="29164-132">Lync Server 2013 載入設定工具。</span><span class="sxs-lookup"><span data-stu-id="29164-132">The Lync Server 2013 Load Configuration Tool.</span></span> <span data-ttu-id="29164-133">此工具用來設定要模擬之使用者負載的特性。</span><span class="sxs-lookup"><span data-stu-id="29164-133">This tool is used to configure the characteristics of the user load to simulate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29164-134">LyncPerfTool.exe</span><span class="sxs-lookup"><span data-stu-id="29164-134">LyncPerfTool.exe</span></span></p></td>
<td><p><span data-ttu-id="29164-135">Lync Server 2013 壓力和效能工具。</span><span class="sxs-lookup"><span data-stu-id="29164-135">The Lync Server 2013 Stress and Performance Tool.</span></span> <span data-ttu-id="29164-136">LyncPerfTool 是一種模擬使用者負載的工具。</span><span class="sxs-lookup"><span data-stu-id="29164-136">LyncPerfTool is the tool that simulates the user load.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29164-137">預設的 tmx</span><span class="sxs-lookup"><span data-stu-id="29164-137">Default.tmx</span></span></p></td>
<td><p><span data-ttu-id="29164-138">使用 Lync Server 2013 記錄工具時，必須使用預設 tmx。</span><span class="sxs-lookup"><span data-stu-id="29164-138">Default.tmx is required to use the Lync Server 2013 Logging Tool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29164-139">範例布建腳本</span><span class="sxs-lookup"><span data-stu-id="29164-139">Example provisioning scripts</span></span></p></td>
<td><p><span data-ttu-id="29164-140">這些範例是根據特定案例，用來設定執行負載測試的拓撲</span><span class="sxs-lookup"><span data-stu-id="29164-140">These examples are used to configure the topology for running load tests, based on specific scenarios</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

