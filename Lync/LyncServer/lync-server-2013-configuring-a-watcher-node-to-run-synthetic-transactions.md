---
title: Lync Server 2013：設定觀察程式節點以執行綜合交易
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a watcher node to run synthetic transactions
ms:assetid: cedda508-8881-4079-88d5-49798f342ddf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205314(v=OCS.15)
ms:contentKeyID: 48185578
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ec42f5b0f3839ee0efac84f08344aa1718120b7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974594"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-to-run-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="14a8a-102">將觀察程式節點設定為在 Lync Server 2013 中執行綜合交易</span><span class="sxs-lookup"><span data-stu-id="14a8a-102">Configuring a watcher node to run synthetic transactions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14a8a-103">_**主題上次修改日期：** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="14a8a-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="14a8a-104">安裝系統中心代理盤案之後，您必須接著設定 [觀察程式] 節點本身。</span><span class="sxs-lookup"><span data-stu-id="14a8a-104">After the System Center agent files have been installed, you must next configure the watcher node itself.</span></span> <span data-ttu-id="14a8a-105">您針對配置觀察程式節點所採取的步驟，會根據您的觀察者節點電腦是否位於周邊網路內或周邊網路外部而有所不同。</span><span class="sxs-lookup"><span data-stu-id="14a8a-105">The steps you take to configure a watcher node will vary depending on whether your watcher node computer lies inside your perimeter network or outside your perimeter network.</span></span>

<span data-ttu-id="14a8a-106">當您設定 [觀察程式] 節點時，您也必須選擇該節點要採用的驗證方法類型。</span><span class="sxs-lookup"><span data-stu-id="14a8a-106">When you configure a watcher node, you must also choose the type of authentication method to be employed by that node.</span></span> <span data-ttu-id="14a8a-107">Lync Server 2013 可讓您選擇其中一種驗證方法： [信任伺服器] 或 [認證驗證]。</span><span class="sxs-lookup"><span data-stu-id="14a8a-107">Lync Server 2013 enables you to choose one of two authentication methods: Trusted Server or Credential Authentication.</span></span> <span data-ttu-id="14a8a-108">下列兩種方法間的差異如下表所示：</span><span class="sxs-lookup"><span data-stu-id="14a8a-108">The differences between these two methods are outlined in the following table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="14a8a-109">Configuration</span><span class="sxs-lookup"><span data-stu-id="14a8a-109">Configuration</span></span></th>
<th><span data-ttu-id="14a8a-110">描述</span><span class="sxs-lookup"><span data-stu-id="14a8a-110">Description</span></span></th>
<th><span data-ttu-id="14a8a-111">支援的位置</span><span class="sxs-lookup"><span data-stu-id="14a8a-111">Locations Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="14a8a-112">受信任的伺服器</span><span class="sxs-lookup"><span data-stu-id="14a8a-112">Trusted Server</span></span></p></td>
<td><p><span data-ttu-id="14a8a-113">使用憑證來類比內部伺服器並略過驗證難題。</span><span class="sxs-lookup"><span data-stu-id="14a8a-113">Uses a certificate to impersonate an internal server and bypass authentication challenges.</span></span></p>
<p><span data-ttu-id="14a8a-114">這對想要在每個觀察程式節點上管理單一憑證而不是多個使用者密碼的管理員很有用。</span><span class="sxs-lookup"><span data-stu-id="14a8a-114">This is useful for administrators who would prefer to manage a single certificate instead of many user passwords on each watcher node.</span></span></p></td>
<td><p><span data-ttu-id="14a8a-115">在企業內。</span><span class="sxs-lookup"><span data-stu-id="14a8a-115">Inside the enterprise.</span></span></p>
<p><span data-ttu-id="14a8a-116">請注意，使用此方法時，觀察程式節點必須與受監視的池位於同一個網域中。</span><span class="sxs-lookup"><span data-stu-id="14a8a-116">Note that, with this method, the watcher node must be in the same domain as the pools being monitored.</span></span> <span data-ttu-id="14a8a-117">如果觀察程式節點和受監視的池都在不同的網域中，請改用認證驗證。</span><span class="sxs-lookup"><span data-stu-id="14a8a-117">If the watcher node and the monitored pools are in different domains, use Credential Authentication instead.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14a8a-118">認證驗證</span><span class="sxs-lookup"><span data-stu-id="14a8a-118">Credential Authentication</span></span></p></td>
<td><p><span data-ttu-id="14a8a-119">在每個觀察程式節點上安全地儲存在 Windows 認證管理器中的使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="14a8a-119">Stores user names and passwords securely in Windows Credential Manager on each watcher node.</span></span></p>
<p><span data-ttu-id="14a8a-120">這個模式需要更多的密碼管理，但是位於企業外部的 [觀察程式] 節點唯一的選項。</span><span class="sxs-lookup"><span data-stu-id="14a8a-120">This mode requires more password management, but is the only option for watcher nodes located outside of the enterprise.</span></span> <span data-ttu-id="14a8a-121">這些觀察程式節點無法被視為受信任的端點以進行驗證。</span><span class="sxs-lookup"><span data-stu-id="14a8a-121">These watcher nodes cannot be treated as an endpoint trusted for authentication.</span></span></p></td>
<td><p><span data-ttu-id="14a8a-122">在企業外部。</span><span class="sxs-lookup"><span data-stu-id="14a8a-122">Outside the enterprise.</span></span></p>
<p><span data-ttu-id="14a8a-123">在企業內。</span><span class="sxs-lookup"><span data-stu-id="14a8a-123">Inside the enterprise.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="14a8a-124">您也應該確認您的防火牆對 MonitoringHost 和 ngen.exe 都有入站規則。</span><span class="sxs-lookup"><span data-stu-id="14a8a-124">You should also verify that your firewall has inbound rules for both MonitoringHost.exe and PowerShell.exe.</span></span> <span data-ttu-id="14a8a-125">如果防火牆封鎖這些程式，則您的綜合交易將會失敗，並出現504（伺服器超時）錯誤。</span><span class="sxs-lookup"><span data-stu-id="14a8a-125">If these processes are blocked by the firewall then your synthetic transactions will fail with a 504 (server timeout) error.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

