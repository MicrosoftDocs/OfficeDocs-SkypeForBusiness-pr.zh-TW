---
title: Lync Server 2013：設定監視節點以執行綜合交易
description: Lync Server 2013：設定監視節點以執行綜合交易。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to run synthetic transactions
ms:assetid: cedda508-8881-4079-88d5-49798f342ddf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205314(v=OCS.15)
ms:contentKeyID: 48185578
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd5fdb3d1a1499a6ef79e962a41d9eb3ee174c33
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567879"
---
# <a name="configuring-a-watcher-node-to-run-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="728eb-103">在 Lync Server 2013 中設定監視節點以執行綜合交易</span><span class="sxs-lookup"><span data-stu-id="728eb-103">Configuring a watcher node to run synthetic transactions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="728eb-104">_**主題上次修改日期：** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="728eb-104">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="728eb-105">安裝 System Center agent 檔案之後，您必須接著設定觀察程式節點本身。</span><span class="sxs-lookup"><span data-stu-id="728eb-105">After the System Center agent files have been installed, you must next configure the watcher node itself.</span></span> <span data-ttu-id="728eb-106">您用來設定監看員節點的步驟會隨著您的監看員節點電腦位於周邊網路或周邊網路以外的情況而有所不同。</span><span class="sxs-lookup"><span data-stu-id="728eb-106">The steps you take to configure a watcher node will vary depending on whether your watcher node computer lies inside your perimeter network or outside your perimeter network.</span></span>

<span data-ttu-id="728eb-107">當您設定監視節點時，您也必須選擇該節點要使用的驗證方法類型。</span><span class="sxs-lookup"><span data-stu-id="728eb-107">When you configure a watcher node, you must also choose the type of authentication method to be employed by that node.</span></span> <span data-ttu-id="728eb-108">Lync Server 2013 可讓您選擇兩種驗證方法之一：「信任的伺服器」或「憑證驗證」。</span><span class="sxs-lookup"><span data-stu-id="728eb-108">Lync Server 2013 enables you to choose one of two authentication methods: Trusted Server or Credential Authentication.</span></span> <span data-ttu-id="728eb-109">下表概述這兩種方法之間的差異：</span><span class="sxs-lookup"><span data-stu-id="728eb-109">The differences between these two methods are outlined in the following table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="728eb-110">組態</span><span class="sxs-lookup"><span data-stu-id="728eb-110">Configuration</span></span></th>
<th><span data-ttu-id="728eb-111">描述</span><span class="sxs-lookup"><span data-stu-id="728eb-111">Description</span></span></th>
<th><span data-ttu-id="728eb-112">支援的位置</span><span class="sxs-lookup"><span data-stu-id="728eb-112">Locations Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="728eb-113">受信任伺服器</span><span class="sxs-lookup"><span data-stu-id="728eb-113">Trusted Server</span></span></p></td>
<td><p><span data-ttu-id="728eb-114">使用憑證來模擬內部伺服器並略過驗證挑戰。</span><span class="sxs-lookup"><span data-stu-id="728eb-114">Uses a certificate to impersonate an internal server and bypass authentication challenges.</span></span></p>
<p><span data-ttu-id="728eb-115">這對喜歡管理單一憑證，而不是在每個監看員節點上使用許多使用者密碼的系統管理員非常有用。</span><span class="sxs-lookup"><span data-stu-id="728eb-115">This is useful for administrators who would prefer to manage a single certificate instead of many user passwords on each watcher node.</span></span></p></td>
<td><p><span data-ttu-id="728eb-116">在企業內。</span><span class="sxs-lookup"><span data-stu-id="728eb-116">Inside the enterprise.</span></span></p>
<p><span data-ttu-id="728eb-117">請注意，使用此方法時，監看員節點必須與受監控的集區位於相同的網域中。</span><span class="sxs-lookup"><span data-stu-id="728eb-117">Note that, with this method, the watcher node must be in the same domain as the pools being monitored.</span></span> <span data-ttu-id="728eb-118">如果觀察程式節點與受監視的集區位於不同的網域，請改用認證驗證。</span><span class="sxs-lookup"><span data-stu-id="728eb-118">If the watcher node and the monitored pools are in different domains, use Credential Authentication instead.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="728eb-119">憑證驗證</span><span class="sxs-lookup"><span data-stu-id="728eb-119">Credential Authentication</span></span></p></td>
<td><p><span data-ttu-id="728eb-120">在每個監看員節點上安全地將使用者名稱和密碼儲存在 Windows 認證管理員中。</span><span class="sxs-lookup"><span data-stu-id="728eb-120">Stores user names and passwords securely in Windows Credential Manager on each watcher node.</span></span></p>
<p><span data-ttu-id="728eb-121">這種模式需要較多的密碼管理，但對於位於企業以外的觀察器節點而言，這是唯一的選擇。</span><span class="sxs-lookup"><span data-stu-id="728eb-121">This mode requires more password management, but is the only option for watcher nodes located outside of the enterprise.</span></span> <span data-ttu-id="728eb-122">這些觀察器節點不能視為可信任的端點以進行驗證。</span><span class="sxs-lookup"><span data-stu-id="728eb-122">These watcher nodes cannot be treated as an endpoint trusted for authentication.</span></span></p></td>
<td><p><span data-ttu-id="728eb-123">在企業外。</span><span class="sxs-lookup"><span data-stu-id="728eb-123">Outside the enterprise.</span></span></p>
<p><span data-ttu-id="728eb-124">在企業內。</span><span class="sxs-lookup"><span data-stu-id="728eb-124">Inside the enterprise.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="728eb-125">您也應該確認您的防火牆同時具有 MonitoringHost.exe 和 PowerShell.exe 的輸入規則。</span><span class="sxs-lookup"><span data-stu-id="728eb-125">You should also verify that your firewall has inbound rules for both MonitoringHost.exe and PowerShell.exe.</span></span> <span data-ttu-id="728eb-126">如果這些程式被防火牆封鎖，則綜合交易會失敗，並顯示 504 (伺服器超時) 錯誤。</span><span class="sxs-lookup"><span data-stu-id="728eb-126">If these processes are blocked by the firewall then your synthetic transactions will fail with a 504 (server timeout) error.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

