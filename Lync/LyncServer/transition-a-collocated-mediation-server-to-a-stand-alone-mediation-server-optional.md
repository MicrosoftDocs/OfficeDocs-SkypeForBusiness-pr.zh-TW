---
title: '將組合的轉送伺服器轉換成獨立轉送伺服器 (選用) '
description: 將組合的轉送伺服器轉換成獨立轉送伺服器 (選用) 。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)
ms:assetid: 7c3c2fb4-4ff2-47b1-aab3-0aa91472eadb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205026(v=OCS.15)
ms:contentKeyID: 48184602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e99eb445e8377a52901f54f52ca3933babe15571
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559419"
---
# <a name="transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional"></a><span data-ttu-id="99d29-103">將組合的轉送伺服器轉換成獨立轉送伺服器 (選用) </span><span class="sxs-lookup"><span data-stu-id="99d29-103">Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99d29-104">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="99d29-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="99d29-105">使用下列程序來將 Standard Edition Server 或前端集區上組合的中繼伺服器轉換成獨立中繼伺服器，以用於單一網站部署。</span><span class="sxs-lookup"><span data-stu-id="99d29-105">Use the procedure that follows to transition your Mediation Server, collocated on your Standard Edition server or Front End pool, to a stand-alone Mediation Server for a single-site deployment.</span></span>

<div>

## <a name="to-transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server"></a><span data-ttu-id="99d29-106">將組合的中繼伺服器轉換成獨立中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="99d29-106">To transition a collocated Mediation Server to a stand-alone Mediation Server</span></span>

1.  <span data-ttu-id="99d29-107">從拓撲產生器開啟現有拓撲</span><span class="sxs-lookup"><span data-stu-id="99d29-107">Open an existing topology from Topology Builder.</span></span>

2.  <span data-ttu-id="99d29-108">在左窗格中，瀏覽至 [中繼集區]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="99d29-108">In the left pane, navigate to **Mediation pools**.</span></span>

3.  <span data-ttu-id="99d29-109">以滑鼠右鍵按一下 [中繼集區]\*\*\*\*，然後選取 [新增中繼伺服器]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="99d29-109">Right-click **Mediation pools** and select **New Mediation Server**.</span></span>

4.  <span data-ttu-id="99d29-p101">在 [定義新的中繼集區]\*\*\*\* 頁面上，輸入新中繼伺服器集區的 FQDN。此外，也可以選擇此集區是獨立伺服器集區或是多伺服器集區，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="99d29-p101">On the **Define New Mediation Pool** page, provide the FQDN of the new Mediation Server pool. Also, select whether this pool will be a single-server or multiple-server pool, and then click **Next**.</span></span>

5.  <span data-ttu-id="99d29-112">選取新中繼伺服器將要路由傳送撥入通話的下一個躍點前端伺服器集區，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="99d29-112">Select the next hop Front End server pool to which the new Mediation Server will route inbound calls, and then click **Next**.</span></span>

6.  <span data-ttu-id="99d29-113">選取中繼伺服器要使用的 Edge 集區，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="99d29-113">Select the Edge pool to be used by the Mediation Server and then click **Next**.</span></span>

7.  <span data-ttu-id="99d29-p102">在 [指定 PSTN 閘道]\*\*\*\* 頁面上，將舊的 PSTN 閘道關聯到中繼伺服器。選取閘道，然後按一下 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="99d29-p102">On the **Specify PSTN gateways** page, associate the previous PSTN gateway with the Mediation Server. Select the gateway and then click **Add**.</span></span>

8.  <span data-ttu-id="99d29-116">按一下 [完成]\*\*\*\*，以關閉 [定義新的中繼集區精靈]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="99d29-116">Click **Finish** to close the **Define New Mediation Pool** wizard.</span></span>

9.  <span data-ttu-id="99d29-117">在 [ **拓撲**產生器] 中，選取頂端節點 [ **Lync Server 2013**]。</span><span class="sxs-lookup"><span data-stu-id="99d29-117">From **Topology Builder**, select the top node **Lync Server 2013**.</span></span>

10. <span data-ttu-id="99d29-118">在 [動作]\*\*\*\* 窗格中，選取 [發行拓撲]\*\*\*\*，然後完成精靈。</span><span class="sxs-lookup"><span data-stu-id="99d29-118">From the **Actions** pane, select **Publish Topology** and complete the wizard.</span></span>

11. <span data-ttu-id="99d29-119">請依照部署檔中的 [在 [Lync server 2013 中安裝轉送伺服器的](lync-server-2013-install-the-files-for-mediation-server.md) 檔案] 中的步驟，在新的轉送伺服器上安裝檔案。</span><span class="sxs-lookup"><span data-stu-id="99d29-119">Follow the steps in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) in the Deployment documentation to install the files on the new Mediation Server.</span></span>

12. <span data-ttu-id="99d29-120">檔案安裝至中繼伺服器後，請返回拓撲產生器，然後瀏覽左窗格中的集區。</span><span class="sxs-lookup"><span data-stu-id="99d29-120">After the files are installed on the Mediation Server, return to Topology Builder, and in the left pane navigate to the pool.</span></span>

13. <span data-ttu-id="99d29-121">以滑鼠右鍵按一下集區，然後選取 [編輯屬性]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="99d29-121">Right-click the pool and select **Edit Properties**.</span></span>

14. <span data-ttu-id="99d29-122">在 [中繼伺服器]\*\*\*\* 下，清除 [組合的中繼伺服器已啟用]\*\*\*\* 核取方塊，然後按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="99d29-122">Under **Mediation Server**, clear the check box **Collocated Mediation Server enabled** and then click **OK**.</span></span>

15. <span data-ttu-id="99d29-123">在 [ **拓撲**產生器] 中，選取頂端節點 [ **Lync Server 2013**]。</span><span class="sxs-lookup"><span data-stu-id="99d29-123">From **Topology Builder**, select the top node **Lync Server 2013**.</span></span>

16. <span data-ttu-id="99d29-124">從 [動作]\*\*\*\* 功能表中，選取 [發行拓撲]\*\*\*\*，然後完成精靈。</span><span class="sxs-lookup"><span data-stu-id="99d29-124">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

