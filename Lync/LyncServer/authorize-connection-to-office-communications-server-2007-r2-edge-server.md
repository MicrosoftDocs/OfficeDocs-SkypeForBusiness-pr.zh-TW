---
title: 授權連線至 Office 通訊伺服器 2007 R2 Edge Server
description: 授權連線至 Office 通訊伺服器 2007 R2 Edge Server。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Authorize connection to Office Communications Server 2007 R2 Edge Server
ms:assetid: 14f6798a-28d6-4b3d-8734-942192e1bbf5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204702(v=OCS.15)
ms:contentKeyID: 48183493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de8dadb2c476c892f4ffd548ce176d12d3b1a1cf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545829"
---
# <a name="authorize-connection-to-office-communications-server-2007-r2-edge-server"></a><span data-ttu-id="ad21c-103">授權連線至 Office 通訊伺服器 2007 R2 Edge Server</span><span class="sxs-lookup"><span data-stu-id="ad21c-103">Authorize connection to Office Communications Server 2007 R2 Edge Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad21c-104">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="ad21c-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="ad21c-105">針對您的試驗集區中的每個 Lync Server 2013 前端伺服器或 Standard Edition server，您必須更新授權連線至 Office 通訊伺服器 2007 R2 Edge Server 的內部伺服器清單。</span><span class="sxs-lookup"><span data-stu-id="ad21c-105">For each Lync Server 2013 Front End Server or Standard Edition server in your pilot pool, you must update the list of internal servers that are authorized to connect to the Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="ad21c-106">若沒有這些更新，使用舊版 Edge Server 來參與外部音訊/視訊 (A/V) 會議的使用者就不會成功。</span><span class="sxs-lookup"><span data-stu-id="ad21c-106">Without these updates, external audio/visual (A/V) conferencing for users joining by using the legacy Edge Server will not work.</span></span>

<div>

## <a name="to-authorize-connection-to-office-communications-server-2007-r2-edge-server"></a><span data-ttu-id="ad21c-107">授權連線至 Office 通訊伺服器 2007 R2 Edge Server</span><span class="sxs-lookup"><span data-stu-id="ad21c-107">To Authorize Connection to Office Communications Server 2007 R2 Edge Server</span></span>

1.  <span data-ttu-id="ad21c-108">從 Office 通訊伺服器 2007 R2 Edge Server，從 [系統 **管理工具** ] 群組中，開啟 [ **電腦管理** ] 嵌入式管理單元。</span><span class="sxs-lookup"><span data-stu-id="ad21c-108">From the Office Communications Server 2007 R2 Edge Server, from the **Administrative Tools** group, open the **Computer Management** snap-in.</span></span>

2.  <span data-ttu-id="ad21c-109">在主控台樹狀目錄中，展開 [服務和應用程式]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ad21c-109">In the console tree, expand **Services and Applications**.</span></span>

3.  <span data-ttu-id="ad21c-110">以滑鼠右鍵按一下 [Office Communications Server 2007 R2]\*\*\*\*，然後按一下 [內容]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ad21c-110">Right-click **Office Communications Server 2007 R2**, and then click **Properties**.</span></span>

4.  <span data-ttu-id="ad21c-111">按一下 [內部]\*\*\*\* 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="ad21c-111">Click the **Internal** tab.</span></span>

5.  <span data-ttu-id="ad21c-112">在 [新增伺服器]\*\*\*\* 底下，按一下 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ad21c-112">Under **Add Server**, click **Add**.</span></span>

6.  <span data-ttu-id="ad21c-113">在 [新增 Office Communications Server]\*\*\*\* 對話方塊中，輸入適當的資訊：</span><span class="sxs-lookup"><span data-stu-id="ad21c-113">In the **Add Office Communications Server** dialog box, enter the appropriate information:</span></span>
    
      - <span data-ttu-id="ad21c-114">指定每個 Lync Server 2013 前端伺服器或 Standard Edition server 的完整功能變數名稱 (FQDN) ，以及 Lync Server 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="ad21c-114">Specify the fully qualified domain name (FQDN) of each Lync Server 2013 Front End Server or Standard Edition server, and Lync Server 2013 pool.</span></span>
    
      - <span data-ttu-id="ad21c-115">如果您已在指定下一個躍點電腦的集區上設定靜態路由，請指定 Lync Server 2013 Director 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ad21c-115">Specify the FQDN of the Lync Server 2013 Director if you configured a static route on the pool that specifies the next hop computer by its FQDN.</span></span>

7.  <span data-ttu-id="ad21c-116">針對每個 Lync Server 2013、前端伺服器、Standard Edition Server、集區和 Director 新增專案後，按一下 [套用] **，然後** 按一下 **[確定]** 以關閉 [屬性] 頁面。</span><span class="sxs-lookup"><span data-stu-id="ad21c-116">After you have added an entry for each Lync Server 2013, Front End Server, Standard Edition server, pool, and Director, click **Apply** and then click **OK** to close the Properties page.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

