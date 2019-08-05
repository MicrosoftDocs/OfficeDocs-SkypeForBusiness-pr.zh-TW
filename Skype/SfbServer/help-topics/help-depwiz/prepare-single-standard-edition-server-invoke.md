---
title: 準備單一標準版 Server (Invoke)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
description: 在 [執行命令] 頁面上, 安裝 SQL Server Express 和設定來充當中央管理儲存區的工作, 可以在工作窗格中查看。 根據預設, 會建立名稱為「RTC」的 SQL Server 資料庫實例。 您也可以建立防火牆規則, 以允許伺服器和用戶端與資料庫和實例進行通訊的入站和輸出存取。 工作完成後, 您可以從下拉式清單中選取記錄檔。 記錄檔稱為 [引導本機電腦]。 選取記錄檔後, 按一下 [查看記錄]。 檢查記錄檔, 查看是否有任何錯誤和警告。 當您準備好要繼續時, 請按一下 [完成]。 您現在應該使用拓撲建立器定義拓撲 (如果您尚未這麼做)。
ms.openlocfilehash: ec9d3dd8cd1eeadd4d7a69bacdcf6d7e89b1af7d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192329"
---
# <a name="prepare-single-standard-edition-server-invoke"></a><span data-ttu-id="7bb8d-111">準備單一標準版 Server (Invoke)</span><span class="sxs-lookup"><span data-stu-id="7bb8d-111">Prepare Single Standard Edition Server (Invoke)</span></span>
 
<span data-ttu-id="7bb8d-112">在 [**執行命令**] 頁面上, 安裝 SQL Server Express 和設定來充當中央管理儲存區的工作, 可以在工作窗格中查看。</span><span class="sxs-lookup"><span data-stu-id="7bb8d-112">On the **Executing commands** page, the tasks of installing the SQL Server Express and configuring to act as the Central Management store can be viewed in the task pane.</span></span> <span data-ttu-id="7bb8d-113">根據預設, 會建立名稱為「RTC」的 SQL Server 資料庫實例。</span><span class="sxs-lookup"><span data-stu-id="7bb8d-113">By default, an instance of a SQL Server-based database named RTC is created.</span></span> <span data-ttu-id="7bb8d-114">您也可以建立防火牆規則, 以允許伺服器和用戶端與資料庫和實例進行通訊的入站和輸出存取。</span><span class="sxs-lookup"><span data-stu-id="7bb8d-114">Firewall rules are also created to allow inbound and outbound access for servers and clients to communicate with the database and instance.</span></span> <span data-ttu-id="7bb8d-115">工作完成後, 您可以從下拉式清單中選取記錄檔。</span><span class="sxs-lookup"><span data-stu-id="7bb8d-115">After the task is completed, you can select the log file from the drop-down list.</span></span> <span data-ttu-id="7bb8d-116">記錄檔稱為 [**引導本機電腦**]。</span><span class="sxs-lookup"><span data-stu-id="7bb8d-116">The log file is named **Bootstrap local machine**.</span></span> <span data-ttu-id="7bb8d-117">選取記錄檔後, 按一下 [**查看記錄**]。</span><span class="sxs-lookup"><span data-stu-id="7bb8d-117">After selecting the log file, click **View Log**.</span></span> <span data-ttu-id="7bb8d-118">檢查記錄檔, 查看是否有任何錯誤和警告。</span><span class="sxs-lookup"><span data-stu-id="7bb8d-118">Review the log file for any errors and warnings.</span></span> <span data-ttu-id="7bb8d-119">當您準備好要繼續時, 請按一下 **[完成]。**</span><span class="sxs-lookup"><span data-stu-id="7bb8d-119">When you are ready to proceed, click **Finish.**</span></span> <span data-ttu-id="7bb8d-120">您現在應該使用拓撲建立器定義拓撲 (如果您尚未這麼做)。</span><span class="sxs-lookup"><span data-stu-id="7bb8d-120">You should now define your topology with Topology Builder if you have not already done so.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7bb8d-121">安裝 SQL Server Express 可能需要一些時間才能完成。</span><span class="sxs-lookup"><span data-stu-id="7bb8d-121">The installation of the SQL Server Express can take some time to complete.</span></span> <span data-ttu-id="7bb8d-122">在安裝期間, 螢幕或工作窗格中不會顯示任何進度。</span><span class="sxs-lookup"><span data-stu-id="7bb8d-122">During the installation, there is no progress visible on the screen or the task pane.</span></span> <span data-ttu-id="7bb8d-123">若要監視安裝, 您應該使用 Windows 工作管理員, 尋找 MSIExec 進程以及 SQL Server 的安裝檔案。</span><span class="sxs-lookup"><span data-stu-id="7bb8d-123">To monitor the installation, you should use Windows Task Manager and look for the MSIExec processes and the Setup files for SQL Server.</span></span> <span data-ttu-id="7bb8d-124">如此一來, 您就可以查看安裝狀態, 並確定安裝繼續進行。</span><span class="sxs-lookup"><span data-stu-id="7bb8d-124">In this way, you can view the status of the install and be sure that the install is proceeding.</span></span> <span data-ttu-id="7bb8d-125">您可能需要15分鐘以上的時間才能完成安裝 SQL Server 實例, 這取決於此說明主題範圍以外的因素。</span><span class="sxs-lookup"><span data-stu-id="7bb8d-125">Depending on factors beyond the scope of this help topic, it can take up to 15 minutes or more for the install the SQL Server instance to complete.</span></span> 
  

