---
title: 移除封存伺服器關聯
description: 移除封存伺服器關聯。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove the Archiving server association
ms:assetid: dabac157-71ee-4afe-b0b6-4a083d165ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721903(v=OCS.15)
ms:contentKeyID: 49733837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f6c34e49b0217a8318a83752b3878a7625e5d58
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570219"
---
# <a name="remove-the-archiving-server-association"></a><span data-ttu-id="b6c85-103">移除封存伺服器關聯</span><span class="sxs-lookup"><span data-stu-id="b6c85-103">Remove the Archiving server association</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b6c85-104">_**主題上次修改日期：** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="b6c85-104">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="b6c85-105">若要移除封存伺服器，您必須變更或清除關聯的前端集區、前端伺服器、Survivable 分支裝置和 Survivable 分支伺服器上的相依性。</span><span class="sxs-lookup"><span data-stu-id="b6c85-105">To remove an Archiving Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server.</span></span> <span data-ttu-id="b6c85-106">您可以編輯前端集區、前端伺服器、Survivable 分支裝置和 Survivable 分支伺服器的屬性，以移除相依性。</span><span class="sxs-lookup"><span data-stu-id="b6c85-106">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="b6c85-107">清除相依性並在拓撲產生器中刪除伺服器後，系統會通知您也會刪除拓撲產生器中相關聯的資料庫存放區物件。</span><span class="sxs-lookup"><span data-stu-id="b6c85-107">After you clear the dependency and you delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>

<div>

## <a name="to-remove-the-archiving-server-association"></a><span data-ttu-id="b6c85-108">移除封存伺服器關聯</span><span class="sxs-lookup"><span data-stu-id="b6c85-108">To remove the Archiving Server association</span></span>

1.  <span data-ttu-id="b6c85-109">開啟 Lync Server 2013 前端伺服器，開啟拓撲產生器。</span><span class="sxs-lookup"><span data-stu-id="b6c85-109">Open the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="b6c85-110">流覽至 [Lync Server 2010] 節點。</span><span class="sxs-lookup"><span data-stu-id="b6c85-110">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="b6c85-111">在 [拓撲產生器] 中，根據封存伺服器定義的位置，展開 [ **Enterprise Edition 前端**集區]、[ **Standard Edition 前端伺服器**] 或 [ **分支網站**]。</span><span class="sxs-lookup"><span data-stu-id="b6c85-111">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, based on where the Archiving Server is defined.</span></span>

4.  <span data-ttu-id="b6c85-112">如果您有相關聯的 Survivable 分支伺服器，請展開 [ **分支網站**]，展開分支網站名稱，然後展開 [ **Survivable 分支裝置**]。</span><span class="sxs-lookup"><span data-stu-id="b6c85-112">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b6c85-113">使用者介面中的<STRONG>Survivable 分支裝置</STRONG>會同時套用至 Survivable branch Server 和 Survivable branch 裝置。</span><span class="sxs-lookup"><span data-stu-id="b6c85-113"><STRONG>Survivable Branch Appliances</STRONG> in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span>

    
    </div>

5.  <span data-ttu-id="b6c85-114">以滑鼠右鍵按一下與封存伺服器關聯的集區、伺服器或裝置，然後按一下 [ **編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="b6c85-114">Right-click the pool, server, or device that is associated with the Archiving Server, and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="b6c85-115">在 [編輯屬性]\*\*\*\* 的 [一般]\*\*\*\* 底下，清除 [關聯]\*\*\*\* 底下的 [建立封存伺服器的關聯]\*\*\*\* 核取方塊，然後按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b6c85-115">In **Edit Properties**, under **General**, under **Associations**, clear the **Associate Archiving Server** check box, and then click **OK**.</span></span>

7.  <span data-ttu-id="b6c85-116">針對與您要移除之封存伺服器相關聯的任何其他集區、伺服器或裝置，重複上述步驟。</span><span class="sxs-lookup"><span data-stu-id="b6c85-116">Repeat the previous step for any other pool, server or device associated with the Archiving Server that you want to remove.</span></span>

8.  <span data-ttu-id="b6c85-117">以滑鼠右鍵按一下封存伺服器，然後按一下 [ **刪除**]。</span><span class="sxs-lookup"><span data-stu-id="b6c85-117">Right-click the Archiving Server, and then click **Delete**.</span></span>

9.  <span data-ttu-id="b6c85-118">在 [刪除相依存放區]\*\*\*\* 上，按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b6c85-118">On **Delete Dependent Stores**, click **OK**.</span></span>

10. <span data-ttu-id="b6c85-119">發佈拓撲，檢查複寫狀態，然後視需要執行 Lync Server 部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="b6c85-119">Publish the topology, check replication status, and then run the Lync Server Deployment Wizard as needed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

