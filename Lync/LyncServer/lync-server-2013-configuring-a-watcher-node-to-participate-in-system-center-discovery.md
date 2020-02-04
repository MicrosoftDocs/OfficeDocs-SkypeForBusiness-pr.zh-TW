---
title: 將觀察程式節點設定為參與 System Center 探索
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
ms.openlocfilehash: 9ca3724f9b5bc8200e2ca006d9fa7445d7368ab7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763487"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-participate-in-system-center-discovery"></a><span data-ttu-id="1ebe3-102">在 Lync Server 2013 中設定 [觀察程式] 節點，以參與 System Center 探索</span><span class="sxs-lookup"><span data-stu-id="1ebe3-102">Configuring a watcher node in Lync Server 2013 to participate in System Center discovery</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ebe3-103">_**主題上次修改日期：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="1ebe3-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="1ebe3-104">若要確保您的觀察程式節點參與 System Center Operations Manager 的探索程式，您必須在已安裝 System Center Operations Manager 主控台的電腦上完成下列程式：</span><span class="sxs-lookup"><span data-stu-id="1ebe3-104">To make sure that your watcher node participates in the discovery process for System Center Operations Manager, you must complete the following procedure on a computer where the System Center Operations Manager console has been installed:</span></span>

1.  <span data-ttu-id="1ebe3-105">按一下 [**管理**] 索引標籤上的 [**代理程式管理**]。</span><span class="sxs-lookup"><span data-stu-id="1ebe3-105">On the **Administration** tab, click **Agent Managed**.</span></span>

2.  <span data-ttu-id="1ebe3-106">以滑鼠右鍵按一下觀察程式節點電腦的名稱，然後按一下 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="1ebe3-106">Right-click the name of the watcher node computer, and then click **Properties**.</span></span> <span data-ttu-id="1ebe3-107">在 [內容 **] 對話方塊的 [** **安全性**] 索引標籤上，選取 [**允許此代理程式充當 proxy 並探索其他電腦上的 managed 物件**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="1ebe3-107">In the **Properties** dialog box, on the **Security** tab, select **Allow this agent to act as a proxy and discover managed objects on other computers**, and then click **OK**.</span></span>

<span data-ttu-id="1ebe3-108">將觀察程式節點設定為 proxy 之後，請重新開機觀察程式節點電腦。</span><span class="sxs-lookup"><span data-stu-id="1ebe3-108">After configuring the watcher node to act as a proxy, reboot the watcher node computer.</span></span> <span data-ttu-id="1ebe3-109">重新開機電腦之後，請確認該電腦上的 Operations Manager 事件記錄中沒有記錄任何錯誤事件。</span><span class="sxs-lookup"><span data-stu-id="1ebe3-109">After the computer has rebooted, verify that no error events are being recorded in the Operations Manager event log on that computer.</span></span> <span data-ttu-id="1ebe3-110">在電腦執行15分鐘之後，請使用 Operations Manager 主控台驗證 lync Server 電腦是否列在**lync**類別底下。</span><span class="sxs-lookup"><span data-stu-id="1ebe3-110">After the computer has been running for 15 minutes or so, use the Operations Manager console to verify that your Lync Server computers are listed under the **Lync** category.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

