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
ms.openlocfilehash: 893205127b6b1ccba958a0882c3aa0d1360a7c06
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730563"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="introduction"></a><span data-ttu-id="11682-102">簡介</span><span class="sxs-lookup"><span data-stu-id="11682-102">Introduction</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11682-103">_**主題上次修改日期：** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="11682-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="11682-104">Lync Server 2013 的應力和效能工具（稱為 LyncPerfTool）可以模擬使用者載入下列類型：</span><span class="sxs-lookup"><span data-stu-id="11682-104">The Lync Server 2013 Stress and Performance Tool (referred to as LyncPerfTool) can simulate user load of the following types:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11682-105">立即訊息（IM）與目前狀態</span><span class="sxs-lookup"><span data-stu-id="11682-105">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="11682-106">音訊會議</span><span class="sxs-lookup"><span data-stu-id="11682-106">Audio conferencing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11682-107">應用程式共用</span><span class="sxs-lookup"><span data-stu-id="11682-107">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="11682-108">[語音 over IP （VoIP）]，包括公用交換電話網絡（PSTN）模擬</span><span class="sxs-lookup"><span data-stu-id="11682-108">Voice over IP (VoIP), including public switched telephone network (PSTN) simulation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11682-109">Web Access 用戶端會議</span><span class="sxs-lookup"><span data-stu-id="11682-109">Web Access Client conferencing</span></span></p></td>
<td><p><span data-ttu-id="11682-110">Microsoft Lync 2013 助理</span><span class="sxs-lookup"><span data-stu-id="11682-110">Microsoft Lync 2013 Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11682-111">回應群組</span><span class="sxs-lookup"><span data-stu-id="11682-111">Response Groups</span></span></p></td>
<td><p><span data-ttu-id="11682-112">通訊群組清單展開</span><span class="sxs-lookup"><span data-stu-id="11682-112">Distribution list expansion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11682-113">通訊錄下載與通訊錄查詢</span><span class="sxs-lookup"><span data-stu-id="11682-113">Address book download and address book query</span></span></p></td>
<td><p><span data-ttu-id="11682-114">增強型9-1-1 （E9-1）通話和位置設定檔（撥號方案）</span><span class="sxs-lookup"><span data-stu-id="11682-114">Enhanced 9-1-1 (E9-1-1) calls and location profile (dial plan)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11682-115">重視</span><span class="sxs-lookup"><span data-stu-id="11682-115">MultiView</span></span></p></td>
<td><p><span data-ttu-id="11682-116">從會議中查看多個資料流程</span><span class="sxs-lookup"><span data-stu-id="11682-116">Viewing multiple streams from a conference</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="11682-117">Lync Server 2013 應力和效能工具僅支援透過高級設定進行跨池負載產生與同盟。</span><span class="sxs-lookup"><span data-stu-id="11682-117">The Lync Server 2013 Stress and Performance Tool supports cross-pool load generation and federation through advanced configuration only.</span></span>

<span data-ttu-id="11682-118">此工具也不會模擬下列用戶端的使用者負載：</span><span class="sxs-lookup"><span data-stu-id="11682-118">The tool also does not simulate user load for the following clients:</span></span>

  - <span data-ttu-id="11682-119">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="11682-119">Office Live Meeting 2007</span></span>

  - <span data-ttu-id="11682-120">Lync 2013 持續聊天</span><span class="sxs-lookup"><span data-stu-id="11682-120">Lync 2013 Persistent Chat</span></span>

<span data-ttu-id="11682-121">因此，Lync Server 2013 的應力和效能工具將不支援測試下列元件：</span><span class="sxs-lookup"><span data-stu-id="11682-121">As a result, the Lync Server 2013 Stress and Performance Tool will not support testing the following components:</span></span>

  - <span data-ttu-id="11682-122">Lync 2013 持續聊天</span><span class="sxs-lookup"><span data-stu-id="11682-122">Lync 2013 Persistent Chat</span></span>

  - <span data-ttu-id="11682-123">Exchange 整合案例</span><span class="sxs-lookup"><span data-stu-id="11682-123">Exchange integration scenarios</span></span>

<div>

## <a name="applications-and-files-included-with-the-lync-server-2013-stress-and-performance-tool"></a><span data-ttu-id="11682-124">Lync Server 2013 應力和效能工具隨附的應用程式和檔案</span><span class="sxs-lookup"><span data-stu-id="11682-124">Applications and Files Included with the Lync Server 2013 Stress and Performance Tool</span></span>

<span data-ttu-id="11682-125">Lync Server 2013 應力和效能工具組含下列應用程式：</span><span class="sxs-lookup"><span data-stu-id="11682-125">The following applications are included in the Lync Server 2013 Stress and Performance Tool:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11682-126">工具箱</span><span class="sxs-lookup"><span data-stu-id="11682-126">Tool</span></span></th>
<th><span data-ttu-id="11682-127">說明</span><span class="sxs-lookup"><span data-stu-id="11682-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11682-128">UserProvisioningTool</span><span class="sxs-lookup"><span data-stu-id="11682-128">UserProvisioningTool.exe</span></span></p></td>
<td><p><span data-ttu-id="11682-129">Lync Server 2013 使用者提供工具。</span><span class="sxs-lookup"><span data-stu-id="11682-129">The Lync Server 2013 User Provisioning tool.</span></span> <span data-ttu-id="11682-130">此工具可用來建立使用者和連絡人。</span><span class="sxs-lookup"><span data-stu-id="11682-130">This tool is used to create users and contacts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11682-131">UserProfileGenerator</span><span class="sxs-lookup"><span data-stu-id="11682-131">UserProfileGenerator.exe</span></span></p></td>
<td><p><span data-ttu-id="11682-132">Lync Server 2013 載入組態工具。</span><span class="sxs-lookup"><span data-stu-id="11682-132">The Lync Server 2013 Load Configuration Tool.</span></span> <span data-ttu-id="11682-133">此工具可用來設定要模擬的使用者負載特性。</span><span class="sxs-lookup"><span data-stu-id="11682-133">This tool is used to configure the characteristics of the user load to simulate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11682-134">LyncPerfTool</span><span class="sxs-lookup"><span data-stu-id="11682-134">LyncPerfTool.exe</span></span></p></td>
<td><p><span data-ttu-id="11682-135">Lync Server 2013 應力和效能工具。</span><span class="sxs-lookup"><span data-stu-id="11682-135">The Lync Server 2013 Stress and Performance Tool.</span></span> <span data-ttu-id="11682-136">LyncPerfTool 是類比使用者負載的工具。</span><span class="sxs-lookup"><span data-stu-id="11682-136">LyncPerfTool is the tool that simulates the user load.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11682-137">預設的 tmx</span><span class="sxs-lookup"><span data-stu-id="11682-137">Default.tmx</span></span></p></td>
<td><p><span data-ttu-id="11682-138">使用 Lync Server 2013 記錄工具時，必須使用預設的 tmx。</span><span class="sxs-lookup"><span data-stu-id="11682-138">Default.tmx is required to use the Lync Server 2013 Logging Tool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11682-139">配置腳本範例</span><span class="sxs-lookup"><span data-stu-id="11682-139">Example provisioning scripts</span></span></p></td>
<td><p><span data-ttu-id="11682-140">這些範例是用來根據特定案例來設定執行負載測試的拓朴</span><span class="sxs-lookup"><span data-stu-id="11682-140">These examples are used to configure the topology for running load tests, based on specific scenarios</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

