---
title: Lync Server 2013：安裝 SQL Server Reporting Services
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing SQL Server Reporting Services
ms:assetid: 638a1d0c-1ac7-4735-83f2-4df3d03c7cf9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204957(v=OCS.15)
ms:contentKeyID: 48184345
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9044f90146b604f0277b0a5b815c6540849d58b7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534930"
---
# <a name="installing-sql-server-reporting-services-in-lync-server-2013"></a><span data-ttu-id="a6032-102">在 Lync Server 2013 中安裝 SQL Server Reporting Services</span><span class="sxs-lookup"><span data-stu-id="a6032-102">Installing SQL Server Reporting Services in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6032-103">_**主題上次修改日期：** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="a6032-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="a6032-104">如果您想要使用 Microsoft Lync Server 2013 監控報告 (請參閱本檔的下一節，以取得詳細資訊) 您必須先安裝 SQL Server Reporting Services;在安裝 SQL Server 時，或在安裝 SQL Server 之後的任何時間，都可以安裝 Reporting Services。</span><span class="sxs-lookup"><span data-stu-id="a6032-104">If you intend to use Microsoft Lync Server 2013 Monitoring Reports (see the next section of this documentation for more information) you must first install SQL Server Reporting Services; Reporting Services can be installed at the same time you install Microsoft SQL Server or any time after SQL Server has been installed.</span></span> <span data-ttu-id="a6032-105">如果尚未安裝 SQL Server，請遵循本文件中先前提供的指示。</span><span class="sxs-lookup"><span data-stu-id="a6032-105">If you have not installed SQL Server, then follow the instructions provided earlier in this documentation.</span></span> <span data-ttu-id="a6032-106">安裝 SQL Server 時，請務必在 [特徵選取] 頁面選取 [Reporting Services]。</span><span class="sxs-lookup"><span data-stu-id="a6032-106">When installing SQL Server, make sure that, on the Feature Selection page, you select Reporting Services.</span></span> <span data-ttu-id="a6032-107">如此會安裝 SQL Server Reporting Services。</span><span class="sxs-lookup"><span data-stu-id="a6032-107">That will install SQL Server Reporting Services.</span></span>

<span data-ttu-id="a6032-108">若已安裝 SQL Server 但未安裝 SQL Server Reporting Services，您可以視情況遵循針對 SQL Server 2008 R2 或 SQL Server 2012 的一組適當指示，新增該特徵。</span><span class="sxs-lookup"><span data-stu-id="a6032-108">If you have already installed SQL Server but did not install SQL Server Reporting Services you can add that feature by following the appropriate set of instructions for SQL Server 2008 R2 or SQL Server 2012, as appropriate.</span></span>

<span data-ttu-id="a6032-109">若要驗證已成功安裝 Reporting Services，請完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="a6032-109">To verify that the reporting Services have been successfully installed, complete the following steps:</span></span>

1.  <span data-ttu-id="a6032-110">如果執行 Microsoft SQL Server 2008 R2，請依序按一下 **[開始]**、**[所有程式]**、**[Microsoft SQL Server 2008 R2]**、[**組態工具]** 及 **[Reporting Services 組態管理員]**。</span><span class="sxs-lookup"><span data-stu-id="a6032-110">If you are running Microsoft SQL Server 2008 R2, then click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>
    
    <span data-ttu-id="a6032-111">如果執行 Microsoft SQL Server 2012，請依序按一下 **[開始]**、**[所有程式]**、**[Microsoft SQL Server 2012]**、**[組態工具]** 及 **[Reporting Services 組態管理員]**。</span><span class="sxs-lookup"><span data-stu-id="a6032-111">If you are running Microsoft SQL Server 2012, then click **Start**, click **All Programs**, click **Microsoft SQL Server 2012**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>

2.  <span data-ttu-id="a6032-p102">在 **[Reporting Services 組態連接]** 對話方塊中，確認您伺服器的名稱顯示在 **[伺服器名稱]** 方塊中，而儲存您監控資料之 SQL Server 執行個體的名稱顯示在 **[報表伺服器執行個體]** 方塊中，然後按一下 **[連接]**。</span><span class="sxs-lookup"><span data-stu-id="a6032-p102">In the **Reporting Services Configuration Connection** dialog box, verify that the name of your server appears in the **Server Name** box and that the name of the SQL Server instance that stores your monitoring data appears in the **Report Server Instance** box. Click **Connect**.</span></span>

