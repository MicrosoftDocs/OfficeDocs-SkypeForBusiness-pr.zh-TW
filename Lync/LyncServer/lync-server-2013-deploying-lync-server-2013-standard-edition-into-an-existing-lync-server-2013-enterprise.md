---
title: Lync Server 2013：將 Lync Server 2013 Standard Edition 部署到現有的 Lync Server 2013 Enterprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Server 2013 Standard Edition into an existing Lync Server 2013 Enterprise
ms:assetid: 05ea128d-6c94-49b3-b28b-477367196425
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398112(v=OCS.15)
ms:contentKeyID: 48183297
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd3d666eefe04a6650a5c1a10253f490e391ff22
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501510"
---
# <a name="deploying-lync-server-2013-standard-edition-into-an-existing-lync-server-2013-enterprise"></a><span data-ttu-id="61ced-102">將 Lync Server 2013 Standard Edition 部署到現有的 Lync Server 2013 企業版</span><span class="sxs-lookup"><span data-stu-id="61ced-102">Deploying Lync Server 2013 Standard Edition into an existing Lync Server 2013 Enterprise</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61ced-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="61ced-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="61ced-104">將 Standard Edition server 部署至現有的 Enterprise Edition 部署，類似于部署其他伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="61ced-104">Deploying a Standard Edition server into an existing Enterprise Edition deployment is similar to deploying additional server roles.</span></span> <span data-ttu-id="61ced-105">Standard Edition server 可能會部署至另一個網站，讓該網站中的使用者能夠駐留在 Standard Edition server，而不是跨廣域網路) 的前端集區 (。</span><span class="sxs-lookup"><span data-stu-id="61ced-105">A Standard Edition server might be deployed to another site, allowing for users in that site to be homed on the Standard Edition server rather than the Front End pool across a wide area network (WAN).</span></span> <span data-ttu-id="61ced-106">在 [ [部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md) ] 檔的其他區段中已定義安裝新網站及該網站中伺服器的程式。</span><span class="sxs-lookup"><span data-stu-id="61ced-106">The procedures for installing the new site and servers in that site are already defined in other sections of the [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) documentation.</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="61ced-107">**若要定義新網站**</span><span class="sxs-lookup"><span data-stu-id="61ced-107">**To define a new site**</span></span>

1.  <span data-ttu-id="61ced-108">啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。</span><span class="sxs-lookup"><span data-stu-id="61ced-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="61ced-109">在主控台樹中，以滑鼠右鍵按一下 [ **Lync Server 2013**]，然後按一下 [ **新增中央網站**]。</span><span class="sxs-lookup"><span data-stu-id="61ced-109">In the console tree, right-click **Lync Server 2013**, and then click **New Central Site**.</span></span>

3.  <span data-ttu-id="61ced-110">在 **[識別網站]** 頁面上，提供網站的名稱並選擇性輸入描述。</span><span class="sxs-lookup"><span data-stu-id="61ced-110">On the **Identify the site** page, give a name to the site and optionally enter a description.</span></span>

4.  <span data-ttu-id="61ced-111">遵循用於定義網站拓撲其餘部分的程序。</span><span class="sxs-lookup"><span data-stu-id="61ced-111">Follow the procedures for defining the rest of the site topology.</span></span> <span data-ttu-id="61ced-112">如需詳細資訊，請參閱 [在 Lync Server 2013 中定義及設定拓撲](lync-server-2013-defining-and-configuring-the-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="61ced-112">For details, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span>

5.  <span data-ttu-id="61ced-113">發行更新後的拓撲。</span><span class="sxs-lookup"><span data-stu-id="61ced-113">Publish the updated topology.</span></span> <span data-ttu-id="61ced-114">如需詳細資訊，請參閱 [在 Lync Server 2013 中發行拓撲](lync-server-2013-publish-the-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="61ced-114">For details, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md).</span></span>

6.  <span data-ttu-id="61ced-115">設定並安裝 Standard Edition server。</span><span class="sxs-lookup"><span data-stu-id="61ced-115">Set up and install a Standard Edition server.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="61ced-116">如果您已部署只有 Standard Edition server 的環境，則您必須使用 [ <STRONG>準備第一個 Standard edition Server</STRONG> ] 連結，從 [Lync Server 部署嚮導] 中開始安裝程式，將初始資料庫檔案安裝到新的 Standard edition server。</span><span class="sxs-lookup"><span data-stu-id="61ced-116">If you have deployed an environment with only a Standard Edition server, you would have begun the setup process from the Lync Server Deployment Wizard by using the <STRONG>Prepare first Standard Edition server</STRONG> link to install the initial database files to the new Standard Edition server.</span></span> <span data-ttu-id="61ced-117">將 Standard Edition server 安裝至現有的 Lync Server 2013 部署時，<STRONG>請勿</STRONG>遵循此程式。</span><span class="sxs-lookup"><span data-stu-id="61ced-117"><STRONG>Do not</STRONG> follow that process when installing a Standard Edition server into an existing Lync Server 2013 deployment.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

