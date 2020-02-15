---
title: 從現有部署下載拓撲
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Download topology from existing deployment
ms:assetid: e39065a2-d4b0-4f27-8c49-f56be78fa55b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721913(v=OCS.15)
ms:contentKeyID: 49733847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66b68459a1923fcb4a066cafe02c5226b24f9321
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006409"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="download-topology-from-existing-deployment"></a><span data-ttu-id="7bd5f-102">從現有部署下載拓撲</span><span class="sxs-lookup"><span data-stu-id="7bd5f-102">Download topology from existing deployment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7bd5f-103">_**主題上次修改日期：** 2012年-09-29_</span><span class="sxs-lookup"><span data-stu-id="7bd5f-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="7bd5f-104">建立 Lync Server 2013 集區，您會使用關聯 Lync Server 2010 中央管理存放區。</span><span class="sxs-lookup"><span data-stu-id="7bd5f-104">When creating a Lync Server 2013 pool, you will use the Central Management Store that is associated with Lync Server 2010.</span></span> <span data-ttu-id="7bd5f-105">當您啟動拓撲產生器中第一次使用以及後續編輯工作階段，會提示您輸入您希望拓撲產生器來載入目前的設定文件的位置。</span><span class="sxs-lookup"><span data-stu-id="7bd5f-105">When you start Topology Builder on first use and subsequent edit sessions, you are prompted for the location where you want Topology Builder to load the current configuration document.</span></span> <span data-ttu-id="7bd5f-106">因為您已有定義 Lync Server 2010 拓撲，並已建立的中央管理存放區，您應該選擇 [從現有部署下載拓撲。</span><span class="sxs-lookup"><span data-stu-id="7bd5f-106">Because you already have a Lync Server 2010 topology defined and have established the Central Management store, you should choose to download a topology from an existing deployment.</span></span> <span data-ttu-id="7bd5f-107">拓撲產生器將讀取資料庫，並擷取目前的定義。</span><span class="sxs-lookup"><span data-stu-id="7bd5f-107">Topology Builder will read the database and retrieve the current definition.</span></span>

<span data-ttu-id="7bd5f-108">**若要從現有部署下載拓撲**</span><span class="sxs-lookup"><span data-stu-id="7bd5f-108">**To download a topology from an existing deployment**</span></span>

1.  <span data-ttu-id="7bd5f-109">開啟**Lync Server 部署精靈**]。</span><span class="sxs-lookup"><span data-stu-id="7bd5f-109">Open the **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="7bd5f-110">從**Lync Server 2013 – 部署精靈**] 頁面上，按一下 [**安裝系統管理工具**]。</span><span class="sxs-lookup"><span data-stu-id="7bd5f-110">From the **Lync Server 2013 – Deployment Wizard** page, click **Install Administrative Tools**.</span></span>

3.  <span data-ttu-id="7bd5f-111">啟動拓撲產生器： 按一下 [**開始]**、 [**所有程式]**、 [ **Microsoft Lync Server 2013** ]，然後按一下**Lync Server 拓撲產生器]**。</span><span class="sxs-lookup"><span data-stu-id="7bd5f-111">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013** , and then click **Lync Server Topology Builder**.</span></span>

4.  <span data-ttu-id="7bd5f-112">選取 [**從現有部署下載拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="7bd5f-112">Select **Download Topology from existing deployment**.</span></span>
    
    <span data-ttu-id="7bd5f-113">![部署精靈拓撲產生器設定](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "部署精靈拓撲產生器設定")</span><span class="sxs-lookup"><span data-stu-id="7bd5f-113">![Deployment Wizard Topology Builder settings](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "Deployment Wizard Topology Builder settings")</span></span>

5.  <span data-ttu-id="7bd5f-114">選擇 [檔案名稱，預設的.tbxml 檔案類型儲存拓撲。</span><span class="sxs-lookup"><span data-stu-id="7bd5f-114">Choose a file name and save the topology with the default .tbxml file type.</span></span>

6.  <span data-ttu-id="7bd5f-115">展開 [Lync Server] 節點中，所示，以顯示部署中的各種伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="7bd5f-115">Expand the Lync Server node, as shown, to reveal the various server roles in the deployment.</span></span>
    
    <span data-ttu-id="7bd5f-116">![拓撲產生器伺服器角色一般屬性](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "拓撲產生器伺服器角色一般屬性")</span><span class="sxs-lookup"><span data-stu-id="7bd5f-116">![Topology Builder server role general properties](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "Topology Builder server role general properties")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

