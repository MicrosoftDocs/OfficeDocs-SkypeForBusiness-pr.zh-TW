---
title: Lync Server 2013：查看受信任的應用程式清單
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View a list of trusted applications
ms:assetid: f09300b3-67cf-4e70-a51a-23d62479b913
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182604(v=OCS.15)
ms:contentKeyID: 48185844
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d5f9d112e045e753147f7fcffa875177a6feb0d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757497"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-a-list-of-trusted-applications-in-lync-server-2013"></a><span data-ttu-id="acaa2-102">在 Lync Server 2013 中查看信任的應用程式清單</span><span class="sxs-lookup"><span data-stu-id="acaa2-102">View a list of trusted applications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="acaa2-103">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="acaa2-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="acaa2-104">您可以使用 Lync Server 2013 [控制台] 來查看您已在 Lync Server 2013 環境中部署之受信任的應用程式清單。</span><span class="sxs-lookup"><span data-stu-id="acaa2-104">You can use Lync Server 2013 Control Panel to view a list of the trusted applications that you have deployed in your Lync Server 2013 environment.</span></span> <span data-ttu-id="acaa2-105">受信任的應用程式是以 Microsoft 整合通訊 Managed API （UCMA）3.0 核心 SDK （受 Lync Server 2013 信任）為基礎的應用程式。</span><span class="sxs-lookup"><span data-stu-id="acaa2-105">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Lync Server 2013.</span></span> <span data-ttu-id="acaa2-106">下列清單將摘要列出這項信任關係：</span><span class="sxs-lookup"><span data-stu-id="acaa2-106">This trust relationship is summarized in the following list:</span></span>

  - <span data-ttu-id="acaa2-107">受信任的應用程式不會因 Lync Server 的驗證而面臨挑戰。</span><span class="sxs-lookup"><span data-stu-id="acaa2-107">Trusted applications are not challenged for authentication by Lync Server.</span></span>

  - <span data-ttu-id="acaa2-108">Lync Server 不會針對 SIP 交易、連線或透過網際網路通訊協定（VoIP）通話的傳出語音限制受信任的應用程式。</span><span class="sxs-lookup"><span data-stu-id="acaa2-108">Trusted applications are not throttled by Lync Server for SIP transactions, connections or outgoing Voice over Internet Protocol (VoIP) calls.</span></span>

  - <span data-ttu-id="acaa2-109">受信任的應用程式可以模仿任何使用者，而且無需出現在 rosters 中，即可加入會議。</span><span class="sxs-lookup"><span data-stu-id="acaa2-109">Trusted applications can impersonate any user and can join conferences without appearing in rosters.</span></span>

  - <span data-ttu-id="acaa2-110">受信任的應用程式高度可用且具有彈性。</span><span class="sxs-lookup"><span data-stu-id="acaa2-110">Trusted applications are highly available and resilient.</span></span>

<span data-ttu-id="acaa2-111">在 Lync Server [控制台] 中，您可以看見應用程式名稱、其執行所在的池中，以及它們所使用的埠。</span><span class="sxs-lookup"><span data-stu-id="acaa2-111">In Lync Server Control Panel, you can see the name of the applications, the pool where they run, and the port they use.</span></span>

<div>

## <a name="to-view-a-list-of-trusted-applications"></a><span data-ttu-id="acaa2-112">若要查看受信任的應用程式清單</span><span class="sxs-lookup"><span data-stu-id="acaa2-112">To view a list of trusted applications</span></span>

1.  <span data-ttu-id="acaa2-113">從指派給 CsServerAdministrator、CsAdministrator、CsHelpDesk 或 CsViewOnlyAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="acaa2-113">From a user account that is assigned to the CsServerAdministrator, CsAdministrator, CsHelpDesk, or CsViewOnlyAdministrator role, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="acaa2-114">如需有關 Lync Server 2013 中預先定義的管理角色的詳細資訊，請參閱[在 Lync server 2013 中規劃角色式存取控制](lync-server-2013-planning-for-role-based-access-control.md)。</span><span class="sxs-lookup"><span data-stu-id="acaa2-114">For details about the predefined administrative roles available in Lync Server 2013, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

2.  <span data-ttu-id="acaa2-115">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="acaa2-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="acaa2-116">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="acaa2-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="acaa2-117">在左側導覽列中，按一下 [**拓撲**]，然後按一下 [按一下**信任的應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="acaa2-117">In the left navigation bar, click **Topology** and the click **Trusted Application**.</span></span>

4.  <span data-ttu-id="acaa2-118">如有需要，請在 [**受信任的應用程式**] 頁面上，按一下欄標題來排序應用程式。</span><span class="sxs-lookup"><span data-stu-id="acaa2-118">On the **Trusted Application** page, click a column heading to sort the applications, if needed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="acaa2-119">請參閱</span><span class="sxs-lookup"><span data-stu-id="acaa2-119">See Also</span></span>


[<span data-ttu-id="acaa2-120">管理 Lync Server 2013 拓撲</span><span class="sxs-lookup"><span data-stu-id="acaa2-120">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

