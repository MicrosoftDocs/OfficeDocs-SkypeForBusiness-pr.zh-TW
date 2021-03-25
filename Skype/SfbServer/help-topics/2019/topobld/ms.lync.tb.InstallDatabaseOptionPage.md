---
title: 安裝資料庫選項頁面
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.InstallDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 926c47a0-3957-4892-b61a-7a4b569552c3
ROBOTS: NOINDEX, NOFOLLOW
description: 您可以設定 SQL Server 上的資料庫及記錄檔位置的高級選項。 可用選項包括：
ms.openlocfilehash: 4b4323f2b0e953ff24a458a2f28f75f52d4f0149
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121641"
---
# <a name="install-database-options-page"></a><span data-ttu-id="18312-104">安裝資料庫選項頁面</span><span class="sxs-lookup"><span data-stu-id="18312-104">Install Database Options Page</span></span>

<span data-ttu-id="18312-105">您可以設定 SQL Server 上的資料庫及記錄檔位置的高級選項。</span><span class="sxs-lookup"><span data-stu-id="18312-105">You configure advanced options for the placement of database and log files on your SQL Server.</span></span> <span data-ttu-id="18312-106">可用選項包括：</span><span class="sxs-lookup"><span data-stu-id="18312-106">The options available are:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="18312-107">選取最符合您的需求和原則的選項，這些選項與您的 SQL Server 電腦上的資料和記錄檔位置有關。</span><span class="sxs-lookup"><span data-stu-id="18312-107">Select the option that best fits your requirements and policies pertaining to data and log file placement on your SQL Server computers.</span></span>

 <span data-ttu-id="18312-108">**自動判斷資料庫檔案位置**： [預設] 選項使用的演算法決定 SQL Server 上可用的空間，以及散佈資料庫及記錄檔以取得最佳效能。</span><span class="sxs-lookup"><span data-stu-id="18312-108">**Automatically determine database file location**: The default option uses an algorithm that determines the available space on the SQL Server and distributes the database and log files for optimal performance.</span></span>

 <span data-ttu-id="18312-109">**使用 Sql server 實例的預設值**：選取此選項，會根據 SQL Server 上的實例設定，放置資料庫檔案及記錄檔。</span><span class="sxs-lookup"><span data-stu-id="18312-109">**Use SQL Server instance defaults**: Select this option to place database file and log files based on the instance settings at SQL Server.</span></span> <span data-ttu-id="18312-110">選項通常是由資料庫管理員管理及設定。</span><span class="sxs-lookup"><span data-stu-id="18312-110">The options are typically managed and configured by your Database Administrator.</span></span>

 <span data-ttu-id="18312-111">**我們在目標 SQL Server 上的這些路徑**：選取此選項可透過輸入存放資料庫及記錄檔之磁片磁碟機和資料夾的完整路徑，以定義您自己的 SQL server 資料庫和記錄檔路徑。</span><span class="sxs-lookup"><span data-stu-id="18312-111">**Us these path on target SQL Server**: Select this option to define your own paths for SQL Server database and log files by typing the full path to the drive and folder where the database and log files will be placed.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="18312-112">您輸入的路徑可能會根據安裝中的效能優化演算法進行修改。</span><span class="sxs-lookup"><span data-stu-id="18312-112">The paths that you enter may be modified based on performance optimization algorithms in the installation.</span></span> <span data-ttu-id="18312-113">如需詳細資訊，請參閱 [使用 Lync Server 管理命令介面進行資料庫安裝](/previous-versions/office/lync-server-2013/lync-server-2013-database-installation-using-lync-server-management-shell)。</span><span class="sxs-lookup"><span data-stu-id="18312-113">For details, see [Database Installation Using Lync Server Management Shell](/previous-versions/office/lync-server-2013/lync-server-2013-database-installation-using-lync-server-management-shell).</span></span>

 <span data-ttu-id="18312-114">**確定**：按一下 [確定] 按鈕認可您的變更。</span><span class="sxs-lookup"><span data-stu-id="18312-114">**OK**: Click the OK button to commit your changes.</span></span>

 <span data-ttu-id="18312-115">**取消**：按一下 [取消] 捨棄所有變更，並回到 [安裝資料庫] 畫面。</span><span class="sxs-lookup"><span data-stu-id="18312-115">**Cancel**: Click Cancel to discard any changes and return to the Install Database screen.</span></span>

 <span data-ttu-id="18312-116">說明 **：按一下**[說明] 按鈕，存取此說明頁面。</span><span class="sxs-lookup"><span data-stu-id="18312-116">**Help**: Click the Help button to access this Help page.</span></span>

## <a name="see-also"></a><span data-ttu-id="18312-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="18312-117">See also</span></span>

[<span data-ttu-id="18312-118">SQL Server 資料和記錄檔位置</span><span class="sxs-lookup"><span data-stu-id="18312-118">SQL Server Data and Log File Placement</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement)