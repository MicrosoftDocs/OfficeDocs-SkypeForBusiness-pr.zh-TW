---
title: Lync Server 2013：啟用或停用 Microsoft SIP 處理語言（MSPL）伺服器應用程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable a Microsoft SIP Processing Language (MSPL) server application
ms:assetid: b20af38d-224a-4459-991d-0b7eabb3ca7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182573(v=OCS.15)
ms:contentKeyID: 48185145
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da7ff3379f0e32166ceb263e1dbda46117b6984a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977217"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application-in-lync-server-2013"></a><span data-ttu-id="db176-102">在 Lync Server 2013 中啟用或停用 Microsoft SIP 處理語言（MSPL）伺服器應用程式</span><span class="sxs-lookup"><span data-stu-id="db176-102">Enable or disable a Microsoft SIP Processing Language (MSPL) server application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db176-103">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="db176-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="db176-104">您可以使用 Lync Server [控制台] 來啟用或停用您在 Lync Server 2013 環境中執行的 Microsoft SIP 處理語言（MSPL）伺服器應用程式。</span><span class="sxs-lookup"><span data-stu-id="db176-104">You can use Lync Server Control Panel to enable or disable Microsoft SIP Processing Language (MSPL) server applications that run in your Lync Server 2013 environment.</span></span> <span data-ttu-id="db176-105">這些應用程式是只使用指令碼語言的腳本式應用程式，而不是 Microsoft Lync 2013 Preview API。</span><span class="sxs-lookup"><span data-stu-id="db176-105">These applications are script-only applications that use a scripting language instead of the Microsoft Lync 2013 Preview API.</span></span>

<span data-ttu-id="db176-106">並非所有腳本都可以啟用或停用。</span><span class="sxs-lookup"><span data-stu-id="db176-106">Not all scripts can be enabled or disabled.</span></span> <span data-ttu-id="db176-107">例如，DefaultRouting 腳本已啟用，且此選項無法針對 DefaultRouting 進行變更。</span><span class="sxs-lookup"><span data-stu-id="db176-107">For instance, the DefaultRouting script is enabled and this option cannot be changed for DefaultRouting.</span></span>

<div>

## <a name="to-enable-or-disable-an-mspl-server-application"></a><span data-ttu-id="db176-108">啟用或停用 MSPL 伺服器應用程式</span><span class="sxs-lookup"><span data-stu-id="db176-108">To enable or disable an MSPL server application</span></span>

1.  <span data-ttu-id="db176-109">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署 Lync Server 2013 的網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="db176-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="db176-110">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="db176-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="db176-111">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="db176-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="db176-112">在左側導覽列中，按一下 [**拓撲圖**]，然後按一下 [**伺服器應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="db176-112">In the left navigation bar, click **Topology** and then click **Server Application**.</span></span>

4.  <span data-ttu-id="db176-113">如有需要，請在 [**伺服器應用程式**] 頁面上，按一下欄標題來排序應用程式，然後按一下您要修改的伺服器應用程式。</span><span class="sxs-lookup"><span data-stu-id="db176-113">On the **Server Application** page, click a column heading to sort the applications, if needed, and then click the server application that you want to modify.</span></span>

5.  <span data-ttu-id="db176-114">按一下 [**動作**]。</span><span class="sxs-lookup"><span data-stu-id="db176-114">Click **Action**.</span></span>

6.  <span data-ttu-id="db176-115">按一下 [**啟用應用程式**] 或 [**停用應用程式**] （也就是如果腳本支援此選項）。</span><span class="sxs-lookup"><span data-stu-id="db176-115">Click **Enable application** or **Disable application** (that is, if the script supports this option).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="db176-116">請參閱</span><span class="sxs-lookup"><span data-stu-id="db176-116">See Also</span></span>


[<span data-ttu-id="db176-117">在 Lync Server 2013 中將 Microsoft SIP 處理語言（MSPL）應用程式標示為重要或不重要</span><span class="sxs-lookup"><span data-stu-id="db176-117">Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical in Lync Server 2013</span></span>](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  


[<span data-ttu-id="db176-118">在 Lync Server 2013 中檢視 Microsoft SIP Processing Language (MSPL) 伺服器應用程式</span><span class="sxs-lookup"><span data-stu-id="db176-118">View Microsoft SIP Processing Language (MSPL) server applications in Lync Server 2013</span></span>](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[<span data-ttu-id="db176-119">管理 Lync Server 2013 拓撲</span><span class="sxs-lookup"><span data-stu-id="db176-119">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

