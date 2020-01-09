---
title: 備份和還原常設聊天室資料庫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4f2b689b-7f15-48dc-a069-da7bc8527def
description: 摘要：瞭解如何在商務用 Skype Server 2015 中備份及還原持續聊天伺服器資料庫。
ms.openlocfilehash: a8c407c35b9d864889c26cbea7296dbed86516fa
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991968"
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a><span data-ttu-id="b2d6e-103">備份和還原常設聊天室資料庫</span><span class="sxs-lookup"><span data-stu-id="b2d6e-103">Back up and restore Persistent Chat databases in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b2d6e-104">**摘要：** 瞭解如何在商務用 Skype Server 2015 中備份及還原持續聊天伺服器資料庫。</span><span class="sxs-lookup"><span data-stu-id="b2d6e-104">**Summary:** Learn how to back up and restore Persistent Chat Server databases in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="b2d6e-105">持續聊天伺服器需要 SQL Server 資料庫軟體來儲存聊天室資料，例如記錄與內容、設定、使用者提供及其他相關中繼資料。</span><span class="sxs-lookup"><span data-stu-id="b2d6e-105">Persistent Chat Server requires SQL Server database software to store chat room data, such as history and content, configuration, user provisioning, and other relevant metadata.</span></span> <span data-ttu-id="b2d6e-106">此外，如果您的組織有需要封存持久聊天活動的法規，且已啟用 [選用規範服務]，則 SQL Server 資料庫軟體是用來儲存合規性資料，包括聊天內容和事件，例如加入並離開會議室。</span><span class="sxs-lookup"><span data-stu-id="b2d6e-106">In addition, if your organization has regulations that require Persistent Chat activity to be archived, and the optional Compliance service is enabled, SQL Server database software is used to store compliance data, including chat content and events, such as joining and leaving rooms.</span></span> <span data-ttu-id="b2d6e-107">聊天室內容會儲存在持續聊天資料庫（mgc）。</span><span class="sxs-lookup"><span data-stu-id="b2d6e-107">Chat room content is stored in the Persistent Chat database (mgc).</span></span> <span data-ttu-id="b2d6e-108">合規性資料會儲存在規範資料庫（mgccomp）中。</span><span class="sxs-lookup"><span data-stu-id="b2d6e-108">Compliance data is stored in the Compliance database (mgccomp).</span></span> <span data-ttu-id="b2d6e-109">這是應定期備份的業務關鍵型資料。</span><span class="sxs-lookup"><span data-stu-id="b2d6e-109">This is business-critical data that should be backed up regularly.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="b2d6e-110">商務用 Skype Server 2015 提供持續聊天，但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="b2d6e-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="b2d6e-111">團隊中提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="b2d6e-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="b2d6e-112">如需詳細資訊，請參閱[Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。</span><span class="sxs-lookup"><span data-stu-id="b2d6e-112">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="b2d6e-113">如果您需要使用持續聊天，您可以選擇將需要此功能的使用者遷移至小組，或繼續使用商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="b2d6e-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="back-up-the-databases"></a><span data-ttu-id="b2d6e-114">備份資料庫</span><span class="sxs-lookup"><span data-stu-id="b2d6e-114">Back up the databases</span></span>

<span data-ttu-id="b2d6e-115">備份持續聊天資料的方式有兩種。</span><span class="sxs-lookup"><span data-stu-id="b2d6e-115">There are two ways of backing up Persistent Chat data.</span></span> 
  
- <span data-ttu-id="b2d6e-116">SQL Server 備份</span><span class="sxs-lookup"><span data-stu-id="b2d6e-116">SQL Server Backup</span></span>
    
- <span data-ttu-id="b2d6e-117">**匯出 CsPersistentChatData** Cmdlet，可將永久性聊天資料匯出為檔案</span><span class="sxs-lookup"><span data-stu-id="b2d6e-117">The **Export-CsPersistentChatData** cmdlet, which exports Persistent Chat data as a file</span></span>
    
<span data-ttu-id="b2d6e-118">使用 SQL Server 備份所建立的資料所需的磁碟空間可能會比**Export CsPersistentChatData** Cmdlet 所建立的20倍，但 SQL Server 備份可能是您熟悉的程式。</span><span class="sxs-lookup"><span data-stu-id="b2d6e-118">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by the **Export-CsPersistentChatData** cmdlet, but SQL Server backup is likely to be a procedure with which you are familiar.</span></span>
  
<span data-ttu-id="b2d6e-119">如果您想要使用 SQL Server 備份程式，請參閱 SQL 檔以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="b2d6e-119">If you want to use SQL Server backup procedures, see your SQL documentation for more information.</span></span> 
  
<span data-ttu-id="b2d6e-120">如果您想要使用**Export CsPersistentChatData** Cmdlet，您可以指定下列命令：</span><span class="sxs-lookup"><span data-stu-id="b2d6e-120">If you want to use the **Export-CsPersistentChatData** cmdlet, you can specify the command as follows:</span></span>
  
```PowerShell
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

<span data-ttu-id="b2d6e-121">或</span><span class="sxs-lookup"><span data-stu-id="b2d6e-121">or</span></span>
  
```PowerShell
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

<span data-ttu-id="b2d6e-122">例如，下列命令會從位於伺服器 atl-sql-001.contoso.com 上的持久聊天資料庫匯出持續聊天資料;匯出的資料會儲存在 [檔案 C:\Logs\PersistentChatData.zip.] 中。</span><span class="sxs-lookup"><span data-stu-id="b2d6e-122">For example, the following command exports Persistent Chat data from the Persistent Chat database located on the server atl-sql-001.contoso.com; the exported data will be stored in the file C:\Logs\PersistentChatData.zip.</span></span> <span data-ttu-id="b2d6e-123">因為未指定 Level 參數，命令會完全匯出持續聊天資訊：</span><span class="sxs-lookup"><span data-stu-id="b2d6e-123">Because the Level parameter was not specified, the command will do a full export of the Persistent Chat information:</span></span>
  
```PowerShell
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a><span data-ttu-id="b2d6e-124">還原資料庫</span><span class="sxs-lookup"><span data-stu-id="b2d6e-124">Restore the databases</span></span>

<span data-ttu-id="b2d6e-125">您還原持久聊天資料的方式，取決於您用來備份它的方法。</span><span class="sxs-lookup"><span data-stu-id="b2d6e-125">How you restore your Persistent Chat data depends on the method that you used to back it up.</span></span> <span data-ttu-id="b2d6e-126">如果您使用的是 SQL Server 備份程式，您必須使用 SQL Server restore 程式。</span><span class="sxs-lookup"><span data-stu-id="b2d6e-126">If you used SQL Server backup procedures, you must use SQL Server restore procedures.</span></span> <span data-ttu-id="b2d6e-127">如果您使用**Export CsPersistentChatData** Cmdlet 來備份持續聊天資料，您必須使用**Import-CsPersistentChatData** Cmdlet 來還原資料：</span><span class="sxs-lookup"><span data-stu-id="b2d6e-127">If you used the **Export-CsPersistentChatData** cmdlet to back up Persistent Chat data, then you must use the **Import-CsPersistentChatData** cmdlet to restore the data:</span></span>
  
```PowerShell
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

<span data-ttu-id="b2d6e-128">或</span><span class="sxs-lookup"><span data-stu-id="b2d6e-128">or</span></span>
  
```PowerShell
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```
