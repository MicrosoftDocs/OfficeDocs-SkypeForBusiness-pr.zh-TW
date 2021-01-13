---
title: 裝置記錄組態
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientDeviceCfgMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: c9b81f20-ce8c-40f1-8bed-50775cc35e58
ROBOTS: NOINDEX, NOFOLLOW
description: 裝置更新 Web 服務會自動建立記錄檔，記錄裝置更新活動。 在組織的資料管理原則中，您可能會想要設定記錄檔資料快取大小、記錄檔大小，或在清除記錄檔之前保留的時間長度閾值。 您可以根據組織的需求來變更這些設定。 如果您不想讓裝置更新 Web 服務自動清除記錄檔，您可以視需要手動清除記錄檔。 記錄設定可全域變更或每個網站。
ms.openlocfilehash: 118f2e6d90e9c3f7559a5e129c844ccdf1ea9bf1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830333"
---
# <a name="device-log-configuration"></a><span data-ttu-id="34f5e-107">裝置記錄組態</span><span class="sxs-lookup"><span data-stu-id="34f5e-107">Device Log Configuration</span></span>

<span data-ttu-id="34f5e-108">裝置更新 Web 服務會自動建立記錄檔，記錄裝置更新活動。</span><span class="sxs-lookup"><span data-stu-id="34f5e-108">Device Update Web service automatically creates log files that record device update activity.</span></span> <span data-ttu-id="34f5e-109">在組織的資料管理原則中，您可能會想要設定記錄檔資料快取大小、記錄檔大小，或在清除記錄檔之前保留的時間長度閾值。</span><span class="sxs-lookup"><span data-stu-id="34f5e-109">As part of your organization's data management strategy, you may want to set thresholds on log data cache size, log file size, or the length of time a log file is kept before it is purged.</span></span> <span data-ttu-id="34f5e-110">您可以根據組織的需求來變更這些設定。</span><span class="sxs-lookup"><span data-stu-id="34f5e-110">You can change these settings according to your organization's requirements.</span></span> <span data-ttu-id="34f5e-111">如果您不想讓裝置更新 Web 服務自動清除記錄檔，您可以視需要手動清除記錄檔。</span><span class="sxs-lookup"><span data-stu-id="34f5e-111">If you do not want Device Update Web service to purge log files automatically, you can purge them manually, as needed.</span></span> <span data-ttu-id="34f5e-112">記錄設定可全域變更或每個網站。</span><span class="sxs-lookup"><span data-stu-id="34f5e-112">Log settings can be changed globally or per site.</span></span>

