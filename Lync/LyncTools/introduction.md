---
title: 簡介
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Introduction
ms:assetid: 276395be-93df-4a16-97e2-cb468cd0f2e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945588(v=OCS.15)
ms:contentKeyID: 51541414
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a3674742cedbdfb267326e0170703f3fbc3ba3b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044265"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="introduction"></a><span data-ttu-id="39f5d-102">簡介</span><span class="sxs-lookup"><span data-stu-id="39f5d-102">Introduction</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39f5d-103">_**上次修改主題：** 2013年-02-24_</span><span class="sxs-lookup"><span data-stu-id="39f5d-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="39f5d-104">Lync Server 2013 壓力及效能工具 （稱為 LyncPerfTool） 可以模擬下列類型的使用者負載：</span><span class="sxs-lookup"><span data-stu-id="39f5d-104">The Lync Server 2013 Stress and Performance Tool (referred to as LyncPerfTool) can simulate user load of the following types:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="39f5d-105">立即訊息 (IM) 和目前狀態</span><span class="sxs-lookup"><span data-stu-id="39f5d-105">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="39f5d-106">音訊會議</span><span class="sxs-lookup"><span data-stu-id="39f5d-106">Audio conferencing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39f5d-107">應用程式共用</span><span class="sxs-lookup"><span data-stu-id="39f5d-107">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="39f5d-108">語音 over IP (VoIP)，包括公用交換的電話網路 (PSTN) 模擬</span><span class="sxs-lookup"><span data-stu-id="39f5d-108">Voice over IP (VoIP), including public switched telephone network (PSTN) simulation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39f5d-109">Web Access 用戶端會議</span><span class="sxs-lookup"><span data-stu-id="39f5d-109">Web Access Client conferencing</span></span></p></td>
<td><p><span data-ttu-id="39f5d-110">Microsoft Lync 2013 語音應答</span><span class="sxs-lookup"><span data-stu-id="39f5d-110">Microsoft Lync 2013 Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39f5d-111">回應群組</span><span class="sxs-lookup"><span data-stu-id="39f5d-111">Response Groups</span></span></p></td>
<td><p><span data-ttu-id="39f5d-112">通訊群組清單延伸</span><span class="sxs-lookup"><span data-stu-id="39f5d-112">Distribution list expansion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39f5d-113">通訊錄下載和通訊錄查詢</span><span class="sxs-lookup"><span data-stu-id="39f5d-113">Address book download and address book query</span></span></p></td>
<td><p><span data-ttu-id="39f5d-114">增強型 9-1-1 (E9-1-1) 呼叫和位置設定檔 （撥號對應表）</span><span class="sxs-lookup"><span data-stu-id="39f5d-114">Enhanced 9-1-1 (E9-1-1) calls and location profile (dial plan)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39f5d-115">MultiView</span><span class="sxs-lookup"><span data-stu-id="39f5d-115">MultiView</span></span></p></td>
<td><p><span data-ttu-id="39f5d-116">檢視從會議的多個資料流</span><span class="sxs-lookup"><span data-stu-id="39f5d-116">Viewing multiple streams from a conference</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="39f5d-117">Lync Server 2013 壓力及效能工具支援跨集區負載產生和進階設定只透過同盟。</span><span class="sxs-lookup"><span data-stu-id="39f5d-117">The Lync Server 2013 Stress and Performance Tool supports cross-pool load generation and federation through advanced configuration only.</span></span>

<span data-ttu-id="39f5d-118">此工具也 generator 無法模擬使用者負載下的用戶端：</span><span class="sxs-lookup"><span data-stu-id="39f5d-118">The tool also does not simulate user load for the following clients:</span></span>

  - <span data-ttu-id="39f5d-119">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="39f5d-119">Office Live Meeting 2007</span></span>

  - <span data-ttu-id="39f5d-120">Lync 2013 常設聊天室</span><span class="sxs-lookup"><span data-stu-id="39f5d-120">Lync 2013 Persistent Chat</span></span>

