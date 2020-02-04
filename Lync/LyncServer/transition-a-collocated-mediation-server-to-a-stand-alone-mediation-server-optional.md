---
title: 將 collocated 中繼伺服器轉換成獨立的中繼伺服器（選用）
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)
ms:assetid: 7c3c2fb4-4ff2-47b1-aab3-0aa91472eadb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205026(v=OCS.15)
ms:contentKeyID: 48184602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c6a76bceb935900521859911ce5398ae2213e22
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738663"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional"></a><span data-ttu-id="5eee8-102">將 collocated 中繼伺服器轉換成獨立的中繼伺服器（選用）</span><span class="sxs-lookup"><span data-stu-id="5eee8-102">Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5eee8-103">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="5eee8-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="5eee8-104">使用下列程式，將您的中繼伺服器（collocated 標準版伺服器或頂層端池）轉換為單一網站部署的獨立中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="5eee8-104">Use the procedure that follows to transition your Mediation Server, collocated on your Standard Edition server or Front End pool, to a stand-alone Mediation Server for a single-site deployment.</span></span>

<div>

## <a name="to-transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server"></a><span data-ttu-id="5eee8-105">將 collocated 中繼伺服器轉型到獨立的中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="5eee8-105">To transition a collocated Mediation Server to a stand-alone Mediation Server</span></span>

1.  <span data-ttu-id="5eee8-106">從拓撲建立器開啟現有的拓撲。</span><span class="sxs-lookup"><span data-stu-id="5eee8-106">Open an existing topology from Topology Builder.</span></span>

2.  <span data-ttu-id="5eee8-107">在左窗格中，流覽到 [**轉送池**]。</span><span class="sxs-lookup"><span data-stu-id="5eee8-107">In the left pane, navigate to **Mediation pools**.</span></span>

3.  <span data-ttu-id="5eee8-108">以滑鼠右鍵按一下 [**轉送池**]，然後選取 [**新的中繼伺服器**]。</span><span class="sxs-lookup"><span data-stu-id="5eee8-108">Right-click **Mediation pools** and select **New Mediation Server**.</span></span>

4.  <span data-ttu-id="5eee8-109">在 [**定義新的仲介資源池**] 頁面上，提供新的中繼伺服器池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="5eee8-109">On the **Define New Mediation Pool** page, provide the FQDN of the new Mediation Server pool.</span></span> <span data-ttu-id="5eee8-110">此外，選取此池是單一伺服器或多重伺服器池，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="5eee8-110">Also, select whether this pool will be a single-server or multiple-server pool, and then click **Next**.</span></span>

5.  <span data-ttu-id="5eee8-111">選取新的中繼伺服器將路由入站通話的下一個躍點前端伺服器池，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="5eee8-111">Select the next hop Front End server pool to which the new Mediation Server will route inbound calls, and then click **Next**.</span></span>

6.  <span data-ttu-id="5eee8-112">選取要供中繼伺服器使用的邊緣池，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="5eee8-112">Select the Edge pool to be used by the Mediation Server and then click **Next**.</span></span>

7.  <span data-ttu-id="5eee8-113">在 [**指定 PSTN 閘道**] 頁面上，將舊版 PSTN 閘道與中繼伺服器進行關聯。</span><span class="sxs-lookup"><span data-stu-id="5eee8-113">On the **Specify PSTN gateways** page, associate the previous PSTN gateway with the Mediation Server.</span></span> <span data-ttu-id="5eee8-114">選取閘道，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="5eee8-114">Select the gateway and then click **Add**.</span></span>

8.  <span data-ttu-id="5eee8-115">按一下 **[完成]** ，關閉 [**定義新的仲介池**] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="5eee8-115">Click **Finish** to close the **Define New Mediation Pool** wizard.</span></span>

9.  <span data-ttu-id="5eee8-116">從 [**拓撲**建立器] 中，選取最上方節點的**Lync Server 2013**。</span><span class="sxs-lookup"><span data-stu-id="5eee8-116">From **Topology Builder**, select the top node **Lync Server 2013**.</span></span>

10. <span data-ttu-id="5eee8-117">從 [**動作**] 窗格中，選取 [**發佈拓撲**] 並完成嚮導。</span><span class="sxs-lookup"><span data-stu-id="5eee8-117">From the **Actions** pane, select **Publish Topology** and complete the wizard.</span></span>

11. <span data-ttu-id="5eee8-118">請依照部署檔中的 Lync Server 2013 中的 [在 Lync server 中[安裝中繼伺服器](lync-server-2013-install-the-files-for-mediation-server.md)檔案] 中的步驟進行，以在新的中繼伺服器上安裝檔案。</span><span class="sxs-lookup"><span data-stu-id="5eee8-118">Follow the steps in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) in the Deployment documentation to install the files on the new Mediation Server.</span></span>

12. <span data-ttu-id="5eee8-119">將檔案安裝在中繼伺服器之後，請返回 [拓撲建立器]，然後在左窗格中流覽至該池。</span><span class="sxs-lookup"><span data-stu-id="5eee8-119">After the files are installed on the Mediation Server, return to Topology Builder, and in the left pane navigate to the pool.</span></span>

13. <span data-ttu-id="5eee8-120">以滑鼠右鍵按一下該池，然後選取 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="5eee8-120">Right-click the pool and select **Edit Properties**.</span></span>

14. <span data-ttu-id="5eee8-121">在 [**中繼伺服器**] 底下，清除 [**啟用中繼伺服器 Collocated**的核取方塊，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="5eee8-121">Under **Mediation Server**, clear the check box **Collocated Mediation Server enabled** and then click **OK**.</span></span>

15. <span data-ttu-id="5eee8-122">從 [**拓撲**建立器] 中，選取最上方節點的**Lync Server 2013**。</span><span class="sxs-lookup"><span data-stu-id="5eee8-122">From **Topology Builder**, select the top node **Lync Server 2013**.</span></span>

16. <span data-ttu-id="5eee8-123">從 [**動作**] 功能表中，選取 [**發佈拓撲**] 並完成嚮導。</span><span class="sxs-lookup"><span data-stu-id="5eee8-123">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

