---
title: 將 Lync Server 電腦設定為參與 System Center 探索
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring the Lync Server computer to participate in System Center discovery
ms:assetid: 2f9c9cb0-3120-4571-9cd2-657c2123fe21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204776(v=OCS.15)
ms:contentKeyID: 48183731
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4b50fad3e0d197259847db9a94bf9e64618d7e2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974462"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-lync-server-2013-computer-to-participate-in-system-center-discovery"></a><span data-ttu-id="cc754-102">將 Lync Server 2013 電腦設定為參與 System Center 探索</span><span class="sxs-lookup"><span data-stu-id="cc754-102">Configuring the Lync Server 2013 computer to participate in System Center discovery</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc754-103">_**主題上次修改日期：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="cc754-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="cc754-104">若要確保您的新 Lync Server agent 參與 System Center Operations Manager 的探索程式，您必須在安裝 System Center Operations Manager 主控台的每台電腦上完成下列程式：</span><span class="sxs-lookup"><span data-stu-id="cc754-104">To make sure that your new Lync Server agent participates in discovery process for System Center Operations Manager, you must complete the following procedure on each computer where the System Center Operations Manager console has been installed:</span></span>

1.  <span data-ttu-id="cc754-105">按一下 [**管理**] 索引標籤上的 [**代理程式管理**]。</span><span class="sxs-lookup"><span data-stu-id="cc754-105">On the **Administration** tab, click **Agent Managed**.</span></span>

2.  <span data-ttu-id="cc754-106">以滑鼠右鍵按一下電腦的名稱，然後按一下 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="cc754-106">Right-click the name of the computer, and then click **Properties**.</span></span> <span data-ttu-id="cc754-107">在 [內容 **] 對話方塊的 [** **安全性**] 索引標籤上，選取 [**允許此代理程式充當 proxy 並探索其他電腦上的 managed 物件**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="cc754-107">In the **Properties** dialog box, on the **Security** tab, select **Allow this agent to act as a proxy and discover managed objects on other computers**, and then click **OK**.</span></span>

<span data-ttu-id="cc754-108">完成步驟2之後，請重新開機 Health 代理服務。</span><span class="sxs-lookup"><span data-stu-id="cc754-108">After completing step 2, reboot the Health Agent service.</span></span> <span data-ttu-id="cc754-109">（重新開機服務將會「強制」探索新的電腦。</span><span class="sxs-lookup"><span data-stu-id="cc754-109">(Rebooting the service will “force” discovery of the new machine.</span></span> <span data-ttu-id="cc754-110">如果您不重新開機服務，系統中心作業管理員可能需要4小時的時間才能探索新電腦。</span><span class="sxs-lookup"><span data-stu-id="cc754-110">If you do not reboot the service, it could take as long as 4 hours before the new machine is discovered by System Center Operations Manager.).</span></span> <span data-ttu-id="cc754-111">重新開機服務之後，請確認該電腦上的 Operations Manager 事件記錄中沒有記錄任何錯誤事件。</span><span class="sxs-lookup"><span data-stu-id="cc754-111">After the service has rebooted, verify that no error events are being recorded in the Operations Manager event log on that computer.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

