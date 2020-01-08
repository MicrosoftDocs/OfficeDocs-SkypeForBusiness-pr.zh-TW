---
title: Lync Server 2013：將 Lync Server 2013 Standard Edition 部署到現有 Lync Server 2013 Enterprise 中
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Lync Server 2013 Standard Edition into an existing Lync Server 2013 Enterprise
ms:assetid: 05ea128d-6c94-49b3-b28b-477367196425
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398112(v=OCS.15)
ms:contentKeyID: 48183297
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c505a692590662adf03e48d695b3c1ff089d8d7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977527"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-server-2013-standard-edition-into-an-existing-lync-server-2013-enterprise"></a><span data-ttu-id="0ed55-102">將 Lync Server 2013 Standard Edition 部署到現有 Lync Server 2013 Enterprise 中</span><span class="sxs-lookup"><span data-stu-id="0ed55-102">Deploying Lync Server 2013 Standard Edition into an existing Lync Server 2013 Enterprise</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ed55-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="0ed55-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="0ed55-104">將標準版伺服器部署至現有的企業版部署，與部署其他伺服器角色類似。</span><span class="sxs-lookup"><span data-stu-id="0ed55-104">Deploying a Standard Edition server into an existing Enterprise Edition deployment is similar to deploying additional server roles.</span></span> <span data-ttu-id="0ed55-105">標準版伺服器可能會部署至另一個網站，允許該網站的使用者駐留在標準版伺服器上，而不是在廣域網路（WAN）中的前端池。</span><span class="sxs-lookup"><span data-stu-id="0ed55-105">A Standard Edition server might be deployed to another site, allowing for users in that site to be homed on the Standard Edition server rather than the Front End pool across a wide area network (WAN).</span></span> <span data-ttu-id="0ed55-106">在該網站中安裝新網站和伺服器的程式，已在 [[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md) ] 檔的其他章節中定義。</span><span class="sxs-lookup"><span data-stu-id="0ed55-106">The procedures for installing the new site and servers in that site are already defined in other sections of the [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) documentation.</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="0ed55-107">**定義新網站**</span><span class="sxs-lookup"><span data-stu-id="0ed55-107">**To define a new site**</span></span>

1.  <span data-ttu-id="0ed55-108">啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。</span><span class="sxs-lookup"><span data-stu-id="0ed55-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="0ed55-109">在主控台樹中，以滑鼠右鍵按一下 [ **Lync Server 2013**]，然後按一下 [**新的中央網站**]。</span><span class="sxs-lookup"><span data-stu-id="0ed55-109">In the console tree, right-click **Lync Server 2013**, and then click **New Central Site**.</span></span>

3.  <span data-ttu-id="0ed55-110">在 [**識別網站**] 頁面上，提供網站的名稱，並選擇性地輸入描述。</span><span class="sxs-lookup"><span data-stu-id="0ed55-110">On the **Identify the site** page, give a name to the site and optionally enter a description.</span></span>

4.  <span data-ttu-id="0ed55-111">遵循定義網站拓撲其餘部分的程式。</span><span class="sxs-lookup"><span data-stu-id="0ed55-111">Follow the procedures for defining the rest of the site topology.</span></span> <span data-ttu-id="0ed55-112">如需詳細資訊，請參閱[在 Lync Server 2013 中定義及設定拓撲](lync-server-2013-defining-and-configuring-the-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="0ed55-112">For details, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span>

5.  <span data-ttu-id="0ed55-113">發佈更新後的拓撲。</span><span class="sxs-lookup"><span data-stu-id="0ed55-113">Publish the updated topology.</span></span> <span data-ttu-id="0ed55-114">如需詳細資訊，請參閱[在 Lync Server 2013 中發佈拓撲](lync-server-2013-publish-the-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="0ed55-114">For details, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md).</span></span>

6.  <span data-ttu-id="0ed55-115">設定和安裝標準版伺服器。</span><span class="sxs-lookup"><span data-stu-id="0ed55-115">Set up and install a Standard Edition server.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="0ed55-116">如果您已部署只有標準版 server 的環境，您就會從 Lync Server 部署嚮導開始進行設定程式，方法是使用 [<STRONG>準備第一個標準版 Server</STRONG> ] 連結，將初始資料庫檔案安裝到新的標準版伺服器。</span><span class="sxs-lookup"><span data-stu-id="0ed55-116">If you have deployed an environment with only a Standard Edition server, you would have begun the setup process from the Lync Server Deployment Wizard by using the <STRONG>Prepare first Standard Edition server</STRONG> link to install the initial database files to the new Standard Edition server.</span></span> <span data-ttu-id="0ed55-117">將標準版伺服器安裝至現有的 Lync Server 2013 部署時，<STRONG>請勿</STRONG>遵循該程式。</span><span class="sxs-lookup"><span data-stu-id="0ed55-117"><STRONG>Do not</STRONG> follow that process when installing a Standard Edition server into an existing Lync Server 2013 deployment.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