> [!NOTE]
> <span data-ttu-id="34f5e-113">您也可以設定一天中的哪一天，當您想要讓裝置更新 Web 服務自動刪除舊于您設定服務的記錄檔時，其記錄檔的保留天數會為預設值，即超過10天之舊) 記錄檔的記錄檔 (。</span><span class="sxs-lookup"><span data-stu-id="34f5e-113">You can also configure a time of day when you want Device Update Web service to automatically delete log files that are older than the number of days you configured the service to keep log files (by default, that is log files that are more than 10 days old).</span></span> <span data-ttu-id="34f5e-114">此設定無法使用商務用 Skype Server 控制台進行修改。</span><span class="sxs-lookup"><span data-stu-id="34f5e-114">This setting cannot be modified using Skype for Business Server Control Panel.</span></span> <span data-ttu-id="34f5e-115">相反地，您必須使用商務用 Skype Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="34f5e-115">Instead, you must use Skype for Business Server Management Shell.</span></span> <span data-ttu-id="34f5e-116">若要指定一天中刪除過期記錄檔的時間，請使用 **New-CsDeviceUpdateConfiguration** Cmdlet 搭配-LogCleanUpTimeOfDay 參數。</span><span class="sxs-lookup"><span data-stu-id="34f5e-116">To specify the time of day to delete expired log files, use the **New-CsDeviceUpdateConfiguration** cmdlet with the -LogCleanUpTimeOfDay parameter.</span></span> <span data-ttu-id="34f5e-117">如需詳細資訊，請參閱 [New-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="34f5e-117">For details, see [New-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps).</span></span>

> [!CAUTION]
> <span data-ttu-id="34f5e-118">永久清除檔案會將檔案從檔案系統中移除。</span><span class="sxs-lookup"><span data-stu-id="34f5e-118">Purging files permanently removes them from the file system.</span></span> <span data-ttu-id="34f5e-119">清除檔案之後，便無法復原。</span><span class="sxs-lookup"><span data-stu-id="34f5e-119">After you purge a file, it cannot be recovered.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="34f5e-120">您可以執行的工作</span><span class="sxs-lookup"><span data-stu-id="34f5e-120">Tasks you can perform</span></span>

<span data-ttu-id="34f5e-121">您可以在「 **裝置記錄** 檔設定」頁面上執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="34f5e-121">You can perform the following tasks on the **Device Log Configuration** page:</span></span>

- <span data-ttu-id="34f5e-122">全域或針對特定網站或集區，新增裝置記錄檔設定。</span><span class="sxs-lookup"><span data-stu-id="34f5e-122">Add a device log configuration globally or for a particular site or pool.</span></span>

- <span data-ttu-id="34f5e-123">修改現有裝置記錄檔設定的選項。</span><span class="sxs-lookup"><span data-stu-id="34f5e-123">Modify the options for an existing device log configuration.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="34f5e-124">UI 參考</span><span class="sxs-lookup"><span data-stu-id="34f5e-124">UI Reference</span></span>

<span data-ttu-id="34f5e-125">下列清單說明頁面上的功能表、命令、欄位及內容。</span><span class="sxs-lookup"><span data-stu-id="34f5e-125">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="34f5e-126">**新** 您可以使用下列範圍新增新的裝置記錄檔設定：</span><span class="sxs-lookup"><span data-stu-id="34f5e-126">**New** You can add a new device log configuration with the following scope:</span></span>

  - <span data-ttu-id="34f5e-127">全域</span><span class="sxs-lookup"><span data-stu-id="34f5e-127">Global</span></span>

  - <span data-ttu-id="34f5e-128">網站</span><span class="sxs-lookup"><span data-stu-id="34f5e-128">Site</span></span>

- <span data-ttu-id="34f5e-129">**編輯** 您可以在清單中變更裝置記錄檔設定的選項。</span><span class="sxs-lookup"><span data-stu-id="34f5e-129">**Edit** You can change the options of a device log configuration in the list.</span></span> <span data-ttu-id="34f5e-130">使用此選項，您可以執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="34f5e-130">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="34f5e-131">**顯示詳細資料** 此選項會開啟一個對話方塊，您可以在其中變更裝置記錄檔設定的選項。</span><span class="sxs-lookup"><span data-stu-id="34f5e-131">**Show details** This option opens a dialog box in which you can change the options for a device log configuration.</span></span>

  - <span data-ttu-id="34f5e-132">**全選** 此選項會選取清單中的所有裝置記錄檔設定。</span><span class="sxs-lookup"><span data-stu-id="34f5e-132">**Select All** This option selects all device log configuration in the list.</span></span>

  - <span data-ttu-id="34f5e-133">**Delete** 此選項會刪除所有選取的裝置記錄檔設定。</span><span class="sxs-lookup"><span data-stu-id="34f5e-133">**Delete** This option deletes all selected device log configuration.</span></span>

- <span data-ttu-id="34f5e-134">**Refresh** 您可以重新整理裝置記錄檔設定清單，以驗證所有裝置記錄檔設定的選項狀態。</span><span class="sxs-lookup"><span data-stu-id="34f5e-134">**Refresh** You can refresh the device log configuration list to verify the status of the options of all device log configuration.</span></span>

## <a name="see-also"></a><span data-ttu-id="34f5e-135">另請參閱</span><span class="sxs-lookup"><span data-stu-id="34f5e-135">See also</span></span>

[<span data-ttu-id="34f5e-136">修改裝置更新活動的記錄檔設定</span><span class="sxs-lookup"><span data-stu-id="34f5e-136">Modify Settings for Log Files of Device Update Activity</span></span>](https://technet.microsoft.com/library/9b57f126-1853-43b3-bbd4-06401e6498bd.aspx)
