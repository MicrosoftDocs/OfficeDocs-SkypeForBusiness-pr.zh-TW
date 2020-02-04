---
title: 建立資料庫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
description: '[拓撲建立器] 提供在 SQL Server store 上安裝資料庫的方法。 當您使用 [拓撲建立器] 來安裝資料庫時，應用程式會讀取拓撲中的資訊，然後在指定的 SQL Server 電腦或 SQL Server 群集上安裝所需的資料庫。 這是唯一可以使用拓撲產生器進行的資料庫安裝類型。 如果您需要在特定電腦上安裝特定資料庫，或必須安裝 collocated 資料庫，則必須改為使用 Windows PowerShell 命令列介面和安裝 CsDatabase Cmdlet。'
ms.openlocfilehash: 02d754870cb2d2db16424474a68b8ea0245191f7
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684846"
---
# <a name="create-database"></a><span data-ttu-id="625b7-106">建立資料庫</span><span class="sxs-lookup"><span data-stu-id="625b7-106">Create Database</span></span>
 
<span data-ttu-id="625b7-107">[拓撲建立器] 提供在 SQL Server store 上安裝資料庫的方法。</span><span class="sxs-lookup"><span data-stu-id="625b7-107">Topology Builder provides a way to install databases on a SQL Server store.</span></span> <span data-ttu-id="625b7-108">當您使用 [拓撲建立器] 來安裝資料庫時，應用程式會讀取拓撲中的資訊，然後在指定的 SQL Server 電腦或 SQL Server 群集上安裝所需的資料庫。</span><span class="sxs-lookup"><span data-stu-id="625b7-108">When you install databases by using Topology Builder, the application reads information from the topology and then installs the required databases on the specified SQL Server computer or SQL Server cluster.</span></span> <span data-ttu-id="625b7-109">這是唯一可以使用拓撲產生器進行的資料庫安裝類型。</span><span class="sxs-lookup"><span data-stu-id="625b7-109">This is the only type of database installation available by using Topology Builder.</span></span> <span data-ttu-id="625b7-110">如果您需要在特定電腦上安裝特定資料庫，或必須安裝 collocated 資料庫，則必須改為使用 Windows PowerShell 命令列介面和[安裝 CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="625b7-110">If you need to install a specific database on a specific computer, or if you must install a collocated database, you must use Windows PowerShell command-line interface and the [Install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) cmdlet instead.</span></span>
  
### <a name="creating-a-database"></a><span data-ttu-id="625b7-111">建立資料庫</span><span class="sxs-lookup"><span data-stu-id="625b7-111">Creating a Database</span></span>

1. <span data-ttu-id="625b7-112">按一下商務用 Skype Server 2015 節點，然後按一下 [**安裝資料庫**]。</span><span class="sxs-lookup"><span data-stu-id="625b7-112">Click the Skype for Business Server 2015 node and then click **Install Database**.</span></span>
    
2. <span data-ttu-id="625b7-113">在 [**安裝資料庫**] 對話方塊的 [**建立資料庫**] 頁面上，選取要建立新資料庫的 SQL Server store 的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="625b7-113">In the **Install Databases** dialog box, on the **Create Database** page, select the fully qualified domain name (FQDN) of the SQL Server store where the new databases are to be created.</span></span>
    
3. <span data-ttu-id="625b7-p103">按一下 [進階]\*\*\*\*。在 [選取資料庫檔案位置]\*\*\*\* 對話方塊中，選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="625b7-p103">Click **Advanced**. In the **Select Database File Location** dialog box, select one of the following options:</span></span>
    
   - <span data-ttu-id="625b7-p104">**自動判斷資料庫檔案位置**。選取此選項時，拓撲產生器會使用內建的演算法選擇資料庫記錄與資料檔案的儲存位置。</span><span class="sxs-lookup"><span data-stu-id="625b7-p104">**Automatically determine database file location**. If you select this option, Topology Builder uses a built-in algorithm to choose the storage location for the database logs and data files.</span></span>
    
   - <span data-ttu-id="625b7-118">**使用 SQL Server 執行個體預設值**。</span><span class="sxs-lookup"><span data-stu-id="625b7-118">**Use SQL Server instance defaults**.</span></span> <span data-ttu-id="625b7-119">選取此選項時，不會使用內建的演算法選擇資料庫記錄與資料檔案的儲存位置。</span><span class="sxs-lookup"><span data-stu-id="625b7-119">If you select this option, the built-in algorithm is not used to choose the storage locations for the database logs and data files.</span></span> <span data-ttu-id="625b7-120">相反地，記錄和資料檔案會儲存在 SQL Server 預設路徑所指定的位置（這些路徑必須由 SQL Server 系統管理員設定為高級）。</span><span class="sxs-lookup"><span data-stu-id="625b7-120">Instead, log and data files are stored in the locations specified by the SQL Server defaults path (these paths must be configured in advanced by a SQL Server administrator).</span></span> <span data-ttu-id="625b7-121">資料檔案會儲存在預設的 SQL Server 資料檔案位置中，而記錄檔案則儲存在預設的 SQL Server 記錄檔案位置中。</span><span class="sxs-lookup"><span data-stu-id="625b7-121">Data files will be stored in the default SQL Server data file location while log files will be stored in the default SQL Server log file location.</span></span>
    
4. <span data-ttu-id="625b7-122">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="625b7-122">Click **OK**.</span></span>
    
5. <span data-ttu-id="625b7-123">在「建立資料庫」\*\*\*\* 頁面上，按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="625b7-123">On the **Create Database** page, click **Next**.</span></span>
    
6. <span data-ttu-id="625b7-124">在「資料庫建立完成」\*\*\*\* 頁面上，按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="625b7-124">On the **Database Creation Complete** page, click **Finish**.</span></span>
    

