---
title: Lync Server 2013：將 Microsoft SIP 處理語言（MSPL）應用程式標示為重要或不重要
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical
ms:assetid: df68fdc6-b7e6-4f07-acdc-0cd4c2c888a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182598(v=OCS.15)
ms:contentKeyID: 48185622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 419a162e355434972216f0c47d79850af28cd244
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975630"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical-in-lync-server-2013"></a><span data-ttu-id="23ed7-102">在 Lync Server 2013 中將 Microsoft SIP 處理語言（MSPL）應用程式標示為重要或不重要</span><span class="sxs-lookup"><span data-stu-id="23ed7-102">Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23ed7-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="23ed7-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="23ed7-104">Microsoft SIP 處理語言（MSPL）伺服器應用程式是使用 MSPL 指令碼語言（而不是 Microsoft Lync 2010 API）的腳本式應用程式。</span><span class="sxs-lookup"><span data-stu-id="23ed7-104">Microsoft SIP Processing Language (MSPL) server applications are script-only applications that use the MSPL scripting language instead of the Microsoft Lync 2010 API.</span></span> <span data-ttu-id="23ed7-105">某些 MSPL 伺服器應用程式是指定為重要的。</span><span class="sxs-lookup"><span data-stu-id="23ed7-105">Some MSPL server applications are specified as critical.</span></span> <span data-ttu-id="23ed7-106">如果腳本是重要的，則必須在系統啟動期間啟動腳本，才能開始使用 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="23ed7-106">If a script is critical, the script must start during system startup in order for Lync Server 2013 to start.</span></span> <span data-ttu-id="23ed7-107">如果腳本在 Lync Server 執行時失敗，伺服器不會關閉，但會停止傳送資料流程給腳本，而且會在事件記錄檔中寫入錯誤。</span><span class="sxs-lookup"><span data-stu-id="23ed7-107">If the script fails while Lync Server is running, the server does not shut down, but it stops sending traffic to the script, and it writes errors in the event log.</span></span>

<span data-ttu-id="23ed7-108">您可以使用 Lync Server [控制台] 將 Microsoft SIP 處理語言（MSPL）伺服器應用程式標示為重要或解除標記。</span><span class="sxs-lookup"><span data-stu-id="23ed7-108">You can use Lync Server Control Panel to mark Microsoft SIP Processing Language (MSPL) server applications as critical or unmark them.</span></span>

<span data-ttu-id="23ed7-109">並非所有的腳本都支援此選項。</span><span class="sxs-lookup"><span data-stu-id="23ed7-109">Not all scripts support this option.</span></span> <span data-ttu-id="23ed7-110">例如，DefaultRouting 腳本標示為重要，且此選項無法針對 DefaultRouting 進行變更。</span><span class="sxs-lookup"><span data-stu-id="23ed7-110">For example, the DefaultRouting script is marked as critical, and this option cannot be changed for DefaultRouting.</span></span>

<div>

## <a name="to-mark-or-unmark-an-mspl-server-application-as-critical"></a><span data-ttu-id="23ed7-111">將 MSPL 伺服器應用程式標示或解除標記為重要</span><span class="sxs-lookup"><span data-stu-id="23ed7-111">To mark or unmark an MSPL server application as critical</span></span>

1.  <span data-ttu-id="23ed7-112">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署 Lync Server 2013 的網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="23ed7-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="23ed7-113">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="23ed7-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="23ed7-114">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="23ed7-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="23ed7-115">在左側導覽列中，按一下 [**拓撲圖**]，然後按一下 [**伺服器應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="23ed7-115">In the left navigation bar, click **Topology** and then click **Server Application**.</span></span>

4.  <span data-ttu-id="23ed7-116">如有需要，請在 [**伺服器應用程式**] 頁面上，按一下欄標題來排序應用程式，然後按一下您要修改的伺服器應用程式。</span><span class="sxs-lookup"><span data-stu-id="23ed7-116">On the **Server Application** page, click a column heading to sort the applications, if needed, and then click the server application that you want to modify.</span></span>

5.  <span data-ttu-id="23ed7-117">按一下 [**動作**]。</span><span class="sxs-lookup"><span data-stu-id="23ed7-117">Click **Action**.</span></span>

6.  <span data-ttu-id="23ed7-118">按一下 [**標示為重要**] 或 [**取消選取為重要**] （也就是如果腳本支援此選項）。</span><span class="sxs-lookup"><span data-stu-id="23ed7-118">Click **Mark as critical** or **Unselect as critical** (that is, if the script supports this option).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="23ed7-119">請參閱</span><span class="sxs-lookup"><span data-stu-id="23ed7-119">See Also</span></span>


[<span data-ttu-id="23ed7-120">在 Lync Server 2013 中啟用或停用 Microsoft SIP 處理語言（MSPL）伺服器應用程式</span><span class="sxs-lookup"><span data-stu-id="23ed7-120">Enable or disable a Microsoft SIP Processing Language (MSPL) server application in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  


[<span data-ttu-id="23ed7-121">在 Lync Server 2013 中檢視 Microsoft SIP Processing Language (MSPL) 伺服器應用程式</span><span class="sxs-lookup"><span data-stu-id="23ed7-121">View Microsoft SIP Processing Language (MSPL) server applications in Lync Server 2013</span></span>](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[<span data-ttu-id="23ed7-122">管理 Lync Server 2013 拓撲</span><span class="sxs-lookup"><span data-stu-id="23ed7-122">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

