---
title: 將 Lync Server 2013 設定為使用 Office Web Apps Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Lync Server 2013 to work with Office Web Apps Server
ms:assetid: 6231e519-9010-4ff9-b5a6-b5859c2b3e11
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204944(v=OCS.15)
ms:contentKeyID: 48184288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ba6926af243b15449c5b8baa4b29706a2ec8ade
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976983"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-to-work-with-office-web-apps-server"></a><span data-ttu-id="e9e8d-102">將 Lync Server 2013 設定為使用 Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="e9e8d-102">Configuring Lync Server 2013 to work with Office Web Apps Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9e8d-103">_**主題上次修改日期：** 2013-04-22_</span><span class="sxs-lookup"><span data-stu-id="e9e8d-103">_**Topic Last Modified:** 2013-04-22_</span></span>

<span data-ttu-id="e9e8d-104">在您可以將 Lync Server 2013 設定為使用 Office Web Apps Server 之前，必須先部署並設定 Office Web Apps 伺服器。</span><span class="sxs-lookup"><span data-stu-id="e9e8d-104">Before you can configure Lync Server 2013 to use Office Web Apps Server, Office Web Apps Server must be deployed and configured.</span></span> <span data-ttu-id="e9e8d-105">如需有關如何安裝及設定單一 Office Web Apps 伺服器的詳細資訊，請參閱檔**指南**，或瞭解如何安裝和設定 Office Web Apps 伺服器群以獲得高可用性的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="e9e8d-105">See the document **Guide to Deploying Office Web Apps Server and Office Web Apps** for detail information on how to install and configure a single Office Web Apps Server, or for information on how to install and configure an Office Web Apps Server Farm for high availability.</span></span>

<span data-ttu-id="e9e8d-106">成功安裝 Office Web Apps 伺服器並正確設定您的網站伺服器之後，您必須將 Lync Server 設定為與新伺服器通訊;這是透過將 Office Web Apps Server 探索 URL 新增到您的 Lync Server 拓撲中來完成。</span><span class="sxs-lookup"><span data-stu-id="e9e8d-106">After Office Web Apps Server has been successfully installed and your Web farm correctly configured, you must then configure Lync Server to communicate with the new server; this is done by adding the Office Web Apps Server discovery URL to your Lync Server topology.</span></span> <span data-ttu-id="e9e8d-107">若要將 Office Web Apps 伺服器新增到拓撲中，請完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="e9e8d-107">To add Office Web Apps Server to your topology, complete the following steps:</span></span>

