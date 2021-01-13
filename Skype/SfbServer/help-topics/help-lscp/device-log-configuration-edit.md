---
title: 裝置記錄檔設定編輯
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
- ms.lync.lscp.ClientDeviceUpdateEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e534e6a5-fb3e-40b1-a189-fce64c42f512
description: 您可以在 [編輯記錄檔設定] 頁面中新增裝置記錄檔設定，以決定記錄檔快取大小上限、記錄檔大小上限，或在清除記錄檔之前保留記錄檔的時間長度。 您可以根據組織的需求來變更這些設定。
ms.openlocfilehash: 694729b74209715bd87bed0c3bd59d80f31fff59
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807313"
---
# <a name="device-log-configuration-edit"></a><span data-ttu-id="a6dad-104">裝置記錄組態：編輯</span><span class="sxs-lookup"><span data-stu-id="a6dad-104">Device Log Configuration: Edit</span></span>
 
<span data-ttu-id="a6dad-105">您可以在 [ **編輯記錄檔設定** ] 頁面中新增裝置記錄檔設定，以決定記錄檔快取大小上限、記錄檔大小上限，或在清除記錄檔之前保留記錄檔的時間長度。</span><span class="sxs-lookup"><span data-stu-id="a6dad-105">You can add a device log configuration to the **Edit Log Setting** page that determines the maximum log cache size, maximum log file size, or length of time a log file is kept before it is purged.</span></span> <span data-ttu-id="a6dad-106">您可以根據組織的需求來變更這些設定。</span><span class="sxs-lookup"><span data-stu-id="a6dad-106">You can change these settings according to your organization's requirements.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="a6dad-107">永久清除檔案會將檔案從檔案系統中移除。</span><span class="sxs-lookup"><span data-stu-id="a6dad-107">Purging files permanently removes them from the file system.</span></span> <span data-ttu-id="a6dad-108">清除檔案之後，便無法復原。</span><span class="sxs-lookup"><span data-stu-id="a6dad-108">After you purge a file, it cannot be recovered.</span></span> 
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="a6dad-109">您可以執行的工作</span><span class="sxs-lookup"><span data-stu-id="a6dad-109">Tasks you can perform</span></span>

<span data-ttu-id="a6dad-110">您可以在 [ **編輯記錄檔設定** ] 頁面上執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="a6dad-110">You can perform the following tasks on the **Edit Log Setting** page:</span></span>
  
- <span data-ttu-id="a6dad-111">全域或針對特定網站新增裝置記錄檔設定。</span><span class="sxs-lookup"><span data-stu-id="a6dad-111">Add a device log configuration globally or for a particular site.</span></span>
    
- <span data-ttu-id="a6dad-112">修改現有裝置記錄檔設定的選項。</span><span class="sxs-lookup"><span data-stu-id="a6dad-112">Modify the options for an existing device log configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="a6dad-113">UI 參考</span><span class="sxs-lookup"><span data-stu-id="a6dad-113">UI Reference</span></span>

<span data-ttu-id="a6dad-114">下列清單說明頁面上的功能表、命令、欄位及內容。</span><span class="sxs-lookup"><span data-stu-id="a6dad-114">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="a6dad-115">**範圍** 識別裝置記錄檔設定 (全域或網站) 的範圍。</span><span class="sxs-lookup"><span data-stu-id="a6dad-115">**Scope** Identifies the scope (Global or Site) of the device log configuration.</span></span>
    
- <span data-ttu-id="a6dad-116">**名稱** 您可以新增或修改裝置記錄檔設定的名稱。</span><span class="sxs-lookup"><span data-stu-id="a6dad-116">**Name** You can add or modify the name of the device log configuration.</span></span>
    
- <span data-ttu-id="a6dad-117">**(位元組的檔案大小上限)** 您可以指定在清除記錄檔之前，記錄檔可以變為的大小上限。</span><span class="sxs-lookup"><span data-stu-id="a6dad-117">**Maximum file size (bytes)** You can specify the maximum size a log file can become before it is purged.</span></span> <span data-ttu-id="a6dad-118">預設值為1024000位元組 (1 MB) 。</span><span class="sxs-lookup"><span data-stu-id="a6dad-118">The default is 1,024,000 bytes (1 MB).</span></span>
    
- <span data-ttu-id="a6dad-119">**(位元組的最大快取大小)** 您可以指定可在記錄檔快取中保留的最大資訊量 (，) 在該快取必須先加以保留，才能清除快取，而且資料會寫入記錄檔。</span><span class="sxs-lookup"><span data-stu-id="a6dad-119">**Maximum cache size (bytes)** You can specify the maximum amount of information (in bytes) that can be held in the log file cache before that cache must be cleared and the data is written to a log file.</span></span> <span data-ttu-id="a6dad-120">預設值為512000位元組 (0.5 MB) 。</span><span class="sxs-lookup"><span data-stu-id="a6dad-120">The default is 512,000 bytes (0.5 MB).</span></span>
    
- <span data-ttu-id="a6dad-121">**刷新快取 (1-60 的分鐘)** 您可以指定儲存在記錄檔快取中的資訊寫入實際記錄檔的頻率。</span><span class="sxs-lookup"><span data-stu-id="a6dad-121">**Minutes to flush cache (1-60)** You can specify how often information stored in the log file cache is written to the actual log file.</span></span> <span data-ttu-id="a6dad-122">在記錄資料後，會清除快取。</span><span class="sxs-lookup"><span data-stu-id="a6dad-122">After the data is logged, the cache is cleared.</span></span> <span data-ttu-id="a6dad-123">預設值為5分鐘。</span><span class="sxs-lookup"><span data-stu-id="a6dad-123">The default is five minutes.</span></span>
    
- <span data-ttu-id="a6dad-124">**將記錄檔保留在 (1-365 的天數)** 您可以指定在清除記錄檔之前保留的天數。</span><span class="sxs-lookup"><span data-stu-id="a6dad-124">**Days to keep log files (1-365)** You can specify the number of days the log files are kept before they are purged.</span></span> <span data-ttu-id="a6dad-125">預設值為10天。</span><span class="sxs-lookup"><span data-stu-id="a6dad-125">The default is 10 days.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a6dad-126">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a6dad-126">See also</span></span>

[<span data-ttu-id="a6dad-127">裝置記錄組態</span><span class="sxs-lookup"><span data-stu-id="a6dad-127">Device Log Configuration</span></span>](device-log-configuration.md)
