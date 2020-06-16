---
title: 移除監控伺服器關聯
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove the Monitoring server association
ms:assetid: c45b22ae-fc06-484a-a05b-735bd1bb7448
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721877(v=OCS.15)
ms:contentKeyID: 49733810
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7aa78a49686ca555fdbc26d3ffd4953d88d64a95
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756542"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-the-monitoring-server-association"></a><span data-ttu-id="f4bf9-102">移除監控伺服器關聯</span><span class="sxs-lookup"><span data-stu-id="f4bf9-102">Remove the Monitoring server association</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4bf9-103">_**主題上次修改日期：** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="f4bf9-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="f4bf9-104">若要移除監控伺服器，您必須變更或清除關聯的前端集區、前端伺服器、Survivable 分支裝置和 Survivable 分支伺服器上的相依性。</span><span class="sxs-lookup"><span data-stu-id="f4bf9-104">To remove the Monitoring Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server.</span></span> <span data-ttu-id="f4bf9-105">您可以編輯前端集區、前端伺服器、Survivable 分支裝置和 Survivable 分支伺服器的屬性，以移除相依性。</span><span class="sxs-lookup"><span data-stu-id="f4bf9-105">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="f4bf9-106">在 [拓撲產生器] 中清除相依性和刪除伺服器之後，系統會通知您也會刪除拓撲產生器中相關聯的資料庫存放區物件。</span><span class="sxs-lookup"><span data-stu-id="f4bf9-106">After you clear the dependency and delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>

<div>

## <a name="to-remove-the-monitoring-server-association"></a><span data-ttu-id="f4bf9-107">若要移除監控伺服器關聯</span><span class="sxs-lookup"><span data-stu-id="f4bf9-107">To remove the Monitoring Server association</span></span>

1.  <span data-ttu-id="f4bf9-108">開啟 Lync Server 2013 前端伺服器，開啟拓撲產生器。</span><span class="sxs-lookup"><span data-stu-id="f4bf9-108">Open the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="f4bf9-109">流覽至 [Lync Server 2010] 節點。</span><span class="sxs-lookup"><span data-stu-id="f4bf9-109">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="f4bf9-110">在 [拓撲產生器] 中，根據監控伺服器定義的位置，展開 [ **Enterprise Edition 前端**集區]、[ **Standard Edition 前端伺服器**] 或 [**分支網站**]。</span><span class="sxs-lookup"><span data-stu-id="f4bf9-110">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, based on where the Monitoring Server is defined.</span></span>

4.  <span data-ttu-id="f4bf9-111">如果您有相關聯的 Survivable 分支伺服器，請展開 [**分支網站**]，展開分支網站名稱，然後展開 [ **Survivable 分支裝置**]。</span><span class="sxs-lookup"><span data-stu-id="f4bf9-111">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f4bf9-112">使用者介面中的<STRONG>Survivable 分支裝置</STRONG>會同時套用至 Survivable branch Server 和 Survivable branch 裝置。</span><span class="sxs-lookup"><span data-stu-id="f4bf9-112"><STRONG>Survivable Branch Appliances</STRONG> in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span>

    
    </div>

5.  <span data-ttu-id="f4bf9-113">以滑鼠右鍵按一下與監控伺服器相關聯的集區、伺服器或裝置，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="f4bf9-113">Right-click the pool, server, or device that is associated with the Monitoring Server, and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="f4bf9-114">在 [編輯內容]\*\*\*\*，[一般]\*\*\*\* 下方，[關聯]\*\*\*\* 下方，清除 [建立監控伺服器關聯]\*\*\*\* 核取方塊，然後按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f4bf9-114">In **Edit Properties**, under **General**, under **Associations**, clear the **Associate Monitoring Server** check box, and then click **OK**.</span></span>

7.  <span data-ttu-id="f4bf9-115">針對與監控伺服器關聯的任何其他集區、伺服器或裝置，重複上述步驟。</span><span class="sxs-lookup"><span data-stu-id="f4bf9-115">Repeat the previous step for any other pool, server or device associated with the Monitoring Server.</span></span>

8.  <span data-ttu-id="f4bf9-116">以滑鼠右鍵按一下監控伺服器，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="f4bf9-116">Right-click the Monitoring Server, and then click **Delete**.</span></span>

9.  <span data-ttu-id="f4bf9-117">在 [刪除相依存放區]\*\*\*\* 上，按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f4bf9-117">On **Delete Dependent Stores**, click **OK**.</span></span>

10. <span data-ttu-id="f4bf9-118">發佈拓撲，檢查複寫狀態，然後視需要執行 Lync Server 部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="f4bf9-118">Publish the topology, check replication status, and run the Lync Server Deployment Wizard as needed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

