---
title: 建立資料庫
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
ROBOTS: NOINDEX, NOFOLLOW
description: 拓撲產生器提供一種方法，可在 SQL Server 儲存區上安裝資料庫。 當您使用拓撲產生器安裝資料庫時，應用程式會讀取拓撲中的資訊，然後在指定的 SQL Server 電腦或 SQL Server 叢集上安裝所需的資料庫。 這是唯一可以使用拓撲產生器進行的資料庫安裝類型。 如果您需要在特定電腦上安裝特定資料庫，或是必須安裝組合資料庫，則必須改用 Windows PowerShell 命令列介面和 Install-CsDatabase Cmdlet。
ms.openlocfilehash: 92e0c8c0221fbd697ce59587ff4543d6cf7e119d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101829"
---
# <a name="create-database"></a><span data-ttu-id="207f9-106">建立資料庫</span><span class="sxs-lookup"><span data-stu-id="207f9-106">Create Database</span></span>
 
<span data-ttu-id="207f9-107">拓撲產生器提供一種方法，可在 SQL Server 儲存區上安裝資料庫。</span><span class="sxs-lookup"><span data-stu-id="207f9-107">Topology Builder provides a way to install databases on a SQL Server store.</span></span> <span data-ttu-id="207f9-108">當您使用拓撲產生器安裝資料庫時，應用程式會讀取拓撲中的資訊，然後在指定的 SQL Server 電腦或 SQL Server 叢集上安裝所需的資料庫。</span><span class="sxs-lookup"><span data-stu-id="207f9-108">When you install databases by using Topology Builder, the application reads information from the topology and then installs the required databases on the specified SQL Server computer or SQL Server cluster.</span></span> <span data-ttu-id="207f9-109">這是唯一可以使用拓撲產生器進行的資料庫安裝類型。</span><span class="sxs-lookup"><span data-stu-id="207f9-109">This is the only type of database installation available by using Topology Builder.</span></span> <span data-ttu-id="207f9-110">如果您需要在特定電腦上安裝特定資料庫，或是必須安裝組合資料庫，則必須改用 Windows PowerShell 命令列介面和 [Install-CsDatabase](/powershell/module/skype/install-csdatabase?view=skype-ps) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="207f9-110">If you need to install a specific database on a specific computer, or if you must install a collocated database, you must use Windows PowerShell command-line interface and the [Install-CsDatabase](/powershell/module/skype/install-csdatabase?view=skype-ps) cmdlet instead.</span></span>
  
### <a name="creating-a-database"></a><span data-ttu-id="207f9-111">建立資料庫</span><span class="sxs-lookup"><span data-stu-id="207f9-111">Creating a Database</span></span>

1. <span data-ttu-id="207f9-112">按一下 [商務用 Skype 伺服器] 節點，然後按一下 [ **安裝資料庫**]。</span><span class="sxs-lookup"><span data-stu-id="207f9-112">Click the Skype for Business Server node and then click **Install Database**.</span></span>
    
2. <span data-ttu-id="207f9-113">在 [ **安裝** 資料庫] 對話方塊的 [ **建立資料庫** ] 頁面上，選取要用來建立新資料庫之 SQL SERVER 儲存區 (FQDN) 的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="207f9-113">In the **Install Databases** dialog box, on the **Create Database** page, select the fully qualified domain name (FQDN) of the SQL Server store where the new databases are to be created.</span></span>
    
3. <span data-ttu-id="207f9-p103">按一下 [進階]。在 [選取資料庫檔案位置] 對話方塊中，選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="207f9-p103">Click **Advanced**. In the **Select Database File Location** dialog box, select one of the following options:</span></span>
    
   - <span data-ttu-id="207f9-p104">**自動判斷資料庫檔案位置**。選取此選項時，拓撲產生器會使用內建的演算法選擇資料庫記錄與資料檔案的儲存位置。</span><span class="sxs-lookup"><span data-stu-id="207f9-p104">**Automatically determine database file location**. If you select this option, Topology Builder uses a built-in algorithm to choose the storage location for the database logs and data files.</span></span>
    
   - <span data-ttu-id="207f9-118">**使用 SQL Server 執行個體預設值**。</span><span class="sxs-lookup"><span data-stu-id="207f9-118">**Use SQL Server instance defaults**.</span></span> <span data-ttu-id="207f9-119">選取此選項時，不會使用內建的演算法選擇資料庫記錄與資料檔案的儲存位置。</span><span class="sxs-lookup"><span data-stu-id="207f9-119">If you select this option, the built-in algorithm is not used to choose the storage locations for the database logs and data files.</span></span> <span data-ttu-id="207f9-120">相反地，記錄檔和資料檔案儲存在 SQL Server 預設路徑所指定的位置中 (這些路徑必須透過 SQL Server 系統管理員) 進行高級設定。</span><span class="sxs-lookup"><span data-stu-id="207f9-120">Instead, log and data files are stored in the locations specified by the SQL Server defaults path (these paths must be configured in advanced by a SQL Server administrator).</span></span> <span data-ttu-id="207f9-121">資料檔案會儲存在預設的 SQL Server 資料檔案位置中，而記錄檔案則儲存在預設的 SQL Server 記錄檔案位置中。</span><span class="sxs-lookup"><span data-stu-id="207f9-121">Data files will be stored in the default SQL Server data file location while log files will be stored in the default SQL Server log file location.</span></span>
    
4. <span data-ttu-id="207f9-122">按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="207f9-122">Click **OK**.</span></span>
    
5. <span data-ttu-id="207f9-123">在「建立資料庫」頁面上，按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="207f9-123">On the **Create Database** page, click **Next**.</span></span>
    
6. <span data-ttu-id="207f9-124">在「資料庫建立完成」頁面上，按一下 [完成]。</span><span class="sxs-lookup"><span data-stu-id="207f9-124">On the **Database Creation Complete** page, click **Finish**.</span></span>
