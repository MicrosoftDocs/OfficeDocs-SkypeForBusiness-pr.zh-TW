---
title: 移除封存伺服器關聯
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove the Archiving server association
ms:assetid: dabac157-71ee-4afe-b0b6-4a083d165ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721903(v=OCS.15)
ms:contentKeyID: 49733837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93c53ef1e70b174681149593237db3f9d0268209
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189486"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-the-archiving-server-association"></a><span data-ttu-id="d6fec-102">移除封存伺服器關聯</span><span class="sxs-lookup"><span data-stu-id="d6fec-102">Remove the Archiving server association</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6fec-103">_**主題上次修改日期：** 2012年-10-04_</span><span class="sxs-lookup"><span data-stu-id="d6fec-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="d6fec-104">若要移除封存伺服器，您需要變更或清除 [關聯前端集區，前端伺服器、 Survivable Branch Appliance 和 Survivable Branch 伺服器上的相依性。</span><span class="sxs-lookup"><span data-stu-id="d6fec-104">To remove an Archiving Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server.</span></span> <span data-ttu-id="d6fec-105">您編輯的內容的前端集區前端伺服器、 Survivable Branch Appliance 和 Survivable Branch 伺服器移除相依性。</span><span class="sxs-lookup"><span data-stu-id="d6fec-105">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="d6fec-106">清除 [相依性，並刪除拓撲產生器中的伺服器之後，您會收到通知也會刪除在拓撲產生器的相關聯的資料庫存放區物件。</span><span class="sxs-lookup"><span data-stu-id="d6fec-106">After you clear the dependency and you delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>

<div>

## <a name="to-remove-the-archiving-server-association"></a><span data-ttu-id="d6fec-107">移除封存伺服器關聯</span><span class="sxs-lookup"><span data-stu-id="d6fec-107">To remove the Archiving Server association</span></span>

1.  <span data-ttu-id="d6fec-108">開啟 Lync Server 2013 前端伺服器]，再開啟拓撲產生器]。</span><span class="sxs-lookup"><span data-stu-id="d6fec-108">Open the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="d6fec-109">瀏覽至 [Lync Server 2010] 節點。</span><span class="sxs-lookup"><span data-stu-id="d6fec-109">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="d6fec-110">在拓撲產生器中，展開 [ **Enterprise Edition 前端集區**、 **Standard Edition 前端伺服器**或**分支站台**，根據定義封存伺服器的位置。</span><span class="sxs-lookup"><span data-stu-id="d6fec-110">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, based on where the Archiving Server is defined.</span></span>

4.  <span data-ttu-id="d6fec-111">如果您有相關聯的 Survivable Branch 伺服器，依序展開 [**分支站台**，依序展開 [分支網站名稱，然後展開 [ **Survivable Branch Appliance**。</span><span class="sxs-lookup"><span data-stu-id="d6fec-111">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d6fec-112">在使用者介面中的<STRONG>Survivable Branch Appliances</STRONG>會套用至 Survivable Branch 伺服器和 Survivable Branch Appliance。</span><span class="sxs-lookup"><span data-stu-id="d6fec-112"><STRONG>Survivable Branch Appliances</STRONG> in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span>

    
    </div>

5.  <span data-ttu-id="d6fec-113">以滑鼠右鍵按一下集區、 伺服器或封存伺服器，與相關聯的裝置，然後按一下 [**編輯內容]**。</span><span class="sxs-lookup"><span data-stu-id="d6fec-113">Right-click the pool, server, or device that is associated with the Archiving Server, and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="d6fec-114">在 [編輯屬性]\*\*\*\* 的 [一般]\*\*\*\* 底下，清除 [關聯]\*\*\*\* 底下的 [建立封存伺服器的關聯]\*\*\*\* 核取方塊，然後按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d6fec-114">In **Edit Properties**, under **General**, under **Associations**, clear the **Associate Archiving Server** check box, and then click **OK**.</span></span>

7.  <span data-ttu-id="d6fec-115">任何其他集區、 伺服器或您想要移除封存伺服器相關聯的裝置，重複上述步驟。</span><span class="sxs-lookup"><span data-stu-id="d6fec-115">Repeat the previous step for any other pool, server or device associated with the Archiving Server that you want to remove.</span></span>

8.  <span data-ttu-id="d6fec-116">封存伺服器，以滑鼠右鍵按一下，然後按一下 [**刪除**。</span><span class="sxs-lookup"><span data-stu-id="d6fec-116">Right-click the Archiving Server, and then click **Delete**.</span></span>

9.  <span data-ttu-id="d6fec-117">在 [刪除相依存放區]\*\*\*\* 上，按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d6fec-117">On **Delete Dependent Stores**, click **OK**.</span></span>

10. <span data-ttu-id="d6fec-118">發行拓撲，檢查複寫狀態，然後視需要執行 Lync Server 部署精靈。</span><span class="sxs-lookup"><span data-stu-id="d6fec-118">Publish the topology, check replication status, and then run the Lync Server Deployment Wizard as needed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

