---
title: Lync Server 2013：將 Microsoft SIP 處理語言 (MSPL) 應用程式標示為關鍵或非關鍵
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical
ms:assetid: df68fdc6-b7e6-4f07-acdc-0cd4c2c888a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182598(v=OCS.15)
ms:contentKeyID: 48185622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42c40b115e81736cbbf8769292ab251953d3a752
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524760"
---
# <a name="mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical-in-lync-server-2013"></a><span data-ttu-id="eaa1c-102">在 Lync Server 2013 中將 Microsoft SIP 處理語言 (MSPL) 應用程式標示為關鍵或非關鍵</span><span class="sxs-lookup"><span data-stu-id="eaa1c-102">Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eaa1c-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="eaa1c-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="eaa1c-104">Microsoft SIP 處理語言 (MSPL) 伺服器應用程式是僅限腳本的應用程式，使用 MSPL 指令碼語言，而不是 Microsoft Lync 2010 API。</span><span class="sxs-lookup"><span data-stu-id="eaa1c-104">Microsoft SIP Processing Language (MSPL) server applications are script-only applications that use the MSPL scripting language instead of the Microsoft Lync 2010 API.</span></span> <span data-ttu-id="eaa1c-105">某些 MSPL 伺服器應用程式會指定為重要。</span><span class="sxs-lookup"><span data-stu-id="eaa1c-105">Some MSPL server applications are specified as critical.</span></span> <span data-ttu-id="eaa1c-106">如果腳本很重要，必須在系統啟動期間啟動腳本，Lync Server 2013 才能啟動。</span><span class="sxs-lookup"><span data-stu-id="eaa1c-106">If a script is critical, the script must start during system startup in order for Lync Server 2013 to start.</span></span> <span data-ttu-id="eaa1c-107">如果腳本在執行 Lync Server 時失敗，則伺服器不會關機，但是會停止傳送流量至腳本，而且會在事件記錄檔中寫入錯誤。</span><span class="sxs-lookup"><span data-stu-id="eaa1c-107">If the script fails while Lync Server is running, the server does not shut down, but it stops sending traffic to the script, and it writes errors in the event log.</span></span>

<span data-ttu-id="eaa1c-108">您可以使用 Lync Server 控制台，將 Microsoft SIP 處理語言 (MSPL) 伺服器應用程式標示為關鍵或解除標記。</span><span class="sxs-lookup"><span data-stu-id="eaa1c-108">You can use Lync Server Control Panel to mark Microsoft SIP Processing Language (MSPL) server applications as critical or unmark them.</span></span>

<span data-ttu-id="eaa1c-109">並非所有腳本都支援此選項。</span><span class="sxs-lookup"><span data-stu-id="eaa1c-109">Not all scripts support this option.</span></span> <span data-ttu-id="eaa1c-110">例如，DefaultRouting 腳本會標示為 [重要]，而且無法為 DefaultRouting 變更此選項。</span><span class="sxs-lookup"><span data-stu-id="eaa1c-110">For example, the DefaultRouting script is marked as critical, and this option cannot be changed for DefaultRouting.</span></span>

<div>

## <a name="to-mark-or-unmark-an-mspl-server-application-as-critical"></a><span data-ttu-id="eaa1c-111">將 MSPL 伺服器應用程式標示為關鍵或解除標記</span><span class="sxs-lookup"><span data-stu-id="eaa1c-111">To mark or unmark an MSPL server application as critical</span></span>

1.  <span data-ttu-id="eaa1c-112">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您已部署 Lync Server 2013 之網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="eaa1c-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="eaa1c-113">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="eaa1c-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="eaa1c-114">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="eaa1c-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="eaa1c-115">在左導覽列中，按一下 [ **拓撲** ]，然後按一下 [ **伺服器應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="eaa1c-115">In the left navigation bar, click **Topology** and then click **Server Application**.</span></span>

4.  <span data-ttu-id="eaa1c-116">在 [ **伺服器應用程式** ] 頁面上，按一下欄標題以排序應用程式（如有需要），然後按一下您要修改的伺服器應用程式。</span><span class="sxs-lookup"><span data-stu-id="eaa1c-116">On the **Server Application** page, click a column heading to sort the applications, if needed, and then click the server application that you want to modify.</span></span>

5.  <span data-ttu-id="eaa1c-117">按一下 **[動作]**。</span><span class="sxs-lookup"><span data-stu-id="eaa1c-117">Click **Action**.</span></span>

6.  <span data-ttu-id="eaa1c-118">按一下 [ **標示為緊急** ] 或 [ **取消選取為重要** 的 (，也就是，如果腳本支援此選項) 。</span><span class="sxs-lookup"><span data-stu-id="eaa1c-118">Click **Mark as critical** or **Unselect as critical** (that is, if the script supports this option).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="eaa1c-119">另請參閱</span><span class="sxs-lookup"><span data-stu-id="eaa1c-119">See Also</span></span>


[<span data-ttu-id="eaa1c-120">在 Lync Server 2013 中啟用或停用 Microsoft SIP 處理語言 (MSPL) 伺服器應用程式</span><span class="sxs-lookup"><span data-stu-id="eaa1c-120">Enable or disable a Microsoft SIP Processing Language (MSPL) server application in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  


[<span data-ttu-id="eaa1c-121">在 Lync Server 2013 中查看 Microsoft SIP 處理語言 (MSPL) 伺服器應用程式</span><span class="sxs-lookup"><span data-stu-id="eaa1c-121">View Microsoft SIP Processing Language (MSPL) server applications in Lync Server 2013</span></span>](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[<span data-ttu-id="eaa1c-122">管理 Lync Server 2013 拓撲</span><span class="sxs-lookup"><span data-stu-id="eaa1c-122">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

