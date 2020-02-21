---
title: 設定監看員節點以參與 System Center 搜索
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to participate in System Center discovery
ms:assetid: 15c5dcfd-603b-47ea-af1b-8714c2ec08af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204704(v=OCS.15)
ms:contentKeyID: 48183500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e5167ae007379bed9212651eaabfbca7ac7217ba
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208009"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-participate-in-system-center-discovery"></a><span data-ttu-id="63832-102">設定監看員節點以參與 System Center 搜索的 Lync Server 2013 中</span><span class="sxs-lookup"><span data-stu-id="63832-102">Configuring a watcher node in Lync Server 2013 to participate in System Center discovery</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63832-103">_**主題上次修改日期：** 2012年-10-22_</span><span class="sxs-lookup"><span data-stu-id="63832-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="63832-104">若要確保您的監看員節點參與探索程序中的 System Center Operations Manager，您必須完成下列程序已安裝 System Center Operations Manager 主控台的電腦上：</span><span class="sxs-lookup"><span data-stu-id="63832-104">To make sure that your watcher node participates in the discovery process for System Center Operations Manager, you must complete the following procedure on a computer where the System Center Operations Manager console has been installed:</span></span>

1.  <span data-ttu-id="63832-105">在 [管理]\*\*\*\* 索引標籤上，按一下 [代理程式管理]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="63832-105">On the **Administration** tab, click **Agent Managed**.</span></span>

2.  <span data-ttu-id="63832-p101">用滑鼠右鍵按一下監看員節點電腦的名稱，然後按一下 [內容]\*\*\*\*。在 [內容]\*\*\*\* 對話方塊中的 [安全性]\*\*\*\* 索引標籤上，選取 [允許此代理程式作為 Proxy 並探索其他電腦中的受管理物件]\*\*\*\*，然後按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="63832-p101">Right-click the name of the watcher node computer, and then click **Properties**. In the **Properties** dialog box, on the **Security** tab, select **Allow this agent to act as a proxy and discover managed objects on other computers**, and then click **OK**.</span></span>

<span data-ttu-id="63832-108">將監看員節點設為 Proxy 之後，重新啟動監看員節點電腦。</span><span class="sxs-lookup"><span data-stu-id="63832-108">After configuring the watcher node to act as a proxy, reboot the watcher node computer.</span></span> <span data-ttu-id="63832-109">電腦重新開機之後，請確認沒有錯誤事件會被記錄在 Operations Manager 事件記錄檔，該電腦上。</span><span class="sxs-lookup"><span data-stu-id="63832-109">After the computer has rebooted, verify that no error events are being recorded in the Operations Manager event log on that computer.</span></span> <span data-ttu-id="63832-110">已經執行之電腦的 15 分鐘左右之後，使用 Operations Manager 主控台中若要確認您的 Lync Server 電腦會列在**Lync**類別下。</span><span class="sxs-lookup"><span data-stu-id="63832-110">After the computer has been running for 15 minutes or so, use the Operations Manager console to verify that your Lync Server computers are listed under the **Lync** category.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