<span data-ttu-id="39f5d-121">因此，[Lync Server 2013 壓力及效能工具將未支援測試下列元件：</span><span class="sxs-lookup"><span data-stu-id="39f5d-121">As a result, the Lync Server 2013 Stress and Performance Tool will not support testing the following components:</span></span>

  - <span data-ttu-id="39f5d-122">Lync 2013 常設聊天室</span><span class="sxs-lookup"><span data-stu-id="39f5d-122">Lync 2013 Persistent Chat</span></span>

  - <span data-ttu-id="39f5d-123">Exchange 整合案例</span><span class="sxs-lookup"><span data-stu-id="39f5d-123">Exchange integration scenarios</span></span>

<div>

## <a name="applications-and-files-included-with-the-lync-server-2013-stress-and-performance-tool"></a><span data-ttu-id="39f5d-124">應用程式及隨附的 Lync Server 2013 壓力及效能工具的檔案</span><span class="sxs-lookup"><span data-stu-id="39f5d-124">Applications and Files Included with the Lync Server 2013 Stress and Performance Tool</span></span>

<span data-ttu-id="39f5d-125">在 [Lync Server 2013 壓力及效能工具包含下列應用程式：</span><span class="sxs-lookup"><span data-stu-id="39f5d-125">The following applications are included in the Lync Server 2013 Stress and Performance Tool:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="39f5d-126">工具</span><span class="sxs-lookup"><span data-stu-id="39f5d-126">Tool</span></span></th>
<th><span data-ttu-id="39f5d-127">描述</span><span class="sxs-lookup"><span data-stu-id="39f5d-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="39f5d-128">UserProvisioningTool.exe</span><span class="sxs-lookup"><span data-stu-id="39f5d-128">UserProvisioningTool.exe</span></span></p></td>
<td><p><span data-ttu-id="39f5d-129">Lync Server 2013 使用者佈建的工具。</span><span class="sxs-lookup"><span data-stu-id="39f5d-129">The Lync Server 2013 User Provisioning tool.</span></span> <span data-ttu-id="39f5d-130">這項工具用來建立使用者和連絡人。</span><span class="sxs-lookup"><span data-stu-id="39f5d-130">This tool is used to create users and contacts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39f5d-131">UserProfileGenerator.exe</span><span class="sxs-lookup"><span data-stu-id="39f5d-131">UserProfileGenerator.exe</span></span></p></td>
<td><p><span data-ttu-id="39f5d-132">為 Lync Server 2013 負載組態工具。</span><span class="sxs-lookup"><span data-stu-id="39f5d-132">The Lync Server 2013 Load Configuration Tool.</span></span> <span data-ttu-id="39f5d-133">這項工具用來設定模擬的使用者負載的特性。</span><span class="sxs-lookup"><span data-stu-id="39f5d-133">This tool is used to configure the characteristics of the user load to simulate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39f5d-134">LyncPerfTool.exe</span><span class="sxs-lookup"><span data-stu-id="39f5d-134">LyncPerfTool.exe</span></span></p></td>
<td><p><span data-ttu-id="39f5d-135">[Lync Server 2013 壓力及效能工具。</span><span class="sxs-lookup"><span data-stu-id="39f5d-135">The Lync Server 2013 Stress and Performance Tool.</span></span> <span data-ttu-id="39f5d-136">LyncPerfTool 是模擬的使用者負載的工具。</span><span class="sxs-lookup"><span data-stu-id="39f5d-136">LyncPerfTool is the tool that simulates the user load.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39f5d-137">Default.tmx</span><span class="sxs-lookup"><span data-stu-id="39f5d-137">Default.tmx</span></span></p></td>
<td><p><span data-ttu-id="39f5d-138">若要使用 Lync Server 2013 記錄工具，才 Default.tmx。</span><span class="sxs-lookup"><span data-stu-id="39f5d-138">Default.tmx is required to use the Lync Server 2013 Logging Tool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39f5d-139">佈建指令碼的範例</span><span class="sxs-lookup"><span data-stu-id="39f5d-139">Example provisioning scripts</span></span></p></td>
<td><p><span data-ttu-id="39f5d-140">下列範例會用來設定執行負載測試，根據特定案例的拓撲</span><span class="sxs-lookup"><span data-stu-id="39f5d-140">These examples are used to configure the topology for running load tests, based on specific scenarios</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