1.  <span data-ttu-id="e9e8d-108">按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。</span><span class="sxs-lookup"><span data-stu-id="e9e8d-108">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="e9e8d-109">在 [**拓撲**建立器] 對話方塊中，選取 [**從現有的部署下載拓撲結構**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="e9e8d-109">In the **Topology Builder** dialog box, select **Download Topology from existing deployment** and then click **OK**.</span></span>

3.  <span data-ttu-id="e9e8d-110">在 [**將拓朴儲存為**] 對話方塊中，于 **[檔案名]** 方塊中輸入拓撲檔的名稱（例如， **PreWebAppsServerTopology**），然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="e9e8d-110">In the **Save Topology As** dialog box, type a name for your topology document (for example, **PreWebAppsServerTopology**) in the **File name** box and then click **Save**.</span></span> <span data-ttu-id="e9e8d-111">如果您在新的拓撲中遇到問題，可在稍後檢索並重新發佈此拓撲。</span><span class="sxs-lookup"><span data-stu-id="e9e8d-111">This topology can later be retrieved and republished if you encounter problems with your new topology.</span></span>

4.  <span data-ttu-id="e9e8d-112">在 [拓撲結構建立器] 中，展開 [ **Lync Server 2013**]，展開您的網站名稱，展開 [**企業版前端池**]，以滑鼠右鍵按一下其中一個池的名稱，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="e9e8d-112">In Topology Builder, expand **Lync Server 2013**, expand the name of your site, expand **Enterprise Edition Front End pools**, right-click the name of one of your pools, and then click **Edit Properties**.</span></span>

5.  <span data-ttu-id="e9e8d-113">在 [**編輯屬性**] 對話方塊的 [**一般**] 索引標籤上，找到 [**關聯 Office Web Apps 伺服器**] 的 [標題]，然後按一下下拉式清單中的 [**新增**] （或選取現有的 Office Web Apps 伺服器）。</span><span class="sxs-lookup"><span data-stu-id="e9e8d-113">In the **Edit Properties** dialog box, on the **General** tab, find the heading **Associate Office Web Apps Server** and then click **New** (or select an existing Office Web Apps Server from the drop-down list).</span></span>

6.  <span data-ttu-id="e9e8d-114">在 [**定義新的 Office Web Apps 伺服器**] 對話方塊的 [ **Office WEB apps server FQDN** ] 方塊中，輸入您 office web apps server 電腦的完整功能變數名稱（FQDN）;當您這樣做時，您的 Office Web Apps 伺服器探索 URL 應該會自動輸入至 [ **Office Web Apps server 探索 url** ] 方塊中。</span><span class="sxs-lookup"><span data-stu-id="e9e8d-114">In the **Define New Office Web Apps Server** dialog box, type the fully qualified domain name (FQDN) of your Office Web Apps Server computer in the **Office Web Apps Server FQDN** box; when you do this, your Office Web Apps Server discovery URL should automatically be entered into the **Office Web Apps Server discovery URL** box.</span></span>
    
    <span data-ttu-id="e9e8d-115">如果 Office Web Apps 伺服器安裝于內部部署，且位於與 Lync Server 2013 相同的網路區域中，則不應選取 [ **Office Web Apps 伺服器] 部署在外部網路（也就是 [週邊/網際網路]）** 。</span><span class="sxs-lookup"><span data-stu-id="e9e8d-115">If the Office Web Apps Server is installed on-premises and in the same network zone as Lync Server 2013 then the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** should not be selected.</span></span>
    
    <span data-ttu-id="e9e8d-116">如果 Office Web Apps 伺服器是在您的內部防火牆外部署，請選取 [ **Office Web Apps 伺服器] 部署在外部網路（也就是 [週邊/網際網路]）**。</span><span class="sxs-lookup"><span data-stu-id="e9e8d-116">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**.</span></span>

7.  <span data-ttu-id="e9e8d-117">在 [**定義新的 Office Web Apps Server** ] 對話方塊中，按一下 **[確定]**，然後按一下 [**編輯屬性**] 對話方塊中的 **[確定**]。</span><span class="sxs-lookup"><span data-stu-id="e9e8d-117">In the **Define New Office Web Apps Server** dialog box, click **OK**, and then click **OK** in the **Edit Properties** dialog box.</span></span> <span data-ttu-id="e9e8d-118">然後，Office Web Apps 探索 URL 就會列為其中一個池的關聯。</span><span class="sxs-lookup"><span data-stu-id="e9e8d-118">The Office Web Apps discovery URL will then be listed as one of the pool's Associations.</span></span>

<span data-ttu-id="e9e8d-119">您必須針對需要與您的 Office Web Apps 伺服器相關聯的每個池重複此程式。</span><span class="sxs-lookup"><span data-stu-id="e9e8d-119">You will have to repeat this process for each pool that needs to be associated with your Office Web Apps Server.</span></span>

<span data-ttu-id="e9e8d-120">將探索 URL 新增到拓撲之後，您必須發佈此更新的拓撲。</span><span class="sxs-lookup"><span data-stu-id="e9e8d-120">After you have added the discovery URL to the topology you must then publish this updated topology.</span></span> <span data-ttu-id="e9e8d-121">若要在拓撲建立器中執行此動作：</span><span class="sxs-lookup"><span data-stu-id="e9e8d-121">To do that in Topology Builder:</span></span>

1.  <span data-ttu-id="e9e8d-122">按一下 [**動作**]，然後按一下 [**發佈拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="e9e8d-122">Click **Action** and then click **Publish Topology**.</span></span>

2.  <span data-ttu-id="e9e8d-123">在 [發佈拓撲嚮導] 的 [**發佈拓撲**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e9e8d-123">In the Publish Topology wizard, on the **Publish the Topology** page, click **Next**.</span></span>

3.  <span data-ttu-id="e9e8d-124">在 [**發佈嚮導完成]** 頁面上，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="e9e8d-124">On the **Publishing wizard complete** page, click **Finish**.</span></span>

4.  <span data-ttu-id="e9e8d-125">關閉拓撲建立器。</span><span class="sxs-lookup"><span data-stu-id="e9e8d-125">Close Topology Builder.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

