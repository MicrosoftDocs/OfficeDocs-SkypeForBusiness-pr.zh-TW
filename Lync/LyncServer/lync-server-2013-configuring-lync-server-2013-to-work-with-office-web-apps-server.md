---
title: 設定 Lync Server 2013 與 Office Web Apps Server 搭配使用
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server 2013 to work with Office Web Apps Server
ms:assetid: 6231e519-9010-4ff9-b5a6-b5859c2b3e11
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204944(v=OCS.15)
ms:contentKeyID: 48184288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69a5cd13b139cb2544e1d89971a8480d1e1fb296
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030547"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-to-work-with-office-web-apps-server"></a><span data-ttu-id="34e09-102">設定 Lync Server 2013 與 Office Web Apps Server 搭配使用</span><span class="sxs-lookup"><span data-stu-id="34e09-102">Configuring Lync Server 2013 to work with Office Web Apps Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34e09-103">_**上次修改主題：** 2013年-04-22_</span><span class="sxs-lookup"><span data-stu-id="34e09-103">_**Topic Last Modified:** 2013-04-22_</span></span>

<span data-ttu-id="34e09-104">您可以設定 Lync Server 2013 使用 Office Web Apps Server 之前，必須部署和設定 Office Web Apps Server。</span><span class="sxs-lookup"><span data-stu-id="34e09-104">Before you can configure Lync Server 2013 to use Office Web Apps Server, Office Web Apps Server must be deployed and configured.</span></span> <span data-ttu-id="34e09-105">如需如何安裝及設定單一 Office Web Apps Server，或如何安裝及設定 Office Web Apps Server 陣列以取得高可用性的詳細資訊，請參閱**部署 Office Web Apps Server 與 Office Web Apps 指南**文件。</span><span class="sxs-lookup"><span data-stu-id="34e09-105">See the document **Guide to Deploying Office Web Apps Server and Office Web Apps** for detail information on how to install and configure a single Office Web Apps Server, or for information on how to install and configure an Office Web Apps Server Farm for high availability.</span></span>

<span data-ttu-id="34e09-106">已順利安裝 Office Web Apps Server 並正確設定您的 Web 伺服器陣列，您必須接著設定 Lync Server 進行通訊的新伺服器; 之後這是將 Office Web Apps Server 探索 URL 新增至 Lync Server 拓撲。</span><span class="sxs-lookup"><span data-stu-id="34e09-106">After Office Web Apps Server has been successfully installed and your Web farm correctly configured, you must then configure Lync Server to communicate with the new server; this is done by adding the Office Web Apps Server discovery URL to your Lync Server topology.</span></span> <span data-ttu-id="34e09-107">若要將 Office Web Apps Server 新增至拓撲，請完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="34e09-107">To add Office Web Apps Server to your topology, complete the following steps:</span></span>

1.  <span data-ttu-id="34e09-108">按一下 [**開始]**、 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 拓撲產生器]**。</span><span class="sxs-lookup"><span data-stu-id="34e09-108">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="34e09-109">在 **[拓撲產生器]** 對話方塊中，選取 **[從現有的部署下載拓撲]**，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="34e09-109">In the **Topology Builder** dialog box, select **Download Topology from existing deployment** and then click **OK**.</span></span>

3.  <span data-ttu-id="34e09-p103">在 **[另存拓撲]** 對話方塊的 **[檔案名稱]** 方塊中，鍵入拓撲文件的名稱 (例如 **PreWebAppsServerTopology**)，然後按一下 **[儲存]**。如果新拓撲之後發生問題，就可以擷取並重新發行此拓撲。</span><span class="sxs-lookup"><span data-stu-id="34e09-p103">In the **Save Topology As** dialog box, type a name for your topology document (for example, **PreWebAppsServerTopology**) in the **File name** box and then click **Save**. This topology can later be retrieved and republished if you encounter problems with your new topology.</span></span>