<span data-ttu-id="a6032-114">在 [Reporting Service 設定管理員] 中，報表伺服器狀態窗格應該會顯示已安裝 SQL Server Reporting Services，且 Reporting Services 目前正在執行中：報表伺服器狀態應該顯示為 [ **已啟動** ]，而且 [ **開始** ] 按鈕應該會顯示為灰色且無法使用。</span><span class="sxs-lookup"><span data-stu-id="a6032-114">In the Reporting Service Configuration Manager, the Report Server Status pane should show that SQL Server Reporting Services has been installed and that the Reporting Services are currently running: the Report Server Status should be shown as **Started** and the **Start** button should be grayed-out and unavailable.</span></span> <span data-ttu-id="a6032-115">如果 Reporting Service 未執行，請按一下 **[啟動]** 以啟動服務。</span><span class="sxs-lookup"><span data-stu-id="a6032-115">If the Reporting Service is not running, click **Start** in order to start the service.</span></span>

<span data-ttu-id="a6032-116">如果 [報表伺服器資料庫名稱] 標籤旁未列出資料庫，請執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="a6032-116">If no database is listed next to the Report Server Database Name label then do the following:</span></span>

1.  <span data-ttu-id="a6032-117">在 Reporting Services 組態管理員中，按一下 **[資料庫]**。</span><span class="sxs-lookup"><span data-stu-id="a6032-117">In the Reporting Services Configuration Manager click **Database**.</span></span>

2.  <span data-ttu-id="a6032-118">在 [報表伺服器資料庫] 窗格中，按一下 **[變更資料庫]**。</span><span class="sxs-lookup"><span data-stu-id="a6032-118">In the Report Server Database pane click **Change Database**.</span></span>

3.  <span data-ttu-id="a6032-119">在報表伺服器資料庫組態精靈的 [動作] 窗格中，選取 **[建立新的報表伺服器資料庫]**，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="a6032-119">In the Report Server Database Configuration wizard, in the Action pane, select **Create a new report server database** and then click **Next**.</span></span>

4.  <span data-ttu-id="a6032-p104">在報表伺服器資料庫組態精靈的 [資料庫伺服器] 窗格中，確認列於 **[伺服器名稱]**、**[驗證類型]** 及 **[使用者名稱]** 方塊中的資訊是否正確。按一下 **[測試連接]** 以驗證可以連接至資料庫伺服器，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="a6032-p104">In the Report Server Database Configuration wizard, in the Database Server pane, verify that the information listed in the **Server Name**, **Authentication Type**, and **Username** boxes is correct. Click **Test Connection** to verify that a connection can be made to the database server and then click **Next**.</span></span>

5.  <span data-ttu-id="a6032-122">在報表伺服器資料庫組態精靈的 [資料庫] 窗格中，接受 **[資料庫名稱]**、**[語言]** 及 **[報表伺服器模式]** 的預設值，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="a6032-122">In the Report Server Database Configuration wizard, in the Database pane, accept the default values for **Database Name**, **Language**, and **Report Server Mode** and then click **Next**.</span></span>

6.  <span data-ttu-id="a6032-123">在報表伺服器資料庫組態精靈的 [認證] 窗格中，確認列於 **[驗證類型]** 下拉式清單、**[使用者名稱]** 及 **[密碼]** 方塊中的資訊是否正確，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="a6032-123">In the Report Server Database Configuration wizard, in the Credentials pane, verify that the correct information is listed in the **Authentication Type** dropdown list and the **User name** and **Password** boxes, and then click **Next**.</span></span>

7.  <span data-ttu-id="a6032-124">在報表伺服器資料庫組態精靈的 [摘要] 窗格中，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="a6032-124">In the Report Server Database Configuration wizard, in the Summary pane, click **Next**.</span></span>

8.  <span data-ttu-id="a6032-125">在報表伺服器資料庫組態精靈的 [進度和完成] 窗格中，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="a6032-125">In the Report Server Database Configuration wizard, in the Progress and Finish pane, click **Finish**.</span></span>

<span data-ttu-id="a6032-p105">若要驗證是否設定 Reporting Service URL，請按一下 **[Web 服務 URL]**。應該見到在 **[報表伺服器 Web 服務 URL]** 標題下列出一個或多個 URL。請逐一按一下這些 URL，確認是否可以存取本機安裝 SQL Server Reporting Services 的首頁。</span><span class="sxs-lookup"><span data-stu-id="a6032-p105">To verify that the Reporting Service URLs have been configured, click **Web Service URL**. You should see one or more URLs listed under the heading **Report Server Web Service URLs**. Click each of these URLs to verify that you can reach the home page for the local installation of SQL Server Reporting Services.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

