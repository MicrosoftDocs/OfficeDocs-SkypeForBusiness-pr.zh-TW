---
title: 裝置記錄配置編輯
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceUpdateEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e534e6a5-fb3e-40b1-a189-fce64c42f512
description: 您可以將裝置記錄設定新增至 [編輯記錄] 設定頁面, 以判斷最大記錄快取大小、最大記錄檔大小, 或記錄檔案在清除之前所保留的時間長度。 您可以根據組織的需求變更這些設定。
ms.openlocfilehash: 51804fb420c940494017cde86f3f8c62bd335424
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190291"
---
# <a name="device-log-configuration-edit"></a><span data-ttu-id="d3527-104">裝置記錄配置: 編輯</span><span class="sxs-lookup"><span data-stu-id="d3527-104">Device Log Configuration: Edit</span></span>
 
<span data-ttu-id="d3527-105">您可以將裝置記錄設定新增至 [**編輯記錄] 設定**頁面, 以判斷最大記錄快取大小、最大記錄檔大小, 或記錄檔案在清除之前所保留的時間長度。</span><span class="sxs-lookup"><span data-stu-id="d3527-105">You can add a device log configuration to the **Edit Log Setting** page that determines the maximum log cache size, maximum log file size, or length of time a log file is kept before it is purged.</span></span> <span data-ttu-id="d3527-106">您可以根據組織的需求變更這些設定。</span><span class="sxs-lookup"><span data-stu-id="d3527-106">You can change these settings according to your organization's requirements.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="d3527-p103">清除檔案會從檔案系統將檔案永久移除。因此清除檔案後，您便無法復原檔案。</span><span class="sxs-lookup"><span data-stu-id="d3527-p103">Purging files permanently removes them from the file system. After you purge a file, it cannot be recovered.</span></span> 
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="d3527-109">您可以執行的工作</span><span class="sxs-lookup"><span data-stu-id="d3527-109">Tasks you can perform</span></span>

<span data-ttu-id="d3527-110">您可以在 [**編輯記錄] 設定**頁面上執行下列任務:</span><span class="sxs-lookup"><span data-stu-id="d3527-110">You can perform the following tasks on the **Edit Log Setting** page:</span></span>
  
- <span data-ttu-id="d3527-111">全域或針對特定網站新增裝置記錄配置。</span><span class="sxs-lookup"><span data-stu-id="d3527-111">Add a device log configuration globally or for a particular site.</span></span>
    
- <span data-ttu-id="d3527-112">修改現有裝置記錄檔設定的選項。</span><span class="sxs-lookup"><span data-stu-id="d3527-112">Modify the options for an existing device log configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="d3527-113">UI 參考</span><span class="sxs-lookup"><span data-stu-id="d3527-113">UI Reference</span></span>

<span data-ttu-id="d3527-114">下列清單說明頁面上的功能表、命令、欄位及內容。</span><span class="sxs-lookup"><span data-stu-id="d3527-114">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="d3527-115">**範圍**識別裝置記錄配置的範圍 (全域或網站)。</span><span class="sxs-lookup"><span data-stu-id="d3527-115">**Scope** Identifies the scope (Global or Site) of the device log configuration.</span></span>
    
- <span data-ttu-id="d3527-116">**名稱**您可以新增或修改裝置記錄配置的名稱。</span><span class="sxs-lookup"><span data-stu-id="d3527-116">**Name** You can add or modify the name of the device log configuration.</span></span>
    
- <span data-ttu-id="d3527-117">檔案**大小上限 (位元組)** 您可以指定記錄檔在清除前可以達到的大小上限。</span><span class="sxs-lookup"><span data-stu-id="d3527-117">**Maximum file size (bytes)** You can specify the maximum size a log file can become before it is purged.</span></span> <span data-ttu-id="d3527-118">預設值為1024000個位元組 (1 MB)。</span><span class="sxs-lookup"><span data-stu-id="d3527-118">The default is 1,024,000 bytes (1 MB).</span></span>
    
- <span data-ttu-id="d3527-119">**最大快取大小 (位元組)** 您可以指定要在記錄檔案快取中保留的最大資訊數量 (以位元組為單位), 以便在必須清除快取, 並將資料寫入記錄檔。</span><span class="sxs-lookup"><span data-stu-id="d3527-119">**Maximum cache size (bytes)** You can specify the maximum amount of information (in bytes) that can be held in the log file cache before that cache must be cleared and the data is written to a log file.</span></span> <span data-ttu-id="d3527-120">預設值為512000個位元組 (0.5 MB)。</span><span class="sxs-lookup"><span data-stu-id="d3527-120">The default is 512,000 bytes (0.5 MB).</span></span>
    
- <span data-ttu-id="d3527-121">**刷新快取的分鐘數 (1-60)** 您可以指定儲存在記錄檔案快取中的資訊在實際的記錄檔中寫入的頻率。</span><span class="sxs-lookup"><span data-stu-id="d3527-121">**Minutes to flush cache (1-60)** You can specify how often information stored in the log file cache is written to the actual log file.</span></span> <span data-ttu-id="d3527-122">記錄資料之後, 就會清除快取。</span><span class="sxs-lookup"><span data-stu-id="d3527-122">After the data is logged, the cache is cleared.</span></span> <span data-ttu-id="d3527-123">預設值為5分鐘。</span><span class="sxs-lookup"><span data-stu-id="d3527-123">The default is five minutes.</span></span>
    
- <span data-ttu-id="d3527-124">**保留記錄檔的天數 (1-365)** 您可以指定記錄檔案在清除前保留的天數。</span><span class="sxs-lookup"><span data-stu-id="d3527-124">**Days to keep log files (1-365)** You can specify the number of days the log files are kept before they are purged.</span></span> <span data-ttu-id="d3527-125">預設值為10天。</span><span class="sxs-lookup"><span data-stu-id="d3527-125">The default is 10 days.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d3527-126">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d3527-126">See also</span></span>

[<span data-ttu-id="d3527-127">裝置記錄組態</span><span class="sxs-lookup"><span data-stu-id="d3527-127">Device Log Configuration</span></span>](device-log-configuration.md)
