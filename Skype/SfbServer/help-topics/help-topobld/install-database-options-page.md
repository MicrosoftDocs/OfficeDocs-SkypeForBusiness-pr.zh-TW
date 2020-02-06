---
title: 安裝資料庫選項頁面
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.InstallDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 926c47a0-3957-4892-b61a-7a4b569552c3
description: 您可以在 SQL Server 上設定資料庫與記錄檔案位置的高級選項。 可用的選項包括：
ms.openlocfilehash: b24e79a837265930dd853590c9c3139c60a7abd4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819805"
---
# <a name="install-database-options-page"></a><span data-ttu-id="cc994-104">安裝資料庫選項頁面</span><span class="sxs-lookup"><span data-stu-id="cc994-104">Install Database Options Page</span></span>

<span data-ttu-id="cc994-105">您可以在 SQL Server 上設定資料庫與記錄檔案位置的高級選項。</span><span class="sxs-lookup"><span data-stu-id="cc994-105">You configure advanced options for the placement of database and log files on your SQL Server.</span></span> <span data-ttu-id="cc994-106">可用的選項包括：</span><span class="sxs-lookup"><span data-stu-id="cc994-106">The options available are:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cc994-107">選取最符合您的需求與原則的選項，這些選項與您的 SQL Server 電腦上的資料和記錄檔案位置有關。</span><span class="sxs-lookup"><span data-stu-id="cc994-107">Select the option that best fits your requirements and policies pertaining to data and log file placement on your SQL Server computers.</span></span>

 <span data-ttu-id="cc994-108">**自動判斷資料庫檔案位置**： [預設] 選項使用的演算法決定 SQL Server 上可用的空間，並散發資料庫與記錄檔以獲得最佳效能。</span><span class="sxs-lookup"><span data-stu-id="cc994-108">**Automatically determine database file location**: The default option uses an algorithm that determines the available space on the SQL Server and distributes the database and log files for optimal performance.</span></span>

 <span data-ttu-id="cc994-109">**使用 Sql server 實例預設值**：選取此選項以根據 SQL Server 上的實例設定，放置資料庫檔案和記錄檔案。</span><span class="sxs-lookup"><span data-stu-id="cc994-109">**Use SQL Server instance defaults**: Select this option to place database file and log files based on the instance settings at SQL Server.</span></span> <span data-ttu-id="cc994-110">選項通常是由資料庫管理員進行管理和設定。</span><span class="sxs-lookup"><span data-stu-id="cc994-110">The options are typically managed and configured by your Database Administrator.</span></span>

 <span data-ttu-id="cc994-111">**我們在目標 SQL server 上的這些路徑**：選取這個選項，即可定義您自己的 SQL Server 資料庫路徑和記錄檔案，方法是輸入要放置資料庫及記錄檔的磁片磁碟機及資料夾的完整路徑。</span><span class="sxs-lookup"><span data-stu-id="cc994-111">**Us these path on target SQL Server**: Select this option to define your own paths for SQL Server database and log files by typing the full path to the drive and folder where the database and log files will be placed.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cc994-112">您輸入的路徑可能會根據安裝中的效能優化演算法進行修改。</span><span class="sxs-lookup"><span data-stu-id="cc994-112">The paths that you enter may be modified based on performance optimization algorithms in the installation.</span></span> <span data-ttu-id="cc994-113">如需詳細資訊，請參閱[使用 Lync Server 管理命令介面的資料庫安裝](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)。</span><span class="sxs-lookup"><span data-stu-id="cc994-113">For details, see [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx).</span></span>

 <span data-ttu-id="cc994-114">**[確定]**：按一下 [確定] 按鈕，確認您的變更。</span><span class="sxs-lookup"><span data-stu-id="cc994-114">**OK**: Click the OK button to commit your changes.</span></span>

 <span data-ttu-id="cc994-115">[**取消**]：按一下 [取消] 放棄任何變更，然後返回 [安裝資料庫] 畫面。</span><span class="sxs-lookup"><span data-stu-id="cc994-115">**Cancel**: Click Cancel to discard any changes and return to the Install Database screen.</span></span>

 <span data-ttu-id="cc994-116">說明 **：按一下**[說明] 按鈕即可存取此說明頁面。</span><span class="sxs-lookup"><span data-stu-id="cc994-116">**Help**: Click the Help button to access this Help page.</span></span>

## <a name="see-also"></a><span data-ttu-id="cc994-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="cc994-117">See also</span></span>

[<span data-ttu-id="cc994-118">SQL Server 資料與記錄檔的位置</span><span class="sxs-lookup"><span data-stu-id="cc994-118">SQL Server Data and Log File Placement</span></span>](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)
