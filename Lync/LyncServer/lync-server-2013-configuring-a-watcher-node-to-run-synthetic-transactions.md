---
title: Lync Server 2013： 設定監看員節點以執行綜合交易
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
ms.openlocfilehash: 107803caba66c19ec852d4c077e69aec5f7cf5ca
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043465"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-to-run-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="69f2a-102">設定監看員節點以 Lync Server 2013 中執行的綜合交易</span><span class="sxs-lookup"><span data-stu-id="69f2a-102">Configuring a watcher node to run synthetic transactions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69f2a-103">_**上次修改主題：** 2014年-02-07_</span><span class="sxs-lookup"><span data-stu-id="69f2a-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="69f2a-104">在安裝 System Center 代理程式檔案之後，您必須下一步] 設定監看員節點本身。</span><span class="sxs-lookup"><span data-stu-id="69f2a-104">After the System Center agent files have been installed, you must next configure the watcher node itself.</span></span> <span data-ttu-id="69f2a-105">設定監看員節點所採取的步驟將視您的監看員節點電腦位於周邊網路內或周邊網路外而異。</span><span class="sxs-lookup"><span data-stu-id="69f2a-105">The steps you take to configure a watcher node will vary depending on whether your watcher node computer lies inside your perimeter network or outside your perimeter network.</span></span>

<span data-ttu-id="69f2a-106">當您設定監看員節點時，您也必須選擇該節點要使用的驗證方法的型別。</span><span class="sxs-lookup"><span data-stu-id="69f2a-106">When you configure a watcher node, you must also choose the type of authentication method to be employed by that node.</span></span> <span data-ttu-id="69f2a-107">Lync Server 2013 可讓您選擇下列其中一個兩種驗證方法： 信任的伺服器] 或 [認證驗證。</span><span class="sxs-lookup"><span data-stu-id="69f2a-107">Lync Server 2013 enables you to choose one of two authentication methods: Trusted Server or Credential Authentication.</span></span> <span data-ttu-id="69f2a-108">下表列出這兩個方法之間的差異：</span><span class="sxs-lookup"><span data-stu-id="69f2a-108">The differences between these two methods are outlined in the following table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69f2a-109">組態</span><span class="sxs-lookup"><span data-stu-id="69f2a-109">Configuration</span></span></th>
<th><span data-ttu-id="69f2a-110">描述</span><span class="sxs-lookup"><span data-stu-id="69f2a-110">Description</span></span></th>
<th><span data-ttu-id="69f2a-111">支援的位置</span><span class="sxs-lookup"><span data-stu-id="69f2a-111">Locations Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69f2a-112">受信任的伺服器</span><span class="sxs-lookup"><span data-stu-id="69f2a-112">Trusted Server</span></span></p></td>
<td><p><span data-ttu-id="69f2a-113">使用憑證來模擬內部伺服器，並略過驗證質詢。</span><span class="sxs-lookup"><span data-stu-id="69f2a-113">Uses a certificate to impersonate an internal server and bypass authentication challenges.</span></span></p>
<p><span data-ttu-id="69f2a-114">這種方法適合偏好管理單一憑證而不是每個監看員節點上的許多使用者密碼的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="69f2a-114">This is useful for administrators who would prefer to manage a single certificate instead of many user passwords on each watcher node.</span></span></p></td>
<td><p><span data-ttu-id="69f2a-115">企業內部。</span><span class="sxs-lookup"><span data-stu-id="69f2a-115">Inside the enterprise.</span></span></p>
<p><span data-ttu-id="69f2a-116">請注意，使用此方法時，監看員節點必須集區相同網域中受監視。</span><span class="sxs-lookup"><span data-stu-id="69f2a-116">Note that, with this method, the watcher node must be in the same domain as the pools being monitored.</span></span> <span data-ttu-id="69f2a-117">如果監看員節點和受監視的集區是在不同的網域，請改為使用認證驗證。</span><span class="sxs-lookup"><span data-stu-id="69f2a-117">If the watcher node and the monitored pools are in different domains, use Credential Authentication instead.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69f2a-118">認證驗證</span><span class="sxs-lookup"><span data-stu-id="69f2a-118">Credential Authentication</span></span></p></td>
<td><p><span data-ttu-id="69f2a-119">儲存使用者名稱和密碼安全地以 Windows 認證管理員在每個監看員節點上。</span><span class="sxs-lookup"><span data-stu-id="69f2a-119">Stores user names and passwords securely in Windows Credential Manager on each watcher node.</span></span></p>
<p><span data-ttu-id="69f2a-120">此模式需要更多的密碼管理，但位於企業外的監看員節點的唯一選項。</span><span class="sxs-lookup"><span data-stu-id="69f2a-120">This mode requires more password management, but is the only option for watcher nodes located outside of the enterprise.</span></span> <span data-ttu-id="69f2a-121">這些監看員節點無法被視為受信任的驗證端點。</span><span class="sxs-lookup"><span data-stu-id="69f2a-121">These watcher nodes cannot be treated as an endpoint trusted for authentication.</span></span></p></td>
<td><p><span data-ttu-id="69f2a-122">於企業外。</span><span class="sxs-lookup"><span data-stu-id="69f2a-122">Outside the enterprise.</span></span></p>
<p><span data-ttu-id="69f2a-123">企業內部。</span><span class="sxs-lookup"><span data-stu-id="69f2a-123">Inside the enterprise.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="69f2a-124">您也應確認您的防火牆都有輸入規則 MonitoringHost.exe 和 PowerShell.exe。</span><span class="sxs-lookup"><span data-stu-id="69f2a-124">You should also verify that your firewall has inbound rules for both MonitoringHost.exe and PowerShell.exe.</span></span> <span data-ttu-id="69f2a-125">如果這些處理程序會被防火牆封鎖，則您的綜合交易，將會失敗並 504 （伺服器逾時） 時發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="69f2a-125">If these processes are blocked by the firewall then your synthetic transactions will fail with a 504 (server timeout) error.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

