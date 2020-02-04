---
title: 授權連線到 Office 通訊伺服器 2007 R2 Edge 伺服器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: 8dbce32a12f05dff768d23a2bdccfe1b84a567cb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724213"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="authorize-connection-to-office-communications-server-2007-r2-edge-server"></a><span data-ttu-id="72e69-102">授權連線到 Office 通訊伺服器 2007 R2 Edge 伺服器</span><span class="sxs-lookup"><span data-stu-id="72e69-102">Authorize connection to Office Communications Server 2007 R2 Edge Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72e69-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="72e69-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="72e69-104">針對您的試用池中的每個 Lync Server 2013 前端伺服器或標準版伺服器，您必須更新已獲授權連線至 Office 通訊伺服器 2007 R2 Edge 伺服器的內部伺服器清單。</span><span class="sxs-lookup"><span data-stu-id="72e69-104">For each Lync Server 2013 Front End Server or Standard Edition server in your pilot pool, you must update the list of internal servers that are authorized to connect to the Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="72e69-105">如果沒有這些更新，則使用舊版 Edge 伺服器加入的使用者的外部音訊/視覺（A/V）會議將無法運作。</span><span class="sxs-lookup"><span data-stu-id="72e69-105">Without these updates, external audio/visual (A/V) conferencing for users joining by using the legacy Edge Server will not work.</span></span>

<div>

## <a name="to-authorize-connection-to-office-communications-server-2007-r2-edge-server"></a><span data-ttu-id="72e69-106">授權連線到 Office 通訊伺服器 2007 R2 Edge 伺服器</span><span class="sxs-lookup"><span data-stu-id="72e69-106">To Authorize Connection to Office Communications Server 2007 R2 Edge Server</span></span>

1.  <span data-ttu-id="72e69-107">從 [Office 通訊伺服器 2007 R2 Edge 伺服器] 的 [**管理工具**] 群組中，開啟 [**電腦管理**] 管理單元。</span><span class="sxs-lookup"><span data-stu-id="72e69-107">From the Office Communications Server 2007 R2 Edge Server, from the **Administrative Tools** group, open the **Computer Management** snap-in.</span></span>

2.  <span data-ttu-id="72e69-108">在主控台樹中，展開 [**服務和應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="72e69-108">In the console tree, expand **Services and Applications**.</span></span>

3.  <span data-ttu-id="72e69-109">以滑鼠右鍵按一下 [ **Office 通訊伺服器 2007 R2**]，然後按一下 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="72e69-109">Right-click **Office Communications Server 2007 R2**, and then click **Properties**.</span></span>

4.  <span data-ttu-id="72e69-110">按一下 [**內部**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="72e69-110">Click the **Internal** tab.</span></span>

5.  <span data-ttu-id="72e69-111">在 [**新增伺服器**] 底下，按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="72e69-111">Under **Add Server**, click **Add**.</span></span>

6.  <span data-ttu-id="72e69-112">在 [**新增 Office 通訊伺服器**] 對話方塊中，輸入適當的資訊：</span><span class="sxs-lookup"><span data-stu-id="72e69-112">In the **Add Office Communications Server** dialog box, enter the appropriate information:</span></span>
    
      - <span data-ttu-id="72e69-113">指定每個 Lync Server 2013 前端伺服器或標準版伺服器的完整功能變數名稱（FQDN），以及 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="72e69-113">Specify the fully qualified domain name (FQDN) of each Lync Server 2013 Front End Server or Standard Edition server, and Lync Server 2013 pool.</span></span>
    
      - <span data-ttu-id="72e69-114">如果您已在以其 FQDN 指定下一個躍點電腦的池中設定靜態路由，請指定 Lync Server 2013 控制器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="72e69-114">Specify the FQDN of the Lync Server 2013 Director if you configured a static route on the pool that specifies the next hop computer by its FQDN.</span></span>

7.  <span data-ttu-id="72e69-115">針對每個 Lync Server 2013、[前端伺服器]、[標準版伺服器]、[池] 和 [控制器] 新增專案後，請按一下 [套用] **，然後按一下** **[確定]** 以關閉 [屬性] 頁面。</span><span class="sxs-lookup"><span data-stu-id="72e69-115">After you have added an entry for each Lync Server 2013, Front End Server, Standard Edition server, pool, and Director, click **Apply** and then click **OK** to close the Properties page.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

