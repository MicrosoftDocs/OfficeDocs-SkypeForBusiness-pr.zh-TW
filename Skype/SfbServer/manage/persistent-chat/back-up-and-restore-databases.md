---
title: 在商務用 Skype Server 2015 中備份及還原持久聊天資料庫
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4f2b689b-7f15-48dc-a069-da7bc8527def
description: 摘要：瞭解如何在商務用 Skype Server 2015 中備份及還原 Persistent Chat Server 資料庫。
ms.openlocfilehash: 2c99f5e955756020f68b51ea214858c23fee0a48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826373"
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a><span data-ttu-id="98e5b-103">在商務用 Skype Server 2015 中備份及還原持久聊天資料庫</span><span class="sxs-lookup"><span data-stu-id="98e5b-103">Back up and restore Persistent Chat databases in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="98e5b-104">**摘要：** 瞭解如何在商務用 Skype Server 2015 中備份及還原 Persistent Chat Server 資料庫。</span><span class="sxs-lookup"><span data-stu-id="98e5b-104">**Summary:** Learn how to back up and restore Persistent Chat Server databases in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="98e5b-105">Persistent Chat Server 需要 SQL Server 資料庫軟體才能儲存聊天室資料，例如歷史和內容、設定、使用者布建及其他相關的中繼資料。</span><span class="sxs-lookup"><span data-stu-id="98e5b-105">Persistent Chat Server requires SQL Server database software to store chat room data, such as history and content, configuration, user provisioning, and other relevant metadata.</span></span> <span data-ttu-id="98e5b-106">此外，如果貴組織的法規要求封存持續聊天活動，且已啟用選用規範服務，則 SQL Server 資料庫軟體是用來儲存規範資料，包括聊天內容和事件（例如加入和離開聊天室）。</span><span class="sxs-lookup"><span data-stu-id="98e5b-106">In addition, if your organization has regulations that require Persistent Chat activity to be archived, and the optional Compliance service is enabled, SQL Server database software is used to store compliance data, including chat content and events, such as joining and leaving rooms.</span></span> <span data-ttu-id="98e5b-107">聊天室內容會儲存在 Persistent Chat database (mgc) 中。</span><span class="sxs-lookup"><span data-stu-id="98e5b-107">Chat room content is stored in the Persistent Chat database (mgc).</span></span> <span data-ttu-id="98e5b-108">規範資料儲存在規範資料庫中 (mgccomp) 。</span><span class="sxs-lookup"><span data-stu-id="98e5b-108">Compliance data is stored in the Compliance database (mgccomp).</span></span> <span data-ttu-id="98e5b-109">這是應該定期備份的重要業務資料。</span><span class="sxs-lookup"><span data-stu-id="98e5b-109">This is business-critical data that should be backed up regularly.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="98e5b-110">商務用 Skype Server 2015 仍提供持續聊天，但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="98e5b-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="98e5b-111">小組中提供相同的功能。</span><span class="sxs-lookup"><span data-stu-id="98e5b-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="98e5b-112">如需詳細資訊，請參閱 [Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。</span><span class="sxs-lookup"><span data-stu-id="98e5b-112">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="98e5b-113">如果您需要使用持續聊天，您可以選擇將需要這項功能的使用者遷移至小組，或是繼續使用商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="98e5b-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="back-up-the-databases"></a><span data-ttu-id="98e5b-114">備份資料庫</span><span class="sxs-lookup"><span data-stu-id="98e5b-114">Back up the databases</span></span>

<span data-ttu-id="98e5b-115">有兩種方式可以備份 Persistent 聊天資料。</span><span class="sxs-lookup"><span data-stu-id="98e5b-115">There are two ways of backing up Persistent Chat data.</span></span> 
  
- <span data-ttu-id="98e5b-116">SQL Server 備份</span><span class="sxs-lookup"><span data-stu-id="98e5b-116">SQL Server Backup</span></span>
    
- <span data-ttu-id="98e5b-117">**Export-CsPersistentChatData** Cmdlet，可將 Persistent 聊天資料匯出為檔案</span><span class="sxs-lookup"><span data-stu-id="98e5b-117">The **Export-CsPersistentChatData** cmdlet, which exports Persistent Chat data as a file</span></span>
    
<span data-ttu-id="98e5b-118">使用 SQL Server 備份所建立的資料所需的磁碟空間（可能會比 **Export-CsPersistentChatData** Cmdlet 所建立的20倍），但 SQL server 備份可能是您熟悉的程式。</span><span class="sxs-lookup"><span data-stu-id="98e5b-118">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by the **Export-CsPersistentChatData** cmdlet, but SQL Server backup is likely to be a procedure with which you are familiar.</span></span>
  
<span data-ttu-id="98e5b-119">如果您想要使用 SQL Server 備份程式，請參閱您的 SQL 檔以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="98e5b-119">If you want to use SQL Server backup procedures, see your SQL documentation for more information.</span></span> 
  
<span data-ttu-id="98e5b-120">如果您想要使用 **Export-CsPersistentChatData** Cmdlet，您可以指定下列命令：</span><span class="sxs-lookup"><span data-stu-id="98e5b-120">If you want to use the **Export-CsPersistentChatData** cmdlet, you can specify the command as follows:</span></span>
  
```PowerShell
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

<span data-ttu-id="98e5b-121">或</span><span class="sxs-lookup"><span data-stu-id="98e5b-121">or</span></span>
  
```PowerShell
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

<span data-ttu-id="98e5b-122">例如，下列命令會從位於伺服器 atl-sql-001.contoso.com 上的 Persistent Chat 資料庫匯出 Persistent Chat 資料;匯出的資料會儲存在 C:\Logs\PersistentChatData.zip 的檔案中。</span><span class="sxs-lookup"><span data-stu-id="98e5b-122">For example, the following command exports Persistent Chat data from the Persistent Chat database located on the server atl-sql-001.contoso.com; the exported data will be stored in the file C:\Logs\PersistentChatData.zip.</span></span> <span data-ttu-id="98e5b-123">因為未指定 Level 參數，所以命令會完整匯出 Persistent Chat 資訊：</span><span class="sxs-lookup"><span data-stu-id="98e5b-123">Because the Level parameter was not specified, the command will do a full export of the Persistent Chat information:</span></span>
  
```PowerShell
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a><span data-ttu-id="98e5b-124">還原資料庫</span><span class="sxs-lookup"><span data-stu-id="98e5b-124">Restore the databases</span></span>

<span data-ttu-id="98e5b-125">還原持久聊天資料的方式取決於您用來備份它的方法。</span><span class="sxs-lookup"><span data-stu-id="98e5b-125">How you restore your Persistent Chat data depends on the method that you used to back it up.</span></span> <span data-ttu-id="98e5b-126">如果您使用 SQL Server 備份程式，您必須使用 SQL Server 還原程式。</span><span class="sxs-lookup"><span data-stu-id="98e5b-126">If you used SQL Server backup procedures, you must use SQL Server restore procedures.</span></span> <span data-ttu-id="98e5b-127">如果您使用 **Export-CsPersistentChatData** Cmdlet 來備份 Persistent 聊天資料，則必須使用 **Import-CsPersistentChatData** Cmdlet 來還原資料：</span><span class="sxs-lookup"><span data-stu-id="98e5b-127">If you used the **Export-CsPersistentChatData** cmdlet to back up Persistent Chat data, then you must use the **Import-CsPersistentChatData** cmdlet to restore the data:</span></span>
  
```PowerShell
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

<span data-ttu-id="98e5b-128">或</span><span class="sxs-lookup"><span data-stu-id="98e5b-128">or</span></span>
  
```PowerShell
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```