4.  <span data-ttu-id="34e09-112">在拓撲產生器中，依序展開 [ **Lync Server 2013**展開您網站的名稱、 展開 [ **Enterprise Edition 前端集區**、 的其中一個集區名稱上按一下滑鼠右鍵，然後按一下 [**編輯內容]**。</span><span class="sxs-lookup"><span data-stu-id="34e09-112">In Topology Builder, expand **Lync Server 2013**, expand the name of your site, expand **Enterprise Edition Front End pools**, right-click the name of one of your pools, and then click **Edit Properties**.</span></span>

5.  <span data-ttu-id="34e09-113">在 **[編輯內容]** 對話方塊的 **[一般]** 索引標籤上，尋找標題 **[關聯 Office Web Apps Server]**，然後按一下 **[新增]** (或從下拉式清單中選取現有的 Office Web Apps Server)。</span><span class="sxs-lookup"><span data-stu-id="34e09-113">In the **Edit Properties** dialog box, on the **General** tab, find the heading **Associate Office Web Apps Server** and then click **New** (or select an existing Office Web Apps Server from the drop-down list).</span></span>

6.  <span data-ttu-id="34e09-114">在 **[定義新的 Office Web Apps Server]** 對話方塊的 **[Office Web Apps Server FQDN]** 方塊中，鍵入 Office Web Apps Server 電腦的完整網域名稱 (FQDN)；執行此動作時，您的 Office Web Apps Server 探索 URL 應自動輸入至 **[Office Web Apps Server 探索 URL]** 方塊。</span><span class="sxs-lookup"><span data-stu-id="34e09-114">In the **Define New Office Web Apps Server** dialog box, type the fully qualified domain name (FQDN) of your Office Web Apps Server computer in the **Office Web Apps Server FQDN** box; when you do this, your Office Web Apps Server discovery URL should automatically be entered into the **Office Web Apps Server discovery URL** box.</span></span>
    
    <span data-ttu-id="34e09-115">如果 Office Web Apps Server 是安裝在內部和 Lync Server 2013 然後選項位於相同網路地區中**Office Web Apps Server 部署在外部網路 （亦即周邊/網際網路）** 不應選取。</span><span class="sxs-lookup"><span data-stu-id="34e09-115">If the Office Web Apps Server is installed on-premises and in the same network zone as Lync Server 2013 then the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** should not be selected.</span></span>
    
    <span data-ttu-id="34e09-116">如果 Office Web Apps Server 部署在內部防火牆外，則選取 **[Office Web Apps Server 部署在外部網路 (亦即周邊/網際網路]** 選項。</span><span class="sxs-lookup"><span data-stu-id="34e09-116">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**.</span></span>

7.  <span data-ttu-id="34e09-p104">在 **[定義新的 Office Web Apps Server]** 對話方塊中，按一下 **[確定]**，然後按一下 **[編輯內容]** 對話方塊中的 **[確定]**。Office Web Apps 探索 URL 將會列為其中一個集區的關聯。</span><span class="sxs-lookup"><span data-stu-id="34e09-p104">In the **Define New Office Web Apps Server** dialog box, click **OK**, and then click **OK** in the **Edit Properties** dialog box. The Office Web Apps discovery URL will then be listed as one of the pool's Associations.</span></span>

<span data-ttu-id="34e09-119">您必須對每個需要與 Office Web Apps Server 建立關聯的集區重複此程序。</span><span class="sxs-lookup"><span data-stu-id="34e09-119">You will have to repeat this process for each pool that needs to be associated with your Office Web Apps Server.</span></span>

<span data-ttu-id="34e09-p105">在新增探索 URL 至拓撲後，必須發行此更新的拓撲。在拓撲產生器中執行此作業的步驟如下：</span><span class="sxs-lookup"><span data-stu-id="34e09-p105">After you have added the discovery URL to the topology you must then publish this updated topology. To do that in Topology Builder:</span></span>

1.  <span data-ttu-id="34e09-122">按一下 **[動作]**，然後按一下 **[發行拓撲]**。</span><span class="sxs-lookup"><span data-stu-id="34e09-122">Click **Action** and then click **Publish Topology**.</span></span>

2.  <span data-ttu-id="34e09-123">在發行拓撲精靈的 **[發行拓撲]** 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="34e09-123">In the Publish Topology wizard, on the **Publish the Topology** page, click **Next**.</span></span>

3.  <span data-ttu-id="34e09-124">在 **[發行精靈完成]** 頁面上，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="34e09-124">On the **Publishing wizard complete** page, click **Finish**.</span></span>

4.  <span data-ttu-id="34e09-125">關閉拓撲產生器。</span><span class="sxs-lookup"><span data-stu-id="34e09-125">Close Topology Builder.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

