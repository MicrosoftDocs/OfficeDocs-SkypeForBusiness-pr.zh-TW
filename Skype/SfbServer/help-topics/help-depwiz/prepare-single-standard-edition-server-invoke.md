---
title: 準備單一 Standard Edition Server (叫用)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
description: 在 [執行命令] 頁面上，安裝 SQL Server Express 和設定以充當中央管理存放區的工作可以在工作窗格中查看。 根據預設，會建立名為 RTC 之 SQL Server 資料庫的實例。 也會建立防火牆規則，允許輸入和輸出存取，讓伺服器和用戶端能夠與資料庫及執行個體進行通訊。 工作完成之後，您可以從下拉式清單選取記錄檔。 記錄檔名稱為 [啟動程序本機電腦]。 選取記錄檔之後，請按一下 [檢視記錄檔]。 請檢閱記錄檔中是否有任何錯誤和警告。 準備好可以繼續時，按一下 [完成]。 您現在應該使用拓撲產生器來定義拓撲（如果尚未這麼做）。
ms.openlocfilehash: adf980ec2576eb4e23983fcd99befb1fc6bfb6ee
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829743"
---
# <a name="prepare-single-standard-edition-server-invoke"></a><span data-ttu-id="a2a74-111">準備單一 Standard Edition Server (叫用)</span><span class="sxs-lookup"><span data-stu-id="a2a74-111">Prepare Single Standard Edition Server (Invoke)</span></span>
 
<span data-ttu-id="a2a74-112">在 [ **執行命令** ] 頁面上，安裝 SQL Server Express 和設定以充當中央管理存放區的工作可以在工作窗格中查看。</span><span class="sxs-lookup"><span data-stu-id="a2a74-112">On the **Executing commands** page, the tasks of installing the SQL Server Express and configuring to act as the Central Management store can be viewed in the task pane.</span></span> <span data-ttu-id="a2a74-113">根據預設，會建立名為 RTC 之 SQL Server 資料庫的實例。</span><span class="sxs-lookup"><span data-stu-id="a2a74-113">By default, an instance of a SQL Server-based database named RTC is created.</span></span> <span data-ttu-id="a2a74-114">也會建立防火牆規則，允許輸入和輸出存取，讓伺服器和用戶端能夠與資料庫及執行個體進行通訊。</span><span class="sxs-lookup"><span data-stu-id="a2a74-114">Firewall rules are also created to allow inbound and outbound access for servers and clients to communicate with the database and instance.</span></span> <span data-ttu-id="a2a74-115">工作完成之後，您可以從下拉式清單選取記錄檔。</span><span class="sxs-lookup"><span data-stu-id="a2a74-115">After the task is completed, you can select the log file from the drop-down list.</span></span> <span data-ttu-id="a2a74-116">記錄檔名稱為 **[啟動程序本機電腦]**。</span><span class="sxs-lookup"><span data-stu-id="a2a74-116">The log file is named **Bootstrap local machine**.</span></span> <span data-ttu-id="a2a74-117">選取記錄檔之後，請按一下 **[檢視記錄檔]**。</span><span class="sxs-lookup"><span data-stu-id="a2a74-117">After selecting the log file, click **View Log**.</span></span> <span data-ttu-id="a2a74-118">請檢閱記錄檔中是否有任何錯誤和警告。</span><span class="sxs-lookup"><span data-stu-id="a2a74-118">Review the log file for any errors and warnings.</span></span> <span data-ttu-id="a2a74-119">準備好可以繼續時，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="a2a74-119">When you are ready to proceed, click **Finish.**</span></span> <span data-ttu-id="a2a74-120">您現在應該使用拓撲產生器來定義拓撲（如果尚未這麼做）。</span><span class="sxs-lookup"><span data-stu-id="a2a74-120">You should now define your topology with Topology Builder if you have not already done so.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a2a74-121">安裝 SQL Server Express 可能需要一些時間才能完成。</span><span class="sxs-lookup"><span data-stu-id="a2a74-121">The installation of the SQL Server Express can take some time to complete.</span></span> <span data-ttu-id="a2a74-122">在安裝期間，畫面或工作窗格上不會看到任何進度。</span><span class="sxs-lookup"><span data-stu-id="a2a74-122">During the installation, there is no progress visible on the screen or the task pane.</span></span> <span data-ttu-id="a2a74-123">若要監視安裝，您應該使用 Windows 工作管理員，並尋找適用于 SQL Server 的 MSIExec 處理常式和安裝檔案。</span><span class="sxs-lookup"><span data-stu-id="a2a74-123">To monitor the installation, you should use Windows Task Manager and look for the MSIExec processes and the Setup files for SQL Server.</span></span> <span data-ttu-id="a2a74-124">如此您可以檢視安裝的狀態，並確定安裝正在進行中。</span><span class="sxs-lookup"><span data-stu-id="a2a74-124">In this way, you can view the status of the install and be sure that the install is proceeding.</span></span> <span data-ttu-id="a2a74-125">根據此說明主題範圍以外的因素，安裝 SQL Server 實例最多可能需要15分鐘的時間才能完成。</span><span class="sxs-lookup"><span data-stu-id="a2a74-125">Depending on factors beyond the scope of this help topic, it can take up to 15 minutes or more for the install the SQL Server instance to complete.</span></span> 
  

