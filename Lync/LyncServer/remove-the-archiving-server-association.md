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
ms.openlocfilehash: 04bf1a5a3c68ab1123431543e08618c4eacb7559
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727113"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-archiving-server-association"></a><span data-ttu-id="277c3-102">移除封存伺服器關聯</span><span class="sxs-lookup"><span data-stu-id="277c3-102">Remove the Archiving server association</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="277c3-103">_**主題上次修改日期：** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="277c3-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="277c3-104">若要移除封存伺服器，您需要變更或清除相關聯的 [前端] 池、[前端伺服器]、[Survivable 分支裝置] 和 [Survivable 分支伺服器] 的相依性。</span><span class="sxs-lookup"><span data-stu-id="277c3-104">To remove an Archiving Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server.</span></span> <span data-ttu-id="277c3-105">您可以編輯 [前端] 池、[前端伺服器]、[Survivable 分支裝置] 和 [Survivable 分支伺服器] 的屬性，以移除相依性。</span><span class="sxs-lookup"><span data-stu-id="277c3-105">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="277c3-106">在您清除相依性並刪除拓撲建立器中的伺服器之後，系統會通知您在拓撲建立器中相關聯的資料庫存放物件也會被刪除。</span><span class="sxs-lookup"><span data-stu-id="277c3-106">After you clear the dependency and you delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>

<div>

## <a name="to-remove-the-archiving-server-association"></a><span data-ttu-id="277c3-107">移除存檔伺服器關聯</span><span class="sxs-lookup"><span data-stu-id="277c3-107">To remove the Archiving Server association</span></span>

1.  <span data-ttu-id="277c3-108">開啟 Lync Server 2013 前端伺服器，然後開啟 [拓撲建立器]。</span><span class="sxs-lookup"><span data-stu-id="277c3-108">Open the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="277c3-109">流覽至 Lync Server 2010 節點。</span><span class="sxs-lookup"><span data-stu-id="277c3-109">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="277c3-110">在拓撲建立器中，根據存檔伺服器的定義位置，展開 [**企業版前端池**]、[**標準版前端伺服器**] 或 [**分支網站**]。</span><span class="sxs-lookup"><span data-stu-id="277c3-110">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, based on where the Archiving Server is defined.</span></span>

4.  <span data-ttu-id="277c3-111">如果您有關聯的 Survivable 分支伺服器，請展開 [**分支網站**]，展開分支網站名稱，然後展開 [ **Survivable 分支裝置**]。</span><span class="sxs-lookup"><span data-stu-id="277c3-111">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="277c3-112">使用者介面中的<STRONG>Survivable 分支裝置</STRONG>同時適用于 Survivable 分支伺服器和 Survivable 分支裝置。</span><span class="sxs-lookup"><span data-stu-id="277c3-112"><STRONG>Survivable Branch Appliances</STRONG> in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span>

    
    </div>

5.  <span data-ttu-id="277c3-113">以滑鼠右鍵按一下與封存伺服器相關聯的 [池]、[伺服器] 或 [裝置]，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="277c3-113">Right-click the pool, server, or device that is associated with the Archiving Server, and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="277c3-114">在 **[編輯屬性**]**的 [一般**] 底下的 [**關聯**] 底下，清除 [關聯**存檔伺服器**] 核取方塊，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="277c3-114">In **Edit Properties**, under **General**, under **Associations**, clear the **Associate Archiving Server** check box, and then click **OK**.</span></span>

7.  <span data-ttu-id="277c3-115">針對與您要移除之存檔伺服器相關聯的任何其他池、伺服器或裝置，重複上述步驟。</span><span class="sxs-lookup"><span data-stu-id="277c3-115">Repeat the previous step for any other pool, server or device associated with the Archiving Server that you want to remove.</span></span>

8.  <span data-ttu-id="277c3-116">以滑鼠右鍵按一下 [封存伺服器]，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="277c3-116">Right-click the Archiving Server, and then click **Delete**.</span></span>

9.  <span data-ttu-id="277c3-117">在 [**刪除相依儲存區**] 中，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="277c3-117">On **Delete Dependent Stores**, click **OK**.</span></span>

10. <span data-ttu-id="277c3-118">發佈拓撲，檢查 [複製狀態]，然後視需要執行 Lync Server 部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="277c3-118">Publish the topology, check replication status, and then run the Lync Server Deployment Wizard as needed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

